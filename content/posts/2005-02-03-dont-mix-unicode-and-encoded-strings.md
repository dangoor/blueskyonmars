---
title: Don’t mix unicode and encoded strings
author: Kevin Dangoor
type: post
date: 2005-02-03T15:52:40+00:00
url: /2005/02/03/dont-mix-unicode-and-encoded-strings/
categories:
  - Python

---
The key to my [unicode-in-python problems][1] was that using unicode objects within Python feels the same as using a string object. But, they are really not the same ([as pointed out by Diez Roggisch and Just van Rossum][2]), and you see this when you start talking to C extensions. My original solution to working with elementtidy involved making elementtidy understand unicode objects.

The cleaner solution is to pass in UTF-8 encoded strings. That&#8217;s the trick: a unicode object in Python is a &#8220;perfect&#8221; representation of a unicode string, whereas UTF-8 is a way to represent a unicode string as a bunch of bytes. I&#8217;m pretty sure I read this somewhere in my recent travels, but now I really see the effects of this when it comes to talking with C modules.

This didn&#8217;t change the fact that elementtidy was hardcoded to encode as ASCII. The solution to this is simpler than the unicode change I made the other day. Taking a stock _elementtidy.c from 1.0a3, here is the breakdown of changes:

<pre>/* snip */
static PyObject*
elementtidy_fixup(PyObject* self, PyObject* args, PyObject* kwdict)
{
/* snip */
    char* encoding = "ascii";
    
    static char* kwlist[] = {"data", "encoding", NULL};

    char* text;
    if (!PyArg_ParseTupleAndKeywords(args, kwdict, "s|s", kwlist, &text,
        &encoding))
        return NULL;

    doc = tidyCreate();

    /* options for nice XHTML output */
    tidyOptSetValue(doc, TidyCharEncoding, encoding);

/* snip */
static PyMethodDef _functions[] = {
    {"fixup", (PyCFunction) elementtidy_fixup, METH_VARARGS | METH_KEYWORDS, 
            "Use HTML Tidy to convert to XHTML"},
    {NULL, NULL}
};
</pre>

These changes are very straightforward. Add an &#8220;encoding&#8221; keyword argument to the fixup function, and pass that in to tidylib, rather than the previous hardcoded &#8220;ascii&#8221;. The default is still &#8220;ascii&#8221; though. I also made minor changes to TidyHTMLTreeBuilder to add the encoding option (and use cElementTree, if available).

This solution works great and there is no sitecustomize.py needed to make it work. Unicode in Python looks quite well designed, especially given the needs of interfacing with C code that has its own ideas about text encoding and multibyte characters.

 [1]: http://www.blueskyonmars.com/archives/2005/01/31/microsoft_opening_their_office_file_formats.html
 [2]: http://news.gmane.org/find-root.php?message_id=%3cjust%2d279A4A.20091102022005%40news1.news.xs4all.nl%3e