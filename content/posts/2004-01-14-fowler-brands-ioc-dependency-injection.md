---
title: Fowler brands IoC “Dependency Injection”
author: Kevin Dangoor
type: post
date: 2004-01-14T21:01:08+00:00
url: /2004/01/14/fowler-brands-ioc-dependency-injection/
categories:
  - Software Development

---
Martin Fowler provides a good dissection of the current [lightweight container hullabaloo][1]. He&#8217;s promoting the term &#8220;Dependency Injection&#8221; over &#8220;Inversion of Control&#8221;, because IoC is a bit generic for the pattern. The article also contrasts Dependency Injection with the Service Locator pattern, and does a nice job of list the pros and cons of each approach.

For Dependency Injection, he ultimately sides with PicoContainer&#8217;s constructor injection approach, admitting that ThoughtWorks folks are involved in PicoContainer&#8217;s development. I agree with his reason, though: you can use your constructors to ensure that your objects are always valid, even upon initial creation.

Any decent-sized, loosely-coupled system is going to run into the types of issues solved by these patterns. This article is a nice treatment of the topic.

 [1]: http://martinfowler.com/articles/injection.html "Inversion of Control Containers and the Dependency Injection pattern"