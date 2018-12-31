---
title: Does $1 hosting matter?
author: Kevin Dangoor
type: post
date: 2008-01-14T03:06:31+00:00
url: /2008/01/13/does-1-hosting-matter/
categories:
  - Software Development
  - TurboGears

---
Back when I was in the thick of my involvement with [TurboGears][1], I remember seeing an email from someone complaining that, unlike with PHP apps, TurboGears apps cuoldn&#8217;t be hosted on <span style="font-style: italic;">$1 per month</span> hosting accounts. While I was always interested in seeing TG apps on inexpensive shared hosts, I had no expectation that people could host TG apps for $1 per month. And, frankly, I don&#8217;t think I care about that.

Software development is full of tradeoffs. As Ian Bicking points out, [PHP&#8217;s deployment model has some good aspects][2]. As long as you stick to the constructs provided by PHP, it&#8217;s fast and the programming model is very simple and side-effect free. Now, however, PHP users want the productivity goodness that you get from higher-level OO frameworks like TG, Django and Rails. To create frameworks like those in PHP means optimizing the framework so that it loads the minimal amount of code in any given request. This is a constraint that TG, Django and Rails don&#8217;t have to consider at all, since the code is loaded once and kept resident (in any sane deployment).

The [DreamHost][3] blog recently [lamented the pain of Rails deployment][4] in their shared hosting environment. I&#8217;m frankly not too sympathetic. [WebFaction][5] seems to be able to manage shared deployments of modern frameworks quite nicely, and I assume they&#8217;re making a profit at it. [WestHost][6] provides quite inexpensive VPSes for folks who want to do it all themselves. I like DreamHost, and I&#8217;m a satisfied customer, but if others can figure out reasonably priced ways to host Rails and TG, DreamHost should be able to as well. (Full disclosure: those links are the same affiliate links that I have in my sidebar. I mention them here because they are relevant to the topic at hand, but it&#8217;s worth mentioning that following those links and buying services there does give me some money.)

Maybe DreamHost shouldn&#8217;t be looking at it like &#8220;how can I get Rails into an existing $10/month package&#8221; but rather what kind of good Rails hosting setup can i do for $15/month. Rails seems like a fine value-add&#8230; and if there are others undercutting them, then they can figure out how to compete on price.

All of this is not to say that we shouldn&#8217;t try it make deployment easier or frameworks better. It&#8217;s just not likely to be worth making the tradeoffs required to match PHP&#8217;s deployment in an effort to shave a couple bucks a month off of low-end hosting.

 [1]: http://www.turbogears.org/
 [2]: http://blog.ianbicking.org/2008/01/12/what-php-deployment-gets-right/
 [3]: http://www.dreamhost.com/r.cgi?313844
 [4]: http://blog.dreamhost.com/2008/01/07/how-ruby-on-rails-could-be-much-better/
 [5]: http://www.webfaction.com/?affiliate=kdangoor
 [6]: http://affiliates.westhost.com/z/8/CD686/