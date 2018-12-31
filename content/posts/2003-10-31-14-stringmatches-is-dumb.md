---
title: 1.4 String.matches is dumb
author: Kevin Dangoor
type: post
date: 2003-10-31T21:46:29+00:00
url: /2003/10/31/14-stringmatches-is-dumb/
categories:
  - Software Development

---
The regex package found in Java 1.4 is a very nice thing to have available as a standard library. It also seems like a great convenience that there are methods right on [java.lang.String][1] for using regexes. The crazy thing is that with String.matches the regex is essentially turned into &#8220;^regex$&#8221;, meaning that the entire string has to match the pattern you give it.

Why on Earth would they make the only regex searching function built into java.lang.String work like _that_? Clearly, if the behavior you want is to match the entire string, you can easily type those two characters&#8230; And, rather than documenting this right there at String.matches, you have to trudge through the javadoc until you get to the top of the Matcher javadoc to discover this magic behavior.

Unlike some other nameless blog that just rants about stuff without providing any solutions, I&#8217;ve got a solution to recommend to Sun: add either the find() or lookingAt() method to java.lang.String. I&#8217;m not sure what made them think that entire string matching was the most useful behavior, but at least they can easily do something about this without breaking existing programs. In the meantime, without changing any code, they can at least add a line to the java.lang.String.matches javadoc that says 

> &#8220;Warning: this method requires the entire string to match the regular expression, as if you had typed ^regex$ even though you hadn&#8217;t. By using the pattern .\*regex.\* this will probably do what you expect. Or you can increase your chances of RSI and use Pattern.compile(regex).matcher(string).find() to do what you really want.

 [1]: http://java.sun.com/j2se/1.4.2/docs/api/java/lang/String.html#matches(java.lang.String) "String (Java 2 Platform SE v1.4.2)"