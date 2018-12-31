---
title: Future Firefox Developer Tools Updates Nov 17
author: Kevin Dangoor
type: post
date: 2011-11-17T13:55:15+00:00
url: /2011/11/17/future-firefox-developer-tools-updates-nov-17/
categories:
  - Mozilla

---
## Information Gathering and Organizing {#information_gathering_and_organizing}

Since my last update, I had some back-to-back busy-ness. First, I was prepping and presenting at the [1DevDay Detroit][1] conference. I spoke about [a number of web developer tools][2] there.

That was followed by a work week in San Francisco and Mountain View. Mozilla&#8217;s product team is working on the product roadmaps for 2012. You should start seeing drafts coming out for review and comment soon.

I also did three more user interviews. These have been very interesting, and will undoubtedly improve our product plans. I&#8217;ve also heard about some other user research going on at Mozilla around app development that may have some interesting information for developer tools as well. Once I figure out the best way to package up the research we&#8217;ve been doing, I&#8217;ll get it posted.

## Aurora 10 {#aurora_10}

The most exciting news is the release of a new Aurora build last week. [Five of our feature pages][3] landed for Firefox 10. You can find a more coherent version of what&#8217;s exciting about Firefox 10 (due January 31, 2012) in [this Mozilla Hacks][4] article that I posted yesterday.

## New Feature Pages {#new_feature_pages}

Consistently, the users I&#8217;ve interviewed use the console, CSS tools and network request timeline the most. We have other data that shows a great many users also use the debugger features of web development tools. We now have a console, CSS tools and a debugger in the works. That leaves a [network timeline][5], for which we&#8217;re figuring out scope and a plan.

In the meantime, I added feature pages to cover a couple of things that didn&#8217;t make it into Firefox 10. The [enhanced property views][6] page is about making the way CSS properties are displayed and edited in the Style Inspector even better.

The [Layout In Highlighter][7] page is for adding a feature that web developers find useful in other tools: being able to see margins and padding around an element right around the element itself on the page.

I had created a page to track against our plans for multi-process (&#8220;electrolysis&#8221;) Firefox. The engineering team has decided to take other approaches to improve Firefox&#8217;s responsiveness, which means that we don&#8217;t need to tackle multi-process rearchitecture work right now.

## A Comment on the Feature Page System {#a_comment_on_the_feature_page_system}

Something that has felt a little awkward to me about our feature pages system is that improvements (like the &#8220;enhanced property views&#8221; above) to previously shipped features need to either get glommed together into a feature page or just live as bugzilla bugs. So, there are actually two places (feature pages and bugzilla) where useful work to be done or things that have been done can appear.

The line for me seems to be that bugzilla is used for the details of implementation and prioritizing the parts of the implementation that need to happen. The feature pages provide higher level context of what we&#8217;re trying to accomplish.

If you&#8217;re interested in helping out with Firefox web developer tools, I&#8217;d suggest looking at our [Get Involved][8] page which has links to both our feature pages _and_ to our bugzilla bugs.

 [1]: http://1devdaydetroit.com/
 [2]: http://www.blueskyonmars.com/2011/11/10/tools-for-web-developers-1devday/
 [3]: https://wiki.mozilla.org/Firefox/Flight_Tracking#Firefox_10:_Dev_Tools
 [4]: http://hacks.mozilla.org/2011/11/developer-tools-in-firefox-aurora-10/
 [5]: https://wiki.mozilla.org/DevTools/Features/TimelineView
 [6]: https://wiki.mozilla.org/DevTools/Features/EnhancedPropertyViews
 [7]: https://wiki.mozilla.org/DevTools/Features/LayoutInHighlighter
 [8]: https://wiki.mozilla.org/DevTools/GetInvolved#Where_to_Dive_In