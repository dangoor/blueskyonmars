---
title: Force use of launchd in Tiger
author: Kevin Dangoor
type: post
date: 2005-06-04T02:25:19+00:00
url: /2005/06/03/force-use-of-launchd-in-tiger/
categories:
  - Technology

---
Here&#8217;s a useful tip: [upgraded Tiger installs don&#8217;t use launchd][1]. Even better, that link tells you how to make Tiger use launchd. Why would you want to? Because launchd breaks the bottleneck that caused earlier Mac OS Xs and still causes Linux to boot slowly. It allows daemons to more easily launch in parallel.

 [1]: http://www.macosxhints.com/article.php?story=20050504185019359