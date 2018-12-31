---
title: Using Unicode with ElementTidy
author: Kevin Dangoor
type: post
date: 2005-01-31T17:13:51+00:00
url: /2005/01/31/using-unicode-with-elementtidy/
categories:
  - Python

---
I want to do some HTML scraping, and there are at least two Python packages to help with that: BeautifulSoup and ElementTidy. For what I&#8217;m doing, the input and output need to be UTF-8. I have had some success if I set my default encoding to utf8 via sitecustomize.py, but it would be nicer if I could explicitly set the encoding as needed.

I&#8217;m going to talk mostly about ElementTidy in this posting. Briefly, the problem I had with BeautifulSoup was that passing in a unicode string resulted in tags getting glommed together. For example, if I had two <a> tags, the content of the first tag would include the second tag, and the second tag would also appear separately. I didn&#8217;t spend any significant time looking at this problem.

With ElementTidy, the problems have been clearer, but not necessarily easy to fix. I still don&#8217;t have it working fully without using a sitecustomize.py file. What happens with ElementTidy is that the unicode string is being coerced to ASCII, causing an exception whenever there is a character that is not compatible with 7-bit ASCII. The first step along the way brought me to the _elementtidy.c module. This is the one that calls the HTML Tidy library to generate clean XHTML for ElementTree to work with. The first clue that something is amiss is that tidylib is called with an encoding of &#8220;ascii&#8221;. Sadly, just setting that to utf8 won&#8217;t do it, because the input from Python and the output to Python both need to be unicode objects, rather than standard strings. Here&#8217;s how I did it (for brevity, I&#8217;ll highlight the changes):

<pre>static PyObject*
elementtidy_fixup(PyObject* self, PyObject* args)
{
/* snip */
    char* text;
    if (!PyArg_ParseTuple(args, "es:fixup", "utf8", &text))
        return NULL;

    doc = tidyCreate();

    /* options for nice XHTML output */
    tidyOptSetValue(doc, TidyOutCharEncoding, "utf8");
    tidyOptSetValue(doc, TidyInCharEncoding, "utf8");

/* snip */
    pyout = PyUnicode_DecodeUTF8(out.bp ? out.bp : "", out.size, NULL);
    if (pyout)
        pyerr = PyUnicode_DecodeUTF8(err.bp ? err.bp : "", err.size, NULL);
/* snip */
    PyMem_Free(text);
/* snip */
</pre>

What I had to do was pretty simple, but I haven&#8217;t looked at Python extensions in a few years, so I had to do a bit of reading to make these few minor changes. The first change is to tell PyArg\_ParseTuple that we&#8217;re looking for utf8 coming in. By doing that, the incoming text will not be coerced to ASCII, and the text buffer will contain UTF-8 text. Then, in the options to tidylib, we need to specify that utf8 is our input and output format of choice. Once the response comes back, we create unicode objects rather than string objects. Thankfully, there is a function to take a UTF-8 encoded byte buffer and generate a Python unicode object. Finally, don&#8217;t forget to free the incoming argument, because the &#8220;es&#8221; option to PyArg\_ParseTuple allocates a new buffer for the encoded string.

I&#8217;m pretty sure that there would be a way to directly get the unicode object out of the tuple so that no additional buffer needs to be created. I haven&#8217;t looked into that at all. Secondly, this function now only does utf-8 in and out (though if you pass it an ASCII string, that will still work). This is not ideal, but it meets my needs.

That works fine, and it would have been nice if that was the end of the story. Of course, it&#8217;s not, otherwise I would&#8217;ve stopped typing. By making the changes above, _elementtidy.fixup will nicely do UTF-8 in and out. Unfortunately, I then ran into problems with ElementTree coercing my document to ASCII. Looking at the Python implementation, I see that no encoding is passed to the expat parser. The docs for that package say that it will try to determine from the document what encoding to use. So, I made sure that I had a <?xml version=&#8221;1.0&#8243; encoding=&#8221;utf-8&#8243; ?> declaration, but that didn&#8217;t do the trick either.

I&#8217;m hoping there&#8217;s some way other than sitecustomize.py to pass along that the object needs to stay in unicode form. I&#8217;m sure I can do it if I hack at ElementTree a little bit, but I really don&#8217;t like altering third party packages unless I can send in a useful patch that will get integrated.