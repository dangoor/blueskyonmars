---
title: 'Go: reasonably high level programming, but with performance'
author: Kevin Dangoor
type: post
date: 2009-11-11T15:37:13+00:00
url: /2009/11/11/go-reasonably-high-level-programming-but-with-performance/
categories:
  - Software Development

---
I&#8217;ve always thought that it should be possible to design a language that is both usable and performant. JavaScript performance has improved tremendously, but it is still quite a distance behind C and even Java. Of course, programmer productivity is certainly more important than raw performance for most applications. It&#8217;s only as you try to scale up services that you really wish you could squeeze out more performance. In fact, being able to squeeze out more performance is one way to avoid the complexity shift of moving from one box to two/many. Of course, there&#8217;s always an upperbound to this, but that upperbound can be remarkably high.

I always thought that [D][1] looked like the language that could unify high level programming and performance. But D has failed to catch on and seems to be in a state that would [make anyone seriously question using the language for real work][2].

Now, along comes [Go][3], a new language sponsored by Google. More interesting than the Google part, is that Go was created by people with a long history dating back to the origins of Unix (Rob Pike, Ken Thomson, apparently even Brian Kernighan are involved). The language is designed to support super fast compilation (yay for programmer ergonomics!) and C-like performance. Importantly, the language also has built in features to help support [scalable and safe concurrent programming][4], via &#8220;channels&#8221; for passing data back and forth, rather than something like transactional memory.

Go has a [simplified object model][5] that looks cool, but I&#8217;d be curious to see how it feels to use in practice. Go [_doesn&#8217;t_ have exceptions][6], which seems like a real drag to me. Apparently, exceptions are still considered an open issue and they present thorny issues when you&#8217;re dealing with concurrent processes.

Go&#8217;s [standard library][7] looks to have a decent collection of features, and [you can call C code pretty easily][8]. More care needs to be taken if you want C code to call into Go. If Go can get its packaging story together [more quickly than Python has][9], it may indeed start having appeal as a high-level, fast, concurrent programming language.

It&#8217;s still very early for Go. It&#8217;s not used in production in Google yet. [It doesn&#8217;t run on Windows][10]. But it has arrived on the scene hitting many points at the &#8220;good enough&#8221; level (fast compiler, decent library, ok interface to C, decent docs). Google has full-time staff assigned to it, and they&#8217;re even [hiring a program manager][11]. With [speculation that Google doesn&#8217;t want to use Python for their high volume services][12], I wouldn&#8217;t be surprised to hear that Google really _wants_ to use Go internally. With an &#8220;anchor tenant&#8221; like Google, Go has a lot more potential than D ever had.

Now they just need to deal with the [pesky issue of the name][13].

 [1]: http://www.digitalmars.com/d/
 [2]: http://www.jfbillingsley.com/blog/?p=53
 [3]: http://golang.org/
 [4]: http://golang.org/doc/go_tutorial.html#tmp_331
 [5]: http://golang.org/doc/go_lang_faq.html#inheritance
 [6]: http://golang.org/doc/go_lang_faq.html#exceptions
 [7]: http://golang.org/pkg/
 [8]: http://code.google.com/p/go/source/browse/misc/cgo/gmp/gmp.go?r=release
 [9]: http://article.gmane.org/gmane.comp.python.distutils.devel/11359
 [10]: http://groups.google.com/group/golang-nuts/browse_thread/thread/0a1dfa6724a326c3#
 [11]: http://wordpress.chanezon.com/?p=1203
 [12]: http://groups.google.com/group/unladen-swallow/browse_thread/thread/4edbc406f544643e
 [13]: http://code.google.com/p/go/issues/detail?id=9