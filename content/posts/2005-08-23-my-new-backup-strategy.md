---
title: My new backup strategy
author: Kevin Dangoor
type: post
date: 2005-08-23T18:42:22+00:00
url: /2005/08/23/my-new-backup-strategy/
categories:
  - Technology

---
A friend of mine had a hard drive failure yesterday. This, and [Ian&#8217;s hard drive failure][1] last month have jostled me into changing my backup strategy.

For years, I&#8217;ve been using a central Linux server and rsync to back up. I wrote a small script with all of the rsync options, and I&#8217;d run that script to get data files and documents up-to-date on the server.

This is generally fine, and I&#8217;m not likely to lose important data with a hard drive failure. I even burn some data to DVDs for offsite backups. What I will lose with this setup is time. Sure, I&#8217;ve got my data files, but how long will it take to reinstall the apps that I use regularly: TextMate, Python with various libraries, Firefox (with extensions), Omni Outliner, Photoshop, Skype, etc. How many preferences for these apps will be lost?

I&#8217;m lucky to have not had a hard drive failure on my primary machine for a few years. But just thinking about the lost time is frightening. So, my new backup strategy is to buy external hard drives for our machines.

Back in &#8220;the old days&#8221;, buying extra hard drives was extravagant, and so people would run backup utilities and backup to floppies (and then CDs). Hard drives are dirt cheap. Here&#8217;s a [60GB 7200 RPM drive][2] for $40. Add $22 and you get it in a USB 2.0 case. Who cares if it&#8217;s not a name brand, this is just a backup drive. If it fails, you just get a new one.

On the Mac, the free [Carbon Copy Cloner][3] will make a complete duplicate of your hard drive. I used this to save my Panther install so that I could make Panther Zesty News builds. It works great. Ian recommended [Super Duper!][4], which is only $20 and sounds fairly similar to CCC. They also have a free version that does cloning only. The full version of Super Duper will let you checkpoint your files so that you can go back in time if something gets really hosed (and is even hosed in your backup).

If you&#8217;ve got a desktop machine, you can just go mirrored RAID (which is what Ian chose to do after his failure), and you&#8217;re always in sync.

The hard drive is the both the most important thing in your computer (because of your data), and the most likely to fail. Secondary hard drives are way cheaper than the time required to deal with the data, application and configuration loss. I have no idea why I didn&#8217;t get this setup going sooner.

Special bonus link: Here is a [Firewire/USB 2.0 combo external chassis][5] that even has fancy lights in the included cables, all for $30.

Update: By the way, before I get a bunch of comments saying &#8220;everybody knows that!&#8221;, I know enough people with \*no\* backup strategy, so I&#8217;m sure that not quite everyone knows this. I&#8217;d imagine I&#8217;m also not the last person stuck in the old fashioned &#8220;backup your data files&#8221; mindset.

Update 2: Apparently, [Macs don&#8217;t boot from USB drives][6] at this point. Good to know&#8230;

 [1]: http://www.userscape.com/blog/2005/07/18/murphy-strikes-back/
 [2]: http://3btech.net/whlamadate601.html
 [3]: http://www.bombich.com/software/ccc.html
 [4]: http://www.shirt-pocket.com/SuperDuper/SuperDuperDescription.html
 [5]: http://store.4linkcomm.com/lide53usb201.html
 [6]: http://www.shirt-pocket.com/forums/showthread.php?t=461