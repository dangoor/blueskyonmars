---
title: The kind of user you should strive to please
author: Kevin Dangoor
type: post
date: 2004-12-18T18:39:48+00:00
url: /2004/12/18/the-kind-of-user-you-should-strive-to-please/
categories:
  - Software Development

---
Mary Hodder ran into a problem with NetNewsWire that [lost some of her data][1]. The discussion that follows there and in the [follow-up post][2] is interesting and worth a read for any software developer working on a commercial product. There are a bunch of intertwined issues here: stability and level of support for an inexpensive product, expectations for a public beta and expectations for commercial software in general.

It has traditionally been the case that features win out over low bug count. (Microsoft is proof-positive of this). I believe this to be true particularly in a quickly-evolving area like RSS readers. But, that doesn&#8217;t extend to (1) data loss and (2) security.

As you&#8217;ll read in Mary&#8217;s post, people don&#8217;t care about the cost of the software in comparison to the cost of their time. Here is the guideline I would use:

  * Don&#8217;t ship software (even public betas) with any known data loss bugs
  * Don&#8217;t ship software until you&#8217;re comfortable that your test suite tackles potential data loss scenarios
  * Provide a good way to allow users to back up their data, and make it clear to the user exactly how they do it
  * If a data loss bug comes up (or even one that appears to be a data loss bug) drop _everything_ and work on that.

There&#8217;s no way to know for sure that you&#8217;ve caught every data loss bug, which is why I make that forth point. I remember sending a message to a Zope mailing list back in &#8217;99, with what I thought had been a data loss issue. Jim Fulton, CTO of Zope Corp., jumped on the issue right away. Since Zope has its own database engine, the ZODB, this is the right kind of response. (It&#8217;s also a good idea not to write your own database engine, unless you feel like dealing with these issues yourself!)

The security issue was almost a non-issue a few years ago. Then, everyone got connected to the Internet. The only thing worse than a user losing the data that your program creates is the user losing _all_ of their data (and possibly getting their identity stolen as well!).

One last comment on Mary&#8217;s post. She is clearly a &#8220;power-user&#8221;. NetNewsWire probably doesn&#8217;t have many users that use the software the way she does. Since she represents a small percentage of the user population, someone running a small business can, quite reasonably, decide that this is not a market they wish to serve.

On the other hand, if you can make a power-user happy, they will generally be very strong advocates for your software. In an age like today, where bloggers can quickly spread the word among hundreds or thousands of people, I think that working to please folks like Mary is a good way to shape up your overall business.

(Though I wanted to wrap on that point, I just want to add a clarification: pleasing the power-users on _quality_ is an important thing to do. Pleasing them on features, however, is a marketing position choice&#8230;)

**Update:** I just realized that I didn&#8217;t comment at all on Ranchero&#8217;s handling of this particular problem (Ranchero makes NetNewsWire). From what I read and have seen in the past from Brent Simmons, I don&#8217;t think Ranchero was far off here. What I would have done differently: if a problem crops up that eats data and I already have a public beta, I would send out a warning and pull the public beta until the problem is fixed. It also sounds like Brent didn&#8217;t grab the files and do the investigation until later, whereas I would have dropped everything and moved the investigation to the top of my queue. Prioritization is tough, because you&#8217;re always strapped for resources. I just put data loss and security issues at the top of the heap. Others may view it differently.

 [1]: http://napsterization.org/stories/archives/000372.html
 [2]: http://napsterization.org/stories/archives/000373.html "Napsterization"