---
title: The Brackets Scrum to Kanban Switch
author: Kevin Dangoor
type: post
date: 2014-02-18T14:51:57+00:00
url: /2014/02/18/bracketsscrumtokanban/
categories:
  - Brackets
  - Software Development

---
The Adobe Brackets team has switched its development process from Scrum to Kanban. I thought that others might be interested in why we changed the process that we use to build an [open source code editor built on web technology][1].

## From What to What?

Wikipedia has a good [article about Scrum][2]. Boiled down, it goes something like this:

  * Work is broken into timeboxed sprints (ours were 12 days)
  * A sprint planning meeting determines what work will be done during the sprint, based on estimated &#8220;points&#8221; for a story and the expected &#8220;velocity&#8221; (number of points) for the sprint
  * No one is supposed to change the work that is committed to for the sprint (we had some exceptions in practice)
  * At the end of the sprint, we had a review meeting where we showed off the completed work for the sprint
  * There would also be a retrospective meeting where we discuss how the work went and things we should do differently
  * Daily meetings would keep people in sync

Wikipedia also has an [article about Kanban][3]. Here&#8217;s a quick summary:

  * Visualize the flow of work
  * Limit the amount of work-in-progress (so that the focus is on shipping)
  * Evolve the process as needed

As you can see, Kanban is not very prescriptive. As the Wikipedia article says, you &#8220;**start with what you do now**&#8220;. I can imagine Scrum being a more comfortable starting point for people moving from a more &#8220;heavyweight&#8221; process because it gives you a clear path forward.

## Why Change?

We&#8217;ve been successfully shipping software with Scrum for a while, so it&#8217;s reasonable to ask why we would make this change. Since we&#8217;ve been holding retrospectives, couldn&#8217;t we just tweak the process along the way?

Based on our findings from our retrospectives, we did make minor tweaks to our way of doing things. But if we made too many changes, or certain kinds of changes, then we&#8217;d no longer be doing Scrum.

Here are some of the problems that we sought to fix:

### Sprint Boundaries

The end of a sprint was boring, overly exciting or both at the same time. Some sprints, everyone had to work really hard at the end to get the stories wrapped up and done. Other sprints, we might have a single engineer that&#8217;s up against the time box while everyone else is just fixing bugs and doing random other work.

It was always an _option_ to start working on the next story in the product backlog, even though it wouldn&#8217;t ship during the same sprint. But, it felt unnatural to the process to do so. Besides, we had plenty of bugs we could fix, which brings me to&#8230;

### Priorities

A sufficiently complex project with a significant number of users who have an easy way to report bugs means that a lot of bugs will be reported. As Brackets has become more popular, so has our bug tracker.

We have a process by which we prioritize bugs, but there&#8217;s still an awful lot of them. Our &#8220;medium&#8221; priority bugs are annoyances that we&#8217;d really like to fix. But there are also a lot of features that we&#8217;d really like to have.

Our process was such that bugs were counted as &#8220;overhead&#8221;. They didn&#8217;t get assigned &#8220;points&#8221; and they weren&#8217;t prioritized along with the feature work. Bugs also seemed to be the default work that someone would do when they&#8217;re not working on a story, like at the end of a sprint.

With a project like Brackets, it&#8217;s easy to argue for some features being more important than nearly all open bugs, but we didn&#8217;t put the two head-to-head that way. For example, it&#8217;s not good that [app layout is a bit laggy when you resize the window][4], but I would bet that [the ability to split the editor to show multiple files][5] will make people happier.

This could have been fixed in our Scrum process, but we likely would have had to make some changes to how we pointed stories.

### Research Stories

We&#8217;ve had a number of features that we wanted to implement but needed to learn more about before we could reasonably come up with criteria and estimates for the implementation.

Our process for this was to create a Research story card, the output of which would generally be well-defined stories to properly create the desired feature.

The trouble with this process is that the developer doing the research may wrap up the work after a few days, and then we&#8217;d have to wait until the next sprint to start working on the implementation, because you&#8217;re not allowed to change the committed stories for a sprint.

The purpose of putting the research story there in the first place is because our product owner thinks that&#8217;s a feature we need to have—in other words, to build the feature in some form. The gap between the research and the implementation felt a bit artificial.

### Estimates and Velocity

