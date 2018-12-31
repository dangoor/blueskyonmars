---
title: 'Some Jython musings: Red Robin for Eclipse, Zope under Java'
author: Kevin Dangoor
type: post
date: 2004-08-28T04:51:46+00:00
url: /2004/08/27/some-jython-musings-red-robin-for-eclipse-zope-under-java/
categories:
  - Software Development

---
Sadly, Groovy&#8217;s Eclipse plugin has been out of commission for a while (since I&#8217;ve been using the 3.0 Eclipse versions for a while). I don&#8217;t think Groovy&#8217;s plugin at its height was as complete as [Red Robin][1], the Jython (Python) plugin for Java. Looks like a bunch of great features, and it&#8217;s 3.0 compatible. I plan to give this a whirl next week.

On the more general topic of Groovy and Jython&#8230; I like Groovy because it has some nice language features but can also run a good deal of Java code straight up. This makes it a more seamless transition between Java and Groovy.

On the other hand, I&#8217;ve liked Python for many years, and Jython can open the doors to using many Python-based libraries in addition to your Java favorites. One big downside, though, is that the current release version of Jython has fallen way behind, ever since the big class/type mashup that happened in Python 2.2. I was using Jython quite a bit in 2001, and I think Jython 2.1 was current _then_. There&#8217;s an early test release of Jython 2.2. I&#8217;d love to see them get caught up.

Part of what I was using Jython for back in 2001 was an attempt to port Zope to Jython. I started this project (Phabric) while at Web Elite. Though we had ported enough of ExtensionClass and Acquisition to make a bunch of unit tests pass, there were some gnarly differences between CPython and Jython and we ran out of time on the project. The changes in Python 2.2, once integrated into Jython, could make porting Zope to Java much more of a reality. Wouldn&#8217;t that be cool?

 [1]: http://home.tiscali.be/redrobin/jython/ "Red Robin - Jython"