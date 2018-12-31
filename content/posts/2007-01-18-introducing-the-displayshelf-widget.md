---
title: Introducing the DisplayShelf widget
author: Kevin Dangoor
type: post
date: 2007-01-19T01:47:46+00:00
url: /2007/01/18/introducing-the-displayshelf-widget/
categories:
  - Python
  - TurboGears

---
This afternoon, at CodeMash, James Ward and I took over an open spaces table, got some extra displays set up and hacked up a TurboGears widget wrapper for Ely Greenfield&#8217;s [Display Shelf Flex component][1]. The Display Shelf gives you the effect that Apple created in iTunes 7 with the cover art view. Now, in TurboGears, you can display your own photos the same way trivially. Just call the widget with a Python list of image URLs, and you&#8217;ve got your shelf!

This was completely unrehearsed live coding, and it went surprisingly well. The widget itself is far simpler than Ely&#8217;s Flex component, so Ely really deserves the credit for how cool a widget this is. This was a good chance for me to learn a bit more about Flex and the Flex Ajax Bridge. James got to learn about making TurboGears widgets. Some screencasts might come out of what we did there, and I&#8217;ll link to them if they pop up.

In the meantime, you can easy_install DisplayShelf to get the widget, or go to the [DisplayShelf Cheeseshop page][2] to get the source.

 [1]: http://www.quietlyscheming.com/blog/components/tutorial-displayshelf-component/
 [2]: http://cheeseshop.python.org/pypi/DisplayShelf/1.0