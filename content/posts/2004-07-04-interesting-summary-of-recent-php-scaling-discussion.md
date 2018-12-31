---
title: Interesting summary of recent PHP scaling discussion
author: Kevin Dangoor
type: post
date: 2004-07-04T22:18:51+00:00
url: /2004/07/04/interesting-summary-of-recent-php-scaling-discussion/
categories:
  - Software Development

---
There&#8217;s been a lot of discussion recently about PHP vs. Java in terms of scalability. This discussion happened as a result of Friendster&#8217;s move from Jav to PHP. Here&#8217;s one summary (PHP leaning), by Chris Shiflett, of the discussions: [PHP Scales][1].

My takeaway from both this and the recent talk of eBay&#8217;s use of Java is to keep in mind how the web works. It is inherently stateless. The more you really on maintaining state, the harder it is to scale your application. Some applications inherently require more state than others, but it&#8217;s just a consideration to remember.

I think that PHP is a quicker language to develop in (for the same reasons that Perl, Python and Groovy are). Maybe that speed of development and experimentation (make mistakes faster!) avoids premature optimization and helps people spend time tuning where it really counts.

 [1]: http://www.oreillynet.com/pub/wlg/5155 "O'Reilly Network: PHP Scales [Jul. 02, 2004]"