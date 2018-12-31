---
title: On IDE Bloat
author: Kevin Dangoor
type: post
date: 2003-06-16T22:34:04+00:00
url: /2003/06/16/on-ide-bloat/
categories:
  - Uncategorized

---
Danno Ferrin chose [to respond to][1] the [IDE rant on BileBlog][2]. (BTW, if you&#8217;re in the mood for commisserating with a perpetual ranter, check out BileBlog. You may start feeling like your own life isn&#8217;t so bad after all 🙂 Anyhow, Danno had the following to say about IDE bloat:

> Issue #1 : IDE Bloat. Yea, I&#8217;ve noticed this alot lately. All the IDEs need to have some fangleled spangeled tool to do the latest programming fad. Well based on what was said at JavaOne I&#8217;de say it&#8217;s only going to get worse. The 20% that can do without it are probobly using Emacs or TextPad anyway.

One nice thing to come of the Eclipse project viewing itself as a &#8220;platform&#8221; is that the baseline tool does not need to do _everything_. It just has to enable everything to be done. People can then pick and choose the things that matter to them. Emacs is much the same way&#8230; you can do everything with Emacs, including making it do many of the common things that IDEs do (outline views of the code, method name completion, etc.)
  
I&#8217;ve been a big fan of Python for many years and have felt that it is tremendously more productive than Java. However, a nice IDE eliminates some of the pain of Java by doing things like method lookup which can&#8217;t readily be done in a dynamically typed language. The integrated debugger, handy JUnit view (for those test-driven among us), etc. can really make things go faster than running command line tools.

Jackpot is not the only work underway aiming to provide new views of Java code. I forget what the product was called, but SD Magazine mentioned a forthcoming product that allows you to visually see a design pattern in your code, or click again to see what a Swing control you&#8217;ve instantiated looks like, or click again to see a UML view. Some of these tools could prove to give big productivity gains. Others may just prove to be hype&#8230; but, either way, I&#8217;m happy to see that people are looking at new ways to work with code.

Luckily, there is plenty of choice in the world. For those who think that IDEs are bloated, no one&#8217;s going to stop you from using &#8220;ed&#8221;, if that&#8217;s your choice. For me, a tool that helps to reduce the amount of code I need to type to get things done is most welcome on my machine.

 [1]: http://shemnon.com/speling/archives/000106.html "Danno Ferrin: ... Speling Errors: Swiss Army IDE Problem"
 [2]: http://www.freeroller.net/page/fate/20030614#idea_on_the_chopping_block