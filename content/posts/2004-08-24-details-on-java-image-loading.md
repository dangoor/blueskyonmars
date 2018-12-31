---
title: Details on Java image loading
author: Kevin Dangoor
type: post
date: 2004-08-24T19:59:20+00:00
url: /2004/08/24/details-on-java-image-loading/
categories:
  - Software Development

---
Chet Haase has provided very detailed information on strategies for loading images in Java and acheiving good display performance: [java.net: ToolkitBufferedVolatileManagedImage Strategies][1]. We&#8217;re doing quite a bit of image work (with 600 dpi 8.5&#8243;x11&#8243; images), so I&#8217;ve already become acquainted with Java 1.4 ImageIO and JDK 1.2 BufferedImage. Most recently, I&#8217;ve been looking at the operation chaining features of Java Advanced Imaging in an attempt to quickly provide high-quality screen resolution scalings of those 600 dpi images. Too bad we can&#8217;t just get 600 dpi screens 🙂

 [1]: http://weblogs.java.net/pub/wlg/1739 "java.net: ToolkitBufferedVolatileManagedImage Strategies [August 24, 2004]"