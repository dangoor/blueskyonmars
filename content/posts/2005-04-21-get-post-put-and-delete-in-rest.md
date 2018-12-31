---
title: GET, POST, PUT and DELETE in REST
author: Kevin Dangoor
type: post
date: 2005-04-21T19:41:08+00:00
url: /2005/04/21/get-post-put-and-delete-in-rest/
categories:
  - Software Business

---
No, I&#8217;m not yelling in the title. I&#8217;m just following up on Dare Obasanjo&#8217;s post about [misunderstanding REST: A look at the Bloglines, del.icio.us and Flickr APIs][1]. Dare&#8217;s complaint is that these services all have URLs that have side effects via HTTP GET. This is an interesting distinction to make.

I just set up a new Drupal installation, and I&#8217;m reminded of Drupal&#8217;s cron.php. cron.php runs whatever periodic maintenance tasks are needed. In other words, it changes data. But, you really want to use GET in that case, because it makes it trivial to add a wget crontab entry to ping it periodically.

My own app keeps does housekeeping as links are clicked, which is far easier via a GET than to rig up a POST via JavaScript. Maybe the difference here is whether or not one is making a claim of a RESTful interface. Or maybe the difference is how caught up in the semantics of it one is. Josh Alen has a good comment on this:

> people chose between GET and POST based on other critera than suggested in the Fielding paper

I think this is on target. If you&#8217;re conciously providing an API for the public to use, following the RESTful standards that Dare mentions is worthwhile, because it helps with the principle of least surprise. But, you also need to look at the overall convenience of what you&#8217;re doing&#8230; if you have a good reason to bend the rules, do so and make sure you document it. If it&#8217;s truly a good reason for rule-bending, it shouldn&#8217;t really take people by surprise or throw them off.

This makes me think of the general notion that APIs are a user interface for developers. In Swing programming, to add a widget to a window you had to do this:

frame.getContentPane().add(somewidget)

This is the &#8220;correct&#8221; thing to do, because the JFrame object itself is not actually a container for UI widgets. But, it _has_ a container: the content pane. Correct or not, it was annoying. Java 1.5 now allows you to do this:

frame.add(somewidget)

Though it is less &#8220;correct&#8221; for the architecture, I think this is more inline with what programmers expect and want to do with the API.

I don&#8217;t know if this is the case with the Bloglines, Flickr and De.licio.us APIs, but my main point is that there are times when user experience is worth more than &#8220;following the spec&#8221;.

 [1]: http://www.25hoursaday.com/weblog/CommentView.aspx?guid=7a2f3df2-83f7-471b-bbe6-2d8462060263 "Dare Obasanjo aka Carnage4Life - Misunderstanding REST: A look at the Bloglines, del.icio.us and Flickr APIs"