---
title: Watch out for permissions in Fedora Core 3 with Subversion behind Apache
author: Kevin Dangoor
type: post
date: 2004-12-22T18:22:37+00:00
url: /2004/12/22/watch-out-for-permissions-in-fedora-core-3-with-subversion-behind-apache/
categories:
  - Software Development

---
Getting Subversion in Fedora Core 3 is easy. You can use yum to get subversion and the mod\_dav\_svn Apache module. But it won&#8217;t work, because FC3 has SELinux configured out of the box. The [Subversion FAQ][1] talks about this now (but I didn&#8217;t see this in the Subversion Book yet). Yes, your files can be 777 and still not accessible to Apache. Unfortunately, the command listed in the Subversion FAQ didn&#8217;t work for me. I ended up using system-config-securitylevel to turn off SELinux for Apache.

Also interesting: there is a debate in Subversion land about using Berkeley DB vs. the Filesystem storage (FSFS). The crux of the debate is that your Berkeley DB can get hosed for a number of reasons (borked permissions, out of disk space, process dying, cosmic rays). Scripts are provided to allow a hot backup of your repository, so this shouldn&#8217;t be a big deal once you get your backups running in cron. But, I opted to go with the newer FSFS setup, which is really simple and seems pretty foolproof.

 [1]: http://subversion.tigris.org/project_faq.html#reposperms "subversion: Subversion FAQ"