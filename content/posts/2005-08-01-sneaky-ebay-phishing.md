---
title: Sneaky eBay phishing
author: Kevin Dangoor
type: post
date: 2005-08-02T02:06:46+00:00
url: /2005/08/01/sneaky-ebay-phishing/
categories:
  - Software Development

---
I&#8217;ve seen lots of phishing scams, but this one is particularly clever and has a lesson for us folks developing web apps.

The email was formatted better than many phishing scams, but had the common fingerprint of &#8220;you need to update your account information&#8221;. Out of curiousity, I took a look at the link they were directing me to:

&#8212;&#8211;://signin.ebay.com/ws/eBayISAPI.dll?SignIn&UsingSSL=1&pUserId=&ru=http://servlet.ebay.com/ForumController?dest=&#8212;-://217.159.171.237/.aw-cgi/eBayISAPI.dll/ebay/login.html

(I&#8217;ve yanked the https from the beginning so that no one accidentally gets caught from this site.)

At first, I was very confused. The link was actually going to eBay! Unless someone had hacked eBay&#8217;s DNS servers (not very likely), then signin.ebay.com is an eBay machine. The trick is this (http blocked out again):

dest=&#8212;-://217.159.171.237/

eBay&#8217;s signin page allows (or allowed, I didn&#8217;t try it), arbitrary redirection. So, you login on the real eBay page, and then get bumped over to the phisher&#8217;s site. On the plus side, the phisher will have to ask for your username/password again, because I&#8217;m pretty sure that eBay is not just going to send that along blithely to some random destination. Being forced to sign in twice is, well, fishy. I don&#8217;t know how many people would recognize that, though.

Moral of the story: if you&#8217;re implementing a signin page using redirects, which is a very common thing, make sure that you&#8217;re only redirecting back to your domain.