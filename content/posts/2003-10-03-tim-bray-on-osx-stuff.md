---
title: Tim Bray on OSX stuff
author: Kevin Dangoor
type: post
date: 2003-10-03T20:02:15+00:00
url: /2003/10/03/tim-bray-on-osx-stuff/
categories:
  - Technology

---
I have joined the ranks of Mac OS X users with a new 12&#8243; PowerBook. If you&#8217;re wondering why I opted for the 12&#8243; model, I chose it because I wanted a really portable notebook. The 12&#8243; is one pound (20%) lighter and considerably smaller than the 15&#8243;. 

Onto the main topic&#8230; using the new machine! I&#8217;ve spent quite a bit of time with Windows and Linux machines and only a little time with Macs. Mac OS X is a dream! It&#8217;s got a GUI that looks and works great and a full-featured Unix underbody.

Recently, Tim Bray, who has written some great articles, wrote about troubles he had [getting open source tools to run under OS X][1]. There are a few things in this article that don&#8217;t line up with my experiences:

> First of all, fink only knows about perl 5.6, which just doesn’t cut it for XML and Unicode.

When I look at the list of packages available via Fink Commander (a nice GUI interface to Fink that comes in the Fink install package), I see Perl 5.8 listed there.

> sudo apt-get install mysql&#8230; This gets binaries rather than source

Fink&#8217;s readme says that it actually uses apt-get. Within Fink Commander, it&#8217;s really easy to choose between downloaded source and downloading binary.
  
The next bit is a matter of preference. In [How To Use OS X][2] Tim says:

> Of course, implicit in this is the notion that the default workings of the Dock, which whimsically mix shortcuts, applications you can run, applications that are running, minimized windows, and the wastebasket, are totally B.A.D. (Broken As Designed).

I think the dock (as designed) is actually a neat idea. As computer science folk, we often want to lord over the domain of our machines, letting nothing run without being completely aware of it. I like the Dock, though, because I can think &#8220;I want to use Safari now&#8221;, click the Dock icon and Safari pops up, whether it was running or not. And, it&#8217;s still pretty easy to tell what&#8217;s running because the Dock has little triangles below each docked app that is running.

Tim&#8217;s suggestion to put the Dock on the side is a good one, because screen real estate does come at quite a premium, especially on a 12&#8243; screen.

 [1]: http://www.tbray.org/ongoing/When/200x/2003/09/26/GDHell2 "ongoing Â· Open Source OS X Hell Again"
 [2]: http://www.tbray.org/ongoing/When/200x/2003/10/01/HowToUseOSX