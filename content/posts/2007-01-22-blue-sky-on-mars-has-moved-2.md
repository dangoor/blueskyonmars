---
title: Blue Sky On Mars has moved
author: Kevin Dangoor
type: post
date: 2007-01-22T18:37:29+00:00
url: /2007/01/22/blue-sky-on-mars-has-moved-2/
categories:
  - Random

---
At long last, I have moved Blue Sky On Mars to a new machine with a couple of config changes along the way. The new BSOM is on a CentOS machine at Zogmo, sitting behind lighttpd instead of Apache. I also changed over a couple of tables from myisam to InnoDB. Hopefully, all of this will improve server uptime, because the old server was still seeing very high load even with BSOM as the highest traffic site on the box. I had other reasons to move and switch to lighttpd, which is why I didn&#8217;t spend more time troubleshooting the old server.