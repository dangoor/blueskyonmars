---
title: Swing and CSS
author: Kevin Dangoor
type: post
date: 2003-10-16T20:25:54+00:00
url: /2003/10/16/swing-and-css/
categories:
  - Software Development

---
In the article [Swing and CSS][1], Joshua Marinacci shows a simple implementation of a CSS-like system for styling Swing interfaces. It&#8217;s an interesting idea, and the implementation looks potentially flexible enough to do interesting things. However, I agree with some of the commenters that what this is trying to do is essentially the same as what L&Fs are all about. Maybe the syntax will be more accessible to non-programmers.

CSS is great for the web, because the web is presenting documents. Swing is not used for presenting documents&#8230; it&#8217;s used for creating desktop applications, which (generally) should have a consistent L&F with the rest of the desktop. If you&#8217;re making MP3 playing software, sure, you may want to make that skinnable. But, for large business applications you want something that looks like a normal desktop app. Standard Swing L&Fs are designed to do that (regardless of how well they succeed at that task).

 [1]: http://today.java.net/pub/a/today/2003/10/14/swingcss.html "Swing and CSS"