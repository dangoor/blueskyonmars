---
title: TurboGears on day 4 and some Jeremy Jones commentary
author: Kevin Dangoor
type: post
date: 2005-09-21T15:26:57+00:00
url: /2005/09/21/turbogears-on-day-4-and-some-jeremy-jones-commentary/
categories:
  - Python
  - TurboGears

---
[TurboGears][1] certainly got going with a bang this past Saturday. We&#8217;re almost at the 4 day mark now, and the &#8220;20 Minute Wiki&#8221; screencast has been viewed more than 2,800 times. (Consuming 225GB of bandwidth!). turbogears.org has served up more than 2,600 eggs. The discussion mailing list has 89 members.

Before Saturday, doing a Google search for TurboGears yielded a few dozen results. Now, Google says there are 23,400 results.

The mailing list is getting some good discussion going. Monday was &#8220;Installation Day&#8221; with Phillip Eby fielding questions and figuring out how installation on Linux and other systems that already have Python can be improved.

Discussions now are turning more toward building webapps. With CherryPy as a base, you can certainly do whatever you need to do to create webapps. But, that&#8217;s not why TurboGears exists. The questions that people are asking now are the features we&#8217;re going to see in TurboGears tomorrow. For any kind of common requirement, &#8220;you can integrate this other package, good luck!&#8221; is not the right answer.

Luckily, there are great solutions to many problems already built in Python. We can pick the one that looks like the most fun and productive way to get the job done, document it and bake it in. Ian Bicking has taken some time out to point out some features of Paste and how they can work with TurboGears.

If there&#8217;s something that&#8217;s been bothering you about writing webapps currently, drop by the <a href="http://groups.google.com/group/turbogears</a>TurboGears mailing list</a> and speak up.

I&#8217;m also working on getting a 1-day initial TurboGears sprint going in Ann Arbor, Michigan. We have a location, and the date looks to be firming up as October 8th. Discussions about that are happening on the <a href="http://groups.google.com/group/michipug</a>Michigan Python Users Group mailing list</a>.

In other news, I&#8217;m expecting to have a public SVN repository soon. I&#8217;ll keep you posted on that one. I&#8217;m planning to meet the documentation schedule listed on the site, so expect to see the Getting Started Guide later today.

One thing I&#8217;ve had no time to do is comment on a lot of the interesting things being said about TurboGears on the blogs that have been talking about it.

Since Jeremy Jones has had three TurboGears related postings _and_ sent a nice email to boot, I wanted to comment a little on what he&#8217;s written.

In his first posting, [TurboGears: a slap-it-together web framework for Python][2], Jeremy says that he was impressed by the video, but&#8230;

> I&#8217;m still a little skeptical, however, of what appear to be &#8220;me, too&#8221; Ruby on Rails projects. I guess maybe it&#8217;s a knee-jerk reaction against the massive amount of publicity they&#8217;ve received and wondering if they really are as good as they claim to be or if it&#8217;s just hype from &#8220;the analysts&#8221; and the masses.

In my opinion, neither TurboGears nor Django are &#8220;me, too&#8221; Ruby on Rails wannabees. Django has a history of being used to manage content on a variety of sites going back in time before Rails was in vogue.

In TurboGears&#8217; case, I had to pull together the tools necessary to build my product. When I decided that plugins are an important part of the overall product I&#8217;m creating, I knew that I would have to provide good documentation on using those tools. I could have just done documentation completely in terms of Zesty News but, to me, that would be a waste when these projects can all really benefit from some more docs. That, and I found that this collection of tools made for an exceptional overall way to work on a webapp.

At the end of the day, TurboGears, Django and Rails all exist to take drudgery away from building a webapp, so that you can focus on the fun parts that are _actually useful for people_. That&#8217;s what has people talking. They&#8217;re better for programmers and better for the customers, too.

In his second post, Jeremy highlights CherryPy:

> This is an easy to use web framework which, even by itself (meaning without TurboGears), allows you to put together a web site in little time. This project has done well standing on its own and has gained momentum and appears to be gaining market share in the Python web frameworks arena.

CherryPy is a fabulous tool and can reasonably be said to sit [at the heart of TurboGears][3]. There was some recent discussion on the CP list about a post-2.1 wish list. While there are some small things that I think will be good to move from TurboGears to CherryPy, I didn&#8217;t have anything at the time to add to a CP wish list. It handles its layer of the stack _really well_.

In Jeremy&#8217;s third posting, [It&#8217;s all in the marketing &#8211; TurboGears&#8217; cool demo video][4], he says:

> I think what TurboGears has done with its marketing is going to get people excited about it, gain it market share, and will help drive its credibility. Credibility? Yes, credibility. I&#8217;m not saying that it makes it any better, but when people see with their own eyes how someone can create a wiki in 20 minutes, it will make them believe that it is a capable web framework. It will make them believe that it&#8217;s easy to use. It will make them believe that they can make a website with it with less work than an alternative.

Months before I had assembled TurboGears and decided to package it and release it, I wrote about how [Ruby on Rails wins the marketing war][5]. This has been one of my most popular posts of the year. When you&#8217;re in a small business, you _have_ to think about marketing. In a world overflowing with information, you have to have a story to tell people so that they know why they should care about what you&#8217;ve got. David Heinemeier Hansson told his story very well indeed, and a thriving community has grown around his dream.

For my part, I had found this amazing set of tools that worked well together, and I _wanted_ to tell people about it. I wanted to yell out &#8220;hey! look how easy it can be, even in Python!&#8221;. Maybe that should be &#8220;especially in Python&#8221;, because Python has been my language of choice for a decade.

There is more to say about this, though: once you&#8217;ve gotten the story out there, you&#8217;ve got to follow through on it. A significant part of the TurboGears appeal is the documentation and the promise of more, and we&#8217;ll keep that going. TurboGears doesn&#8217;t have _all_ of the answers to common webapp needs yet, but it will. I was comfortable with this picture before, because TurboGears already had a community of sorts even before day 1: all of the users who have been building cool things with CherryPy, SQLObject, MochiKit and Kid.

Now that there are 89 people with enough interest to join the mailing list, I&#8217;m that much more certain that TurboGears will become far cooler than the humble 0.5 release.

 [1]: http://www.turbogears.org
 [2]: http://www.oreillynet.com/pub/wlg/7835
 [3]: http://www.turbogears.org/about/howitallfits.jpg
 [4]: http://oreillynet.com/pub/wlg/7869
 [5]: http://www.blueskyonmars.com/2005/03/23/ruby-on-rails-wins-the-marketing-war/