---
title: Storing data on the browser
author: Kevin Dangoor
type: post
date: 2005-09-06T02:17:03+00:00
url: /2005/09/05/storing-data-on-the-browser/
categories:
  - Software Development

---
Cookies have some pretty severe limitations in terms of the amount of data you can store. Besides, they get transmitted to the server on every request, so you don&#8217;t necessarily want to store a ton of data in there anyway.

On the other hand, using sessions on the server to store data for the current user is also a bad idea unless you have a small or very predictable user base. If you&#8217;ve got a heavily dynamic app and you want to scale it up somewhat linearly, you need to work with HTTP&#8217;s generally stateless model.

The Ajaxian blog points to [a couple of posts by Brad Neuberg][1] about keeping session state in the browser. Using AJAX and Brad&#8217;s techniques, you&#8217;re only sending the state back to the server when you need to, not every time as you do with cookies.

The quick trick (it&#8217;s worth linking through to [Brad&#8217;s original article][2]) is to store your &#8220;session&#8221; data in a text field in a form. (It _must_ be in a form.) Brad tested in IE, Firefox and Safari and found that he could store data in all three, and it would still be there when he hit the back button. Additionally, he tried storing 1MB in both IE and Firefox and had no problem.

That can certainly solve session affinity problems, couldn&#8217;t it?

 [1]: http://www.ajaxian.com/archives/2005/08/internet_explor.html
 [2]: http://codinginparadise.org/weblog/2005/08/ajax-tutorial-saving-session-across.html