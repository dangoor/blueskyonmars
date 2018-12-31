---
title: PasswordMaker, a very clever password system
author: Kevin Dangoor
type: post
date: 2005-08-14T03:38:17+00:00
url: /2005/08/13/passwordmaker-a-very-clever-password-system/
categories:
  - Technology

---
I&#8217;ve tried a couple of different password managers over the years. They all have their shortcomings&#8230; these days, since I&#8217;m cross platform, my choices are even more limited. Recently, I&#8217;ve started using the Java-based [Password Manager][1] by Ramesh N. It&#8217;s not entirely pleasant, but it does the job fine and is cross-platform.

Lifehacker mentioned [a few password managers][2], including the intriguing [PasswordMaker. One Password To Rule Them All.â„¢][3]. PasswordMaker is neat because it&#8217;s totally cross-platform (and even has a JavaScript version that you can run in whatever browser you&#8217;re using at the time). But, what makes it _really_ cool is the fact that it doesn&#8217;t store anything. You use a master password, and it usually a cryptographically secure hashing algorithm against your master password and the URL to determine a password for the site. All you ever need to remember is your master password, and the options you used for the password generation.

This is a most excellent use of the technology. Of course, this will force me to actually change my password everywhere, but that&#8217;s not an entirely bad thing.

 [1]: http://www.geocities.com/ramix_info/passwordmanager.html
 [2]: http://www.lifehacker.com/software/security/os-x-password-manager-roundup-117004.php
 [3]: http://www.passwordmaker.org/