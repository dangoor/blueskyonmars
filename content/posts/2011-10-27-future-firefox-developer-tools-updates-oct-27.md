---
title: Future Firefox Developer Tools Updates Oct 27
author: Kevin Dangoor
type: post
date: 2011-10-27T19:05:02+00:00
url: /2011/10/27/future-firefox-developer-tools-updates-oct-27/
categories:
  - Mozilla

---
Unlike most organizations, Mozilla&#8217;s product management is open. You can see what we&#8217;re building now and planning to make in the future just by looking at our [feature pages][1]. Open, however, is not always discoverable and it should be easy for interested people to follow along as plans are revised, help make those plans better and make it easier for everyone to spot features they&#8217;d like to get involved with.

As the product manager for Firefox developer tools, I am most heavily involved in the creation of [these feature pages][2].

We had a feature page that conflated two different concerns with a joint user interface. While the user interface we talked about _might_ be a great way to go, the two features have different priorities and it&#8217;s worth considering other approaches properly. The more important feature is the ability to [lock in a pseudo-class][3] when working on the styling of a page element. For example, viewing the styles for the element as if you were hovering over the element. This is high priority because web developers have no way to peek into the details of hovered styles without tools support. Once they&#8217;ve moved the mouse from the page element to the tools, the element is no longer hovered!

The [Web Console&#8217;s queued messages display][4] is a feature that will allow the Web Console to display messages logged from before the console was opened. There was some complexity found during review of the code and, given the other things on the plate for Firefox 10, this feature is not likely to make that release. This is definitely still a feature we want, but I have dropped it down to P2 to reflect that the other items on the list are higher priority.

There are also some recent additions to the feature pages:

  * [Tilt in the Page Inspector][5] adds a 3D view to the forthcoming page inspector (aka highlighter). Victor Porof recently [wrote about the add-on][6] which has a whole bunch of interesting features. The core 3D view is something we want to be directly available in our tools, as it will help people solve nesting problems in their markup.
  * [CSS Source Mapping][7] The buzz around source mapping continues to grow (see this recent [issue for HTML5 Boilerplate][8]) and CSS needs source mapping for exactly the same reasons that JS needs source mapping.

I created some other stub feature pages, and I&#8217;ll write more about those as they&#8217;re fleshed out.

I&#8217;ll be writing more about Firefox developer tools feature ideas from this point onward. Your feedback is always welcome. You can talk about ideas on [dev-apps-firefox][9] or contact me via email, Twitter or G+ (see the sidebar on my site).

 [1]: https://wiki.mozilla.org/Features
 [2]: https://wiki.mozilla.org/Features/DevTools
 [3]: https://wiki.mozilla.org/DevTools/Features/PseudoClassLock
 [4]: https://wiki.mozilla.org/DevTools/Features/ConsoleQueuedMessages
 [5]: https://wiki.mozilla.org/DevTools/Features/PageInspectorTilt
 [6]: http://hacks.mozilla.org/2011/10/debugging-and-editing-webpages-in-3d/
 [7]: https://wiki.mozilla.org/DevTools/Features/CSSSourceMap
 [8]: https://github.com/h5bp/html5-boilerplate/issues/820
 [9]: https://lists.mozilla.org/listinfo/dev-apps-firefox