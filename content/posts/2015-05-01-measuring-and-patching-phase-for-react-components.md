---
title: Measuring and patching phase for React components
author: Kevin Dangoor
type: post
date: 2015-05-01T16:42:25+00:00
url: /2015/05/01/measuring-and-patching-phase-for-react-components/
linked_list_url:
  - http://devchat.tv/js-jabber/157-moving-your-rendering-engine-to-react-with-amit-kaufman-and-avi-marcus
categories:
  - JavaScript
format: link

---
On the [latest episode of JavaScript Jabber][1], Amit Kaufman and Avi Marcus talk about how your web app performance is killed if you interleave your reading and writing from the DOM. For their now React-based app, they needed to measure certain elements for their layout work. Their solution sounds clever: components specify what information they&#8217;re going to need and they batch up all of the DOM reads and do them all at once and then they do all of the adjustments that come as a result of those reads all in one separate pass. This minimizes the amount of churn and recalculation that the browser needs to deal with.

 [1]: http://devchat.tv/js-jabber/157-moving-your-rendering-engine-to-react-with-amit-kaufman-and-avi-marcus