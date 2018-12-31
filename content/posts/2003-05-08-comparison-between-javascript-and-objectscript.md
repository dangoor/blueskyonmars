---
title: Comparison between JavaScript and ObjectScript
author: Kevin Dangoor
type: post
date: 2003-05-08T22:26:18+00:00
url: /2003/05/08/comparison-between-javascript-and-objectscript/
categories:
  - Technology

---
This is a comparison of [Rhino JavaScript][1] and [ObjectScript][2]. Since both languages offer a Java-like syntax and reasonable compiled performance, the details of the language will ultimately break the tie.

The solution in boldface is, in my opinion, the winner on that topic.

  * **Both** have functions as first class objects and allow for true closures
  * **Both** are dynamically typed
  * **ObjectScript** provides lexically scoped variables, which is what we&#8217;re used to from Java, etc. JS provides variables that are either global or scoped within a function (they are not scoped within local statements)
  * **Both** allow for polymorphic use of &#8220;+&#8221;: &#8220;Foo&#8221; + 3 = &#8220;Foo3&#8221;
  * **JS** provides a syntax for using an expression to look up a property (field): x[s], where s is the expression. So, x[&#8216;hello&#8217;] is equivalent to x.hello
  * **JS** has a bunch of array handling functions: sort, splice, slice, concat, join, push, pop, shift, unshift. These are familiar to perl programmers and handy. ObjectScript does not mention these functions but does provide a convenience syntax for array slicing: var a = (1, 2.0, &#8220;c&#8221;); a[1..2] => (2.0, &#8220;c&#8221;). This syntax also works for strings, which is really nice.
  * **Both** define objects as functions. JS provides a _this_ variable to define the object that is being operated on. ObjectScript just assumes that you&#8217;re working with variables in the scope of your object.
  * **ObjectScript** provides inheritance through an &#8220;extends&#8221; keyword, much like Java. JS uses a somewhat strange &#8220;prototype&#8221; construct. You set object.prototype equal to the function that you&#8217;re inheriting from, and that will be searched for any properties that are not defined within the object itself.
  * **Both** provide straightforward mechanisms for extending Java classes
  * **JS** with LiveConnect 3 automatically coverts Java Arrays and Strings to the JS equivalents. Example:
  
    > s = new java.lang.String(&#8220;foo&#8221;)
        
    > s = s + &#8220;&#8221;; // s is now a JS string
        
    > s.match(&#8220;oo&#8221;) 

  * **JS** is well-documented in books, because it is widely used. Most books, however, cover JavaScript usage in web browsers. However, the language itself is well-covered because it is a standard. There are formal language definitions and [some articles][3] that cover the language design

The [proposed JavaScript 2.0 language][4] aims to provide greater power for creating large applications with JavaScript and better interoperability with Java. It adds a more disciplined class syntax with versioning, a package system, optional types and type-checking, conditional compilation and access controls. JS 2.0 adds a strict mode which adds a few rules that are not onerous but clean up the language a bit (and adds lexical scoping, instead of the odd function scoping that exists in JS1.5).

**Conclusion**

ObjectScript and JavaScript have very similar language features. I would give the win to JavaScript for its easy hashtable (associative array) syntax, and useful collection of array functions. Rhino JavaScript (ECMAScript) is a commonly-used, well-supported, well-documented tool. The JavaScript 2.0 future offers some nice features. Plus, the ability to use the same language on the server side that we may use on the browser is a plus. Add decent performance to all of this, and you end up with JavaScript being a solid choice.

 [1]: http://www.mozilla.org/rhino
 [2]: http://objectscript.sf.net
 [3]: http://www.mozilla.org/js/language/evolvingJS.pdf
 [4]: http://www.mozilla.org/js/language/js20/introduction/motivation.html