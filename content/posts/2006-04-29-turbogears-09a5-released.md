---
title: TurboGears 0.9a5 released!
author: Kevin Dangoor
type: post
date: 2006-04-29T12:04:00+00:00
url: /2006/04/29/turbogears-09a5-released/
categories:
  - Python
  - TurboGears

---
Just in time for today&#8217;s documentation sprint, and packed with more
  
goodies than originally planned, TurboGears 0.9a5 (&#8220;incredible&#8221;) is
  
out!
  
This release unifies logging under the Python standard library logging module and makes it conveniently configurable. We&#8217;ve also added a new cron-like scheduler (based on Irmen de Jong&#8217;s Kronos). And, what I&#8217;m sure is going to be a big relief to our Python 2.3 users, Simon Belak has incorporated Phillip Eby&#8217;s convenient, 2.3-compatible decorator syntax:

> [expose()]
  
> def index(self):
  
> pass

Of course, Python 2.4 users can continue to use the standard @expose decorator syntax. But the example above is a whole lot more convenient than index = expose()(index). Especially given that TurboGears now has several valuable decorators to determine how your code behaves when accessed via the web.

There&#8217;s a lot more in this release: continued improvements to the widgets API, quickstart improvements, your usual round of bug fixes, etc.

As of now, there are no docs for the new features, but we&#8217;ll start
  
correcting that at 10AM Eastern today (join us at #turbogears on
  
freenode if you dare!).

Several people put in quite a bit of effort this week to make this
  
release possible (many of the folks in the Contributors section for this release
  
were quite active on the trunk list this week). The plan is for this
  
to be the last &#8220;0.9 alpha&#8221; release, so we pulled out the stops to get
  
the last upheavals done.

Check out the changes in the [TurboGears Changelog][1]

 [1]: http://www.turbogears.org/preview/about/changelog.html