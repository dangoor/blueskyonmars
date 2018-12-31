---
title: Does TDD shun reuse?
author: Kevin Dangoor
type: post
date: 2003-07-09T00:05:41+00:00
url: /2003/07/08/does-tdd-shun-reuse/
categories:
  - Software Development

---
Mike Hogan asks whether [Test Driven Development discourages component reuse][1]. He gave a simple, clear example where he made a &#8220;grep&#8221; routine more flexible by delegating some of the function to other interfaces. My response:

Reusability is not really orthogonal to function, but comes as part of the function. Because we&#8217;ve all been taught in school that changing software is really expensive, the tendency has been to generalize software where it&#8217;s not required. If you never plug a new logger or regex provider into that code, the extra effort (and obfuscation) that comes in the ReusableGrep is just not worth it.

If it&#8217;s a customer requirement that the grep routine supports those plug points (and you&#8217;re delivering an API to them), then that should indeed be tested for and written. If someone is really doing test driven development, they will write those tests.

Or, if in the course of meeting customer requirements, you find that you&#8217;ve created a Log4JGrep and a JDK14Grep, then you&#8217;ll create the pluggable form through the course of normal refactoring.

I&#8217;m echoing some of what Rod said in his post, but I do think that the simplicity aspect is one of the critical parts of being agile. The point is that you don&#8217;t add additional layers for the sake of reusability until there is a customer need that requires it.

 [1]: http://www.softwarecraftsmen.com/blog/archives/000003.html "Software Craftsmen: Test Driven Development versus Component Reuse"