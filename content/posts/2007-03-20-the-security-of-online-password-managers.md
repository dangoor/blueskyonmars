---
title: The security of online password managers
author: Kevin Dangoor
type: post
date: 2007-03-20T22:42:18+00:00
url: /2007/03/20/the-security-of-online-password-managers/
categories:
  - Technology

---
Today, I learned about [PassPack &#8211; Free Online Password Manager.][1] PassPack appears to do everything right. The encryption/decryption happens _in your browser_, which means that the data simply cannot be decrypted by the people at PassPack or someone that gets ahold of PassPack&#8217;s data.Â  They also offer a reasonable technique for dealing with phishers.

Fundamentally, though, there is still a risk with a service like this. If someone manages to get into PassPack&#8217;s servers, they can modify the software that gets sent to your browser so that it passes along your encryption key, which they can then use to decrypt your passwords at their leisure.

Granted, the people running PassPack are undoubtedly security concious. They&#8217;ll run their servers as securely as they can, keep up with patches, and would disconnect the boxes as soon as they see a sign of a potential breach.Â  The risk is relatively minimal, but you still have to decide if it&#8217;s a chance you want to take.

 [1]: https://www.passpack.com/info/home/