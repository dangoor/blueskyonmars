---
title: Optimizing JavaScript Performance Through Custom Memory Allocation
author: Kevin Dangoor
type: post
date: 2013-08-08T13:09:11+00:00
url: /2013/08/08/optimizing-javascript-performance-through-custom-memory-allocation/
categories:
  - JavaScript

---
Mozilla&#8217;s Kannan Vijayan had an [intriguing result][1] in running SunSpider ported to C++, asm.js and Dalvik. In the &#8220;Binary Trees&#8221; test, asm.js was the fastest _by far_. Kannan&#8217;s untested theory is that it boils down to memory allocation performance:

> In asm.js, the compiled C++ is executed using a Javascript typed array as the “machine memory”. The machine memory is allocated once and then used for the entire program runtime. Calls to malloc from asm.js programs perform no syscalls. This may be the reason behind asm.js-compiled C++ doing better than native-compiled C++, but requires further investigation to confirm.

In the [Hacker News discussion][2] there were some comments there about the memory performance. duaneb said:

> Anyone who has implemented a memory allocator knows how expensive it can be. If you have a simpler algorithm that works with your data, allocate a huge chunk and manage it yourself.

Some [game developers reuse objects][3] as a way to avoid unnecessary allocations/GC. An article was just posted in Smashing Magazine about Emmet LiveStyle which [talks about how they reused objects][4] in order to save allocations.

I don&#8217;t think that selective reuse of big chunks of memory is a tool in most JavaScript developers&#8217; toolboxes right now, but it seems like a good idea in cases where you need consistent and smooth performance.

Update: Vyacheslav Egorov emailed me a link to [Kannan&#8217;s graph that includes the JavaScript engine performance][5]. In the binary tree case, the JavaScript implementation was the fastest by far. Perhaps the C++ was not well-tuned.

I don&#8217;t want to get too hung up on the benchmarks, because my main point is not &#8220;asm.js is faster than C++&#8221; (in fact, I&#8217;m not stating that at all). My point is that there ways to control memory management in JS that may be a non-obvious way to improve responsiveness.

 [1]: https://blog.mozilla.org/javascript/2013/08/01/staring-at-the-sun-dalvik-vs-spidermonkey/
 [2]: https://news.ycombinator.com/item?id=6173757
 [3]: http://blog.sklambert.com/javascript-object-pool/
 [4]: http://coding.smashingmagazine.com/2013/08/08/release-livestyle-css-live-reload/
 [5]: https://blog.mozilla.org/javascript/files/2013/08/Dalvik-vs-ASM-vs-Native-vs-JS.png
