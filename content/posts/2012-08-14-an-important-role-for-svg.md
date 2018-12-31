---
title: An Important Role for SVG
author: Kevin Dangoor
type: post
date: 2012-08-14T12:49:38+00:00
url: /2012/08/14/an-important-role-for-svg/
categories:
  - Software Development

---
Yesterday, I came across a link to [JustGage][1], a JavaScript library that uses [Raphaël.js][2] to create attractive, dashboard-style gauges. Since it uses Raphaël, which in turn builds upon SVG, these gauges will be resolution-independent. Thanks to vector-based graphics, they&#8217;ll look smooth at basically any size.

This morning, I saw John Gruber&#8217;s [ode to lots of pixels][3]. When Apple introduced the iPhone 4, their first product with a &#8220;Retina display&#8221;, they took the first massive, single-step leap in pixel density since we started reading off of glowing screens decades ago. As Gruber points out, displays crept up from 72ppi to 110ppi over the decades, before jumping to more than 300ppi on the iPhone 4. Now, we&#8217;re seeing high-dpi screens all over the place.

The trouble with the high-dpi displays is that bitmapped image files need to be _much_ higher resolution than we have been making them. On the web, that means more bandwidth used. For apps, that means larger app sizes.

Which brings me back to JustGage. It&#8217;s nice to see libraries like that and the popular [D3.js][4], because no matter what the resolution of the display, these visualizations will look good.

Gruber mentions this about the new high resolution displays:

> The sort of rich, [data-dense information design][5] espoused by [Edward Tufte][6] can now not only be made on the computer screen but also enjoyed on one.

Ironically, it was the combination of JustGage and Gruber&#8217;s article that made me think about just how important SVG will be in this new era of screens of many sizes and resolutions. Ironic, because I&#8217;m pretty sure that the kinds of visualizations provided by JustGage are exactly the sort of low-density displays that Tufte seems to dislike[<sup>[1]</sup>][7]{#refmark-1.fn-ref-mark}.

<div id="footnote-list" style="display:inherit">
  <span id=fn-heading>Footnotes</span> &nbsp;&nbsp;&nbsp;(&crarr; returns to text)</p> 
  
  <ol>
    <li id="footnote-1" class="fn-text">
      D3, on the other hand, is capable of some very nice displays, including the <a href="http://skedasis.com/d3/slopegraph/">slopegraph</a> that Tufte himself proposed.<a href="#refmark-1">&crarr;</a>
    </li>
  </ol>
</div>

 [1]: http://justgage.com/
 [2]: http://raphaeljs.com/
 [3]: http://daringfireball.net/2012/08/pixel_perfect
 [4]: http://d3js.org/
 [5]: http://thedoublethink.com/2009/08/tufte%E2%80%99s-principles-for-visualizing-quantitative-information/
 [6]: http://www.edwardtufte.com/tufte/
 [7]: #footnote-1