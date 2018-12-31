---
title: Michael Foord’s Mock
author: Kevin Dangoor
type: post
date: 2007-12-04T13:22:42+00:00
url: /2007/12/04/michael-foords-mock/
categories:
  - Python

---
I&#8217;ve started using [Mock &#8211; Mocking and Test Utilities][1] by Michael Foord (that&#8217;s fuzzyman to you :). Python&#8217;s dynamic nature (monkeypatching and whatnot) means that you don&#8217;t need to come up with some of the elaborate constructs for testing that Javafolk have had to. Mock gives you a few handy features to make stubbing out and verifying behavior easy and natural.

Fuzzyman&#8217;s new release of Mock (0.3.1) includes a couple of features that I suggested to make it more nose-friendly and to eliminate the need for global variables when using the &#8220;patch&#8221; decorator.

Thanks for the groovy module, Michael!

 [1]: http://www.voidspace.org.uk/python/mock.html