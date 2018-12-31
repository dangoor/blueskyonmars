---
title: Perl/Python Advantage is not Dynamic Typing
author: Kevin Dangoor
type: post
date: 2003-05-14T20:22:54+00:00
url: /2003/05/14/perlpython-advantage-is-not-dynamic-typing/
categories:
  - Technology

---
The latest entry into the strong/dynamic typing debate comes from [Dave Copeland][1]. He does make a good point in that Perl and Python have many features other than dynamic typing which make them faster to program in. I think he misses something when he talks about code being skipped in unit tests because there isn&#8217;t time. For those of us doing test driven development, the tests _come first_! The only code that I don&#8217;t write tests for now is code that is really, really onerous to test, and there&#8217;s not much of that. And where it does exist, I try to isolate it as much as possible.

 [1]: http://www.naildrivin5.com/davec/archives/000041.shtml "n a i l d r i v i n 5 . c o m / d a v e c"