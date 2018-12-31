---
title: 'del.icio.us direc.tor: Delivering A High-Performance AJAX Web Service Broker :: Johnvey'
author: Kevin Dangoor
type: post
date: 2005-06-25T11:49:47+00:00
url: /2005/06/25/delicious-director-delivering-a-high-performance-ajax-web-service-broker-johnvey/
keywords:
  - programming,ajax,xml,xsl,javascript
categories:
  - Software Development

---
After the [recent appearance of Google&#8217;s AJAXSLT][1], it&#8217;s interesting to read about [del.icio.us direc.tor][2] (page subtitle: Delivering A High-Performance AJAX Web Service Broker). As I commented yesterday, I don&#8217;t like the XSL-T syntax. However, when I look at [the XSL used by this project][3], I will freely admit that this XSL is not bad. It is more verbose than a [Velocity][4]-like template language, but there just wasn&#8217;t a lot of template code necessary for direct.or.

When working with a fairly good size chunk of data (80,000 records!), leveraging as much C code as possible makes good sense. It&#8217;s a shame that Safari didn&#8217;t expose the XSL engine to JavaScript. That would have made tools like this one work well in every major browser except Opera.

 [1]: http://www.blueskyonmars.com/2005/06/24/google-ajaxslt/
 [2]: http://johnvey.com/features/deliciousdirector/
 [3]: http://johnvey.com/features/deliciousdirector/xslt-filter-sort.html
 [4]: http://jakarta.apache.org/velocity/