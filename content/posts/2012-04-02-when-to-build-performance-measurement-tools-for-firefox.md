---
title: When to Build Performance Measurement Tools for Firefox
author: Kevin Dangoor
type: post
date: 2012-04-02T15:22:52+00:00
url: /2012/04/02/when-to-build-performance-measurement-tools-for-firefox/
categories:
  - Mozilla

---
We&#8217;re well on our way to having a full-featured set of tools for web developers that ship with every release of Firefox, in addition to the already great Firebug add-on. In our [roadmap][1], I talk about building &#8220;bundled tools for the most common tasks&#8221;. Lately, people have been asking me about tools to help web developers improve the performance of their applications.

**Firefox is very fast.** In fact, Firefox and its competitors are so fast that most web developers only care about one aspect of web application performance: network access. **Latency and the amount of data transferred** are the biggest issues for most web developers. We&#8217;ll be working on [providing insight into network access][2] soon in Firefox.

Developers working on three sorts of web applications in particular are asking for deeper insight into what the platform is doing:

  * games
  * complex layouts involving large amounts of data
  * applications that have features you&#8217;d traditionally associate with &#8220;desktop applications&#8221;

Each browser has different performance characteristics, and these developers need tools that give them hints on how to make their apps responsive on each browser. They care about things like garbage collection pauses, repaints and reflows and hot spots in their JavaScript code where the just-in-time compilers aren&#8217;t able to make the JS zoom.

**Most web developers aren&#8217;t working on these kinds of apps**, and we&#8217;re focused on building tools that are useful for the &#8220;most common tasks&#8221;. However, we want these kinds of applications to run well on Firefox. Firefox developer tools really serve two groups: the web developers who use the tools directly, and the hundreds of millions of Firefox users who are looking to experience the web in the best way possible.

I think that our focus needs to remain on building the best tools for the most common tasks. But **we also need to accommodate these sophisticated developers**. Fortunately, we have more options than just &#8220;build it&#8221; or &#8220;don&#8217;t&#8221;.

For a feature to ship in Firefox, it goes through _a lot_ of work to ensure that the feature is of a quality that is ready to ship to many millions of people and in many languages. The developers building these performance intensive apps do not number in the millions, and they are capable of installing add-ons. Some are even willing to produce their own custom builds of Firefox, if that&#8217;s what it takes to get the performance data they want.

In my opinion, that&#8217;s the planning lever we need to pull here. **We can try to get these developers the data they need, albeit in a rough form, in add-ons as soon as possible.** Along those lines, Brian Hackett has made his [JIT Inspector][3] tool available as an add-on.

If you need help figuring out performance issues with your application in Firefox, [get in touch][4].

 [1]: https://wiki.mozilla.org/DevTools/RoadmapDec2011
 [2]: https://wiki.mozilla.org/DevTools/Features/NetworkView
 [3]: https://addons.mozilla.org/en-US/firefox/addon/jit-inspector/
 [4]: https://lists.mozilla.org/listinfo/dev-apps-firefox