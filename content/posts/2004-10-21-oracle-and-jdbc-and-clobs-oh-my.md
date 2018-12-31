---
title: Oracle and JDBC and CLOBs, oh my!
author: Kevin Dangoor
type: post
date: 2004-10-21T22:15:07+00:00
url: /2004/10/21/oracle-and-jdbc-and-clobs-oh-my/
categories:
  - Software Development

---
It&#8217;s pretty well-known that the Oracle JDBC drivers pre-10g don&#8217;t support CLOBs that are larger than 4K. The 10g drivers do support large CLOBs (up to 4GB, I think) and even work with 9i, which is what we&#8217;re using. But there appear to be some creepy, made-for-Halloween bugs in there&#8230;
  
<!--more-->


  
The particular table that is causing me grief has two CLOBs in it (which may be contributing to the problem). I&#8217;m using Hibernate to do my SQL, which is really great.

So, the first problem that I encountered was that the values that I was setting for the two CLOBs _were getting reversed_. The specific scenario: both CLOBs were fairly large. Hibernate does a setCharacterStream when you declare a field to be Hibernate type &#8220;text&#8221;. Only with large strings (the ones I used were greater than 4K), these fields were getting swapped on the way in to the database. getCharacterStream seemed to behave &#8220;properly&#8221;, meaning that the values were still swapped when we pulled them out.

My workaround for this was to set the Hibernate property type to &#8220;string&#8221; and the database column sql-type to &#8220;clob&#8221;. Having Hibernate do setString and getString on the PreparedStatement worked fine.

Until problem number two. I did an insert via a PreparedStatement with large (about 1700 characters) strings. That insert worked fine. However, if you reuse the PreparedStatement, as Hibernate wisely does, the _next_ insert fails. What&#8217;s the error you see? &#8220;Cannot set (primary key column) to null&#8221;. Of course, no one was trying to set that column to null.

These are drivers I picked up from Oracle&#8217;s site just a couple weeks back, so I think they&#8217;re the latest. I guess it&#8217;s time to file a bug report.