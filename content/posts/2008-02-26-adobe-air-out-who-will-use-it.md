---
title: Adobe AIR out, who will use it?
author: Kevin Dangoor
type: post
date: 2008-02-26T15:47:37+00:00
url: /2008/02/26/adobe-air-out-who-will-use-it/
categories:
  - JavaScript
  - Software Development

---
Yesterday, Adobe shipped [AIR 1.0][1], an open source toolkit and runtime for creating desktop apps using web technologies. For a time there, I really wondered why someone would want AIR, rather than just building a normal webapp that runs from the server. I can now think of four reasons:

  1. offline &#8211; This one is obvious. AIR is a [Google Gears][2] competitor as a way to take a webapp offline.
  2. performance &#8211; Rather than relying on the browsers&#8217; caching behavior to make parts of your software load snappily, just ship the whole app to the user so that the whole thing is local as they navigate.
  3. browser consistency &#8211; Maybe you&#8217;re sick of trying to make IE work (I wouldn&#8217;t blame you for that, really). AIR uses [WebKit][3], which is a nice browser platform to target. Of course, this is a lame reason to use AIR. Forcing one&#8217;s users to install the AIR runtime and accept the download of one&#8217;s app rather than just using [a good JavaScript toolkit][4] and common cross-browser coding practices seems like a bad attitude toward one&#8217;s users.
  4. local data access &#8211; You can manipulate files on the user&#8217;s hard drive. This lets you more comfortably do things like build a password manager. [Pownce][5] uses AIR to allow people to conveniently drag-and-drop files into the Pownce service.

Installing your first AIR app is amazingly easy. I&#8217;m not sure what trickery Adobe pulled to do that, but it&#8217;s pretty cool. The only app I&#8217;ve used so far is [eBay Desktop][6]. In my opinion, there&#8217;s no reason that app is an AIR app rather than just a normal webapp. As far as I can tell, you need to be online to do anything useful with it. I don&#8217;t think any of the 4 criteria above apply to eBay Desktop.

It&#8217;s also notable that [SitePen has announced AIR support with Dojo 1.1][7]. That means that you can build cross-platform desktop applications using Dojo. That&#8217;s nifty.

AIR is a gamble for Adobe. From what I&#8217;ve seen, they seem to be putting a lot of money into it. Time will tell if any truly compelling apps appear.

 [1]: http://www.adobe.com/products/air/
 [2]: http://gears.google.com/
 [3]: http://webkit.org
 [4]: http://dojotoolkit.org
 [5]: http://pownce.com
 [6]: http://desktop.ebay.com/
 [7]: http://www.sitepen.com/blog/2008/02/25/adobe-engages-sitepen-to-make-dojo-toolkit-compatible-with-adobe-air/