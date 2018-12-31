---
title: On the failure of Swing
author: Kevin Dangoor
type: post
date: 2003-11-18T16:27:16+00:00
url: /2003/11/18/on-the-failure-of-swing/
categories:
  - Software Development

---
Joshua Marinacci opened up a big discussion with his java.net blog entry: [Swing has failed. What can we do?][1]. He makes _some_ good points, and the discussion that follows has all sorts of interesting input. 

> (Comment from ocean): There are plenty of valid reasons to criticize Swing but &#8220;Swing is not VB&#8221; is not one of them. Swing is \*\*not an application framework\*\*.

This is absolutely correct. SWT has already gotten a lot of praise for its use of native widgets, and IBM may get another leg up with the [Eclipse Rich Client Platform][2], which provides an application framework.
  
A couple of months ago, I went looking for a Swing GUI app framework. I found several, and spent a fair amount of time with Eclipse. Ultimately, what I went with was a combination of approaches provided by different Swing frameworks. This approach is easy to use, removes none of Swing&#8217;s power, and provides good flexibility for your application&#8217;s model objects.
  
[Wotonomy][3] (and WebObjects) had the greatest philosophical influence on me, because it eliminates a lot of controller code and provides for an excellent separation of concerns.

 [1]: http://weblogs.java.net/pub/wlg/633 "Swing has failed. What can we do?"
 [2]: http://dev.eclipse.org/viewcvs/index.cgi/platform-ui-home/rcp-proposal/rich_client_platform_facilities.html?rev=HEAD
 [3]: http://wotonomy.sf.net