---
title: What I tested wasn’t really a mock
author: Kevin Dangoor
type: post
date: 2004-01-12T23:58:13+00:00
url: /2004/01/12/what-i-tested-wasnt-really-a-mock/
categories:
  - Software Development

---
[Aslak Hellesoy&#8217;s uncommon sense &#8211; Oh no, we&#8217;re testing the Mock!][1] describes an anti-pattern (and I agree with him here) about testing a subclass of the class you&#8217;re trying to test, rather than the class itself. In his example, he used inversion of control to make things easier to test, which is great. Unfortunately, I had a case a few months ago where implementing his anti-pattern seemed the simplest and most reasonable testing solution (below is my comment to his post):

I agree in general with what you write here, but I ran into a spot where your anti-pattern seemed to be the most straightforward approach to take. I was test driving a new piece of code that was dependent on ancient code (that I don&#8217;t &#8220;own&#8221;) that was not developed in a test-driven, loosely coupled way. The ancient code was a DAO of a sort, and it was a concrete class and not an interface. And, what I was developing was a servlet.

The way this particular class that I had to use was written, there was really no way to do IoC. So, I broke out the database-related actions (only a couple of lines worth) into separate methods that I overrode in a test subclass and then tested the subclass.

Is it icky? Sure, and I certainly wouldn&#8217;t have done the data access the way it was implemented way back when. But, in the case of the code that I was writing, I was successfully testing the functionality provided by my servlet.

I like what you&#8217;ve done in your example. Inversion of control is definitely a lot cleaner and nicer than a subclass inside your test class.

 [1]: http://blogs.codehaus.org/people/rinkrank/archives/000551_oh_no_were_testing_the_mock.html "Aslak Hellesoy's uncommon sense - Oh no, we're testing the Mock!"