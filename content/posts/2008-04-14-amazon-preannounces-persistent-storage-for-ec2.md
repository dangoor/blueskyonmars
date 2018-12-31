---
title: Amazon preannounces persistent storage for EC2
author: Kevin Dangoor
type: post
date: 2008-04-14T13:34:16+00:00
url: /2008/04/14/amazon-preannounces-persistent-storage-for-ec2/
categories:
  - Python
  - Software Development
tags:
  - aws

---
I don&#8217;t know if this preannouncement comes as a result of all of the Google App Engine publicity, but here it is: [Amazon Web Services Blog: Storage Space, The Final Frontier][1]. In a nutshell: AWS now lets you create a storage volume of 1GB to 1TB that can be mounted in one EC2 instance and will persist beyond the lifetime of an EC2 instance. As an added bonus, you can have automatic snapshots of your volume plunked into S3.

They say that this storage is a low-latency, high-throughput block device. So, you can run all kinds of traditional software on top of it.

This will change the competitive outlook a bit between AWS and GAE a bit, because it makes it easier for people to use all of the software pieces that they&#8217;re used to when they use AWS to manage the hardware infrastructure. This means that it&#8217;s easier to take your existing apps and skills and get them up on AWS. GAE has a fight ahead in terms of getting people to write their apps differently&#8230; but the benefit to doing so is that you no longer think of hardware infrastructure at all.

 [1]: http://aws.typepad.com/aws/2008/04/block-to-the-fu.html