---
title: Summer of Code Goodies Arriving
author: Kevin Dangoor
type: post
date: 2006-08-21T12:43:51+00:00
url: /2006/08/21/summer-of-code-goodies-arriving/
categories:
  - Python

---
Though we still have more than a month of good weather to look forward to here in Michigan, the thought of summer ending and heading into another long winter isn&#8217;t pleasant. On the plus side, the end of summer brings the results of Google&#8217;s Summer of Code.

The one that I&#8217;ve been most looking forward to is [Migrate,][1] assistance for SQLAlchemy database schema migration. I just spotted Evan&#8217;s 0.2.0 release on the Cheeseshop. Looks good, but it&#8217;s a shame that sqlite is left out of some of the goodies.

I&#8217;ve also been keeping an eye on Ryan Forsythe&#8217;s [PyCells][2] project. Cells is one of these libraries that gives you a different way to think about how your code is setup. It&#8217;s a sort of event-driven system where changing one value will automatically cause dependent values to recalculate, much like a spreadsheet.

Also of interest is Alex Boterolowry&#8217;s [TurboX2][3] frontend for XMMS2. TurboX2 is a TurboGears web-based front end for the XMMS2 media player. From a code perspective, it features a number of interesting JavaScript bits that use MochiKit. These include a lazy list loader that will load in additional information as the list is scrolled. Even cooler sounding is an event loop that is designed to pick up and react to data that comes in from the server.

I&#8217;d be interested in hearing about other neat Python Summer of Code projects that went on.

 [1]: http://erosson.com/migrate/
 [2]: http://pycells.pdxcb.net/
 [3]: http://xmms2.xmms.org/~alex/turbox2/