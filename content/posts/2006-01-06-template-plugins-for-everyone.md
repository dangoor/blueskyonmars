---
title: Template plugins for everyone!
author: Kevin Dangoor
type: post
date: 2006-01-06T18:26:52+00:00
url: /2006/01/06/template-plugins-for-everyone/
categories:
  - Python

---
A few days ago, I mentioned that [TurboGears][1] 0.9 (currently in svn only) now supports template plugins with four available (Cheetah, Stan, ZPT, plus Kid which was built in to TurboGears). Meanwhile, [Buffet][2] (a template rendering filter for CherryPy) supports Cheetah, CherryTemplate, Kid, Myghty, Python String Templates and XSLT. Not only that, Buffet used a very similar pattern for choosing a template and sending data to it.

So, I emailed Christian Wyglendowski about it&#8230; and we settled on an interface for our template plugins. I just checked in the code to make this work in TurboGears, plus new [TurboKid][3] and [TurboCheetah][4] plugins to match. When Christian updates Buffet, it will automatically be able to use these plugins.

The really cool thing here is that these plugins only depend on their template engines. They don&#8217;t require TurboGears, Buffet or CherryPy to use them.

All of this is made not just possible but easy through setuptools entry_points. I&#8217;ve updated the documentation on the TurboGears site to reflect the new interface for anyone that wants to create a plugin.

Also, if you&#8217;re interested in taking over the Cheetah plugin, I (and everyone using Cheetah with TurboGears) would appreciate that.

 [1]: http://www.turbogears.org
 [2]: http://projects.dowski.com/projects/buffet
 [3]: http://cheeseshop.python.org/pypi/TurboKid/0.9.0
 [4]: http://cheeseshop.python.org/pypi/TurboCheetah/0.9.3