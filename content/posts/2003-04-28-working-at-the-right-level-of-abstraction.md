---
title: Working at the right level of abstraction
author: Kevin Dangoor
type: post
date: 2003-04-28T21:51:53+00:00
url: /2003/04/28/working-at-the-right-level-of-abstraction/
categories:
  - Technology

---
Eric Sink writes about the [.NET Abstraction Pile][1] in SourceGear&#8217;s Vault product. This is a nicely written article that highlights some of the issues that programmers face every day. The issue of complexity that comes with abstraction is a large motivator for the XP rule of &#8220;Do the simplest thing that can possibly work&#8221;. Don&#8217;t add that complexity on before you actually need it. Eric&#8217;s experince with their SOS Collab product sounds exactly like the kind of problem that comes up when you try to overengineer and get the most perfect and flexible solution.

I&#8217;ve been reading about O-R mapping tools recently, and have read a lot of positive comments about [Hibernate][2]. A major competitor to Hibernate is [Jakarta OJB][3], which adds layers of abstraction in order to support ODMG and JDO interfaces. Many of the positive comments about Hibernate have praised it for being simple and fast, which is exactly the effect one would expect you would get by stripping away a couple of layers.

I find it interesting that he has moved from Java to .NET and found that .NET is &#8220;Java done right&#8221;. I&#8217;m definitely keeping my eyes on .NET, particularly as [Mono][4] gets up to speed. I&#8217;m not certain which layers of abstraction were contributing to their bug list, though. Java itself does not imply much of anything in terms of layers of abstraction. If he&#8217;s talking about Swing, certainly Swing has many layers. For doing web apps in Java, you can choose to go with few layers (HttpServletRequest, anyone) or [many][5].

 [1]: http://biztech.ericsink.com/Abstraction_Pile.html "Eric.Weblog()"
 [2]: http://hibernate.sourceforge.net
 [3]: http://db.apache.org/ojb
 [4]: http://www.go-mono.com
 [5]: http://jakarta.apache.org/struts