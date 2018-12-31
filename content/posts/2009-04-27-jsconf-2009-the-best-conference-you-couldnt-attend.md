---
title: 'JSConf 2009: the best conference you couldn’t attend!'
author: Kevin Dangoor
type: post
date: 2009-04-27T18:17:06+00:00
url: /2009/04/27/jsconf-2009-the-best-conference-you-couldnt-attend/
categories:
  - JavaScript
tags:
  - jsconf

---
(sorry for the lack of links in here. I wrote this on a plane and haven&#8217;t had a chance to do anything else to it&#8230;)

I just returned from JSConf 2009, the first JSConf conference. It was possibly even the first conference to feature JavaScript as a general scripting language in the same vein as Python or Ruby.

Overall, it was a very good conference. The organizers did a terrific job and paid great attention to detail. The sponsored evening events were an awesome idea and well-executed. (At least, Friday night&#8217;s was, I flew home Saturday evening). It was a relatively small conference at 130 people. I think they can easily have double that number next year, if they want to. But, that would require a change of venue, because the Hotel Palomar&#8217;s meeting rooms were filled almost to overflowing. From talking with Chris Williams on Friday evening, it doesn&#8217;t sound like they&#8217;re interested in changing venues next year, which is a shame because a lot of people will have to miss out on a great conference.

Francisco Tolmasky from 280 North gave the perfect kind of talk to kick things off. I&#8217;ve been following Cappucino&#8217;s development, so I was not surprised in the least with what I saw. But, Francisco is a polished speaker and many people had not seen Apple&#8217;s Interface Builder used to create webapps (via Cappucino&#8217;s nib2cib tool). We didn&#8217;t get a demo of Atlas, which would certainly have wowed this audience.

One thing that pleased a great many people in the audience, myself included, was word that Safari&#8217;s debugger would start looking at a &#8220;displayName&#8221; on functions to determine what name to show in the debugger/profiler. JavaScript has many places where it&#8217;s impossible to guess a reasonable name, and it&#8217;s nice to have a way to give the debugger a hint like this. Let&#8217;s hope we get this in Firebug soon.

Toward the end of the second day, there was a talk about SproutCore, so we had a chance to two different ways to apply the style of Apple&#8217;s Cocoa to building webapps. As with anything, there are tradeoffs. Cappucino builds on Objective-J, which gives you a more concise syntax than straight JavaScript for things like Key Value Observing. If JavaScript today had getters and setters, then this particular benefit of Objective J would go away. For now, though, using SproutCore effectively means calling get\* and set\* methods to get variable values rather than just looking up the value directly.

There were two presentations on server side JavaScript, a topic that people who know me know that I am currently very into. Nick Campbell showed off the Axiom Stack, which builds on Helma. Axiom is presently AGPL-licensed, which means I won&#8217;t go anywhere near it. But, that&#8217;s just me. On the plus side, Nick has been peripherally following the activity on ServerJS and is quite in tune with our goals. Nick&#8217;s company, by the way, has a unique and useful sounding web marketing-related product coming out soon, so keep an eye on those folks if you&#8217;re a marketer.

The second Track A presentation about server side JS was James Duncan&#8217;s presentation about Joyent&#8217;s Smart platform. I must say that this looks like an excellent offering, and I&#8217;m looking forward to seeing a lot more of it as it hits general availability. The best parallel I can draw is &#8220;App Engine on JavaScript&#8221;, but that doesn&#8217;t really do it justice. They have a key-value store that they will scale transparently for you. No more manual sharding! Just start tossing data in. Of course, that&#8217;s the promise&#8230; and the devil&#8217;s in the details with such things. I came in a bit late to James&#8217; presentation and I forgot to ask him afterwards about their data store&#8217;s indexing capabilities and whether it is eventual-consistency based or more immediate than that.

The Smart platform is SpiderMonkey-based, and they pull some interesting tricks to overcome the lack of a decent stack of libraries for SpiderMonkey. Their web server interface looked very much like Jack, which is a bonus. It would be nice if we can harmonize it with Jack in some fashion. Intriguingly, their web framework, which is apparently based on Sinatra, looks an awful lot like the home grown one that I made for Bespin in Python and then duplicated in JavaScript.

I didn&#8217;t lump my former SitePen colleague Kris Zyp&#8217;s talk in with the other server side JS talks, because Kris was talking a lot more about JS that spans from client to server and using standards such as JSON Path, JSON Query, Persistent JS, and JSON object referencing to move data around seamlessly. Of course, he used Dojo and Persevere as his demo platform, but the ideas he presented can be applied anywhere.

Brian LaRoux&#8217;s talk on PhoneGap was quite interesting and entertaining. Brian&#8217;s talk had a refreshing lack of gravity, while still providing useful content. For one, he mentioned that Dashcode actually offers good tools for making iPhone web apps. He talked about a variety of iPhone-related JS toolkits, and gave a demo of Nitobi&#8217;s iPhone &#8220;stimulator&#8221; which does a better job of representing how an iPhone app will behave than Apple&#8217;s own simulator.

I should note that there were probably 50% fewer bullet points than what I have seen at some other tech conferences I&#8217;ve been to. I think the message is sinking in that bullet points suck (except for actual lists of things).

My Mozilla colleague, John Resig gave a wide-ranging talk about JavaScript performance testing, games and his project of the moment, TestSwarm. TestSwarm looks fantastic and fills a gap: it will provide a way to do cross-browser continuous integration tests. People join the test swarm by opening their browser up to the TestSwarm page, and the server will send them test jobs as they come in. So, for example, a revision gets checked into jQuery, and the TestSwarm server will pull out the tests and send them down the wire to a collection of testers who are using different browsers. The results from all of the browsers will come back and get logged. This tool will be useful for a lot more than just jQuery, and John offered help connecting it up with, say, DOH for Dojo&#8217;s tests.

Another former SitePen colleague, Pete Higgins gave a Dojo roundup at the very end of the conference. I saw half of his talk before I had to go to the airport. There are lots of good things afoot in Dojo-land. The new conditional compilation stuff seems useful for a variety of things. For example, Dojo can be built in a super-slim variety (6K) that loads everything dynamically. Or you can dump all of the IE compatibility stuff. With the Bespin project, we have a plan to ship a variety of packagings, and I can see this being useful for that as well.

Pete&#8217;s Plugd (which he pronounces &#8220;plug-dee&#8221; as opposed to &#8220;plugged&#8221;) project provides a bunch of extra convenient ways to use Dojo and I do hope to see that stuff included in 1.4. Pete says that Plugd will likely add 4K to Dojo&#8217;s gzipped size, but I think it&#8217;s likely worth it.

Malte Ubi likely takes the prize for JSConf attendee who came the longest distance to attend, having flown in all the way from Hamburg, Germany. Malte has been doing some fantastic work on Bespin. Actually, the things he&#8217;s been doing go beyond the realm of fantastic and into &#8220;crazy&#8221;: using Narcissus (JavaScript parser in JavaScript) to read your JavaScript file in a web worker to provide completely client-based outline views and code completion. Awesome.

Malte did a Track B talk on Joose, his JS object system that is built on ideas from Perl&#8217;s Moose. It looks like a very powerful system that provides things like type coercion and traits (called roles here) that you don&#8217;t find in the type systems that typically come with JS toolkits. If I recall correctly, Joose weighs in at about 16K gzipped, so it&#8217;s not a small package.

Nick Carter gave a Track B talk on his JS ORM, JazzRecord It&#8217;s a direct descendant of Rails&#8217; ActiveRecord. It looks like a nice enough package, but seeing his samples made me that much more convinced that Atul is right: SQL does not belong in the browser. The sqlite storage engine may very well, but SQL itself does not. TaffyDB, dojo.data, CouchDB, whatever&#8230; just as long as the principal form of expression, persistence and querying is JS. The needs of a typical web client are very different from the kinds of things to which we apply SQL on the server. And, even then, people are starting to realize that SQL is not the best tool for every job.

I spoke on Track B about ServerJS. I called the session &#8220;a standard library for JavaScript in non-browser contexts&#8221;, or something catchy like that, because it is clear that what we&#8217;re building applies just as much to command line tools and other kinds of non-browser programs as it does to the server side of web apps.

My talk came immediately after James Duncan spoke about dynamic loading of C code into a SpiderMonkey environment. I lamely brought up ctypes as one approach, but dynamic loading of binaries is not my strength. I suggested that James would get useful feedback for his idea on the ServerJS list, given the number of people who are linking C/C++ libraries up with SpiderMonkey and v8.

As for ServerJS itself, I spoke about the project in general and our biggest milestone to date: the &#8220;SecurableModule&#8221;. I had a simple &#8220;math.js&#8221; module with a fibonacci function in it. I picked a lovely O(n^2) function to show the performance difference between Rhino and v8 which is considerable. Since math.js is a &#8220;pure JavaScript&#8221; module, I was able to demo that module being loaded into: Narwhal on Rhino, Narwhal on k7, Persevere, Helma NG (as a Jack app, no less) and GPSEE. I also demonstrated how with Narwhal/Rhino, I could &#8220;forget&#8221; to put a &#8220;var&#8221; in and my variable would not suddenly leak into the global namespace.

I also mentioned that we&#8217;re working on binary objects and files and that Jack (the interface) has good prospects given how proven the technique is in Python and Ruby.

I hope that at JSConf 2010, we&#8217;ll be able to see some significant apps built on a fairly complete platform.

Conference co-organizer Chris Williams thanked me for my endorsement of the conference, saying that I pushed Mozilla over the edge on sponsoring the conference. I had no idea I had such pull :). Anyhow, Mozilla&#8217;s sponsorship apparently had a direct impact on the conference food, which was quite beyond typical conference fare. Thanks to whomever it was at Mozilla who gave the a-ok on this.

As with any conference, the hallway track is among the most important, and I had a good time meeting new people and talking about a range of things. Community-driven conferences do bring in a good collection of people to meet.

I am doubtless leaving people out of this roundup, and I apologize for that. I am sure there are some other JSConf roundups that will provide additional insight. Also, the videos will be showing up online over time, so keep an eye out for that.