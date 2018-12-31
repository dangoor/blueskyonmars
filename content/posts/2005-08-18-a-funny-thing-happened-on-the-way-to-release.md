---
title: A funny thing happened on the way to release…
author: Kevin Dangoor
type: post
date: 2005-08-18T12:21:38+00:00
url: /2005/08/18/a-funny-thing-happened-on-the-way-to-release/
categories:
  - Blazing Things
  - Software Business

---
Last week, Ian Landsman wrote about [leaving features out][1] in order to get a product out the door, and I promised to write about delaying a product to make it stronger.

One thing about writing a blog is that, as long as you&#8217;re honest, you give yourself an automatic history. Something you can look back and reflect on. For example, on May 10th, I wrote that the [Zesty News alpha was feature complete][2], and that there was only bug fixing and interface cleanup to go. And that was true, at that instant. [Rich Sheridan][3] is fond of saying &#8220;last minute change is a competitive advantage&#8221;. If change is necessary to succeed, changing at the last minute is better than not changing at all.

So, a funny thing happened on the way to the alpha release: I decided to make some changes. Two things kicked off what I&#8217;m calling my Summer of Refactoring (aka, Thank God for Automated Tests): a desire for better perceived performance and an acknowledgement that plugins are more important to Zesty News than I had first thought.

I&#8217;ve been actively using Zesty News for months now. One thing that had bothered me a little bit, but not enough to take immediate action, was that the UI would sometimes pause for a second or two if feeds were being updated while I was reading. On one hand, it was a minor niggle&#8230; what&#8217;s a second or two, right? But, on the other hand, it breaks the flow of reading and lessens the total experience.

So, I started looking at my options. I ended up concluding that the sqlite database was just not the right database for Zesty News. It&#8217;s a _great_ database for a large number of desktop applications. But, Zesty News is almost like a multiuser application in that the feed updating happens right alongside the user&#8217;s reading. sqlite is very fast, but Zesty News has a fair bit of bookkeeping to do to work its magic.

At about the same time I came to that conclusion, I also looked at the field of competitors at the time and knew that plugins are going to be an important part of what Zesty News can offer. I&#8217;ve been planning all along that the difference between Zesty News Lite, the free version, and the full Zesty News would be completely implemented in plugins. That will greatly ease my maintenance burden, and it will also ensure that others who want to make plugins have a powerful facility to do so.

With a decision to change the database engine already there, I decided that I would open my mind to other changes that would make things easier for people who want to write plugins.

The first couple of weeks of June were lost to a false start on the database change. I liked many aspects of the change, but there was [a different performance problem][4] introduced there. One that was just not acceptable to me. Once I discovered that the Firebird database was actually a viable option, I was all set and could proceed forward.

The next step was to put in the best pieces for plugin writers, so that I could make writing plugins easier. I changed around a whole bunch of infrastructure parts that I had chosen. The shape of the Zesty News code changed around the edges, and everything was streamlined a bit and became more pleasant to work with.

The Zesty News of today no longer has the concurrency problem that it had on May 10th. The main interface looks _much_ better (thanks, Kirsten!), there is a smattering of new features, and the infrastructure is fun to work with. I&#8217;m exceedingly happy to have changed course, because I know that the Zesty News of today is going to be much better for what comes next: real users.

Sounds like a good time to start the alpha for real! And [that&#8217;s what I&#8217;m doing][5].

 [1]: http://www.blueskyonmars.com/2005/08/09/ian-landsman-on-leaving-features-out/
 [2]: http://www.blueskyonmars.com/2005/05/10/zesty-news-10-alpha-is-feature-complete/
 [3]: http://www.menloinstitute.com/
 [4]: http://www.blueskyonmars.com/2005/06/18/zodb-vs-pysqlite-with-sqlobject/
 [5]: http://www.blazingthings.com/