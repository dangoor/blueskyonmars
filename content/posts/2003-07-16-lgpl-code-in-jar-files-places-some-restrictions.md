---
title: LGPL code in jar files places some restrictions
author: Kevin Dangoor
type: post
date: 2003-07-16T18:41:18+00:00
url: /2003/07/16/lgpl-code-in-jar-files-places-some-restrictions/
categories:
  - Software Development

---
(This entry has been revised&#8230; see below&#8230;) I&#8217;m surprised I hadn&#8217;t heard this before, but it appears that Java code that uses an LGPL&#8217;ed library must [be released under the LGPL as well][1]. Gadzooks. I&#8217;ll have to pay a bit more attention. The [AspectWerkz][2] folks convinced [JMangler][3] to switch back to the LGPL, but I guess it&#8217;s still viral!

**Update:** Thanks to Paul Rivers for pointing out his post in the comments for the link above. I&#8217;ve changed the title and I&#8217;m adding this text to provide more info for anyone who happens to come by here.

Using an LGPL&#8217;ed Java library _does not_ require you to license your code under the terms of the LGPL. (Sorry about even saying that!) It does require you to follow [section 6][4]. Section 6 basically says that you must allow the customer to reverse engineer and modify your code for their own use (which is contrary to some commercial licenses). You must also distribute the source to the library (if people want it).

There is a part of section 6 about providing data and utility programs needed for reproducing the executable that uses the library. The way I read this section, I don&#8217;t think it&#8217;s a problem for a typical Java-based program, but IANAL.

So, the LGPL does place some different kinds of restrictions than other licenses, but these are probably workable.

 [1]: http://linuxintegrators.com/hl30/blog/technology/?permalink=LGPL in Java.html "Hacking Log 3.0: America's Blog"
 [2]: http://aspectwerkz.codehaus.org/
 [3]: http://javalab.cs.uni-bonn.de/research/jmangler/
 [4]: http://www.gnu.org/copyleft/lesser.html