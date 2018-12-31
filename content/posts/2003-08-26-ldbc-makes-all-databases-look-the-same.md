---
title: LDBC Makes All Databases Look The Same
author: Kevin Dangoor
type: post
date: 2003-08-26T19:38:38+00:00
url: /2003/08/26/ldbc-makes-all-databases-look-the-same/
categories:
  - Software Development

---
If you&#8217;re writing Java code and trying to support multiple databases, your best bet is probably to use [Hibernate][1] and not write queries directly. Assuming you just really like SQL, you can also use[LDBC Liberty Database Connectivity][2] which provides a common SQL syntax and common behavior regardless of which database engine you attach to.

 [1]: http://hibernate.sf.net
 [2]: http://ldbc.sourceforge.net/ "LDBC Liberty Database Connectivity"