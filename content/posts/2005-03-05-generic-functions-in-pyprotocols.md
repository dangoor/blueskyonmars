---
title: Generic functions in PyProtocols
author: Kevin Dangoor
type: post
date: 2005-03-06T05:38:50+00:00
url: /2005/03/05/generic-functions-in-pyprotocols/
categories:
  - Python

---
There are certain situations where generic functions make a whole lot of sense. (If you find yourself writing a method or function with a bunch of if/elif/else cases, you might be looking at one of these situations.) This week, I had a clear cut case of rules that I wanted to combine in a certain way and to also allow extensions of the rules. The PyProtocols dispatch package made this straightforward.

I ran into a situation where two rules applied equally well. The standard combination mechanism throws an exception in this case, rather than making an arbitrary choice as to which should apply. I wrote my own combination function already, but I&#8217;m still glad to see a new page of documentation specifically about result combination: [CombiningResults &#8211; The PEAK Developers&#8217; Center][1].

Generic functions are a handy tool to have in your belt. Sure, anything you can do with them you could have done before. But, some problems feel like a class or interface is the right solution, other problems feel like a generic function is a better fit.

 [1]: http://peak.telecommunity.com/DevCenter/CombiningResults "CombiningResults - The PEAK Developers' Center"