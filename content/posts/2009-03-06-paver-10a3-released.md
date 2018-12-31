---
title: Paver 1.0a3 released
author: Kevin Dangoor
type: post
date: 2009-03-06T16:14:26+00:00
url: /2009/03/06/paver-10a3-released/
categories:
  - Paver
  - Python

---
I have just released [Paver][1] 1.0a3. This has some good refinements on the way to 1.0 final and a couple of nice, new features (the &#8220;auto&#8221; task and the &#8220;pushd&#8221; context manager):

  * <p class="first">
      Added automatic running of â€œautoâ€ task. If thereâ€™s a task with the name â€œautoâ€, it is run automatically. Using this mechanism, you can write code that sets up the options any way you wish, and without using globals at all (because the auto task can be given options as a parameter).
    </p>

  * <p class="first">
      When generating egg_info running â€œpaverâ€, the full path to the Paver script was getting included in egg-info/SOURCES.txt. This causes installation problems on Windows, at the very least. Paver will now instead place the pavement that is being run in there. This likely has the beneficial side effect of not requiring a MANIFEST.in file just to include the pavement.
    </p>

  * <p class="first">
      the options help provided via the cmdopts decorator now appears
    </p>

  * <p class="first">
      pavements can now refer to __file__ to get their own filename. You can also just declare pavement_file as an argument to your task function, if you wish.
    </p>

  * <p class="first">
      call_pavement now switches directories to the location of the pavement and then switches back when returning
    </p>

  * <p class="first">
      if you try to run a function as a task, youâ€™ll now get a more appropriate and descriptive BuildFailure, rather than an AttributeError
    </p>

  * <p class="first">
      paver can now again run tasks even when there is no pavement present. any task accessible via paver.easy (which now also includes misctasks) will work.
    </p>

  * <p class="first">
      added the pushd context manager (Python 2.5+). This will switch into another directory on the way in and then change back to the old directory on the way out. Suggested by Steve Howe, with the additional suggestion from Juergen Hermann to return the old directory:
    </p>
    
    <div class="highlight-python">
      <div class="highlight">
        <pre>&lt;span class="k"&gt;with&lt;/span&gt; &lt;span class="n"&gt;pushd&lt;/span&gt;&lt;span class="p"&gt;(&lt;/span&gt;&lt;span class="s"&gt;'newdirectory'&lt;/span&gt;&lt;span class="p"&gt;)&lt;/span&gt; &lt;span class="k"&gt;as&lt;/span&gt; &lt;span class="n"&gt;olddirectory&lt;/span&gt;&lt;span class="p"&gt;:&lt;/span&gt;&lt;br /&gt;    &lt;span class="o"&gt;...&lt;/span&gt;&lt;span class="n"&gt;do&lt;/span&gt; &lt;span class="n"&gt;something&lt;/span&gt;&lt;span class="o"&gt;...&lt;/span&gt;&lt;br /&gt;&lt;br /&gt;</pre>
      </div>
    </div>

<div class="zemanta-pixie">
  <img class="zemanta-pixie-img" src="http://img.zemanta.com/pixy.gif?x-id=12d55277-c5e6-4625-8065-ad2bd49c9d26" />
</div>

 [1]: http://www.blueskyonmars.com/projects/paver/