---
title: Why I switched from Drupal to Movable Type
author: Kevin Dangoor
type: post
date: 2003-04-29T16:16:20+00:00
url: /2003/04/29/why-i-switched-from-drupal-to-movable-type/
categories:
  - Random

---
[Drupal][1] is a flexible, powerful program. They bill it as &#8220;Community Plumbing&#8221; and provide a whole slew of features, either built-in or as plugins. It supports many of the common weblog features and adds many uncommon ones: the ability to share authentication, the &#8220;collaborative book&#8221;, the RSS news feed reader, and on and on.

My decision to switch to [Movable Type][2] is certainly not based upon lack of features in Drupal. In fact, I decided to switch because Drupal has too many features and too flexible an architecture for me.

MT was very easy to setup and is extremely ease to use. It doesn&#8217;t have a collaborative book or forums or news feeds. It just does blogging, and it does it gracefully. The blogging interface is nicely laid out and the relevant section of the decent user manual is a click away. Comments don&#8217;t require users to become members of the site and are easily integrated. Templates are trivial to edit and can be edited on the web or as external files. The bookmarklets are a great timesaver and will doubtless lead me to create many more blog entries. Trackback is a cool feature that is tightly integrated (not surprisingly, since SixApart created the initial spec).

I&#8217;m sure that everything I&#8217;m getting out of MT can be done with Drupal, but with MT it&#8217;s very easy to do those things and I didn&#8217;t have to spend any real time getting it up and running. Since I&#8217;m a geek, you&#8217;d think I&#8217;d go for the most powerful tool. But, I want my blogging to be effortless and MT gives me that.

One last bit: the Drupal folks have worked hard on performance and provide a sophisticated caching infrastructure to allow a Drupal site to survive a slashdotting (as Kernel Trap has had to in the past). MT gets around this altogether by rendering out everything people are most likely to see as static HTML. I&#8217;m certain a typical Apache can push out a _whole lot_ of static HTML and the only likely problem would be if thousands of people wanted to comment all at once, since that&#8217;s still a perl cgi.

If you&#8217;re looking to set up a web community, particularly one revolving around a piece of software you&#8217;re releasing, I wouldn&#8217;t hesitate to recommend Drupal. If you&#8217;re looking to run a weblog and want a tool that stays out of your way, MT is definitely a good choice and I can see why so many people out there are using it.

 [1]: http://www.drupal.org
 [2]: http://www.movabletype.org