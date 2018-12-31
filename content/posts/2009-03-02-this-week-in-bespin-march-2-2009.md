---
title: This Week in Bespin March 2, 2009
author: Kevin Dangoor
type: post
date: 2009-03-02T14:32:51+00:00
url: /2009/03/02/this-week-in-bespin-march-2-2009/
categories:
  - Bespin
  - JavaScript

---
For the week of February 23rd:

<div>
</div>

  * Roberto Saccon **ported Bespin to Dojo**! Dojo leader Peter Higgins helped to clean things up a bit. This has significantly changed (and improved) the use of namespaces in the frontend code, which will make Bespin much easier to drop into other pages.
  * For people keeping score at home, there is now a **0.1 branch** in the Bespin repository that we will be using to update the server. The default branch has the Dojo work and all of the other forward-looking work going on. Until the trunk work stabilizes a bit, <a href="http://bespin.mozilla.com/" target="_blank">bespin.mozilla.com</a> will be running a bit behind on the changes here.
  * **autoindent**&nbsp;setting. When you hit return/enter you&#8217;re placed at the same indentation point on the next line.
  * Select an area and hit TAB and it all indents. SHIFT+TAB and it unindents. Thanks to Jay Bird!
  * Special support for certain keys so German keyboards etc can get in &#8216;{&#8216; and the like. Thanks to Julian Viereck&nbsp;&nbsp;
  * For people following the trunk/tip, the project build script has changed a bit. Be sure to follow the instructions in the top-level README file to get the Bespin server running.
  * PHP, Java and Aduino syntax highlighting, thanks to Sean Burke and&nbsp;Olle Jonsson, respectively. The Arduino support is optional. Use&nbsp;include(&#8220;bespin.syntax.<wbr />arduino&#8221;); in your config.js to load.
  * Multithreaded development server, which speeds up page loads a bit now that there are more modules loading.
  * Config work has short cuts now so you can simply use: include(file), execute(cmd), publish(), subscribe()&nbsp;

<div>
  Coming up the week of March 2nd:
</div>

<div>
  <ul>
    <li>
      I&#8217;ll be working on backend changes to make VCS integration possible (and to allow us to start using Bespin as our primary editor when working on Bespin itself)
    </li>
    <li>
      Joe will be working on collaboration implementation
    </li>
    <li>
      Ben and Dion will likely have their hands full just keeping up with your patches! (I&#8217;m sure they will sneak some time in to improve the editor and Thunderhead as well 🙂
    </li>
  </ul>
  
  <p>
    By the way, &#8220;This Week in Bespin&#8221; is not just for those of us at Mozilla. If you have anything you want to see show up in these summaries, just send me an email message!
  </p>
</div>

<div>
</div>

<div class="zemanta-pixie">
  <img class="zemanta-pixie-img" src="http://img.zemanta.com/pixy.gif?x-id=41bf0053-c2bb-41b3-bab7-59256a1cb4af" />
</div>