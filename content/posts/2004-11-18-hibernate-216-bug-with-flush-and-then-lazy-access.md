---
title: Hibernate 2.1.6 bug with flush and then lazy access
author: Kevin Dangoor
type: post
date: 2004-11-19T05:25:05+00:00
url: /2004/11/18/hibernate-216-bug-with-flush-and-then-lazy-access/
categories:
  - Software Development

---
Today, I finally had time to spend a couple good, solid hours in the debugger, during which time I came to the conclusion that the problem my code was having was not in my own code. Sure, the exception was actually happening in an org.hibernate class, but what are the odds of encountering an honest to goodness Hibernate bug? Looks like I did find one, though: [Hibernate Forums &#8211; View topic &#8211; NullPointerException &#8211; Set in Collection not initialized][1]

From my forum posting, here are the steps that trigger this:

> 1) create a class with a lazy collection
  
> 2) Load up an entity of that class
  
> 3) do whatever you want, but don&#8217;t touch that lazy collection
  
> 4) flush the session
  
> 5) try to access that lazy collection 

Hibernate is a great tool, and I&#8217;m very thankful that it&#8217;s open source. While I&#8217;m not averse to paying for good software, I wouldn&#8217;t want a library that does not include source. If I had to report this problem to a vendor and wait for them to a) agree that it&#8217;s a problem, b) fix it, c) release the fix, I&#8217;d be hurting. In this case, it was really easy to get the Hibernate source running in Eclipse, learn a bit about how collection initialization works, and find a seemingly reasonable place for a fix.
  
**Update:** This is not a Hibernate bug. It&#8217;s a mistake in my Interceptor code. [Film at 11][2].

 [1]: http://forum.hibernate.org/viewtopic.php?t=936299 "Hibernate Forums - View topic - NullPointerException - Set in Collection not initialized"
 [2]: http://www.blueskyonmars.com/archives/2004/11/19/hibernate_bug_not_a_bug_after_all.html