Software estimation is hard, because almost everything we do has some elements to it that are novel. For most of our stories, our estimates (in points) seemed pretty reasonable. Our typical story cards would wind up in the 2-5 point range, with most landing at 2 or 3. I think the difference between 2 and 3 was pretty fuzzy, and sometimes you&#8217;d have a 5 pointer that turned out to be quicker than a 2 pointer.

A 2 point story would pretty much consume someone for an entire sprint (12 days). A 1 point story would probably take someone a couple of days of work.

We would add these points up to determine what we can fit into a sprint, based on our expected velocity. This was successful for the most part, modulo the end of sprint situations that I talked about earlier.

Velocity itself was based on how many points we were able to complete previously. There was sprints in which this got confusing, however. For example, we had a crashing bug come up late last summer which forced us to displace some work (one of those cases where we needed to change the commitment for a sprint). It was hard to calculate the effect that crasher had on our velocity for a couple of sprints.

We could have adjusted the way we did our estimates, possibly rebooting our notion of points. Switching to Kanban, we embrace a bit of uncertainty in the estimates and use calculated averages for&#8230;

## Planning

A question that I have been asked repeatedly during this transition is around planning for specific releases or for a release that coincides with a conference or some other special event.

With Scrum, this sort of planning is built-in to the process. You estimate all of the stories in question, add them up and divide by the velocity to find out how many sprints it&#8217;ll take. Or, compute how many sprints you have and then you can choose which stories fit best into the time you have.

In the Kanban process, you can get the same kinds of useful estimates by computing &#8220;cycle time&#8221; and &#8220;throughput&#8221;. Cycle time is the average time it takes for similar-sized stories to work their way across the board. Throughput is how many similar-sized stories are done over a given period of time. Using this combination of data, you can do the same sorts of planning you can do in Scrum. As a bonus, cycle time and throughput are easy to compute, and should be easy to adjust when exceptional conditions arise.

Ability to do release and time planning is a strength of Scrum and something people were concerned about with the move to Kanban. Thankfully, this is territory that others have covered.

## Less Time in Meetings

This wasn&#8217;t a driving factor, but our Kanban process has us regularly filling up a &#8220;Ready&#8221; column for the next bit of work to do. We don&#8217;t spend more than a few seconds estimating stories (they&#8217;re small, medium, or need to be broken down further). We no longer spend _any_ time planning out the next sprint. Our product owner just ensures that our Ready column reflects what he thinks we need to work on next.

## What Happens to the Existing Trello Board?

We have a board that we use for tracking our in-progress Kanban work. It&#8217;s on Trello today, but we&#8217;re not certain it will remain there because there are other tools that are more Kanban-oriented that will do things like calculate cycle time and throughput for us.

The [Brackets Trello board][6] that we&#8217;ve had since the project&#8217;s public release contains a lot of information about features that Brackets users are interested in. Jonathan Dunlap, our product manager, will be revamping that board to better reflect our roadmap. Keep an eye on the Brackets blog for more on the roadmap.

## Conclusion

We&#8217;ve only just made this switch, so I can&#8217;t yet comment on how well it has worked for us. I have enjoyed reading about other people&#8217;s experiences with their software development processes and thought I would share in kind. Plus, there&#8217;s a large community of smart people out there, and I&#8217;m sure there are many suggestions that people might have. If you have a comment on this article, please [add to this thread in the googlegroup][7].

Finally, Brackets is open source and I thought it would be valuable for the Brackets community to have an idea of how we work.

## Further Reading

  * Corey Ladas [wrote an article about moving to Scrum-ban][8] and a useful book on the subject as well
  * Michael Dubakov likes an [Issues Board][9] for determining when to have retrospectives
  * Pawel Brodzinski wrote a multi-part [Kanban Story][10] as a logbook for their experiences with Kanban

 [1]: http://brackets.io
 [2]: http://en.wikipedia.org/wiki/Scrum_&#40;software_development&#41;
 [3]: http://en.wikipedia.org/wiki/Kanban_&#40;development&#41;
 [4]: https://github.com/adobe/brackets/issues/4128
 [5]: https://trello.com/c/8YAFyAZD/500-8-split-view-multiple-documents
 [6]: https://trello.com/b/LCDud1Nd/brackets
 [7]: https://groups.google.com/forum/#!topic/brackets-dev/tfxP18-2Yts
 [8]: http://leansoftwareengineering.com/ksse/scrum-ban/
 [9]: http://www.targetprocess.com/blog/2010/11/development-practice-retrospectives-in-kanban.html
 [10]: http://brodzinski.com/2009/10/kanban-story.html