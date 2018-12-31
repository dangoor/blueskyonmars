---
title: Zesty News alpha delayed
author: Kevin Dangoor
type: post
date: 2005-05-25T19:13:34+00:00
url: /2005/05/25/zesty-news-alpha-delayed/
categories:
  - Blazing Things

---
I had, until very recently, been aiming for releasing the first alpha release of Zesty News Lite on May 31st. I do believe in &#8220;release early, release often&#8221; as a way to make great progress on a project, even a closed-source one. However, I also believe in not wasting the time of the people testing my product. That means balancing the desire to get features out there with a bit of stability.

The point of the alpha release of Zesty News is to get the foundation out there, showing off the basic concepts, and then build features based on my plan and feedback I get. The foundation should be solid, so that I can react fairly quickly without spending too much time retooling.

A couple of days ago, I decided that I needed to do some retooling to handle concurrency better. Though I could have done this work between the alpha and beta releases, I decided that it&#8217;s a better idea to get this done before I release at all. There are other benefits to this change, as well: my code will be easier to test and more code will be covered by automated tests as a result, the distributed package has shrunk by about 10%, and programming for the web interfaces will be easier going forward.

When I&#8217;m done with the change, I&#8217;ll write more technical details about it.

Odds are that this change will take about a week, which is not too bad. After that week is over, I&#8217;ll spend the following week or so working on what I had originally planned to do this week and ongoing testing of the big change I&#8217;m making now.