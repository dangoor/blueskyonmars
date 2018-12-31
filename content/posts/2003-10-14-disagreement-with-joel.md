---
title: Disagreement with Joel
author: Kevin Dangoor
type: post
date: 2003-10-14T16:24:45+00:00
url: /2003/10/14/disagreement-with-joel/
categories:
  - Software Development

---
In his most recent article, Joel Spolsky declares that [exceptions are bad][1]. He&#8217;s gotten a lot of [pushback on this (Charles Miller has a nice collection of this)][2], which is not surprising. Many of us have worked with error return codes and exceptions both and have a strong preference for exceptions.

I think it is a powerful testament to how much people appreciate Joel&#8217;s writing that so many people have spoken out on this one saying &#8220;I always enjoy Joel&#8217;s writing, but&#8230;&#8221; Joel has had a great collection of articles that show he really has a clue.

Contrary positions, like this one, from respected folks like Joel often encourage a rethinking of your position on something. In this case, I doubt there will really be much rethinking&#8230; I, for one, have been down the error code path before and don&#8217;t want to go back.

When creating methods, my current thinking on exceptions is to use checked exceptions for things that I think the application can gracefully recover from. Contrary to what Joel is talking about, in Java the programmer _does_ know which exceptions can be thrown by a given method.

If the exception is the kind of thing that it really doesn&#8217;t make sense to continue after, throwing an unchecked exception eliminates a lot of messiness in the code. Just make sure that the UI catches the exception and provides a nice, descriptive message to the user so that support people can help if need be.

 [1]: http://www.joelonsoftware.com/items/2003/10/13.html
 [2]: http://fishbowl.pastiche.org/2003/10/14/taking_exception_to_joel_spolsky "The Fishbowl: Taking Exception to Joel Spolsky"