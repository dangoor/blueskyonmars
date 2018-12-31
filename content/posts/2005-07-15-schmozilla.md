---
title: Schmozilla!
author: Kevin Dangoor
type: post
date: 2005-07-15T18:16:02+00:00
url: /2005/07/15/schmozilla/
categories:
  - Technology

---
A short time ago, this site (and my other sites) were all unavailable. And, of course, I couldn&#8217;t get on the box to figure out what was going on. When I finally got on there, everything \*looked\* pretty normal&#8230; except for the fact that the load average had climbed to more than 100! Sadly, my server doesn&#8217;t have 100 processors and so it was completely hosed until the problem stopped.

It turns out that the problem was someone at 192.114.144.12 (you know who you are!) was running some bot that identified itself as Schmozilla. Apparently, the Perl Cookbook shows you how to do HTTP requests and gives that user agent. Ugh.

Anyhow, one way of dealing with this is detailed here: [Blocking Apache Attacks][1].

 [1]: http://perlcode.org/tutorials/apache/attacks.html