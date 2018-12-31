---
title: Buoy UI toolkit
author: Kevin Dangoor
type: post
date: 2003-07-08T00:41:32+00:00
url: /2003/07/07/buoy-ui-toolkit/
categories:
  - Software Development

---
The [Buoy][1] UI toolkit provides, in the words of the author,

  * A much simpler, cleaner, and more consistent API
  * A better mechanism for laying out interface components
  * A far more powerful event handling mechanism, which is based on dynamic binding of arbitrary methods as event listeners
  * Built in support for serializing user interfaces as XML, then reconstructing them again

Since Swing is already a wrapper of components around AWT and has never been praised for its speed, one has to be a little wary. From a read of the first part of &#8220;About Buoy&#8221;, it looks like one of the things done to simplify the API is to collapse the model and view into one object. This may not be as bad an idea as it sounds, assuming your application has its own model objects to maintain MVC application-wide.
  
I&#8217;ll definitely want to read more and play with this a bit before I pass judgment one way or the other.

 [1]: http://buoy.sourceforge.net/ "Buoy"