---
title: Swing GUI frameworks part deux
author: Kevin Dangoor
type: post
date: 2003-09-11T15:47:35+00:00
url: /2003/09/11/swing-gui-frameworks-part-deux/
categories:
  - Software Development

---
Yesterday, I was looking at Swing GUI frameworks. I got two comments, one from Klaasjan Tukker regarding the [UIC][1] project, and the other from the ever-diligent Gerald Bauer about [XUL-based solutions][2]. There are a wide variety of things that fall into the category of &#8220;framework&#8221;. Both of the commenters presented GUI widget assembly solutions. I&#8217;m looking for something different than that.

Using Eclipse, I actually don&#8217;t find it that difficult to hand assemble my widgets into panels, particularly using something like JGoodies Forms. Eclipse saves on the typing, and makes it so that I don&#8217;t really need to remember what things are called.

What I&#8217;m looking for in a framework is something like Werx or ObjectScript&#8217;s Chimera framework. These provide interesting ways to bind the GUI with the system&#8217;s backend. If the framework also provided a collection of commonly used UI goodies (like multi-window management) that would be a bonus.

Update: [Somnifugi][3] is a single-JVM implementation of JMS, which the author has had good success using in a similar fashion to Werx&#8217;s ReflectionBus.

 [1]: http://uic.sf.net/)
 [2]: http://xul.sourceforge.net/
 [3]: http://somnifugi.sourceforge.net/