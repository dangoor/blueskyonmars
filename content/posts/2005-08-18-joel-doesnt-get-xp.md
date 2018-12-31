---
title: Joel doesn’t “get” XP
author: Kevin Dangoor
type: post
date: 2005-08-18T11:54:41+00:00
url: /2005/08/18/joel-doesnt-get-xp/
keywords:
  - project management
categories:
  - Software Development

---
Understand up front that I&#8217;m not saying that Joel is wrong about how _he_ develops software. Joel&#8217;s comment in [The Project Aardvark Spec][1] about extreme programming doesn&#8217;t seem to fully appreciate what goes on (or is supposed to go on) in an XP project. 

> As I worked through the screens that would be needed to allow either party to initiate the process, I realized that Aardvark would be just as useful, and radically simpler, if the helper was required to start the whole process. Making this change in the spec took an hour or two. If we had made this change in code, it would have added weeks to the schedule.

Joel is confusing XP with the ad hoc &#8220;just dive in and code &#8217;til it&#8217;s done&#8221; methodology. He uses the statement above to support Big Design Up Front vs. XP. But, this implies that an XP project would have gone and implemented _the whole thing_ before someone finally slapped themselves on the forehead and said &#8220;D&#8217;oh! We should&#8217;ve just made the helper start the process!&#8221; Let&#8217;s take a look at how a real XP project might have addressed this:

  1. There _is_ up front work in the form of story cards. It&#8217;s entirely possible that in creating and estimating the story cards at the beginning of the process, &#8220;helper initiates process&#8221; and &#8220;victim initiates process&#8221; may have been two separate cards. They may have _had_ to be two separate cards, since a given story can&#8217;t be longer than an iteration. Given that, the &#8220;victim initiates process&#8221; story just might never have been scheduled in the first place.
  2. Particularly if there are UI questions, it is not unreasonable in an XP project to put some effort into UI mockups in the first iteration. At this point &#8220;victim initiates&#8221; may suddenly start looking very clumsy, causing the story to get dropped.
  3. Let&#8217;s say that the problem was not in the UI, but how the code needs to work in order for the victim to initiate. When going through the story cards at the initial estimation session, one of the programmers might have thought of a potentially tricky aspect of &#8220;victim initiates&#8221;. If that&#8217;s the case, they might get a new card written for a &#8220;spike&#8221;, which is a brief experiment to test out the potentailly problematic area.
  4. Assuming that &#8220;victim initiates&#8221; made it all the way through the steps above. It gets scheduled and worked on. Odds are good that the programmers would notice that something&#8217;s up mid-iteration. It _is_ legal to change things mid-iteration, if new information arises. Worst case scenario: they go the whole iteration (2 weeks, usually) working on that story before it gets ditched at the next planning session.
XP is _not_ dive in and code. The whole point of XP is written on the cover of Kent Beck&#8217;s book: &#8220;Embrace Change&#8221;. At the beginning of Joel&#8217;s Project Aardvark spec, he mentions that the spec is not cast in stone. The problem with many Big Design Up Front (BDUF) projects is not that a spec is written&#8230; the problem with many projects is that the spec _is_ cast in stone and requires an elaborate &#8220;Change Request&#8221; procedure to alter the spec.

Before you call me an XP lunatic: I don&#8217;t think XP is the be-all and end-all development methodology. Different projects need different processes. To me, the biggest thing to come out of XP is not the XP process, but Test Driven Development, which I consider a good thing regardless of how the project itself is planned and run.</ol>

 [1]: http://www.joelonsoftware.com/articles/AardvarkSpec.html