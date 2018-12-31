---
title: XP Debiled
author: Kevin Dangoor
type: post
date: 2003-08-26T00:05:33+00:00
url: /2003/08/25/xp-debiled/
categories:
  - Software Development

---
I&#8217;m not sure why I&#8217;m taking the bait from this [anti-XP rant at the BileBlog][1], but I am. Before I start: I am _not_ saying that everyone should use XP everywhere all the time. Now that that&#8217;s out of the way&#8230;

> The customer wants to get the most bang for the buck, and wants to cram in as much as possible for as little expenditure (both financial and time) as possible to them.

Yes, times are tough and people have to go for business where they can find it. But, if that&#8217;s truly what your customers want, I&#8217;m sure there&#8217;s an increased chance of the project [not being successful][2]. Companies want to spend as little as possible, but they also want their projects to succeed. The point of having a lot of customer interaction is not to air your dirty laundry but to make sure that what you implement is actually what the customer wants. It&#8217;s not uncommon for the view of what the customer wants to change between the start of the project and the end, and lack of customer interaction is one signficant reason for project failure&#8230; the customer simply didn&#8217;t get a product that did what they wanted at the end of the development.

> More important is to define milestones and releases, rather than just churn out release after release.

XP is not about making frequent &#8220;releases&#8221;. XP is about having visible, demonstrable results on a predictable (2-3 week) schedule. The customer decides when an actual release (as in code shipped to end user) happens.

> Unit tests are wonderful things, and can provide a great deal of robustness and regression testing for a system. However, I&#8217;ve found that in real life, QA engineers will still always find a whole bunch of issues.

Undoubtedly, though they will probably find fewer issues than if you weren&#8217;t doing test driven development. Also, it seems that you missed the fact that you are supposed to have [automated functional tests][3], too. Ideally the customer would create these, so that they have something they can trust that says that development is done. I do think reality diverges from the ideal here, only the savviest of customers could create their own automated functional tests.

> Almost as much time is spent (wasted?) on getting unit tests up to date, functional, and well behaved as fixing the actual code itself.

It doesn&#8217;t sound like you&#8217;ve ever actually done XP. If you&#8217;re doing test driven development, you should never be working on &#8220;getting unit tests up to date&#8221;. You would have written a failing unit test before changing any of your main code. Getting unit tests up to date can be a lot of work, because code that is written test-driven looks different than code that is not. It&#8217;s designed to be tested, and your test code is usually very simple.

> Many projects require very specific in-depth domain knowledge, and shuffling people around such that chances are that most are moved away from their main areas of expertise is simply flushing talent down a toilet.

I don&#8217;t think an XP team would stick a pair of clueless newbies in a room by themselves to work on something they&#8217;ve never seen before. If something is very esoteric and one person on the team knows about that, odds are that person will be paired with someone working on that part. _Most_ programming is not quite that far out. XP teams are usually located in an open environment which means that the pairs are not working in isolation. Someone from one pair can toss in some guidance as needed.

> It simply expects too much from everyone, and assumes that the &#8216;average&#8217; developer is versatile, talented, experienced, motivated, and highly enthusiastic

Any team will be made up of a combination of people, with varying skill sets. In fact, you want a team with varying skill sets. People at [Menlo Innovations, a local XP shop,][4] mention that they have had great success where less-experienced developers would come up with novel solutions that are better than what the more-experienced developers came up with. Not because of any failing of the experienced developers, but because the less-experienced ones are not set in any particular ways of doing things.
  
Anyone who is not motivated to do good work and help the project be a success should be fired.
  
In response to comments on the original posting: I do view the XP practices as a toolset that you can pick and choose from, but you can&#8217;t really say you&#8217;ve been doing XP without doing them all. There are synergies that come up when you do all of them. Doing unit testing and refactoring alone is a big win for code maintainability and the ability to add features quickly.

> Finally, if your developers are equally talented, one of them is bound to spend a lot of time being bored to tears as the &#8216;typist&#8217; fleshes out mundane but necessary aspects of the system.

Generally, people switch back and forth from the driver seat frequently. And if the person who is not driving is &#8220;bored&#8221;, they&#8217;re not doing what they&#8217;re supposed to be doing. While the driver (typist) is handling the mundane details, the other person is supposed to be keeping an eye out for the big picture: how well does this code fit the overall design? are there places that this can be refactored?

> Write tests for the parts that are critical. A sound architecture will usually take care of the rest.

And what happens when a new requirement comes up that the &#8220;sound architecture&#8221; designed 2 years ago doesn&#8217;t address? People generally end up adding warts to an otherwise nice architecture, because they don&#8217;t want to break anything. When you do test first development and your tests cover the bulk of your code, you can change things a lot more comfortably.

> IT: &#8220;Which are the most important features?&#8221;
  
> USER: &#8220;They all are&#8221;
  
> IT: &#8220;Can you please rank them&#8221;
  
> USER: &#8220;OK, as long as you deliver them all&#8221;

Yes, we all know that user. The fact of the matter is that if the user is defining the features _and_ the timeline, the project is likely to fail. Most projects have a fixed time horizon. The point with XP is to give the user the knowledge they need to make choices about their end-result product. If you want to say &#8220;Sure, we&#8217;ll give you all of the (undefined) features you want in 4 weeks&#8221;, go for it&#8230; and be ready to spend 80 hour weeks on a project that is buggy and comes out 4 weeks late.
  
There&#8217;s always got to be a process for managing the scope of a project. XP is an &#8220;agile&#8221; method, which means that the process supports changes in feature set anywhere along the cycle, as opposed to the &#8220;big design up front&#8221; methods. Either one can work, it just depends on the project and customer expectations.

 [1]: http://www.freeroller.net/page/fate/20030824#xp_debunked "The BileBlog"
 [2]: http://www.standishgroup.com/press/article.php?id=2
 [3]: http://www.xprogramming.com/xpmag/whatisxp.htm#customer
 [4]: http://www.menloinstitute.com/