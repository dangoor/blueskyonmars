---
title: Using JavaScript Widgets with TurboGears
author: Kevin Dangoor
type: post
date: 2006-05-30T14:25:37+00:00
url: /2006/05/30/using-javascript-widgets-with-turbogears/
categories:
  - Python
  - Software Development
  - TurboGears

---
I&#8217;ve just put up a new screencast showing how easy it is to use JavaScript libraries that have been packaged as TurboGears widgets: [Using JavaScript with TurboGears][1]. This screencast actually shows off a few things:

  * Using a widget (obviously)
  * How widgets include the necessary JavaScript
  * The widget browser in the TurboGears Toolbox
  * How cool setuptools/Python Eggs are (I start from not even having the widget package installed).

This shows off setuptools, because I used the Lightbox widget, which in turn requires the Scriptaculous widget. Without any additional configuration, the widgets show up in the widget browser. easy_install and go!

 [1]: http://www.turbogears.org/preview/JSwithTG.html