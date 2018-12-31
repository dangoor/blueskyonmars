---
title: Web Widgets for everyone at PyCon 2007!
author: Kevin Dangoor
type: post
date: 2006-12-05T13:21:15+00:00
url: /2006/12/05/web-widgets-for-everyone-at-pycon-2007/
categories:
  - Python
  - TurboGears

---
The talks and tutorials for [PyCon 2007][1] were recently announced. I&#8217;ll be talking about ToscaWidgets, Alberto Valverde&#8217;s web component system. Make no mistake about it: my talk is not TurboGears-specific (though I&#8217;ll likely demo with TurboGears). Last December, I put up a rough version of how I thought Python-based web components should work. I wanted them to encapsulate:

  1. Display of form elements
  2. Display of potentially complex non-form elements
  3. Inclusion of JavaScript and CSS as needed (without additional Python or template code)
  4. Validation to convert to and from the web
  5. Automatic error handling (as much as is possible)

In other words, I wanted to remove the boilerplate code from working with forms. Alberto and Michele Cella picked up what I started off with and really ran with it. It was great to see that development unfold, and we have an awesome widgets package in TurboGears today as a result.

Within the past couple of months, Alberto has gone through a rewrite of the widgets. He&#8217;s cleaned up some of the niggling issues and made it _web framework independent_! The result is [ToscaWidgets][2], and that&#8217;s what I&#8217;ll be talking about at PyCon 2007.

PyCon has a lot of other great talks coming, TurboGears-related and otherwise. Mark Ramm will be doing a full day of TurboGears tutorials. Jonathan Ellis will be doing in-depth SQLAlchemy tutorials. Mark will also be introducing SQLAlchemy in a standard talk. Jonathan LaCour will be talking about WhatWhat Status, a project tracking tool that he implemented in TurboGears, which also features prominently in the TurboGears book.

Jacob Kaplan-Moss will be talking about how Django came to be open sourced and how they&#8217;ve kept the project going. I can totally relate to the kinds of things they&#8217;ve been going through.

Finally, Titus Brown will be hosting a Web Frameworks panel discussion that I&#8217;ll be taking part in.

Quite a cool lineup right there, and I&#8217;ve barely skimmed the surface of what&#8217;s going on at PyCon 2007.

 [1]: http://us.pycon.org/TX2007/HomePage
 [2]: http://www.toscawidgets.org