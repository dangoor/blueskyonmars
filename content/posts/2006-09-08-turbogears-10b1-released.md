---
title: TurboGears 1.0b1 released!
author: Kevin Dangoor
type: post
date: 2006-09-08T12:25:33+00:00
url: /2006/09/08/turbogears-10b1-released/
categories:
  - Python
  - TurboGears

---
TurboGears got its first public display at the first Michigan Python Users Group meeting in September 2005. Last night, at the end of the latest michipug meeting, I flipped the switch to release TurboGears 1.0b1. Here is the announcement email that went out:

I am pleased to announce TurboGears 1.0b1, which now supersedes the 0.8.9 release as the preferred TurboGears release. Many people have been using the TurboGears 0.9x releases for several months now and have been very happy with the results. The 1.0 APIs are stable and weâ€™re focused on bugs and docs for the final 1.0 release. This is a bugfix release over 0.9a9.

## What is TurboGears? {#what_is_turbogears}

TurboGears is a popular rapid web development megaframework, built from a number of great Python projects and with a bunch of high-level features built within the TurboGears project.

TurboGears is a front-to-back framework helping you on the front end (the MochiKit JavaScript library), templates for the view (Kid), the controller in the middle (based on CherryPy) and an object-relational mapper for your database (SQLObject).

To that mix of projects, TG adds:

  * Widgets: Python objects that bundle JavaScript, CSS, HTML and server-side validation to make form creation and powerful JavaScript features easy.
  * Internationalization: Tools and APIs to help you localize the strings in your application.
  * Identity: Authentication and authorization made easy
  * Toolbox: a web-based GUI to help you work on your project (write your own as well!) Includes CatWalk to help you work with your database data and Model Designer to help you design your database graphically.
  * tg-admin: command line tool that gives you a quick start to your project, helps you set up your database and more!
  * Easy Ajax: flexible template support allows you to choose a different template engine (output HTML, JSON, plain text, etc. all from one method)
  * Built-in database transactions: keeps your database (and you!) sane. Transactions are committed or rolled back based on the success or failure of your controller code.
  * flexibility as needed: though Kid and SQLObject are the standards, we already support many other template engines (Cheetah, Markup, Django) and the powerful SQLAlchemy object-relational mapper.
  * community: last but definitely not least â€” more than 2,000 users on the main mailing list, and others on non-English mailing lists

In short, there are lots of tools to help you get the job done quickly.

## Whatâ€™s New Since 0.8 {#what8217s_new_since_08}

Nearly everything. All of the projects that TG uses have had significant upgrades, and nearly all of the features that have been built by TurboGears contributors are new.

Website: <http://www.turbogears.org/>

Download: <http://www.turbogears.org/download/>

Mailing list: <http://groups.google.com/group/turbogears>