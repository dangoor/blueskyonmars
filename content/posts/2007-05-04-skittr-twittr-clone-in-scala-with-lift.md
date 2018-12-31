---
title: 'Skittr: Twittr clone in Scala with Lift'
author: Kevin Dangoor
type: post
date: 2007-05-04T09:08:51+00:00
url: /2007/05/04/skittr-twittr-clone-in-scala-with-lift/
categories:
  - Software Development

---
David Pollack quotes Sandra Boynton in the title of this more-interesting-for-grownups post: [Prance with the Horses, Skittr with the Mice][1]. David has provided a more complete example of his [_lift_][2] web framework for [Scala][3]. This example shows why I&#8217;m paying attention to what&#8217;s going on with Scala and _lift_.

The generally accepted way to do scaling in the LAMP world is to go for &#8220;shared nothing&#8221; as much as possible and throw more boxes at the problem. But what if you could have a reasonable (and extensible) syntax that performs really well _and_ neatly supports event-driven applications that handle enormous numbers of simultaneous users getting Comet-style updates?

David claims that a single dual-core machine could handle 1M simultaneous users in his little Skittr application. I would be surprised if there wasn&#8217;t something unexpected that falls over before then, but the real point is that a single box can handle many users because of the speed of Scala and the Actor-based concurrency.

Don&#8217;t get me wrong: premature optimization remains the root of all evil. But, this doesn&#8217;t look like a bad way to put together apps, which means that the zippy performance is just a bonus, not a premature optimization.

 [1]: http://blog.circleshare.com/index.php?/archives/55-Prance-with-the-Horses,-Skittr-with-the-Mice.html
 [2]: http://liftweb.net/
 [3]: http://www.scala-lang.org/