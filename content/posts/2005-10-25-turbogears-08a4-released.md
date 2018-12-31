---
title: TurboGears 0.8a4 released
author: Kevin Dangoor
type: post
date: 2005-10-25T19:29:56+00:00
url: /2005/10/25/turbogears-08a4-released/
categories:
  - Python
  - TurboGears

---
This is a minor update to [TurboGears][1], including 3 project upgrades and a fix. The use of setuptools 0.6a6 means that it should now be much easier to do a [non-root installation][2] of TurboGears on Unix-like systems.

Here&#8217;s the changelog entry:

## 0.8a4 (October 25, 2005)

_Project Updates_

  * setuptools 0.6a6
  * CherryPy 2.1 final
  * MochiKit 1.0

_Fixes_

  * On some servers, TurboGears can take a minute to start answering
  
    connections due to the way the OS handles incoming connections to
  
    ports that have nothing listening on them.

 [1]: http://www.turbogears.org
 [2]: http://peak.telecommunity.com/DevCenter/EasyInstall#non-root-installation