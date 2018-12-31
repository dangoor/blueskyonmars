---
title: Greenspun on .NET
author: Kevin Dangoor
type: post
date: 2001-08-28T17:33:24+00:00
url: /2001/08/28/greenspun-on-net/
categories:
  - Random

---
Philip Greenspun [responded to a request for information about what technology to learn][1]. His response was Microsoft .NET. After a bit of push back from [Dave Winer][2], he qualified that he is a very big fan of the unification of languages allowed by .NET. I disagreed with his assessment of Java, however. My response follows&#8230;
  
<!--more-->


  
In general, I believe the Intermediate Language, Common Language Runtime and &#8220;automatic&#8221; support for SOAP in .NET are good things, and I hope that Microsoft does not get patents that allow them to control those areas. In that, I am in agreement with Philip&#8217;s comments above.

However, regarding Java, I disagree with this statement:

> The competition is Java, Java, Java, an environment in which it is impossible to provide a scripting language alternative for some or all of a system&#8217;s programmers.

There are _many_ scripting choices for Java. Take a look at [this list of Java VM languages][3]. IBM&#8217;s [Bean Scripting Framework][4] even makes it possible to write a single Java component that is scriptable in the user&#8217;s langauge of choice.
  
I&#8217;ve used [Jython][5] quite a bit, and it&#8217;s great. It works almost completely like standard Python, but allows me to work directly with Java objects.
  
The technology to do what .NET promises has been available for some time&#8230; but Microsoft is the first to bundle it all up and market it in one concerted effort. And marketing is something Microsoft is very good at.

 [1]: http://philip.greenspun.com/bboard/q-and-a-fetch-msg?msg_id=000tYs&topic_id=22&topic=Ask%20Philip
 [2]: http://www.scripting.com
 [3]: http://grunge.cs.tu-berlin.de/~tolk/vmlanguages.html
 [4]: http://www.alphaworks.ibm.com/tech/bsf
 [5]: http://www.jython.org