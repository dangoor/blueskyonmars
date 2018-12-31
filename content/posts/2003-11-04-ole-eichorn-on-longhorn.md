---
title: Ole Eichorn on Longhorn
author: Kevin Dangoor
type: post
date: 2003-11-04T20:39:47+00:00
url: /2003/11/04/ole-eichorn-on-longhorn/
categories:
  - Software Development

---
Tim Bray linked to [The Emperor&#8217;s New Code][1] by Ole Eichorn. It&#8217;s a rant about the new technologies in the eventually coming Windows &#8220;Longhorn&#8221; release. The jury hasn&#8217;t even stepped into the box yet with regards to Microsoft&#8217;s new UI paradigm (XAML) and the WinFS filesystem/database, because no one is really using that stuff yet. Ole comments on these untested technologies. Rather than commenting on that, I&#8217;m going to comment on the commentary.

First of all, Ole is hung up on speed. He gives tremendous importance to the speed of the code, saying that development velocity really doesn&#8217;t matter. It&#8217;s true that people aren&#8217;t likely to use dog slow programs. But today&#8217;s hardware is fast enough that writing everything in C++ is simply not a requirement. If speed were what it was all about, we&#8217;d still be writing assembly language.

Ole cautions us to &#8220;look at what XUL did to Mozilla&#8221;. All right, I&#8217;ll look at what XUL did to Moz. Yes, it&#8217;s not quite as snappy as a native app. But, it works identically on both my Mac and PCs, and the XUL/JavaScript combination has enabled the Mozilla developers (and plugin developers) to add all sorts of useful features that would take ages to put together in C++. On all of my machines, Moz&#8217;s UI is responsive enough, and the rendering engine (written in C++) is plenty fast and does a much better job of rendering than that of IE. So, Moz puts the speed where it really counts: rendering performance (C++) and new feature development (XUL/JavaScript).

I think that features, usability, and possibly marketing are more important than speed. Java programs have generally failed to make any inroads in the desktop app space because they looked like crap and didn&#8217;t work like any of the other programs that people owned or used. Windows Media Player is an example of a slow piece of software, but people still use it because of its marketing (it comes with Windows!) and features like the media library. I think most of an app like Quicken could be written in a higher-level language than C++ and still be snappy.

> I can appreciate that there may be debug code and features which haven&#8217;t yet been optimized, but performance isn&#8217;t something you add in later. It has to be designed in from the start.

The phrase &#8220;premature optimization is the root of all evil&#8221; has been around a _long_ time, and is even cited in Eric Raymond&#8217;s [Art of Unix Programming][2], where ESR talks about the pain that can be caused by trying to optimize things before you know where performance problems are. Especially if you&#8217;re working the agile way and have tests to back you up, you can make major implementation changes step-by-step to improve performance where it counts.

I do agree with Ole that XAML will not necessarily add anything. There are many things that people have created XML syntaxes for that could just as well be done in standard code.

For some reason, Ole insists that &#8220;WinFS is going to be glacial&#8221;. I have no idea where that thought comes from. Others have been experimenting with database-driven filesystems for some time. Microsoft has been in the database business for quite a while, and I think they&#8217;re quite capable of making a database engine that can handle a typical desktop user&#8217;s filesystem efficiently.

> Of the 140,000 files, there is one file I care about more than any other, my Outlook .PST file. This one file is a repository of all my emails, sent and received, all my calendar items, and all my contacts. Know why it is one file? For performance. Try storing every email, appointment, or contact in a separate file, and you&#8217;ll have the slowest PIM known to man.

The Outlook.pst file is a database. As I understand WinFS, that&#8217;s a database too. And it&#8217;s probably going to be based on very similar code. Storing every email in a separate file will be _the same thing_ as storing them in separate records in the Outlook.pst file.

Microsoft is taking some large steps with Longhorn, but they&#8217;ve got a ways to go yet. There are interesting projects (like [Storage][3]) going on in Linux-land and I&#8217;d really like to see some Linux-based desktops gain traction before Longhorn ships. Competition is a good thing.
  
(Updated to add a paragraph about program speed)

 [1]: http://w-uh.com/index.cgi/articles/031102-emperors_new_code.html "Critical Section - The Emperor's New Code"
 [2]: http://www.catb.org/~esr/writings/taoup/html/ch01s06.html#rule_of_optimization
 [3]: http://www.gnome.org/~seth/storage/