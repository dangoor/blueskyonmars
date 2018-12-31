---
title: 'jMock: the latest mock library for Java'
author: Kevin Dangoor
type: post
date: 2004-05-27T04:04:33+00:00
url: /2004/05/26/jmock-the-latest-mock-library-for-java/
categories:
  - Software Development

---
Via Erik&#8217;s always helpful [Linkblog][1], [jMock &#8211; A Lightweight Mock Object Library for Java][2]. This started as a fork of the mockobjects.com DynaMock package (which I was using earlier today, in fact). I&#8217;ll give this one points on readability, which is certainly important in tests. I have to subtract points, though, because you need to extend their base class (or at least that&#8217;s all they show in the examples I&#8217;ve seen thus far), which is not always an option. Also, the readbility does come at the cost of verbosity, and I&#8217;m not completely sure about that.

Something that might be interesting would be to create a mockobjects package in Groovy. Since Groovy is dynamically typed, you don&#8217;t have quite the same pain in dealing with all of Java&#8217;s primitive types. That was one of the complaints the jMock authors had about the DynaMock way.

 [1]: http://www.thauvin.net/linkblog/?date=2004-05-25#Beat:736
 [2]: http://www.jmock.org/ "jMock - A Lightweight Mock Object Library for Java"