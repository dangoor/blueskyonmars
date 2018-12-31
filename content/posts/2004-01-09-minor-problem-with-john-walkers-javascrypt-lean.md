---
title: Minor problem with John Walker’s JavaScrypt lean
author: Kevin Dangoor
type: post
date: 2004-01-09T22:48:09+00:00
url: /2004/01/09/minor-problem-with-john-walkers-javascrypt-lean/
categories:
  - Software Development

---
John Walker&#8217;s really nifty [JavaScrypt: Browser-Based Cryptography Tools][1] comes in a monolithic &#8220;lean&#8221; version, which you can theoretically cart around with you and use on demand. I discovered that this version wasn&#8217;t working for me offline, because utf-8.js was still externally referenced.

This would be super simple for John to fix, but he doesn&#8217;t have any contact info on his [website][2]. So, I&#8217;ll post this here and maybe he&#8217;ll eventually notice 🙂

 [1]: http://www.fourmilab.ch/javascrypt/ "JavaScrypt: Browser-Based Cryptography Tools"
 [2]: http://www.fourmilab.ch/