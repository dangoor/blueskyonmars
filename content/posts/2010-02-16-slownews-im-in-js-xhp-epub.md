---
title: 'SlowNews: IM in JS, XHP, ePub'
author: Kevin Dangoor
type: post
date: 2010-02-16T14:00:43+00:00
url: /2010/02/16/slownews-im-in-js-xhp-epub/
categories:
  - SlowNews

---
## Ajax IM: Open Source IM, Totally JavaScript

The MIT-licensed [Ajax IM][1] library lets you add instant messaging to your site and features a new [node.js][2] server side. This is certainly a good use for an async framework like node! The one thing I noticed while sitting on their site is that it has an unpleasant way of tacking things onto your browser&#8217;s history without actually going anywhere. Should you want to roll your own messaging, you could fire up [Faye][3] on node.js and use your favorite [Bayeux client side library][4].

## XHP: E4X for PHP

Did you know that some implementations of ECMAScript allow you to [embed XML right in your JavaScript][5]? I&#8217;d imagine many people don&#8217;t, because folks in the &#8220;real world&#8221; need to make sites that run on IE. Well, if you&#8217;ve been pining for the ability to embed XML right there in your code, or if you&#8217;ve been looking for a chance to turn PHP inside out, you&#8217;re going to love [XHP][6], which Facebook recently open sourced. At the very least, you&#8217;ll go read about it and then [learn about XHP&#8217;s implementation performance characteristics][7] from none other than Rasmus himself.

## wtfjs

OK, so I&#8217;m a well-known booster of JavaScript. But, you&#8217;ll never hear me say that it&#8217;s perfect. _Every_ language has its warts, and [wtfjs][8] has an enjoyable collection of JavaScript&#8217;s.

## LESS.app Now With Automatically More Less

[LESS.app][9] lets Mac users write their CSS in [LESS][10] and have that LESS automatically turned into valid CSS as they work. Languages like LESS are cool, because they have an opportunity to influence how the actual standards will evolve.

## ePub in JavaScript

The ePub standard looks to be gaining serious momentum as an ebook format, albeit without the support of the [top selling ebook reader][11] to date. There has been a good bit of work done to create usable ePub readers in JavaScript, and Michael Mahemoff has [a good roundup][12] over at Ajaxian.

## > list
  
11 goto 11

Top 11 JavaScript Features (from wtfjs)

11. `"string" instanceof String; // false.`
  
10. `typeof NaN // number, of course.`
  
1.

<pre>(function(){
  var x = y = 1;
})();
alert(x); // undefined
alert(y); // 1 -- oops, auto-global!
</pre>

 [1]: http://ajaxim.com/
 [2]: http://nodejs.org/
 [3]: http://github.com/jcoglan/faye
 [4]: http://api.dojotoolkit.org/jsdoc/1.3.2/dojox.cometd
 [5]: http://en.wikipedia.org/wiki/ECMAScript_for_XML
 [6]: http://www.facebook.com/notes/facebook-engineering/xhp-a-new-way-to-write-php/294003943919
 [7]: http://toys.lerdorf.com/archives/54-A-quick-look-at-XHP.html
 [8]: http://wtfjs.com/
 [9]: http://incident57.com/less/
 [10]: http://lesscss.org/
 [11]: http://www.amazon.com/gp/product/B0015T963C?ie=UTF8&tag=blueskyonmars-20&linkCode=as2&camp=1789&creative=390957&creativeASIN=B0015T963C
 [12]: http://ajaxian.com/archives/javascript-epub-readers