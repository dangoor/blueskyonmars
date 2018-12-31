---
title: Anthill looks pretty spiffy
author: Kevin Dangoor
type: post
date: 2003-06-18T22:51:37+00:00
url: /2003/06/18/anthill-looks-pretty-spiffy/
categories:
  - Software Development

---
Looking to turn on automated builds, I started looking at [Cruise Control][1] yesterday. The documentation left a little to be desired and before I had gotten too far I searched to see what other docs there were. That&#8217;s when I encountered [Anthill][2], which is an automated build system that runs in a webapp. Anthill is available in both open source and commercial versions. Deploying Anthill was very quick and easy, and all configuration could be done through the web.

I did run into a problem with JDK versions, because we have one project that is 1.3 and others that are 1.4. Anthill Pro ($1,299) allows you to select which JDK to use for each project (plus many other features over the open source version). We&#8217;re not ready to commit that much money to the tool. It looks straightforward to add that one feature in, though.

Which leads to an interesting question&#8230; Does a vendor with open source and commercial versions of a product accept patches to the open source version that add features that previously only existed in the commercial one?

 [1]: http://cruisecontrol.sourceforge.net/
 [2]: http://www.urbancode.com/projects/anthill/default.jsp "Anthill Build Management Server - Build and Release Management Tool"