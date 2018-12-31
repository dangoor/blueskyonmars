---
title: Hibernate bug – not a bug after all
author: Kevin Dangoor
type: post
date: 2004-11-20T03:40:22+00:00
url: /2004/11/19/hibernate-bug-not-a-bug-after-all/
categories:
  - Software Development

---
The [bug in Hibernate][1] that I reported yesterday turned out to be [a bug in my Interceptor][2]. To get to this conclusion, we did a bit more tracing through the code and managed to put together a minimal failing test (see the forum posting). I had read the Interceptor docs several months back when we implemented the first features we needed. Max from the Hibernate team reminded me of this requirement:

> * The <tt>Session</tt> may not be invoked from a callback (nor may a callback cause a collection or proxy to
  
> * be lazily initialized).

Oops. You&#8217;ll see in my test that my Interceptor is indeed causing a lazy collection to be initialized. The workaround I suggested, which involved deleting a couple lines of code, does actually solve this problem. It is, however, unclear what other problem might be caused by that change.

So, what&#8217;s the solution? For the case that I was dealing with today, it was simple to just not touch the Collections at all. There are other possible places that the Interceptor _could_ cause a lazily loaded Collection to be initialized. My general strategy is this: use Hibernate.isInitialized to check it&#8217;s status. If it&#8217;s not initialized and I really need to use it, I&#8217;ll load the object up in a different Session.

 [1]: http://www.blueskyonmars.com/
 [2]: http://forum.hibernate.org/viewtopic.php?t=936299 "Hibernate Forums - View topic - NullPointerException - Set in Collection not initialized"