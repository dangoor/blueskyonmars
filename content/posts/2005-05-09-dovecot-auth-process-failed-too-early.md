---
title: Dovecot auth process failed too early
author: Kevin Dangoor
type: post
date: 2005-05-10T06:06:30+00:00
url: /2005/05/09/dovecot-auth-process-failed-too-early/
categories:
  - Technology

---
For some reason (I don&#8217;t know what the reason is yet), my server rebooted twice a couple hours ago. Generally speaking, reboots aren&#8217;t that big a deal&#8230; journaling databases, journaling filesystems. Logs get processed and bam, everything is up.

Tonight, everything except for dovecot, the imap/pop servier, started up. The wonderfully descriptive error message that maillog provided me was that the &#8220;auth process died too early&#8221;. I&#8217;m not sure why having the auth process die later is a good thing, and I really wish there was some more detail in the log, but there wasn&#8217;t.

Googling for an error message is often a useful thing. I found an email message where running ldd (ldd /usr/libexec/dovecot/dovecot-auth) was recommended to see if something was missing. Sure enough, the FC3 dovecot was compiled expecting mysql support, and I have installed a newer mysql than what dovecot was expecting. I&#8217;m not even using mysql, but the fact that the auth program was expecting libmysqlclient.so.10 was enough to make dovecot die a cryptic death.

A symlink in /usr/lib later and dovecot is back up and running. Finally, I was able to pick up all of the latest copies of [the Sober.P worm][1]. You can never have too many, right?

 [1]: http://it.slashdot.org/article.pl?sid=05/05/08/1429219&tid=220&tid=218