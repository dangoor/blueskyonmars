---
title: TurboGears 0.8.7 released!
author: Kevin Dangoor
type: post
date: 2006-01-05T18:00:15+00:00
url: /2006/01/05/turbogears-087-released/
categories:
  - TurboGears

---
[TurboGears][1] 0.8.7 is out and available for [download][2].

## 0.8.7 (January 4, 2006) {#087_january_4_2006}

This update primarily solves installation issues and is not required otherwise.

  * quickstart corrected to properly produce egg-info directories (previously, directories could be created with &#8220;-&#8221; when it should have a &#8220;_&#8221;). Note that setuptools 0.6a9 will warn you if you have a &#8211; in your egg-info directory name. Just rename the directory, and you&#8217;ll be fine.
  * Installation issues that people may have had earlier are resolved in this setuptools update.
  * version number set to 0.8.7 to reflect that this is considered the &#8220;stable&#8221; version of TurboGears vs. the current 0.9 code in svn.

_Project Updates_

  * setuptools 0.6a9
  * sqlobject 0.7.1dev_r1457 (updated to handle the setuptools change, but also includes other bugfixes)

## 0.8a6 (December 26, 2005) {#08a6_december_26_2005}

  * Chained validators will now cause an Invalid exception to be raised as appropriate.
  * When validation would fail, previously an unexpected exception may be raised when an Invalid exception is expected
  * quickstart didn&#8217;t look out for .pyo files in the same way that it did .pyc files.

_Project Updates_

  * json-py updated to 3.4

 [1]: http://www.turbogears.org
 [2]: http://www.turbogears.org/download/index.html