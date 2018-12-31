---
title: 'P2P Sockets: convenient firewall circumvention'
author: Kevin Dangoor
type: post
date: 2003-09-18T19:46:19+00:00
url: /2003/09/18/p2p-sockets-convenient-firewall-circumvention/
categories:
  - Software Development

---
Standard Internet routing techniques allow any machine on the network to talk to any other. It&#8217;s a basic part of how the net works. Then, people started setting up firewalls to protect their less-secure (or more private) hosts. Now, some folks have [reimplemented java.net.Socket][1] to allow you to run any service over JXTA, essentially doing nothing of value other than circumventing your firewall. I guess there is a little value in that a lot of people are not behind firewalls, but are behind NAT devices because of their limited IP space. Anyway, this still feels a bit crazy to me.

 [1]: http://p2psockets.jxta.org/ "Project Home Page"