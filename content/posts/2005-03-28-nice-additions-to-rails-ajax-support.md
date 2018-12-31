---
title: Nice additions to Rails’ Ajax support
author: Kevin Dangoor
type: post
date: 2005-03-29T05:15:27+00:00
url: /2005/03/28/nice-additions-to-rails-ajax-support/
categories:
  - Software Development

---
Ruby on Rails [0.11.1][1] features some improvements to the Ajax support added in 0.11.

> The Ajax wave is sweeping across Rails. In this release, we’ve added a :position option to both link\_to\_remote and form\_remote\_tag that can be set to either :before, :top, :bottom, or :after. These options make it possible to add new DOM elements to existing lists without replacing the whole list. When working on big lists that are in a fixed order anyway, there’s a considerable speed increase to be had.

Nice! In my [earlier post mentioning Ajax in Rails][2], I talked about Nevow&#8217;s LivePage coming first. While that is true, and while it is also true (as far as I know) that Rails doesn&#8217;t support LivePage&#8217;s ability to call from server-to-client at will, it is cool to see new ease-of-use API ideas coming up.

 [1]: http://weblog.rubyonrails.com/archives/2005/03/27/rails-0111-more-ajax-verifications-sql-server-updated-loads-of-fixes/ "Weblog | Ruby on Rails"
 [2]: http://www.blueskyonmars.com/archives/2005/03/23/ruby_on_rails_wins_the_marketing_war.html