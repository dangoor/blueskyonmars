---
title: 'Rebooting Bespin: Embedded and SproutCore'
author: Kevin Dangoor
type: post
date: 2009-11-13T16:40:59+00:00
url: /2009/11/13/rebooting-bespin-embedded-and-sproutcore/
categories:
  - Bespin

---
This post is a collection of random thoughts about the Bespin Reboot project so far.

The past summer, the [Bespin][1] team at Mozilla (Ben, Dion, Joe and me) started thinking that the time had come to make some significant changes to the Bespin project code. These changes would make it easier for others to use and contribute to Bespin and also make it easier for Bespin core contributors to add new features. We did a collection of releases during the summer and then slammed on the brakes for what we&#8217;ve called the &#8220;[Reboot][2]&#8220;.

The Reboot involves a serious refactoring of the code, plus changes in priorities and processes. We started fresh with a [new source code repository][3] (two, actually, since [the Python server][4] has been pushed into a separate repo). Then, we poured the code from the old repository into a new structure of [CommonJS][5] [modules][6]. We changed our underlying GUI framework to use [SproutCore][7], so that we could spend less time thinking about getting things on the screen and more time with features that help people write their code.

Once you get into the groove of doing releases and adding good stuff for your users, it&#8217;s really painful to stop doing releases. I&#8217;ve been itching to ship since the beginning of October when we shifted full-time to the Reboot repository. Our goal all along has been to get the editor running again as soon as possible. Our initial thought was &#8220;get it running on a mix of old infrastructure and new and evolve from there over time&#8221;. That was a nice thought, but it didn&#8217;t work out very well that way.

SproutCore&#8217;s event model is based on adding a small number of global event listeners and delegating events to the proper components. Bespin had been using Dojo with the far more common model of attaching events to DOM nodes directly. In order to take advantage of what SproutCore has to offer, we very quickly ended up on the slippery slope of doing other refactorings to the editor, which is something we had not initially planned to do.

I&#8217;m thankful that we decided to go ahead with those changes, though! For example, the editor&#8217;s event handlers all had code in them to figure out &#8220;is the cursor over the scrollbars?&#8221; because the editor itself was responsible for painting the scrollbars! The editor had one canvas and it managed everything on there itself. We had discussed the possibility of using the [Thunderhead][8] project to manage the different pieces that appear in the editor canvas, but we&#8217;re a small team and don&#8217;t have time to work on a GUI toolkit in addition to our other ambitions for Bespin.

And so it came to pass that we started down the road of refactoring the editor into separate SproutCore components. Patrick Walton joined Mozilla last month and immediately dove into the task of breaking the scrollbars out into separate components. In the process, Bespin&#8217;s editor is now a scrollable SproutCore component, so you could even use the standard scrollbars with the editor. Bespin&#8217;s scrollbars are a bit tricky, though&#8230; rather than living just outside of the scrolled area, they are actually drawn _on top of_ the scrolled area. We also found that the gutter of the editor really should be a separate component (or maybe even more than one), which is why the horizontal scrollbar is not positioned properly right now. Patrick is actively working on fixing that.

Meanwhile, Joe has been hard at work fixing lots of other things: random uses of Dojo, how our singleton components are managed (since we ultimately want to be able to support multiple editors on a single page), copy and paste issues, etc. I&#8217;ve spent a bunch of time working through building, module loading and documentation issues.

From where we sit now, the code is shaping up quite nicely. Soon enough, if you have a SproutCore app, you&#8217;ll be able to just drop an editor right into your app. As of today, [anyone with a website can grab a copy of Bespin][9] and include the editor component very simply in their pages. We figure that we&#8217;ve got another month of work to do before we&#8217;re ready to update [bespin.mozilla.com][10]. We have a whole bunch of features to port over from the old code and we need to make good on another big part of the Reboot promise: opening Bespin up for plugins. It&#8217;s been hard even for Bespin core people to contribute because of the state of the code, and I&#8217;m looking forward to getting past that hurdle soon. Before I know it, we&#8217;ll be back to shipping new features regularly (and quicker than before!) at bespin.mozilla.com. I can&#8217;t wait!

 [1]: http://mozillalabs.com/bespin/
 [2]: https://wiki.mozilla.org/Labs/Bespin/Roadmap/Reboot
 [3]: http://hg.mozilla.org/labs/bespinclient
 [4]: http://hg.mozilla.org/labs/bespinserver
 [5]: http://commonjs.org/
 [6]: http://commonjs.org/specs/modules/1.0.html
 [7]: http://sproutcore.com/
 [8]: http://benzilla.galbraiths.org/2009/02/18/bespin-and-canvas-part-2/
 [9]: http://mozillalabs.com/bespin/2009/11/13/bespin-embedded-first-preview-release/
 [10]: https://bespin.mozilla.com/