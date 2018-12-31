---
title: 'CodeMash 2008 brain dump (summary: you should come in 2009!)'
author: Kevin Dangoor
type: post
date: 2008-01-15T19:04:19+00:00
url: /2008/01/15/codemash-2008-brain-dump-summary-you-should-come-in-2009/
categories:
  - Software Development

---
<img src="file:///Users/admin/Library/Application%20Support/ecto3/cache/6D48561F-E41D-4C33-8751-CCDF09F9B20F.jpeg" width="139" height="174" style="margin-left: 10px; padding-left: 10px; float: right;" name="6D48561F-E41D-4C33-8751-CCDF09F9B20F.jpeg" />

I spoke at [CodeMash][1] for a second year in a row. I think this year&#8217;s conference was even better than last year&#8217;s, particularly for me because I was only able to attend for one day last year. It&#8217;s a shame that CodeMash has such regional attendance, because where else do you find a conference with talks on C#, LINQ, Silverlight, Python (3 talks!), Rails, Dojo, Concurrency in Java and more?

It might seem like such a broad range of topics dilutes the conference, but it&#8217;s really cool because it gives you a chance to gain exposure to things you wouldn&#8217;t normally encounter. There are a lot of interesting things going on in the Microsoft world, but I don&#8217;t normally encounter those since I travel mostly in the &#8220;open source&#8221; world.

The only thing that keeps CodeMash regional, I believe, is that it&#8217;s in Sandusky, Ohio. There&#8217;s nothing wrong with a cool conference in the midwest, but Sandusky is just not very easy to get to from most places. The biggest nearby airport would be in Cleveland, and that&#8217;s not a huge airport and is probably an hour away from the conference.

For me, personally, the location is nice. The [Kalahari][2] resort is nicely done and the waterpark is fun, and the drive is only 2 hours for me. But, this location will definitely skew the crowd to a midwest one.

## Concurrency

