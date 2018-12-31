---
title: Joel explains Hungarian notation
author: Kevin Dangoor
type: post
date: 2005-05-11T20:30:44+00:00
url: /2005/05/11/joel-explains-hungarian-notation/
categories:
  - Software Development

---
Joel Spolsky, as always, is entertaining and takes a bit of exposition to get to the point in his latest article: [Making Wrong Code Look Wrong][1]. In the article, he makes a differentiation between &#8220;Apps Hungarian&#8221; notation and &#8220;Systems Hungarian&#8221; notation, and now it makes sense to me. Whenever I saw people talking about Hungarian Notation, I always saw the Systems version which seemed completely nonsensical: why would someone have a variable name that just duplicates information that you&#8217;ve already got? Conveying more useful information, as in the unsafe string example Joel gives, is a good thing.

I don&#8217;t buy the exceptions argument that Joel makes. When you&#8217;re writing the code, if you&#8217;re calling some outside function you need to know whether that function throws exceptions or if it returns an error code. Either way, when you&#8217;re calling something that can fail, you need to decide how you&#8217;re going to handle that failure. If you use error codes, you&#8217;re forced to do bookkeeping all the way up the chain until the error hits a point where it can be properly dealt with (sometimes requiring action from the user). With exceptions, you can just say &#8220;this method is not in a position to do something about this problem, pass it along&#8221;.

CompSci is all about tradeoffs: Joel&#8217;s preference is for more explicit code that requires more bookkeeping. My preference is for something that requires a bit less bookkeeping, and saves a bit of time by leaning on the tools a bit more. People writing macros in LISP are all the way at the extreme of hiding much of the bookkeepnig behind the tools provided by the language.

There&#8217;s no proveably correct answer to this, so pick your poision as they say.

Regardless of how you feel about exceptions, though, Joel&#8217;s article is worth the read because of his Hungarian Notation explanation. If you&#8217;ve been turned off by Hungarian Notation in the past, it&#8217;s worth taking a look at Joel&#8217;s view on it.

 [1]: http://www.joelonsoftware.com/articles/Wrong.html