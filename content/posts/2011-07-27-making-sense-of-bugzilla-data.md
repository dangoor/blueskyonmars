---
title: Making sense of Bugzilla data
author: Kevin Dangoor
type: post
date: 2011-07-27T14:07:25+00:00
url: /2011/07/27/making-sense-of-bugzilla-data/
categories:
  - Mozilla

---
tldr; I have created a [project status page][1] for Mozilla developer tools and a library called [Buggerall][2] that helps to make pages like this.

Poor Bugzilla. It started life as an innocent bug tracker and has come to be counted on as the source of truth for a collection of significant software development projects, and the workflow tracker of Mozilla&#8217;s development process.

As manager of Mozilla&#8217;s developer tools group, I was responsible for keeping an eye on how our projects were moving toward completion. It very quickly became apparent to me during the Firefox 4 cycle that getting code through the process was just as important as writing the code in the first place. At the time, &#8220;through the process&#8221; meant gaining blocker/approval status in addition to getting a slot on the super busy review queues of browser peers and successfully managing the back-and-forth of the review process. There is no query you can run in Bugzilla&#8217;s web interface to show you how bugs are doing in this process.

Enter [Bugzilla&#8217;s REST API][3]. Using this API, you can gather whatever data you need from Bugzilla and munge it any way you want. Even better, you can use this API entirely in client side JavaScript, even cross-domain. For my initial report, which showed where a given bug was in the Firefox development process, I had a bunch of code in the page to gather and format the data.

More recently, I&#8217;ve made that code more generic and given it new superpowers. It&#8217;s called Buggerall, it&#8217;s [lightly documented][4] CoffeeScript and it&#8217;s [available on GitHub][2].

In my new role as product manager for developer tools, I want to be aware of how things are going with the projects, but at a higher level. I also want to be able to track developer tools work as it relates to [Firefox features][5]. To that end, I have created a [project status][1] page that builds on Buggerall to give me (and anyone else that&#8217;s interested) a view into developer tools work.

Some interesting features of Buggerall:

  * run queries easily
  * you can serialize the result so that reports (like my status report) can use cached data and load _very_ quickly
  * but you don&#8217;t have to! queries can be live and cross-domain
  * new Timeline object lets you gather a feed of events for the bugs in a query

My status page has an [updater script][6] (invoked from an update page in the browser) that runs the queries using Buggerall and then mashes the data down to a simpler format used by the status page. The updater uses a Firefox-specific API for saving files which I found in [TiddlyWiki][7].

The status page is built around [project metadata][8] that I set up. This metadata allows me to group together arbitrary collections of bugs, which is very handy. This can be done with meta bugs in Bugzilla, but it takes a lot more work to do so. Also, since this is all in git, it&#8217;s easy to collaborate with other people on the metadata.

I&#8217;m always interested to hear about other techniques people have for getting useful info out of Bugzilla. The query interface that Bugzilla provides is quite powerful on its own, but the REST API makes it easy to gather any data you need and present it any way you want.

 [1]: http://mozilla.github.com/devtools/status/index.html
 [2]: https://github.com/dangoor/buggerall
 [3]: https://wiki.mozilla.org/Bugzilla:REST_API
 [4]: http://dangoor.github.com/buggerall/docs/buggerall.html
 [5]: https://wiki.mozilla.org/Features
 [6]: https://github.com/mozilla/devtools/blob/gh-pages/js/specjs/updater.coffee
 [7]: http://www.tiddlywiki.com/
 [8]: https://github.com/mozilla/devtools/blob/gh-pages/status/projects.coffee