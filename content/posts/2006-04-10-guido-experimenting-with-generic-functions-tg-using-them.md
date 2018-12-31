---
title: Guido experimenting with generic functions, TG using them
author: Kevin Dangoor
type: post
date: 2006-04-10T19:59:05+00:00
url: /2006/04/10/guido-experimenting-with-generic-functions-tg-using-them/
categories:
  - Python
  - TurboGears

---
Guido has blogged about a generic function implementation (he uses the term [Dynamic Function Overloading][1]) that he has checked into the Python sandbox. It is good news to see work on this going into the core of Python. TurboGears 0.9 makes heavy use of Phillip Eby&#8217;s RuleDispatch package and it gives a lot of power in choosing an error handler, choosing an output format and even determining if a user is authorized for a resource, if you use a new package created by Alberto. We&#8217;re using it quite a bit behind the scenes and strategically exposing it here and there. If this becomes a standard part of Python, we don&#8217;t have to worry about people not understanding how the implementation works. Most excellent.

**Update**: in the comments, Bob Ippolito points out that Guido&#8217;s code is just doing dispatch by type and not by expression, as RuleDispatch does. I had noticed this originally, but tuned it out when I was posting. RuleDispatch is exceedingly powerful because of the way it handles expressions. What Guido describes is certainly a useful addition to Python and give people a chance to get used to functions being chosen at runtime, which will lessen the barriers to folks using RuleDispatch.

 [1]: http://www.artima.com/weblogs/viewpost.jsp?thread=155514