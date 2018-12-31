---
title: Why are people still afraid of JavaScript?
author: Kevin Dangoor
type: post
date: 2006-05-19T14:27:21+00:00
url: /2006/05/19/why-are-people-still-afraid-of-javascript/
categories:
  - Software Development

---
The recent introduction of the [Google Web Toolkit][1], which allows you to write your JavaScript in Java put a thought back into my conciousness: why are people going so far out of their way to avoid writing JavaScript today?

To their credit, the Google Web Toolkit provides some distinct reasons to choose it over hand-coded JavaScript: static typign (for those who like that kind of thing) and the ability to use the IDE you know and love.

And I&#8217;m certainly not opposed to encapsulating JavaScript into features that are native to your server-side toolkit&#8217;s language. Reducing the amount of code you need to write is always a good thing. (And TurboGears widgets do that very thing).

The part that I have trouble grokking is the various projects that implement Dynamic Language X (say Python or Ruby) to JavaScript conversions. Yes, JavaScript is prototype-based rather than class-based. But, otherwise it&#8217;s not a big leap to go from Python or Ruby to a language like JavaScript. Adding a layer that converts Python to JavaScript seems to me that it just introduces another place to fail, and a somewhat difficult one to troubleshoot at that since the execution environment is quite different from the environment in which you&#8217;re writing your code. If you run into problems with that conversion, you&#8217;ve got to learn the JavaScript and the JavaScript debugging tools and then also figure out what&#8217;s wrong with the translation!

For a dynamic language user, I just don&#8217;t see the benefit as being with the risk at this point.

You _should_ certainly use a JavaScript library of some sort to ease common programming tasks. JavaScript-the-language is easy enough to follow, but there are certainly inconveniences in the built-in library and pitfalls in browser compatibility which any one of a number of great toolkits will help you deal with.

This is not a rant, by the way. I&#8217;m genuinely curious to hear why people who are already using a dynamic language feel that it&#8217;s a big leap to go to JavaScript. Or, if you don&#8217;t feel it&#8217;s a big leap, what other reasons are there to use Language Foo -> JavaScript translators.

 [1]: http://code.google.com/webtoolkit/