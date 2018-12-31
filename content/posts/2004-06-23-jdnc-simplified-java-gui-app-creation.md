---
title: 'JDNC: Simplified Java GUI app creation'
author: Kevin Dangoor
type: post
date: 2004-06-24T04:30:29+00:00
url: /2004/06/23/jdnc-simplified-java-gui-app-creation/
categories:
  - Software Development

---
Sun has introduced a new open source project called [JDNC][1] which, unfortunately, stands for JDesktop Network Components. (It&#8217;s the &#8220;Network&#8221; part that seems a little out of place&#8230;)

I probably would not have started working on my own framework a few months back had this existed. JDNC takes a markedly different approach to the one I took, but there are very similar goals.

Sadly, the project was apparently initially motivated to make the JDNC markup language, which is yet another XML UI definition language. Ick. The ability to define your GUI in XML, in my opinion, is not a gigantic win. The ability to define your GUI declaratively _is_ a big win, and that&#8217;s the approach I&#8217;ve been taking.

Thankfully, though, JDNC looks like it has some really nice ideas and components. I&#8217;m going to have to see where the touchpoints are between JDNC and our framework, because I think that I can reasonably use JDNC components and probably even offer improvements back.

 [1]: http://javadesktop.org/articles/JDNC2/index.html "JavaDesktop: JDNC"