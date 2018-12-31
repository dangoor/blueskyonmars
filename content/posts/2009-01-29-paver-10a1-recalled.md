---
title: Paver 1.0a1 recalled
author: Kevin Dangoor
type: post
date: 2009-01-29T15:03:35+00:00
url: /2009/01/29/paver-10a1-recalled/
categories:
  - Python

---
It turns out that both pip and easy_install have trouble with the Paver 1.0a1 package. I&#8217;m going to look into that, but in the meantime I have removed the Paver 1.0a1 tarball from the cheeseshop so that people don&#8217;t accidentally get it. Sorry about that!

As a side note, it is unfortunate that easy_install and pip both will pick up alpha and beta releases in preference to release versions. I would think that a nicer default would be to prefer the current release version unless there&#8217;s a flag saying &#8220;give me the test release&#8221;.