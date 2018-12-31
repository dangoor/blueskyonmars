---
title: ClearSilver built for Windows
author: Kevin Dangoor
type: post
date: 2005-01-04T20:28:29+00:00
url: /2005/01/04/clearsilver-built-for-windows/
categories:
  - Python

---
I don&#8217;t like make. There, I&#8217;ve said it.

But, of course, there&#8217;s always more to say. I like make plenty when I don&#8217;t personally have to work with makefiles. Typing &#8220;./configure ; make&#8221; is a fine process for building software. But, it wasn&#8217;t that easy when I was trying to build [ClearSilver][1] for Windows with Python 2.4. There are instructions that came in the ClearSilver tarball that got me part of the way. For some reason, though, the configure script just wasn&#8217;t getting my Python include and libs directories right. The simple solution was to just edit rules.mk to point to the correct directory, which worked just fine.

I&#8217;m quite thankful for the work that the MinGW people have put in. This kind of thing would be far harder without it.

 [1]: http://www.clearsilver.net