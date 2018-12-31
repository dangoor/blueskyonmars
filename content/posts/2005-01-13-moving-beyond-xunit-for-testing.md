---
title: Moving beyond xUnit for testing
author: Kevin Dangoor
type: post
date: 2005-01-13T15:44:02+00:00
excerpt: JUnit and breathren are showing their age, but there are alternatives.
url: /2005/01/13/moving-beyond-xunit-for-testing/
categories:
  - Software Development

---
I&#8217;ve used JUnit plenty over the past couple of years. I think that JUnit is an important piece of software, but not because of elegance of design or impressive feature set. JUnit is important because it is ubiquitous. It&#8217;s the first testing framework to gain widespread adoption. In fact, JUnit&#8217;s best feature today isn&#8217;t even a feature a JUnit itself: integration with IDEs. Doing Test Driven Development in Eclipse, you get into this nice rhythm Run Test->Red Bar->Fix Code->Ctrl-F11->Green Bar.

JUnit is also nice because it integrates with Ant, making it easy to set up automated builds.

Many people out there have complained that JUnit is getting a [little long in the tooth][1]. Cedric Beust has done something about it for Java: [TestNG][2]. The main thing that Cedric&#8217;s project fixes is JUnit&#8217;s test suite system, making it far easier to slice and dice your tests into different groups for selectively testing parts of your project. Cedric also did away with the assertEquals() and assertTrue() methods, instead sticking with Java&#8217;s native assert keyword. TestNG now works with J2SE 1.4 (the last I had looked at it, it required 1.5).

Python has always had testing options. Python&#8217;s doctest lets you take an interactive Python session and rerun it, verifying that the results are the same. That seems useful for simpler test cases with less fixture. Like every other language on the planet, Python has its own xUnit framework. It&#8217;s even part of the Python standard library. But, of course, there are people who aren&#8217;t completely happy with those options&#8230;

That&#8217;s where [py.test][3] comes in. I&#8217;ve been playing with py.test since Bob Ippolito [clued me into it][4] a few days ago.

When used within an IDE, JUnit is great. If there&#8217;s a failure, you can just click to jump to the line that failed. When run via Ant, however, all you get is the exception traceback. And you&#8217;ll be sorry if you forgot to include debug info in your compiled files.

py.test has some nice features that attracted my interest immediately and really make up for the fact that it&#8217;s not running in an IDE with a nice green/red bar. py.test has nothing for you to subclass. It will hunt down modules, functions and methods that start with test and run those. Just like in TestNG, you use the native assert keyword rather than special methods, but py.test produces output from the failure that provides at least as much information as assertEquals in JUnit:

> <pre>def test_failing():
    rabbit = {"inthe" : 1}
    hat = {"inthe" : 0}
>   assert rabbit == hat</pre>

shows the failure as:

> <pre>assert {'inthe': 1} == {'inthe': 0}</pre>

Notice the marker next to the assert line in the test code? When a test fails, py.test displays the test&#8217;s code up to the line that failed. This is more natural in Python than in Java, since the source is generally right there whereas Java is compiled and its unclear where the source would be. It would be a nice option in Java test frameworks to be able to point it at the source and see that kind of view.

py.test also automatically captures stdout. Only if a test fails will the output be displayed. It keeps your test run output nice and tidy. Sure, Java has a logging framework built in (so does Python), but it&#8217;s certainly more of a pain to use than doing &#8220;print&#8221;s and displaying the output when the test fails. This could easily be done in Java as well.

There are other features, like test generators and whatnot, but these couple of features I listed above already make things so much more pleasant than xUnit. I&#8217;d be curious to learn about other test frameworks that people are working on.

 [1]: http://www.randomhouse.com/wotd/index.pperl?date=19961217
 [2]: http://www.beust.com/testng/
 [3]: http://codespeak.net/py/current/doc/test.html
 [4]: http://www.blueskyonmars.com/archives/2005/01/07/jason_orendorff_where_are_you.html#comments