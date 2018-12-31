---
title: Approximating closures in Java
author: Kevin Dangoor
type: post
date: 2003-05-16T18:16:54+00:00
url: /2003/05/16/approximating-closures-in-java/
categories:
  - Technology

---
Charles Miller wrote a nice article: [The Fishbowl: Closures and Java: a Tutorial][1]. He talks about using inner classes to somewhat approximate closures. He also says that &#8220;To implement them properly would involve making changes to some pretty fundamental parts of the JVM&#8221;, which I&#8217;m not sure is completely true. It may be possible for Sun to create java.lang.Function and then add some syntactic sugar to the compiler to create

1) Functions that can be passed around easily, which is something that is potentially quite useful
  
2) Real closures (but there may be more issues to the scoping that I&#8217;m just not thinking through)

 [1]: http://fishbowl.pastiche.org/archives/001325.html "The Fishbowl: Closures and Java: a Tutorial"