The best talk I attended, not counting open spaces, was [Brian Goetz&#8217;s][3] talk about concurrency. Brian works for Sun and knows his concurrency (he&#8217;s a co-author of [&#8220;Java Concurrency in Practice&#8221;)][4]. Concurrency is becoming an increasingly hot topic, as it&#8217;s common now for machines to have two or more CPU cores. He used Java as a backdrop and had a great example of how threads are hard. What made the example perfect was its simplicity: an object representing a bank account that had only three methods.

Fairly quickly, you come to the conclusion that shared state is hard to handle well concurrently. This is part of the reason that Python&#8217;s creator, [Guido van Rossum][5], has [favored using multiple processes for concurrency][6]. Some promising approaches to concurrency mentioned by Brian:

  1. [Software transactional memory][7]. It sounds like a silver bullet, for people who like the threaded model, but it&#8217;s still very much a research project. The idea is that you can declare that an operation is atomic and if two atomic operations try to manipulate the same data, one will fail. This is an optimistic kind of concurrency, because you don&#8217;t actively lock the data. You just assume everything will work out okay and deal with it if it doesn&#8217;t.
  2. [Erlang&#8217;s][8] [Actor][9] model has proven to be quite a successful way for doing many things concurrently. However, Erlang is a functional programming language that doesn&#8217;t have many of the language features that people today are used to (like, say, class-based OO).
  3. [Scala][10] includes an [Actor][11] library modeled after Erlang&#8217;s. It combines functional and OO styles and provides access to the Java libraries. If you write programs in Scala&#8217;s Actor style, you can get excellent, reliable concurrency&#8230; you just have to be careful about Java code that you import

Brian also pointed out that you can improve your concurrency picture in Java by [making your objects immutable][12]. If operations that change the object return new copies of the object instead of mutating in place, your code is much more concurrency friendly. Unfortunately, you&#8217;ll still need to watch out for libraries that other people created.

## Software Engineering

The conference-opening keynote was [Neal Ford&#8217;s][13] talk about Software Engineering and Polyglot Programming. He talked about software development as an engineering discipline and said that, compared to things like bridge building, we&#8217;re still in the very early days. In the early days of any engineering, you need to do a lot of testing to see if what you&#8217;re doing is actually working, and that&#8217;s the stage we&#8217;re at with software. In other words, write tests for your code if you want to consider yourself a software &#8220;engineer&#8221;.

I&#8217;ve been a test-driven development fan for a while, and I definitely agree with Neal on the importance of testing.

The other aspect of Neal&#8217;s talk, polyglot programming, was all about using different languages for different tasks. We already do (HTML, CSS, JavaScript, Python and SQL is one possible stack of languages). Languages that fit the task can save us a lot of effort. I am a fan of DSLs and declarative programming styles, so this all resonated with me as well.

Neal framed a few of his examples as &#8220;static typing vs. dynamic typing&#8221;, using Java examples to represent the &#8220;static&#8221; side of things. I really dislike when the &#8220;static vs. dynamic&#8221; debate has more to do with Java&#8217;s painful syntax than differences in typing. If you want to frame a discussion around &#8220;static vs. dynamic typing&#8221;, use a language like Scala or even C# that has type inference, operator overloading, etc. so that the statically typed examples aren&#8217;t bloated messes.

## Other Talks

I attended a couple other formal talks, but I don&#8217;t really have much to say about them.

Something I did learn from the [Hobo][14] talk is the idea of using small (say, 30 seconds), soundless screencasts for doing demos. You embed the screencast directly in your Keynote presentation. It&#8217;s a way to do a demo where you know everything will work, you don&#8217;t need internet access, and people can see how things run. The only drawback is that the demo is fixed and you can&#8217;t change it based on realtime audience feedback. For some demos, this is a good technique that I&#8217;ll try to keep in mind.

## Open Spaces

Running in parallel to the formal talks, there were o[pen space sessions][15]. Anyone can post a topic and claim a room and people can join a discussion about something. As [Bruce Eckel][16] pointed out at the beginning of the conference, open spaces are awesome because they give you something you can&#8217;t have from your own home: a real conversation with other interesting people. You can view a presentation remotely, but having a real talk about something works much better with physical proximity.

Next year, there may be more emphasis on the open spaces. This year, I thought there was too much competition in each time slot (my introduction to Dojo was up against 5 other formal talks plus who knows how many open spaces sessions). I don&#8217;t think it&#8217;s good to have so many parallel tracks in a conference with 350 attendees. I think the CodeMash organizers are considering some alternative time slot layouts for next year.

## Non-Relational Databases

I hosted two open spaces sessions. The first was about non-relational databases. We discussed when you might consider using a non-relational DB and many of the available options. [CouchDB][17] has gotten a lot of press, but [Persevere][18] seems more &#8220;done&#8221;. We talked a bit about [tuplespaces][19] and [Gigaspaces][20]. The [ZODB][21] is a nice option for Python programmers, though I still long for a ZODB storage that doesn&#8217;t require packing. Amazon has [SimpleDB][22]. There&#8217;s also [MonetDB][23], a column-oriented database. We did also talk a bit about OR mapping, though the focus of the discussion was alternative database technologies.

The mismatch between the kinds of problems we&#8217;re solving and the kinds of development tools we use (largely OO languages today) make other kinds of databases an interesting line of experimentation. Some are ready for prime time use (the ZODB has been used in production environments for a decade), but you have to figure out which problems you&#8217;re trying to solve.

## The Next Big Language

The second open space session I hosted was about the next big language after Java. This is a topic I&#8217;ve been thinking about a fair bit lately, and I have a lot more to say on the subject. The discussion was fun and interesting.

## Python Web Frameworks

[Mark Ramm][24] hosted a Python Web Frameworks open spaces discussion. We talked about things people wanted to see, and we were fortunate to have a couple of Ruby people in the session to bring their perspective in. This was also good timing for Mark, who led an international TurboGears 2 sprint this past weekend.

## The Experts Zone

A new feature at CodeMash 2008 was the &#8220;Experts Zone&#8221;, where the speakers can be found to discuss things in more depth. I didn&#8217;t see a whole lot of activity in the room, and I think that&#8217;s partly because it was one more thing in competition with the talks that were lined up. The schedule for the Experts Zone was also tucked away in the back of the program.

That said, [Dick Wal][25]l had no trouble attracting people to his Experts Zone session where he was showing off [Android][26] tools a bit.

## Software Documentation Tools

During my time in the Experts Zone, I ended up in a conversation with Bruce Eckel and Mark Ramm about programming tool documentation. There are competing needs for nice formatting, code samples that can be run by the reader and code samples that actually <span style="font-style: italic;">work</span>.

Bruce writes his books in Microsoft Word, because he likes to be able to work on the document with all formatting intact. He uses a text editor initially on his code samples, but then copies the code into Word. Word is the authoritative source for the code in his books.

The magic here is that he&#8217;s got a Python script that uses COM to tell Word to export the document as text. Then, it rips through the text file, extracts the code samples, compiles them and tests them.

This seems like a good way to go when your primary output is the printed form. You get complete formatting capability, tables of contents and indices, and it&#8217;s easy to insert pictures and make everything look perfect. This might be even easier to implement with Apple&#8217;s Pages, since Pages documents are actually stored in XML (which I&#8217;m guessing is more readable than that of Word).

I wonder if the same can be applied to Keynote presentations?

Mark told us about another way to go that is more &#8220;open source compatible&#8221;. [Mike Bayer][27] put together tools for [SQLAlchemy][28] that let him write his docs in [Markdown][29] and have his code automatically colorized and executed to generate the SQL, which is also placed into the final HTML document.

This setup seems ideal for producing high-quality docs like the kind that SQLAlchemy has. You could easily support multiple languages and provide ways to handle setup and teardown code for tests. Some people really go for doctest, but I&#8217;d like the ability to have more code that does not necessarily appear in the final output.

## Getting Flushed

This year, I actually got to spend a little time in the waterpark at the Kalahari. That was a lot of fun! The place was much bigger than I expected, and there were slides that others reported as being new this year.

My favorite was a slide where you slide down on a 4 person raft. The raft goes down a surprisingly steep hill and into what can best be described as a toilet bowl. That thing was probably 50 feet in diameter. You go sliding around it once and then there&#8217;s a big spray of water that drenches you, slows the raft down and guides you into a tunnel down to the pool below. I rode on that one with Bruce Eckel, Mark Ramm and Dick Wall while [James Ward][30] graciously stood off to the side taking pictures.

Of course, James didn&#8217;t just walk back down the stairs after taking pictures. He went down the one person version of that toilet bowl&#8230; I found that one a bit more disturbing. You start off in a completely dark tunnel before coming out into the bowl which just has a big hole in the middle. Gravity seems to want to pull you head first into the hole (I steered myself to fall a bit more sideways through the hole), and then you plunge into the pool below.

I also rode on that 4 person one with [David Stanek][31] and the other guys from [American Greetings][32]. We probably rode that one four times.

The other slides were fun as well&#8230; just avoid the waterpark if you&#8217;re afraid of the dark. Most of the slides have you in almost total darkness for much of the ride.

## My Talks

Oh yeah, I had two talks this year: an intro to Dojo and another about Dojo Offline. The talks seemed well-received (we&#8217;ll find out when the evaluations come in!), but the crowds were relatively small given the serious competition for interest that existed in every timeslot.

## Conclusion

CodeMash is a fantastic conference for people wanting to get together with other geeks who care about the craft. The organizers have already declared that CodeMash 2009 is a go, so start planning your trip to Sandusky for January 2009!

<div class="posttagsblock">
  <a href="http://technorati.com/tag/codemash" rel="tag">codemash</a>
</div>

 [1]: http://codemash.org
 [2]: http://kalahariresort.com/hub/
 [3]: http://www.briangoetz.com/
 [4]: http://www.amazon.com/gp/redirect.html%3FASIN=0321349601%26tag=blueskyonmars-20%26lcode=xm2%26cID=2025%26ccmID=165953%26location=/o/ASIN/0321349601%253FSubscriptionId=0PZ7TM66EXQCXFVTMTR2
 [5]: http://www.artima.com/weblogs/index.jsp?blogger=guido
 [6]: http://mail.python.org/pipermail/python-3000/2007-May/007414.html
 [7]: http://en.wikipedia.org/wiki/Transactional_memory
 [8]: http://erlang.org/
 [9]: http://tunes.org/wiki/actor.html
 [10]: http://www.scala-lang.org/
 [11]: http://lamp.epfl.ch/~phaller/actors.html
 [12]: http://java.sun.com/docs/books/tutorial/essential/concurrency/imstrat.html
 [13]: http://www.nealford.com/
 [14]: http://hobocentral.net/
 [15]: http://en.wikipedia.org/wiki/Open_Space_Technology
 [16]: http://www.artima.com/weblogs/index.jsp?blogger=beckel
 [17]: http://couchdb.org/
 [18]: http://code.google.com/p/persevere-framework/
 [19]: http://en.wikipedia.org/wiki/Tuple_space
 [20]: http://www.gigaspaces.com/index.html
 [21]: https://launchpad.net/zodb
 [22]: http://aws.amazon.com/simpledb
 [23]: http://monetdb.cwi.nl/
 [24]: http://compoundthinking.com/blog/
 [25]: http://dickwallsblog.blogspot.com/
 [26]: http://code.google.com/android/
 [27]: http://techspot.zzzeek.org/
 [28]: http://www.sqlalchemy.org/
 [29]: http://daringfireball.net/projects/markdown/
 [30]: http://www.jamesward.org/wordpress/
 [31]: http://www.traceback.org/
 [32]: http://www.aginteractive.com/