---
title: 'Cheetah template tip: you want _namemapper for Windows'
author: Kevin Dangoor
type: post
date: 2005-02-15T16:17:08+00:00
url: /2005/02/15/cheetah-template-tip-you-want-_namemapper-for-windows/
categories:
  - Python

---
I do most of my work on my Mac, hopping over to the PC for additional integration and build testing. I already have someone who is running Windows builds regularly, though, so any Windows-specific problems will get shaken out. I was testing out my latest build on Windows and found that it was _very_ slow. I tossed a timer onto the page and found that it was taking 21 seconds to render. I added a database index I had been meaning to add, but I didn&#8217;t think that would do it because my database had a trivial amount of data.

That was when I remembered that the setup.py script for [Cheetah][1] assumes that you don&#8217;t have a C compiler if you&#8217;re running Windows. I&#8217;m working with enough modules that it was well worth getting a functional MinGW setup going. I changed Cheetah&#8217;s setup.py to enable the _namemapper C module.

The rendering time for that page dropped to 0.06 seconds, 350 times faster. It sure seems like you _need_ _namemapper for any but the most trivial templates. Given that, I would probably make setup.py count on a C compiler first, and let the user comment out that line if they don&#8217;t have one.

If you&#8217;re considering using Cheetah under Windows, don&#8217;t call it &#8220;too slow&#8221; until you&#8217;ve tried it with C _namemapper.

 [1]: http://www.cheetahtemplate.org