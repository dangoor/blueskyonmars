---
title: Comment and trackback spam
author: Kevin Dangoor
type: post
date: 2005-02-04T20:22:06+00:00
url: /2005/02/04/comment-and-trackback-spam/
categories:
  - Technology

---
Over the past few days, I&#8217;ve gotten blasted by a bunch of trackback spam. Comment spam has been all but nonexistent since I installed James Seng&#8217;s [SCode][1] plugin. The new round of trackback spam enticed me to check out whether there had been updates to the popular MT-Blacklist plugin. There had been, so I installed the update.

Bam! I got a slew of new comment spam. I found it hard to believe that a human being would have entered all of that spam. So, I tested out my SCode plugin. I had forgotten that you have to add a small hack to the MT-Blacklist plugin to use it with SCode. Woops. I updated SCode, readding the hack in and should now be comment spam free again.

One plus, was that I discovered that James Seng has a clever solution for [trackback spam][2]. It double checks that the trackback is coming from the same server that the ping refers to. It&#8217;s not perfect, and will shut out some reasonable pings&#8230; but, there&#8217;s only so much time I want to devote to cleaning up trackbacks. (MT-Blacklist does a great job of that, but I&#8217;d rather not even deal with it.)

 [1]: http://james.seng.cc/archives/000145.html
 [2]: http://james.seng.sg/archives/2005/02/04/solution_to_trackback_spams.html