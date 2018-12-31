---
title: Using CGLIB to speed up XML parsing
author: Kevin Dangoor
type: post
date: 2003-10-21T16:01:13+00:00
url: /2003/10/21/using-cglib-to-speed-up-xml-parsing/
categories:
  - Software Development

---
Good stuff from [Chris Nokleberg][1]&#8230; using CGLIB to make SAX parsing zippy:

> For validated documents this is safe and gives a 3X speedup.

I don&#8217;t think I&#8217;d be likely to use the if/else if/else if structure that he mentions, because that seems like the kind of thing that is screaming out for separate objects. I believe Fowler even has a refactoring for this, but it&#8217;s too early in the morning to recall which one.

 [1]: http://sixlegs.com/blog/java/optimizing-xml-parsing.html "Root Beer"