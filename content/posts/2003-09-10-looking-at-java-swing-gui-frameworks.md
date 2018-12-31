---
title: Looking at Java Swing GUI frameworks
author: Kevin Dangoor
type: post
date: 2003-09-10T22:54:14+00:00
url: /2003/09/10/looking-at-java-swing-gui-frameworks/
categories:
  - Software Development

---
I&#8217;ve been poking around today to see if I could find good, general code that glues together Java GUIs. One of the first things I found was [Java For U.com][1], which has a nice directory of a whole bunch of Java packages. It&#8217;s basically just someone&#8217;s bookmarks file, but it&#8217;s a good collection of bookmarks!

I came across the [Explicit Layout Manager][2], which sounds like it warrants further investigation. I&#8217;ve been using the JGoodies Forms layout manager, and that&#8217;s pretty nice.

[Werx][3] is a Swing framework that uses a message bus to separate the front end from the back end. The nice thing about this model is that the framework automatically smooths out the Swing &#8220;freezing&#8221; problem for long running commands. LGPL.

[ObjectScript][4] appears to have a nicely constructed GUI framework as part of its IDE, Chimera. Unfortunately, Chimera is released under the GPL (the ObjectScript compiler is LGPL).

[Wotonomy][5] aims to be an open source implementation of WebObjects and JavaClient.

 [1]: http://www.javaforu.com/start.htm ".::  Java For U.com  ::."
 [2]: http://www.zookitec.com/explicitlayout.html
 [3]: http://www.werx.org/index.jsp
 [4]: http://objectscript.sourceforge.net/
 [5]: http://wotonomy.sourceforge.net/