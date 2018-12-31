---
title: 'PyLucene: Real Lucene in Python via GCJ and SWIG'
author: Kevin Dangoor
type: post
date: 2004-06-26T04:32:49+00:00
url: /2004/06/25/pylucene-real-lucene-in-python-via-gcj-and-swig/
categories:
  - Software Development

---
The OSAF has released [PyLucene][1], which takes the fine [Lucene search engine][2] and compiles it to native code using GCJ, and then wrapping it for Python use using SWIG. There is a Python port of Lucene called Lupy, but it&#8217;s slower than the Java version and, since it&#8217;s a port, lags behind Lucene in development.

There&#8217;s been a lot of interesting work lately in bridging Python and Java (CPython, that is, not Jython, which is already quite attached to Java). The PyLucene approach is an interesting one, and could probably be applied to many fine Java libraries.

 [1]: http://pylucene.osafoundation.org/ "PyLucene @ Open Source Applications Foundation"
 [2]: http://jakarta.apache.org/lucene