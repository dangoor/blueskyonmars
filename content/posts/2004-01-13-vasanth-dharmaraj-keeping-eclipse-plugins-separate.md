---
title: 'Vasanth Dharmaraj: Keeping Eclipse plugins separate'
author: Kevin Dangoor
type: post
date: 2004-01-13T20:37:16+00:00
url: /2004/01/13/vasanth-dharmaraj-keeping-eclipse-plugins-separate/
categories:
  - Software Development

---
An [excellent tip][1] from Vasanth Dharmaraj providing an easy way to drag your third party plugins along as you move between versions of Eclipse:

> Here is how to do it:
  
> 1. Create a folder called &#8216;links&#8217; in your eclipse directory.
  
> 2. Create a file with the extension .link, say plugins.link.
  
> 3. Open the file and add a line &#8216;path=c:\myplugins&#8217; and save the file.
  
> 4. Create the directory mentioned in the link file. (c:\myplugins)
  
> 5. Create a sub directory named &#8216;eclipse&#8217; in the above directory. (c:\myplugins\eclipse)
  
> 6. Create a couple of sub directories named &#8216;features&#8217; and &#8216;plugins&#8217; in the above directory. (c:\myplugins\eclipse\features & c:\myplugins\eclipse\plugins)
  
> 7. Now put all the third party plugins in these directories.
  
> 8. (Re)start eclipse and voilÃ all the plugins in the separate directory are loaded.

 [1]: http://www.vasanthdharmaraj.com/PermaLink.aspx?guid=ed866f73-5ca4-4b7b-bb72-acefd5a8d075 "Vasanth Dharmaraj's Blogs [my blog on dot net, java, eclipse, linux, formula one, xbox gaming... ]"