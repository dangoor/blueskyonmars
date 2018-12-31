---
title: Unit testing against interfaces
author: Kevin Dangoor
type: post
date: 2003-06-24T19:03:47+00:00
url: /2003/06/24/unit-testing-against-interfaces/
categories:
  - Software Development

---
Carlos points out a nice [testing technique used by the Commons VFS folks][1]:

> What they developed was a test harness based on JUnit to test all the different implementations without having to rewrite all the tests for each implementation.

One set of unit tests will ensure that the FTP, SMB, JAR, etc. implementations all work correctly. We&#8217;re working on project with a very componentized architecture right now, and testing against the interfaces this way seems like a very useful idea. This won&#8217;t preclude doing white box test-first development of the implementations, though.

 [1]: http://roller.anthonyeden.com/page/ceperez/20030624#liskov_s_substitution_principle_and "::Manageability::"