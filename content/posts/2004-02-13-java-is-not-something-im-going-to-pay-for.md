---
title: Java is not something I’m going to pay for
author: Kevin Dangoor
type: post
date: 2004-02-14T04:48:59+00:00
url: /2004/02/13/java-is-not-something-im-going-to-pay-for/
categories:
  - Software Development

---
ESR has called on Sun to [open source Java][1]. Sun insists that they want input from outsiders, but don&#8217;t want Microsoft to be able to go off and do evil things with Java.

If they take a look at Linux, they&#8217;d realize that there is power in trademarks for software. Sure, anyone can take Linux and create their own bastardized form of it. But they can&#8217;t call it Linux, because Linus owns the name.

Besides, Microsoft didn&#8217;t need Sun&#8217;s code to create their own bastardized version (.NET). (For any .NET folks out there, I&#8217;m not trying to imply that .NET is inferior to Java, because it isn&#8217;t&#8230; it&#8217;s just very, very similar to Java.)

The article contains this interesting quote:

> Java is indeed a very different creature from open-source software, said Shawn Willett of Current Analysis. &#8220;At its heart, Java is something that you&#8217;re going to pay for,&#8221; and its development is dominated by companies with a financial interest in its success.

Err, huh? Last I looked, Java is free to download and use (both runtime and compilers). Sun makes a free IDE, and Eclipse is free as well. There are many free libraries in use.

And, yes, development of Java generally comes from Sun with some input from other big companies that work there way through the JCP. A whole lot of interesting stuff happens at the fringes, though&#8230; GJ implemented generics some time back in a way that is essentially what Sun has done. Log4J paved the way for 1.4 logging. Sun hasn&#8217;t done anything with scripting, but packages like BeanShell, Jython, Rhino and Groovy are just a few of the JVM-based languages that have gained attention and users.

One interesting thing is that Java is, in some ways, like Microsoft&#8217;s &#8220;Shared Source&#8221;. The code for the whole J2SE library is there for the downloading, and apparently J2SE 1.5 includes the javac source. So, people can contribute patches back to Sun. They&#8217;re just not free to create derivatives or redistribute Java.

One of ESR&#8217;s complaints is that Linux distributions can&#8217;t even include Java because of Sun&#8217;s licensing terms. That&#8217;s something that Sun could fix even without actually open sourcing Java. Seems like a good idea to me.

 [1]: http://news.com.com/2100-7344_3-5159134.html "Open-source advocate: Release Java code | CNET News.com"