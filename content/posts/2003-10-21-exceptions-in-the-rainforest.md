---
title: Exceptions in the Rainforest
author: Kevin Dangoor
type: post
date: 2003-10-21T19:05:16+00:00
url: /2003/10/21/exceptions-in-the-rainforest/
categories:
  - Software Development

---
[Ned Batchelder: Exceptions in the rainforest][1] is a response to Joel Spolsky&#8217;s article on exceptions. He had a nice little breakdown of system code to go with his explanation of why exceptions are &#8220;better&#8221;:

> In my experience, there are three layers to real code (from bottom to top, so this list might look upside-down):
> 
> * Adapting the software beneath you.
      
> * Building pieces of your system.
      
> * Combining it all together.

I agree with Ned&#8217;s article here. This is why exceptions are good. I think Ned is also making the argument for either using unchecked exceptions or for just transparently passing the exceptions all the way back up to the C layer.

 [1]: http://www.nedbatchelder.com/text/exceptions-in-the-rainforest.html "Ned Batchelder: Exceptions in the rainforest"