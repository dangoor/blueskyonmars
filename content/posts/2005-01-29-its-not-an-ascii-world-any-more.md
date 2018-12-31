---
title: It’s not an ASCII world any more
author: Kevin Dangoor
type: post
date: 2005-01-29T20:04:17+00:00
url: /2005/01/29/its-not-an-ascii-world-any-more/
categories:
  - Software Development

---
Actually, that&#8217;s not true. For many software developers, it is an ASCII world. But, if you&#8217;re making software for other developers to use, please keep character encodings in mind. I&#8217;ve had to jump through hoops with many packages along the way to get them using UTF-8.

Luckily, when you use open source libraries, the lack of non-ASCII support is usually not a big problem, because it&#8217;s easy enough to add the support. Not so with a closed-source third party library. Though, anyone offering a commercial library would have to deal with encodings once they start offering the product internationally.