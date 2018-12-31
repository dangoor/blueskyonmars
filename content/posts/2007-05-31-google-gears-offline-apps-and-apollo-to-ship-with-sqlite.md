---
title: Google Gears offline apps and Apollo to ship with SQLite
author: Kevin Dangoor
type: post
date: 2007-05-31T10:55:43+00:00
url: /2007/05/31/google-gears-offline-apps-and-apollo-to-ship-with-sqlite/
categories:
  - Software Development

---
Google has just open sourced a new project; [Google Gears][1]. (Hmm&#8230; sounds like a good companion to another [open source project][2]&#8230;) Google Gears lets you design webapps that can be taken offline and provides an SQLite-based data store. The data store even includes the full text search engine that Google helped fund. They also add a worker thread pool for performing background tasks (notably, their threads do not share state&#8230; so it&#8217;s more like multiprocess programming than multithreaded programming).

Neat stuff, and one can certainly imagine how Google themselves might plan to put this to use.

In other news, Adobe Apollo will include SQLite, which is a move that I would have been shocked if they didn&#8217;t do. If people are serious about making applications that run on standalone desktops, having a real database for storage is a necessity, and SQLite is as small and nice as they come.

Update: Google has already enabled Google Reader to work offline. I&#8217;m not sure if Gmail is offline-capable or not, because I think Google went for the &#8220;modeless&#8221; route, where the user (me) has no idea if the app is running online or off&#8230;

 [1]: http://gears.google.com/
 [2]: http://www.turbogears.org/