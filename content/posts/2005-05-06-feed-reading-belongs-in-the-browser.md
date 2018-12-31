---
title: Feed reading belongs in the browser
author: Kevin Dangoor
type: post
date: 2005-05-06T14:59:36+00:00
url: /2005/05/06/feed-reading-belongs-in-the-browser/
categories:
  - Blazing Things

---
There will certainly be folks that disagree with me on this one, but I think that feed reading belongs in the browser. Most of the feed readers that I&#8217;ve seen have a Windows or Mac user interface and include a web browser in a portion of the window. A few, including Zesty News, have the primary user interface show up directly in the user&#8217;s web browser.

At least at this point, feed reading is largely about resources that are on the web. The items in most feeds point back to pages on the web. This is why feed readers with a Windows interface embed Internet Explorer in their Window: so that you can get the details on an item without leaving their interface.

Once a web browser appears in a feed reader&#8217;s interface, it quickly becomes apparent that you need at least _some_ of the browser&#8217;s features: back, forward, stop and reload buttons. You might also want to get ahold of the browser&#8217;s bookmarks, so that the user has access to those and can add bookmarks to things they like. You&#8217;ll also need to put in the keyboard shortcuts that people are used to. Maybe you&#8217;ll make the browsing experience better by adding tabbed browsing.

But, what happens if the user&#8217;s browser is Firefox and not Internet Explorer? Those users already have tabbed browsing, so that&#8217;s not really an added bonus. If the feed reader doesn&#8217;t specifically support it, adding a bookmark would add it to IE rather than Firefox. Firefox also has many great extensions that the user will miss out on if they&#8217;re forced to use IE for browsing in their feed reader.

What this boils down to is that the author of the feed reader will have to duplicate many features from the web browser&#8217;s interface, and even then will likely be providing a suboptimal experience to those who browse with something other than Internet Explorer on Windows and Safari on the Mac.

The argument in favor of using a &#8220;native&#8221; interface rather than a web browser-based interface is that you can provide a &#8220;richer&#8221; experience. Data can be updated instantly on the screen without redrawing everything. You can have fancy, animated controls. You can have keyboard shortcuts for everything.

Two fairly recent phenomena make the case in favor of a browser-based feed reader: Firefox and the ability to provide more interactivity in modern browsers. Firefox has rapidly pulled market share away from IE. By some estimates, more than 10% of internet users now use Firefox. For those people, an embedded IE will be less than ideal.

More importantly, since Gmail&#8217;s introduction a year ago, it became apparent that browser-based interfaces _can_ be quick, useful and even include keyboard shortcuts. Web browsers also include a very powerful layout engine that allows for all kinds of experimentation in presentation.

For me, building the interface for Zesty News in the web browser also made it easier for me to make Zesty News run on both Macs and PCs. The real driver of my choice to use the browser as the interface is that I can provide as rich an experience as needed while letting the user stick with the web browser that they already know.