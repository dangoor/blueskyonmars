---
title: 'Tim Bray’s sharecropping: hit and miss'
author: Kevin Dangoor
type: post
date: 2003-07-14T18:51:06+00:00
url: /2003/07/14/tim-brays-sharecropping-hit-and-miss/
categories:
  - Software Development

---
Tim Bray wrote another interesting article, this one with a wide enough interest level to reach the [Blogdex][1] top 5. In [The Web&#8217;s the Place][2], Tim draws the comparison between developers working within proprietary systems and sharecroppers (farmers who work land owned by someone else). I think that&#8217;s a great analogy! How many companies have made utility programs for Windows that then got blown away by a built in feature in the next Windows version? How many applications vendors have successfully competed head-to-head with Microsoft? (I can think of [one][3], and they were nearly acquired.)

Tim feels that the best way to avoid being a sharecropper is to create for the Web and that

> All computer applications fall into one of three baskets: information retrieval, database interaction, and content creation. History shows that the Web browser, or something like it, is the right way to do the first two.

Here&#8217;s where my opinion differs from Tim&#8217;s. The Web works great for many applications, to be sure. But there are also many applications that benefit from the &#8220;richer&#8221; interfaces that Tim says are losing.

Tim says that he counts NetNewsWire as a Web browser. I disagree! NetNewsWire is a GUI app with all of the benefits that comes with that (and I guess [Ranchero][4] is a sharecropper because their software only runs under Mac OS X). Calling NetNewsWire a web browser is like calling Quicken a web browser, because it can access online resources.

WinAmp and KaZaA are other examples of applications that benefit from a rich client application. And I&#8217;m certainly glad that Eclipse does not have a web-based UI.

Even when it comes to &#8220;database interaction&#8221; apps, the web offers certain advantages (cross-platform with remote access capabilities for free), but has also traditionally had disadvantages. If you&#8217;re doing a lot of data entry, you need to be able to move very quickly using nothing but the keyboard.

One thing to note: creating a rich client app does not automatically mean that you&#8217;re a sharecropper. People who create apps using [wxPython][5] certainly aren&#8217;t, because those apps work on Unix, Windows and Mac OS X. I don&#8217;t think that people who create Java apps are really sharecroppers either. Sun owns the Java(tm) name, but I think they would have a really hard time making that technology more restrictive. (Check out [gcj][6] if you don&#8217;t believe me.)

All of that said, I&#8217;m not a rich client fanatic. Now that CSS and JavaScript with DOM have become usable across browsers, I feel better about using the web browser as the view technology for a larger variety of apps.

In summary, I agree with Tim that being a sharecropper is a bad thing, and that developing for the web is a way to avoid that. But, it&#8217;s not the only way and there remain compelling reasons to make rich client apps today.

 [1]: http://www.blogdex.net
 [2]: http://www.tbray.org/ongoing/When/200x/2003/07/12/WebsThePlace "ongoing Â· The Webâ€™s the Place"
 [3]: http://www.intuit.com
 [4]: http://ranchero.com/netnewswire/
 [5]: http://www.wxpython.org
 [6]: http://gcc.gnu.org/java/