---
title: This Week in Bespin (Feb 23)
author: Kevin Dangoor
type: post
date: 2009-02-23T16:43:13+00:00
url: /2009/02/23/this-week-in-bespin-feb-23/
categories:
  - Bespin
  - JavaScript
tags:
  - Bespin

---
I&#8217;m crossposting this from the Bespin googlegroup.

Before moving on to the week that is coming, let&#8217;s look back at the week that was:

Week of February 17th:

  * Version 0.1.2 of Bespin was released. Notable changes:

  * System clipboard copy and paste now works in WebKit. Firefox will almost&nbsp;work. Vote up this bug:&nbsp;&nbsp;&nbsp;<a href="https://bugzilla.mozilla.org/show_bug.cgi?id=407983" target="_blank">https://bugzilla.<wbr />mozilla.org/show_bug.cgi?id=<wbr />407983</a>&nbsp;
  * Project names now need only to be unique per user. Previously, they had&nbsp;to be globally unique. This reflects a bit of a change to how we were&nbsp;viewing collaboration. (More on collaboration to come).
  * Thanks to that change, the sample project has been renamed from&nbsp;SampleProjectFor:<wbr />yourusername to just SampleProject.
  * Speaking of project renaming, you can now rename projects from the&nbsp;dashboard or the editor using the &#8220;renameproject&#8221; command. New&nbsp;&#8220;createproject&#8221; and &#8220;deleteproject&#8221; commands make project-level&nbsp;changes much clearer.
  * Every user now has a visible &#8220;BespinSettings&#8221; project. You probably&nbsp;&nbsp; &nbsp; &nbsp;won&#8217;t be surprised to hear that it stores settings for Bespin!&nbsp;You can put custom code (set autoconfig on and put code in&nbsp;config.js) and commands (use the cmd* commands) in there.
  * The login form is now a real form, which means that your password manager can save your Bespin login information.
  * Client and server implementations can make sure they&#8217;re in sync&nbsp;with the X-Bespin-API HTTP header that is returned from the server.&nbsp;The current API version is 2 (which adds the renameproject API).
  * key repetition works for arrows and backspace and lots of other minor fixes.

  * As Dion <a href="http://bit.ly/1Z68M" target="_blank">noted</a>, Boris Bokowski and Simon Kaegi&nbsp;<a href="http://bit.ly/dWGPU" target="_blank">coupled the Bespin Editor with a headless Eclipse</a>&nbsp;. The screenshot&nbsp;showing Java compiler warnings within Bespin is worth at least&nbsp;a couple thousand words!
  * Jerome Velociter got the <a href="http://bit.ly/eeqnu" target="_blank">Bespin editor running in XWiki</a>&nbsp;. Avi Bryant hooked the <a href="http://bit.ly/gzVpV" target="_blank">dashboard and editor&nbsp;up to Squeak</a>&nbsp;:. It&#8217;s been amazing to see&nbsp;the integration going on so far.
  * Oscar Carballa kicked off the creation of a <a href="https://wiki.mozilla.org/Labs/Bespin/UserGuide" target="_blank">User Guide</a> for Bespin
  * Mozilla&#8217;s Joe Walker started working on the collaboration spec. The model that he&#8217;s looking at is designed to allow you to share a project with many people and give them access to view it/collaborate on it in different ways. So, you&#8217;ll be able to selectively use collaborative editing with some people, do a &#8220;webcast&#8221; style sharing with others and more.
  * Three more google groups have been announced: <a href="http://groups.google.com/group/bespin-core/" target="_blank">bespin-core</a> covers the development of Bespin&#8217;s code, <a href="http://groups.google.com/group/bespin-dev/" target="_blank">bespin-dev</a> is for people who want to develop extensions for Bespin. Community member&nbsp;Guilherme Santos created the <a href="http://groups.google.com/group/bespinbrasil" target="_blank">bespinbrasil</a> group for Brazilian Bespin users.
Coming up this week:

  * Ben and Dion are in Miami for <a href="http://events.carsonified.com/fowa/2009/miami" target="_blank">Future of Web Apps</a> where they will be showing off Bespin.
  * Joe is continue to work on collaboration and is experimenting with Neil Fraser&#8217;s&nbsp;<a href="http://code.google.com/p/google-mobwrite/" target="_blank">mobwrite</a>.
  * I will finally be getting to work on the version control spec, and hope to be starting on the version control backend code.
  * And we&#8217;re all going to be working on bug fixes and minor enhancements.

<div class="zemanta-pixie">
  <img class="zemanta-pixie-img" src="http://img.zemanta.com/pixy.gif?x-id=3dfe00cf-2c62-4410-88de-53c8967511a9" />
</div>