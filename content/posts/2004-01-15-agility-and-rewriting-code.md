---
title: Agility and rewriting code
author: Kevin Dangoor
type: post
date: 2004-01-16T03:44:46+00:00
url: /2004/01/15/agility-and-rewriting-code/
categories:
  - Software Development

---
Neil Gunton somehow managed to get [Rewrites Considered Harmful?][1] posted to Slashdot. As others pointed out (and the author himself posted on his article), Joel has written a [better piece][2] about this same topic. (Joel is an excellent writer, so that&#8217;s not really meant as a knock against Neil. I&#8217;m certainly not as good a writer as Joel.)

The interesting bit here is the discussion on Slashdot. There were a lot of comments along the lines of &#8220;specs can&#8217;t go that far in the future&#8221; or &#8220;sometimes rewrites are necessary because the code is too hard to work with&#8221;. Very few people mentioned refactoring, and a number of them seemed to use it to mean &#8220;rewriting small parts of the code at a time&#8221;.

This is what agility and extreme programming are trying to get across. By having a comprehensive test suite, you&#8217;re able to more confidently change your codebase. Because of that, you&#8217;re able to do what Ward Cunningham suggests: if it&#8217;s hard to add a feature, change the code around to make it easy to add the feature, and then add it! If all of your features are added this way, your code will be much cleaner and more maintainable.

Rewrites may still be necessary over the long haul, if there is a platform shift. But, even then, assuming you&#8217;re not moving to an altogether different programming paradigm (like procedural to OO), you can probably just port a well-designed system to the new platform.

The point is that you need to bake in the ability to accept change from day one. As long as your code is ready to be changed, learning a better way to do things is just an opportunity to move the code up to the next level, step by step. It&#8217;s not a cause to rewrite.

 [1]: http://slashdot.org/article.pl?sid=04/01/15/1837242&mode=thread&tid=126&tid=156 "Slashdot | Rewrites Considered Harmful?"
 [2]: http://www.joelonsoftware.com/articles/fog0000000069.html