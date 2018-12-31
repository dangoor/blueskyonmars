---
title: Side Effects vs. Promises
author: Kevin Dangoor
type: post
date: 2015-10-02T01:47:11+00:00
url: /2015/10/01/side-effects-vs-promises/
categories:
  - JavaScript
  - Software Development

---
This past weekend, I saw Chris Armstrong ([@radix][1]) talk about [Side Effects as Public API][2]. From the description on the [Strange Loop page for the talk][3]:

> Haskellers have been isolating their side-effects from their pure code for decades, but most people write code in languages that allow ad hoc side-effects anywhere. In a lot of cases, these side-effects are practically a part of the public API &#8212; they put restrictions the way the code can be used, often obscurely, and have effects that are observable to the caller. It helps a lot to acknowledge this and explicitly treat them as a part of your public API. Here are the basic ideas that I&#8217;ll cover:
> 
>   * represent your side-effects as &#8220;intents to perform an action&#8221; &#8212; transparent objects that expose the details of the side-effect, without actually performing it
>   * combine effects with pure code to describe the execution order and data dependencies (yes, like a monad)
>   * write unit tests for your code without mocking, by specifying the expected content, results, and order of side-effects performed by a function

Chris has made a Python library called [Effect][4] that implements the ideas he was presenting.

In JavaScript-land, we&#8217;ve embraced the idea of promises now to the point that they&#8217;re a [standard part of the language][5], already implemented in multiple browsers (about [66% of those in use][6]!) and in Node. Promises can clean up your asynchronous code and if you&#8217;re not familiar with them, you should go read one of the many tutorials about them.

A promise is a placeholder for a value to come along at some point in the future. Using the `then` method on the `Promise`, you can pass in a function to be called when the value is ready. Here&#8217;s a hypothetical example:

<pre><code class="javascript">function getItemOne() {
    let promise = get("http://foo.barbaz/api/item/1").then((value) =&gt; {
        // Do something with the result
    }, (error) =&gt; {
        // Do something with the error
    });
    return promise;
}
</code></pre>

This example above is not very different from the use of callbacks and isn&#8217;t intended to show off the nice attributes of promises. It _is_ a good example to illustrate the use of an `Effect` rather than a `Promise`.

The first thing I&#8217;ll note is that `getItemOne` is not a pure function. Calling it produces a side effect: an HTTP request. Testing this function, or any function that calls it, is difficult because of that impurity. The usual solution for testing something like this is to replace `get` with a mock function. That doesn&#8217;t really fix the impurity of the function, but it at least makes it testable.

We can make `getItemOne` pure by making a small change like this:

<pre><code class="javascript">function getItemOne() {
    return new SideEffect({
        type: "http-get",
        url: "http://foo.barbaz/api/item/1"
    }).on((value) =&gt; {
        // Do something with the result
    }, (error) =&gt; {
        // Do something with the error
    });
}
</code></pre>

I&#8217;m not suggesting that we&#8217;d _use_ the API above, because I think we can do better than that. In fact, this version could look the same as the previous version, if we wanted it to. But, I wanted to clearly show the difference between promises and the side effects about which I&#8217;m writing.

The function above is pure. Every time you call it, it will return exactly the same value. Calling this from a test is easy and you can verify that the side effect returned matches your expectations. You can also pass in values to test what happens in the success or failure cases, which would also be pure functions.

In a real system, somewhere up the call chain there will be a dispatcher called to actually process the side effect. The Python Effect library points out that this approach allows you to easily swap out how any given side effect is processed.

I asked Chris if he knew of any JS implementations of Effect. He wasn&#8217;t aware of any, but he pointed out that it&#8217;s basically just the IO monad. Here&#8217;s an [implementation of the IO monad in JS][7]. If you look at the Python [Effect library][4] and its [examples][8], though, I think there&#8217;s a need for a JS library that fits in better with the overall JS ecosystem (test runners and whatnot).

In practice, returning side effects rather than performing them and returning promises can increase the size of the [&#8220;functional core&#8221;][9] of your application, which is a win in my book.

 [1]: https://twitter.com/radix
 [2]: https://www.youtube.com/watch?v=D37dc9EoFus
 [3]: http://www.thestrangeloop.com/2015/side-effects-are-a-public-api.html
 [4]: https://github.com/python-effect/effect
 [5]: https://medium.com/ecmascript-2015/es6-promises-9ca8d8b4aca6
 [6]: http://caniuse.com/#search=promise
 [7]: http://cwmyers.github.io/monet.js/#io
 [8]: https://github.com/python-effect/effect-examples
 [9]: https://www.destroyallsoftware.com/talks/boundaries