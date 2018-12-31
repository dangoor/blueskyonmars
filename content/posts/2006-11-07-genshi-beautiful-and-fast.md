---
title: 'Genshi – beautiful *and* fast?'
author: Kevin Dangoor
type: post
date: 2006-11-08T02:28:02+00:00
url: /2006/11/07/genshi-beautiful-and-fast/
categories:
  - Python

---
While I&#8217;m a big fan of his programming (and a [certain other][1] of his projects, I&#8217;m not of a fan of Mike Bayer&#8217;s Myghty template language. The original language itself was invented in Perl-land and Mike adapted and extended it in Python. I just don&#8217;t enjoy the syntax. Admittedly, though, Myghty and other Python template languages are faster than my favorite, [Genshi][2]. So , you can imagine my delight to read that [Mike is working on speeding up Genshi!][3] Thanks Mike!

(By the way, it&#8217;s unlikely that Genshi will ever be as fast as a purely non-structural template language. My choice of Python over Java or C shows that I&#8217;m willing to trade in a little speed to use a better language, and this case is no different. With appropriate caching, I&#8217;m sure that the speed of Genshi will be just fine even on very heavily trafficked sites/apps.)

 [1]: http://sqlalchemy.org
 [2]: http://genshi.edgewall.org
 [3]: http://techspot.zzzeek.org/index.php?/archives/11-Myghty-is-the-Fastest-Python-Template-Language.-What-Can-it-Do-for-Genshi.html