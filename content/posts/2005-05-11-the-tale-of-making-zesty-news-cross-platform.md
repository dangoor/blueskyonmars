---
title: The tale of making Zesty News cross-platform
author: Kevin Dangoor
type: post
date: 2005-05-11T17:00:29+00:00
url: /2005/05/11/the-tale-of-making-zesty-news-cross-platform/
categories:
  - Software Development

---
As I [mentioned earlier][1], [Zesty News][2] has a browser-based interface. But, Zesty News is not a web-based program: it&#8217;s a desktop application. You install it on your computer and access the program through your web browser.

So, I get to deal with the intracacies of cross-browser compatibility _and_ the deployment aspects of a desktop application. Joy!

But, it goes beyond that. While I can imagine telling a geek friend, &#8220;yeah, you just point your browser at http://localhost:xxxx and there you go!&#8221;, I can&#8217;t imagine telling a normal person that. I certainly can&#8217;t imagine selling a product like that. That would just be irresponsible product management. My goal was to have _just enough_ native GUI to give people easy access to Zesty News, and do everything else in the browser. I also decided early in the process that I am only targeting modern and mainstream systems, at least to start with. Here&#8217;s my supported platforms matrix:

<table>
  <tr>
    <th>
      &nbsp;
    </th>
    
    <th>
      Windows XP<sup>1</sup>
    </th>
    
    <th>
      Mac OS X<sup>2</sup>
    </th>
  </tr>
  
  <tr>
    <th>
      Firefox
    </th>
    
    <td>
      Yes
    </td>
    
    <td>
      Yes
    </td>
  </tr>
  
  <tr>
    <th>
      Safari
    </th>
    
    <td>
      Waiting for Apple on this one
    </td>
    
    <td>
      Yes<sup>3</sup>
    </td>
  </tr>
  
  <tr>
    <th>
      Internet Explorer
    </th>
    
    <td>
      Yes<sup>4</sup>
    </td>
    
    <td>
      Blech
    </td>
  </tr>
</table>

<sup>1</sup> In all likelihood, Zesty News will run on any 32-bit Windows. That&#8217;s not part of my initial test plan, though, so I don&#8217;t want to guarantee that.

<sup>2</sup> OS 10.3 and 10.4

<sup>3</sup> My testing will be with the latest version of Safari that comes via Software Update. This means 1.3 on Panther and 2.0 on Tiger.

<sup>4</sup> My testing is with IE6. It is quite possible that IE5.5 will work as well.

Limiting things like this certainly reduces the cross-browser issues. There are some tricky bits, but Firefox, Safari and IE6 are close enough that I don&#8217;t spend all of my time just dealing with browser inconsistencies.

The question then becomes: what is &#8220;just enough native GUI&#8221;? It turns out that there&#8217;s not a lot of native GUI necessary, but that work does extend to providing something for every browser in addition to each platform.

Remember how I said that I couldn&#8217;t imagine telling all of the non-techies to go to http://localhost:xxxx? I have a couple of solutions for this. On both Windows and Mac, firing up Zesty News automatically opens the browser to Zesty News. But, that&#8217;s not a complete solution: people leave news aggregators running all the time. On Windows, as you&#8217;d expect, you get a taskbar icon  ![taskbar image][3]that you can just double-click to get Zesty News to popup in your default browser. Whew! Something that &#8220;just works&#8221; with multiple browsers. The right-click menu also includes the ability to quit Zesty News (but why would you want to do that?):

![menu image][4]

As of this writing, the Mac interface isn&#8217;t quite as slick. That will change somewhere along the way. On the Mac, you can use cmd-Tab to hop over to Zesty News:

![cmd-tab view][5]

Once there, you can use the menu to launch your default browser to the right place:

![Zesty Mac menu][6]

Of course, you can also add a bookmark to Zesty News in your browser, given that the Zesty News software is just sitting at a URL you can point to.

Just opening Zesty News isn&#8217;t all that&#8217;s needed, though. The other key feature that&#8217;s needed when not looking at the Zesty News interface itself is the ability to subscribe to new feeds. Firefox 1.0 added a nifty feature to handle this, and the open source [Feed Your Reader][7] tool by Michael Koziarski made it easy to subscribe to feeds in Zesty News from Firefox.

![zesty firefox][8]

That&#8217;s dandy for the 10-20% of web surfers who are using Firefox. But, what about the 80% who run IE? Zesty News includes an IE toolbar that scans for feeds and makes it as easy to subscribe as it is in Firefox:

![zesty ie][9]

With Mac OS 10.3.9, things aren&#8217;t so pleasant. Registering Zesty News as a reader for the &#8220;feed://&#8221; protocol is easy enough (just add it to the info.plist file). But, with 10.3.9 (and Safari 1.3), Apple took over so that Safari would display a message saying that you need to upgrade to Tiger/Safari 2.0 to do RSS. Ugh.

Zesty News has a &#8220;Browser Setup&#8221; screen that includes an option to make Zesty News your default feed reader. Unfortunately, there&#8217;s no documented way to do this under Mac OS 10.3! Under Windows, you just set a couple of registry entries and you&#8217;re done. Carl Lindberg, author of the excellent [RCDefaultApp][10], gave me some tips on the undocumented, private APIs to do this. I haven&#8217;t had a chance to do it yet, though.

So, the net of all of this is that Safari 1.x doesn&#8217;t have a fancy way to detect and subscribe to feeds right now. However, Zesty News has a Feed Finder bookmarklet that should work in most modern browsers, and that makes it pretty easy to subscribe to feeds.

Of course, Mac OS X Tiger makes this all better. Safari 2.0 detects feeds along the way and provides an easy subscription mechanism that will work with Zesty News. (I haven&#8217;t installed Tiger yet, so I haven&#8217;t tested this. From what I&#8217;ve read, this should work fine, though.) Safari 2.0 also lets you change your default feed reader in much the same way that Safari 1.x lets you set your default web browser.

That seems a little backward to me, though. You really should be able to tell an application &#8220;I want you to be my default&#8221;, rather than having to run some other application which happens to do the same thing. Carl Lindberg reports that Tiger provides public APIs for setting defaults for file types, but not for URLs. And, of course, the private APIs have changed between Tiger and Panther.

Before Zesty News 1.0 final is released, I&#8217;m going to straighten out the Mac support to fix all of this. It&#8217;s ironic, because I use the Mac for all of my work except for Windows-specific development and testing.

Overall, making Zesty News cross-platform and cross-browser has not been _too_ painful. There have been some days where I&#8217;ve been pulling my hair out over one little thing that works on one platform but not the other, or weird APIs or strange compilation problems. But, I feel much better about having a cross-platform Zesty News so that I can support the increasing number of folks running Mac OS X and the masses running Windows.

 [1]: http://www.blueskyonmars.com/archives/2005/05/06/feed_reading_belongs_in_the_browser.html
 [2]: http://www.zestynews.com
 [3]: http://www.blazingthings.com/files/zestytask1.png ""
 [4]: http://www.blazingthings.com/files/zestytask2.png ""
 [5]: http://www.blazingthings.com/files/zestymac1.png ""
 [6]: http://www.blazingthings.com/files/zestymac2.png ""
 [7]: http://projects.koziarski.net/fyr/
 [8]: http://www.blazingthings.com/files/zestyff.png ""
 [9]: http://www.blazingthings.com/files/zestytool1.png ""
 [10]: http://www.rubicode.com/Software/RCDefaultApp/