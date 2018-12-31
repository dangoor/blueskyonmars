---
title: Python dynamic code replacement
author: Kevin Dangoor
type: post
date: 2004-12-31T20:34:54+00:00
url: /2004/12/31/python-dynamic-code-replacement/
categories:
  - Python

---
It&#8217;s interesting the stuff you see when you&#8217;re looking at an aggregator. Michael Lucas-Smith of Software WithStyle writes about how [updating live server code is so easy in Smalltalk][1]. You replace the code, and all of the instances of those classes immediately get the new behavior.

Not so in Python, [laments Chui Tey][2]. He says that Twisted has a metaclass trick to do this and mentions one on ASPN. I&#8217;m not sure if this is the one, but the [RubyClass][3] hack does look like it&#8217;s designed for code replacement.

There was debate following [Guido&#8217;s discussion of optional static typing][4] in Python about whether adding static typing is a good use of time. While Python&#8217;s metaclasses do allow addition of all sorts of interesting behavior, I do think that supporting Smalltalk-like live system updating is a bigger win for Python developers than static typing would be.

Update: I&#8217;ve corrected the mention of Michael Lucas-Smith&#8217;s employer based on the comment from James Robertson.

 [1]: http://www.cincomsmalltalk.com/userblogs/mls/blogView?showComments=true&entry=3281559434 "Smalltalk and my misinterpretations of life: Server, heal thy-self"
 [2]: http://teyc.editthispage.com/2004/12/31
 [3]: http://aspn.activestate.com/ASPN/Cookbook/Python/Recipe/361167
 [4]: http://www.artima.com/weblogs/viewpost.jsp?thread=85551