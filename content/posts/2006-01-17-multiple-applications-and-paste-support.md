---
title: Multiple applications and Paste support
author: Kevin Dangoor
type: post
date: 2006-01-17T18:43:05+00:00
url: /2006/01/17/multiple-applications-and-paste-support/
categories:
  - TurboGears

---
Here&#8217;s a decent [summary of a #cherrypy meeting (deFuze.org)][1] we had yesterday in which we discussed the ability to run multiple CherryPy &#8220;apps&#8221; in the same server process and running CherryPy apps behind Paste. The short of it is that TurboGears 0.9 won&#8217;t run multiple apps in process, but somewhere between 0.9 and 1.0 we&#8217;ll either go with Ian Bicking&#8217;s CherryPaste or with CherryPy 2.2&#8217;s new tree.mount feature to allow multiple TurboGears apps to run in process. The choice between the two will be dependent on how comfortable with the mechanisms used. The CherryPaste solution is better because it brings Paste integration and looks more like what people have in mind for CherryPy 3.0. But, I want to be sure about how well it&#8217;s going to work with things we&#8217;ve got running now and different approaches to declaring multiple apps.

 [1]: http://www.defuze.org/oss/blog/entry/2006/01/17/multi-applications-and-paste-support