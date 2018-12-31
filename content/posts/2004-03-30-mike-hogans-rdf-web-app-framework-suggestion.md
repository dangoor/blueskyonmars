---
title: Mike Hogan’s RDF web app framework suggestion
author: Kevin Dangoor
type: post
date: 2004-03-31T02:23:29+00:00
url: /2004/03/30/mike-hogans-rdf-web-app-framework-suggestion/
categories:
  - Software Development

---
Mike Hogan pitches [an application architecture that should yield superior productivity][1]. He talks about using RDF as his data model, though he admits that there isn&#8217;t very good tool support for RDF at this point. That&#8217;s certainly one trouble I&#8217;ve seen with putting RDF to practical application.

He talks about storing the data in Prevayler. Sure, there is a class of applications for which having all of your data in memory is fine. But, there are also plenty of applications where a larger data store is needed.

I&#8217;ve been thinking of this problem a little bit recently. I used Zope extensively for about a year, and find that the ZODB provides really great transparent persistence and doesn&#8217;t require you to have your entire database in memory. Of course, you have to be using Python to use the ZODB.

Recently, I also came across the IO Language, which seems like an unfortunate name because searching for &#8220;IO&#8221; on Google does not retrieve useful results. That said, I noticed something interesting in IO&#8217;s SQLLite interface: a &#8220;Soup&#8221; module. A &#8220;Soup&#8221; is a concept from the Newton. It&#8217;s basically an object store that indexes on named properties of your choosing.

Once you&#8217;ve worked with flexible, transparent persistence, you don&#8217;t want to go back. Hibernate is reasonably transparent (at least about as transparent as you can get in Java), but it still requires all of the maintenance of an SQL database. Yes, yes, I know that no one has yet made an object database that can scale as well as an RDBMS. But, there are a whole lot of applications you can do that fit within the scale that various object databases can accomodate.

I hope that Groovy will help to bring a little bit of dynamic behavior to the sometimes overly static world of Java. [Nanoweb][2] seems like a good start, because there&#8217;s just way too much housekeeping required for a typical Java webapp.

 [1]: http://www.softwarecraftsmen.com/blog/archives/000031.html "Software Craftsmen: An application architecture that should yield superior productivity (updated)"
 [2]: http://docs.codehaus.org/display/NANO/NanoContainer+NanoWeb