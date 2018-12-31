---
title: rdiff-backup efficient mirroring/incremental backup
author: Kevin Dangoor
type: post
date: 2003-10-30T03:35:54+00:00
url: /2003/10/29/rdiff-backup-efficient-mirroringincremental-backup/
categories:
  - Technology

---
From time to time, the discussions on slashdot lead to some useful information&#8230; like this: [rdiff-backup][1] is a program that utilizes rsync&#8217;s rdiff code to do incremental backups. Using rdiff, it can save just the parts of files that have changed, making it possible to store incremental changes in a much smaller amount of space. It can run on Linux, Windows (via cygwin) and Mac OS X, so I&#8217;ll be able to back up all of the data we&#8217;ve got.

 [1]: http://rdiff-backup.stanford.edu/ "rdiff-backup: Main"