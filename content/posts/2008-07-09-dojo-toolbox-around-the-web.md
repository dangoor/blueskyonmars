---
title: Dojo Toolbox around the web
author: Kevin Dangoor
type: post
date: 2008-07-09T17:29:39+00:00
url: /2008/07/09/dojo-toolbox-around-the-web/
aktt_tweeted:
  - 1
categories:
  - JavaScript
tags:
  - dojo
  - dojo toolbox
  - sitepen

---
Rey Bango at Ajaxian says that [&#8220;This is a â€œmust-haveâ€ for Dojo developers.&#8221;][1]. I also enjoyed jdalton&#8217;s comment &#8220;I totally love this. I donâ€™t even use Dojo and I totally love this. Well done :)&#8221;.

Adobe AIR evangelist Ryan Stewart mentions that [&#8220;itâ€™s basically 100% Dojo&#8221;][2]. I did get an email from someone who was curious about what it&#8217;s like to create an AIR app using JavaScript. It&#8217;s really just like creating any JavaScript-intensive webapp, except you only target one, very capable browser engine (WebKit) and have additional APIs available for things like files, sqlite databases and native windows. Everything you know about web development translates very nicely.

Alex Russell mentions that we were able to [port James Burke&#8217;s excellent work][3] on the Rhino-based build tool that comes with Dojo. James did a great job on Dojo&#8217;s build system. Had he structured things differently, or not written the build system in JavaScript, it would have been difficult to impossible to create the Builder tool. But, as it was things fell into place fairly neatly. We need to get a patch together against Dojo&#8217;s build scripts and then the Toolbox will be able to share the code with the Rhino build directly.

Vote us up [on DZone][4]!

Peter Higgins, who was quite involved in the development of the Toolbox, put [his take][5] up on dojotoolkit.org.

And for the German speakers among you, here&#8217;s [a take on the Toolbox for you][6]. Vielen dank!

 [1]: http://ajaxian.com/archives/offline-access-to-dojo-resources
 [2]: http://onair.adobe.com/blogs/onair/2008/07/08/get-offline-access-to-dojo-resources-with-adobe-air/?sdid=DEKTH
 [3]: http://alex.dojotoolkit.org/?p=686
 [4]: http://www.dzone.com/links/rss/sitepens_dojo_toolbox.html
 [5]: http://dojotoolkit.org/2008/07/08/dojo-floating-air
 [6]: http://tas.tdbengine.org/blog/path/dojo-toolbox-endlich-eine-offline-api-doku-zu-dojo.html