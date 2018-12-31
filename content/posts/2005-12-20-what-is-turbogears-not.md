---
title: What is TurboGears not?
author: Kevin Dangoor
type: post
date: 2005-12-20T14:38:53+00:00
url: /2005/12/20/what-is-turbogears-not/
categories:
  - Product Management
  - Python
  - TurboGears

---
In product management, the things you choose not to do are at least as important as the things you choose to do. Though it might seem like adding features is always a good thing, there are actually tradeoffs being made with each feature added. Consider my cell phone (a Nokia Series 60): this thing can do many different things. It keeps my contacts, has games, takes pictures and can wake me up via its alarm clock. Because it has so many features, I have to do \*a lot\* of clicking around to set an alarm on the alarm clock. If the phone had fewer features, the user experience could be optimized better for setting alarms.

In an open source project, having an idea of what your product truly is becomes critical. Many people will have patches or apparently complementary projects that are ready and free for the taking. But, should you take them?

Numerous times along the way, people have asked about using &#8220;template package X&#8221; or &#8220;database thingy Y&#8221; with TurboGears. There have been thoughts of making TurboGears abstract away some of the underlying pieces so that they can be swapped out. (My responses have been that TurboGears shouldn&#8217;t stand in the way of using those other packages, but TurboGears itself will not directly support them.)

If what you want is to pick and choose every piece of the application stack, then the web framework you want is CherryPy or, I guess, one of the other controller frameworks. If one tried to support everything in order to become the web framework &#8220;to rule them all&#8221;, you&#8217;d eventually end up with just Python (or some hideous layer on top of Python) and the current collection of fine components available for Python.

TurboGears is not going to go that route. Here are the overarching thoughts that go in to TurboGears&#8217; evolution:

  1. best-of-breed
  2. one way to do it

I want to start with and maintain use of the &#8220;best-of-breed&#8221; components for each part of the stack. If you use great quality ingredients, you&#8217;ll get a great tasting cake.

Of course, &#8220;best&#8221; is in the eye of the beholder. Often, two components may be equally capable, but have a different feel. That&#8217;s when you get into a more subjective area which makes the second rule that much more important: rather than punting when faced with two nearly equal choices, pick one and run with it.

I can&#8217;t overstate the importance of TurboGears providing &#8220;one obvious way to do it&#8221; (at least when it comes to the big picture items). Let&#8217;s say that TurboGears specifically supported several templating packages (and there are certainly several to choose from in Python). The documentation would balloon, because it would have to cover both. The users would somehow have to have a basis for choice and the mailing list will get frequent questions of &#8220;which one should I use?&#8221;. Email traffic related to template issues would likely double. Features like internationalization would need to account for both. _And_, the path to adding more features that integrate multiple components would be a lot less clear. The new TurboGears widgets package uses Kid to power the appearance of the widgets. The Toolbox makes full use of all of TurboGears&#8217; components.

Am I saying it&#8217;s always wrong to provide a choice? No. But, if there is going to be a choice, there has to be a good reason for it. If it&#8217;s a specific use case that one tool handles tremendously better than another, document that use case and encourage people to use the right tool for the job. If it&#8217;s a case where one component is far better overall, but is just missing a feature that another has, maybe it&#8217;s better to try to build that feature into the component of choice.

Wouldn&#8217;t some people be turned away if you don&#8217;t support the exact component they want to use? Sure. But, expending the effort to support that rather than truly enhancing the user experience will cost far more users than simply not supporting one group&#8217;s preference. An example of this is alternative database technologies. Python has quite a few interesting non-relational databases available. There are certainly applications for which those databases make life easier. And, you can even use those technologies with TurboGears, just without special tool support. But, for the vast majority of people writing web applications today, relational databases are the primary storage option and which means that providing optimum support for relational databases is key. Providing support in TurboGears for non-relational databases would muddy the waters considerably. (Would CatWalk have to support those other tools? How about the tg-admin command line tool?) You could end up with half-baked support for a whole bunch of things rather than robust support for the &#8220;best-of-breed&#8221; toolset.

Note that I&#8217;m not saying that TurboGears won&#8217;t have plugin support to allow people to mix in other components. The balance being struck here is that TurboGears provides a distinct way to get things done. If you agree in general with the TurboGears approach, but have some specific unusual needs you want to meet, TurboGears should at least try provide a reasonable way to meet those needs while you use the rest of the framework. The &#8220;reasonable way&#8221; to meet those other needs cannot conflict with the primary tools being used, however.

One more point about when to say &#8220;no&#8221;: Good ideas come along all the time. At some point, you&#8217;ve just gotta ship it. Particularly with software, &#8220;good enough&#8221; today is worth a lot more than &#8220;perfect&#8221; at some distant point in the future. 1.0 is not the end, but just the beginning.

TurboGears as envisioned and implemented can meet a wide variety of web app needs in a way that many people find fun to use. It&#8217;s impossible to make a framework that makes _everyone_ happy, and to try would mean creating a framework that ultimately makes no one truly happy.