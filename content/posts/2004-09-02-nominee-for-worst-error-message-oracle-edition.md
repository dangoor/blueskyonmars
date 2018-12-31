---
title: Nominee for worst error message (Oracle edition)
author: Kevin Dangoor
type: post
date: 2004-09-02T22:34:47+00:00
url: /2004/09/02/nominee-for-worst-error-message-oracle-edition/
categories:
  - Software Development

---
So, we&#8217;ve been happily using Hibernate to store our object graph in Oracle with a minimum of fuss. Yesterday, trying to work with a certain set of data, we started hitting this lovely error message from Oracle:

ORA-01483: invalid length for DATE or NUMBER bind variable

By setting logging to &#8220;COPIOUS BUCKETFULLS&#8221; we could conveniently see that the query in question was an insert into a table with three columns. There was only one column that was a date or number, so one would think that column was the problem.

Of course, one would turn out to be wrong. The other two columns were CLOBs, and Oracle CLOBs don&#8217;t just let you setString to something larger than 4000 characters. Java [programmers][1] [everywhere][2] are [suffering][3] through this. Gah.

The problem itself is really annoying, but that error message is the real kicker. It doesn&#8217;t even mention a CLOB! Just goes to show that usability is important for APIs, and not just end-user software.

If you&#8217;re a Hibernate user, the [official Hibernate page on this topic][4] has some code to help get around this problem. It&#8217;s not pleasant, but what else can you do? (Short of writing your own Oracle JDBC driver, I guess&#8230;)

 [1]: http://www.objectstyle.org/cayenne/lists/cayenne-user/2003/05/0003.html
 [2]: http://www.mail-archive.com/jboss-user@list.working-dogs.com/msg10169.html
 [3]: http://forum.hibernate.org/viewtopic.php?t=928701&highlight=invalid+length+number
 [4]: http://www.hibernate.org/56.html