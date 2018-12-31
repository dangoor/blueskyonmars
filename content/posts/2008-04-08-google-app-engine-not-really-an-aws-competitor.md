---
title: Google App Engine, not really an AWS competitor?
author: Kevin Dangoor
type: post
date: 2008-04-08T11:09:25+00:00
url: /2008/04/08/google-app-engine-not-really-an-aws-competitor/
categories:
  - Python
  - Software Development
tags:
  - amazon
  - app engine
  - aws
  - google

---
It occurred to me just now that Google App Engine and Amazon Web Services are only barely in competition right now. If you want an infinite storage system like AWS S3 in App Engine, you need to code it yourself (ignoring the preview limits App Engine currently has). If you want to deploy apps as easily as you can with App Engine in AWS, you need a bunch of infrastructure that AWS does not provide.

I&#8217;m happy to see that App Engine&#8217;s datastore is transactional, unlike SimpleDB. I didn&#8217;t see anything in my skim of some docs about whether App Engine has eventual consistency or if you can immediately pull out data that you stuff in. My guess is that you can immediately pull out the data you shove in. This is a win over SimpleDB, in my opinion.

App Engine is just tons higher-level than AWS. Of course, you can host anything you want in AWS. But, by trading away a bunch of that flexibility, Google has made a service that allows people to build apps that scale well with a minimum of fuss.