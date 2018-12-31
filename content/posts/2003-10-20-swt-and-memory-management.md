---
title: SWT and memory management
author: Kevin Dangoor
type: post
date: 2003-10-20T19:23:25+00:00
url: /2003/10/20/swt-and-memory-management/
categories:
  - Software Development

---
Pazu laments the [pain of SWT][1]. I was seriously considering Eclipse as an application framework, and SWT&#8217;s memory management needs were among the reasons that I opted for another path.

For those who haven&#8217;t looked at SWT, here&#8217;s the scoop: every SWT component (including ones that you write) have a dispose() method. If you make a panel that has several widgets (or even fonts and colors!) on it, you need to keep track of those and explicitly call their dispose() methods from your own dispose() method. If you don&#8217;t, you&#8217;ve got a memory leak&#8230; because SWT will never release the native widgets that it has allocated.

Why does SWT have this bit of nastiness and Swing does not? Because Swing doesn&#8217;t allocate native widgets. It draws all of its widgets, directly in Java code, using basic AWT calls.

If Java had real, reliable destructors this would not be a problem. But, alas&#8230;

 [1]: http://www.animegaiden.com.br/blogs/pazu/archives/001217.html "WIRED::SWT woes : Close the world, open the neXt"