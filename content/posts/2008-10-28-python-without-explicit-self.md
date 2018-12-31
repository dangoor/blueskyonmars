---
title: Python without explicit self
author: Kevin Dangoor
type: post
date: 2008-10-28T18:02:21+00:00
url: /2008/10/28/python-without-explicit-self/
categories:
  - Python

---
A month ago, Bruce Eckel wrote about wanting to [remove the explicit self parameter][1] from function argument lists in Python. Personally, I don&#8217;t mind the explicit self. To me, it makes it feel like all function objects are equal, even those that happen to be methods on classes. That said, Guido wrote [an in-depth response][2], and I certainly recommend that you check that out if you&#8217;ve ever considered getting rid of the explicit self.

After reading Guido&#8217;s response, I assumed that there must still be some way to eliminate the need for self in Python. Python is an amazingly flexible language. Further, I assumed that somebody had already done it. And sure enough, Michael Foord wrote an article that includes a [metaclass called Selfless][3]. As I suspected, this metaclass had to resort to bytecode manipulation. You really can&#8217;t change a lot about code objects in Python. I have no intention of using Selfless myself, but the Byteplay library that Michael links to seems neat and interesting.

 [1]: http://www.artima.com/weblogs/viewpost.jsp?thread=239003
 [2]: http://neopythonic.blogspot.com/2008/10/why-explicit-self-has-to-stay.html
 [3]: http://www.voidspace.org.uk/python/articles/metaclasses.shtml