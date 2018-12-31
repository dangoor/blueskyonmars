---
title: 'UPX: Packer for Executables'
author: Kevin Dangoor
type: post
date: 2003-11-12T03:32:07+00:00
url: /2003/11/11/upx-packer-for-executables/
categories:
  - Software Development

---
Here&#8217;s a nifty tool: [UPX: the Ultimate Packer for eXecutables][1]. It will compress your executable programs and then decompress them (quickly!) on the fly, thus allowing them to take up less disk space. The authors claim there is no additional memory usage caused by the in-place decompression.

Of course, with machines having 100GB+ hard drives it&#8217;s hard to see where the gain is in compressing a 4MB program down to 3MB&#8230; but this tool could be useful if you&#8217;re distributing software or if you&#8217;ve got a program that you want to be able to run from a floppy. (A what?)

 [1]: http://upx.sourceforge.net/ "UPX: the Ultimate Packer for eXecutables - Homepage"