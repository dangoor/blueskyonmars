---
title: TurboGears 0.8.8 security fix release
author: Kevin Dangoor
type: post
date: 2006-01-10T18:21:26+00:00
url: /2006/01/10/turbogears-088-security-fix-release/
categories:
  - Python
  - TurboGears

---
I have just released TurboGears 0.8.8. The only change from 0.8.7 is the requirement of CherryPy 2.1.1.

The staticfilter of CherryPy 2.1.0 has a serious security flaw that would allow people to retrieve files from &#8220;..&#8221;. You should update as soon as possible:

  * You can run &#8220;easy_install CherryPy>=2.1.1&#8221; as the simplest update path
  * You can also use the standard TurboGears upgrade instructions: <http://www.turbogears.org/download/upgrade.html>

Thanks to Remi Delon and the others on the CherryPy team for a fast fix and release on this issue!