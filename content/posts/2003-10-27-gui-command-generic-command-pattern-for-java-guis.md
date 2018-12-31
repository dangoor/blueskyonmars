---
title: GUI Command generic command pattern for Java GUIs
author: Kevin Dangoor
type: post
date: 2003-10-27T20:10:18+00:00
url: /2003/10/27/gui-command-generic-command-pattern-for-java-guis/
categories:
  - Software Development

---
I&#8217;ve been thinking about (and working on/with) Java Swing GUI frameworks quite a bit lately. The [GUI-Commands][1] project incorporates some ideas that I&#8217;ve seen in Eclipse (the notion of menus and toolbars being built up dynamically, called contributions in Eclipse). I&#8217;m somewhat surprised to not see any mention of UndoableEdits in there, because that&#8217;s a great benefit to using the command pattern with Swing&#8230; it&#8217;s fairly straightforward to do undo.

I had initially thought of having commands in my system provide UI components as they do in GUI-Commands, but had changed my mind because I found a way to make the commands themselves largely transparent to the application. We&#8217;ve got a lot of apps to write, though, and I may change my mind if I find that we need to create the same menu items all over the place.

It seems entirely likely that I may want to look this project up again sometime. It&#8217;s released (according to the java.net page) under the LGPL.

 [1]: http://members.optusnet.com.au/~apietsch/gui-commands/index.html "GUI-Commands"