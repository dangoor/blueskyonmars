---
title: Just because we’re always changing doesn’t mean we shouldn’t
author: Kevin Dangoor
type: post
date: 2008-01-04T16:36:22+00:00
url: /2008/01/04/just-because-were-always-changing-doesnt-mean-we-shouldnt/
categories:
  - Software Development

---
Bruce Eckel is recommending that the Java language should be declared &#8220;stable&#8221; and left as is, rather than grafting on features that don&#8217;t fit well (particularly in the face of maintaining backwards compatibility). See: [Java: Evolutionary Dead End][1]. I agree with Bruce. As long as a high-degree of backwards compatibility is required, adding language features to Java will be clumsy at best. [ECMAScript][2] has the same backwards compatibility with forward movement challenges, but the language is much more flexible at its base, so I think ES4 can be a more successful evolution than Java 5 was.

Something interesting in this discussion is a comment from [Vincent O&#8217;Sullivan][3] that echoes the [Scala Will Do][4] cartoon from a couple days back. The implication there is that people in software development are always just chasing after the next shiny thing to help them with their projects&#8230; and, since it&#8217;s a joke, the implication is that people shouldn&#8217;t do that.

Software is the stuff of thoughts. It&#8217;s very malleable and new ideas can be tested out fairly cheaply. With the internet, new ideas and code can spread far and wide quickly. This is all a good thing. For me, creating software today is tremendously better than it was 5, 10, 15, 20 years ago. I watch many of the shiny things go flying by, but I don&#8217;t actually _use_ them. But I consider the shiny things to be very important. There are all kinds of ideas wrapped up in there that can be applied in different contexts and with different tools. Some of the implementations that come out of those ideas will make it into the mainstream.

Generally speaking, people don&#8217;t switch to all of the shiny things that fly by. Some people _will_ give them an honest try and will either be rewarded for being a successful early adopter or will suffer some pain and head back to other solutions. If enough people like the idea and follow through, it will become mainstream. Rails was the shiny new thing in 2004. There were undoubtedly people who felt the pain of being early adopters, but many more were far more productive than people using other tools that were common back in those days. Regardless of how many people ultimately adopt Rails, the fact is that many of the ideas presented there have had a significant influence on work that has happened since.

Scala is a cool language. There are many other cool languages, but the reason Scala is getting talked about is because it is more than a toy and it&#8217;s something that people can apply today. Until Scala has the kind of IDE support that Java users are used to, I&#8217;d consider the people using it to be early adopters. Regardless of whether Scala enters the mainstream, it contains interesting ideas and it&#8217;s worth looking at. I actually rather doubt that Scala will become mainstream, because the gap between its syntax and what mainstream programmers find &#8220;familiar&#8221; is too large. Steve Yegge made a [similar comment about Scheme][5].

My point in all of this is that the way we write software is _always_ changing and is generally evolving for the better. Look back on how you&#8217;ve created software in the past, and I&#8217;m sure you&#8217;ll find that it&#8217;s better today. If not, you probably haven&#8217;t been looking at enough of the shiny things that have flown by.

 [1]: http://www.artima.com/weblogs/viewpost.jsp?thread=221903
 [2]: http://ecmascript.org
 [3]: http://www.artima.com/forums/flat.jsp?forum=106&thread=221903&start=15&msRange=15
 [4]: http://stuffthathappens.com/blog/2008/01/02/scala-will-do/
 [5]: http://steve-yegge.blogspot.com/2007/12/codes-worst-enemy.html#c812623484442160497