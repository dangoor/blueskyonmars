---
title: The adventures of scaling, Stage 1
author: Kevin Dangoor
type: post
date: 2006-03-28T16:03:31+00:00
url: /2006/03/28/the-adventures-of-scaling-stage-1/
categories:
  - Software Development

---
Simon Belak on the TurboGears list points to [The adventures of scaling, Stage 1][1], an article about scaling a database-intensive reasonably high traffic (~1M page views a day) site based on Ruby on Rails. The author hits upon many of the common topics in scaling LAMP architecture sites. One thing I didn&#8217;t see mentioned, probably because it wasn&#8217;t particularly relevant for his application, is data partitioning. Any opportunity to break up your database into multiple chunks that can potentially be deployed separately can be a big win in terms of scalability.

The kinds of things they had to do for eins.de is very common in the LAMP stack and certainly applicable to TurboGears users.

 [1]: http://poocs.net/articles/2006/03/13/the-adventures-of-scaling-stage-1