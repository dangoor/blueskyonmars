---
title: 'memcached: high-performance in-memory caching'
author: Kevin Dangoor
type: post
date: 2005-02-10T16:37:10+00:00
url: /2005/02/10/memcached-high-performance-in-memory-caching/
categories:
  - Software Development

---
[memcached: a distributed memory object caching system][1] has APIs in Perl, Python, PHP, Ruby, C and Java and is designed for websites that have heavy database-intensive, mostly-read pages. The interesting thing here is that memcached does not exist through some theoretical &#8220;what if?&#8221; premature optimization. It was created by the LiveJournal folks who were dealing with 20 million dynamic page views per day. Other high-traffic sites like Slashdot and WikiPedia are users.

(Discovered via [Titus Brown][2].

Update (4/8): memcached [has been forked][3], apparently to fix some bugs. The new project is called Tummy.

 [1]: http://www.danga.com/memcached/ "memcached: a distributed memory object caching system"
 [2]: http://www.advogato.org/person/titus/
 [3]: http://www.python.org/pypi/Sean%20Reifschneider/1.2_tummy3