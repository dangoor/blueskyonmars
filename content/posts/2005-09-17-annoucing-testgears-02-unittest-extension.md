---
title: Annoucing TestGears 0.2 unittest extension
author: Kevin Dangoor
type: post
date: 2005-09-17T17:42:49+00:00
url: /2005/09/17/annoucing-testgears-02-unittest-extension/
keywords:
  - testgears
categories:
  - Python

---
Last month, I [introuced Testido][1], a unittest extension that removes the need to write TestSuites by hand and simplifies some testing. To be in line with [TurboGears][2], for which Testido was originally created, the package has been renamed TestGears.

Here are the changes between Testido 0.1 and TestGears 0.2:

* unittest.TestCase instances are collected regardless of whether their names begin with &#8220;test&#8221;. (Thanks to Robert Brewer for the report.)
  
* Now calls setup\_module(module) and teardown\_module(module) as in py.test.

 [1]: http://www.blueskyonmars.com/2005/08/27/announcing-testido-automatic-unittest-testsuite-generator/
 [2]: http://www.turbogears.org