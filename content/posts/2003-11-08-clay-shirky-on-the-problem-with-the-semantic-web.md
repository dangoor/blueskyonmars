---
title: Clay Shirky on the problem with the Semantic Web
author: Kevin Dangoor
type: post
date: 2003-11-08T15:43:32+00:00
url: /2003/11/08/clay-shirky-on-the-problem-with-the-semantic-web/
categories:
  - Software Development

---
It was hard to classify this between &#8220;Technology&#8221; and &#8220;Software Development&#8221;. I ended up going with Software Development because the thought process that the W3C has gone through is not unusual for those of us in development. We look at the world we&#8217;re trying to model and try to simplify and generalize as much as possible so that we can make a powerful software system. Clay Shirky reasons that there are problems when you take this too far in: [The Semantic Web, Syllogism, and Worldview][1]

> This example sets the pattern for descriptions of the Semantic Web. First, take some well-known problem. Next, misconstrue it so that the hard part is made to seem trivial and the trivial part hard. Finally, congratulate yourself for solving the trivial part.

I think Clay is correct here. For someone to make software that deals with a given RDF file, there may often be more context needed than what RDF gives you. That&#8217;s one thing about XML files. When a person creates an XML format, they&#8217;re declaring what everything in that file means relative to how they will be using it. Sure, this will not always hold true, because people will often repurpose XML formats for their own nefarious needs&#8230; but at least there&#8217;s more context around an entire XML data definition than there is around a single RDF descriptor.

 [1]: http://www.shirky.com/writings/semantic_syllogism.html "Shirky: The Semantic Web, Syllogism, and Worldview"