---
title: Swing/multithreaded unit testing tips
author: Kevin Dangoor
type: post
date: 2004-02-16T03:47:56+00:00
url: /2004/02/15/swingmultithreaded-unit-testing-tips/
categories:
  - Software Development

---
Came across a few great links at the Java.net JavaDesktop site. [Multithreaded Tests with JUnit][1] describes how to use [GroboUtils][2] to manage multithreaded test scenarios. I wrote some tests a couple months ago that really could have benefitted from this. JavaDesktop also linked to [jfcUnit][3] for doing tests of Swing code. This looks similar to [Jemmy][4] which has worked well for us so far.

 [1]: http://today.java.net/pub/a/today/2003/08/06/multithreadedTests.html "Multithreaded Tests with JUnit"
 [2]: http://groboutils.sourceforge.net/
 [3]: http://jfcunit.sourceforge.net/
 [4]: http://jemmy.netbeans.org/