---
title: 'TurboGears 2: a reinvention and back to its roots'
author: Kevin Dangoor
type: post
date: 2007-06-27T13:08:57+00:00
url: /2007/06/27/turbogears-2-a-reinvention-and-back-to-its-roots/
categories:
  - Python
  - TurboGears

---
Mark Ramm has just posted a glimpse of [The Future of TurboGears][1]. I wanted to post a little of my perspective and a historical view.

This past weekend, Jonathan LaCour, Mark Ramm, Rick Copeland, Noah Gift, and Mike Schinkel sprinted on TurboGears 2 (along with a bit of coding-from-starbucks-while-on-vacationby Alberto). TurboGears 2 is at once a reinvention of TurboGears and a return to TG&#8217;s roots. My original TurboGears 0.5 release was just a few hundred lines of Python code that built upon thousands of lines of other libraries. As people flocked to TG and added new, high-level features, it swelled to about 20,000 lines (and brought in even more third-party code).

TG is a project that is built upon a foundation of reuse and building up. In retrospect, much of the code that was home grown in the TurboGears project should have been released as independent projects that integrate with TurboGears. This would have allowed better growth of those pieces.

Alberto and I have talked about this a bit along the way. And there were lots of interesting discussions at PyCon this year about how Pylons and TurboGears have similar philosophies, though we disagree about some of the details (Hi, Ben!). The details that we disagree on are important and user-facing, but are actually not a big deal when it comes to the framework code. We can share an awful lot of code.

Just days ago, Mark Ramm and Jonathan LaCour (both at Optio) had the realization that TurboGears should just go ahead and make the switch. When Mark told me about the idea, I thought it made perfect sense. TurboGears 2 will go back to what TG originally was: a powerful package of best-of-breed tools. TG2 is once again a tiny core, getting features from a variety of other packages.

A lot of the groundwork for this had been set in place prior to the new TG2 sprint. Alberto&#8217;s ToscaWidgets reimplemented the TurboGears widgets API. Babel provides an internationalization package with features similar to, but more extensive than, TurboGears&#8217;. Various authentication and authorization systems have been worked on, though I don&#8217;t believe one has been chosen yet for TurboGears 2.

I&#8217;m really excited about TurboGears 2 and the significant activity that is going on in the project right now. After some months of deciding what TurboGears 2 would look like, we now have an answer that will get us to release in short order and fine form. \*And\* we have a good path set up for the TurboGears project to build new high- level tools as independent (and hopefully usable by others!) projects.

Of course, there are details to work out, docs to write, some tools to build, etc. But I, for one, am quite happy and thankful to the folks who have pitched in to put TG2 on this path. Thanks to all who have worked on Pylons, Paste, Genshi, SQLAlchemy (and Mako when speed is critical), Beaker (and MyghtyUtils, without which there would be no Beaker), all of the template engine plugins, setuptools, the still- quite-cool RuleDispatch, Babel, CherryPy, and, of course, TurboGears.

 [1]: http://groups.google.com/group/turbogears/browse_thread/thread/d1d2e416023e7033