---
title: Java object allocation and deallocation is cheap
author: Kevin Dangoor
type: post
date: 2004-02-18T20:22:47+00:00
url: /2004/02/18/java-object-allocation-and-deallocation-is-cheap/
categories:
  - Software Development

---
I missed this one a couple weeks ago, but Gavin King brought it up in the context of [evil finalizers][1]. [Java theory and practice: Garbage collection and performance][2] talks about how modern JVMs perform allocation and deallocation of objects and how it&#8217;s _cheap_, so you really shouldn&#8217;t make your programs harder to read for anticipated GC-related performance gains.

 [1]: http://blog.hibernate.org/cgi-bin/blosxom.cgi/2004/02/18#finalize
 [2]: http://www-106.ibm.com/developerworks/library/j-jtp01274.html "Java theory and practice: Garbage collection and performance"