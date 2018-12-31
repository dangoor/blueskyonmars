---
title: iPhone 2.0 apps and synchronization
author: Kevin Dangoor
type: post
date: 2008-08-01T02:17:34+00:00
url: /2008/07/31/iphone-20-apps-and-synchronization/
categories:
  - Technology
tags:
  - iphone
  - synchronization

---
I&#8217;ve installed a number of iPhone applications, some of which I&#8217;m already using quite regularly. Unlike Apple&#8217;s own applications, third party apps cannot synchronize data via iTunes. That&#8217;s a real shame, given that Apple clearly has built support for such a thing. It&#8217;s possible that iTunes itself is not set up to handle third party sync while still ensuring that Apple controls what&#8217;s getting synced to where. Whatever the reason, developers have had to come up with their own means for syncing data between desktop and phone.

To make matters worse, the SDK has been available only under NDA all of this time. So, developers couldn&#8217;t even go into much detail with each other about how they were handling their sync functions, let alone actually sharing useful framework code.

My first synchronization experience was with [OmniFocus][1]. You could either sync via [MobileMe][2] or via your own WebDAV server. I don&#8217;t need MobileMe&#8217;s services, so $99/year simply wasn&#8217;t worth it. I set up WebDAV on my hosting server (which proved to not be very difficult), and sync works.

But, it&#8217;s _slow_. Agonizingly so (though there [may be a temporary solution][3] to this). On my computer, I don&#8217;t really notice, because my computer can do more than one thing at a time. Not so with the phone. I can do other stuff with OmniFocus while sync is going on, but I can&#8217;t use other apps.

So, OmniFocus&#8217; sync is either a pain to set up and slow, or will set you back $99 a year.

Intriguingly, OmniFocus will transfer synchronization settings from your computer to your phone via wifi and Bonjour. It&#8217;s super simple to use and quick. Why didn&#8217;t OmniGroup just use that as the sync mechanism for the data? That would have saved a lot of pain for a lot of people.

I&#8217;ll grant that they can have a somewhat more transparent sync process now, but I&#8217;d much rather have a quick (with no wacky setup and no $99/year) manually-started sync process. It turns out that OmniGroup is [working on this][4].

It also turns out that the _free_ new [1Password][5] application for the iPhone does its sync in just that way. They&#8217;ve even got high-quality security checks to ensure that people can&#8217;t hijack your synchronization session while you&#8217;re trying to set it up. 1Password is different from any other password manager I&#8217;ve used, but I will say that these guys have definitely thought through the many wrinkles of convenient password management. Let&#8217;s hope that iPhone 2.1 includes copy-and-paste so that you can copy passwords out of 1Password and into Safari. (Right now, they have their own little browser, since there&#8217;s no way to copy passwords out.)

If you find yourself writing an iPhone app that you want to sync up with a Mac app, please consider the wifi+Bonjour, manually-started synchronization route.

 [1]: http://www.omnigroup.com/applications/omnifocus/iphone/
 [2]: http://www.apple.com/mobileme/
 [3]: http://forums.omnigroup.com/showthread.php?t=9145
 [4]: http://forums.omnigroup.com/showthread.php?t=9081
 [5]: http://1password.com/