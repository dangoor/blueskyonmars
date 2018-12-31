---
title: Carlos on the BeanContext API
author: Kevin Dangoor
type: post
date: 2003-07-01T16:20:45+00:00
url: /2003/07/01/carlos-on-the-beancontext-api/
categories:
  - Software Development

---
Carlos Perez talks about [the BeanContext API][1] as the [Forgotten Standard Java API][2]. He is absolutely correct that we programmers have reinvented the wheel repeatedly, making the same mistakes that were made before, and I don&#8217;t think programmers are the only ones in this world who suffer from this. Still, if there is a Java standard API that&#8217;s often (but not always!) a better bet than some random API available out there in the wild. Why do they tend to be better? Documentation, multiple high-quality implementations, and so on.

The places where the standard APIs most often fall down are the ones that are either a) overengineered for most apps or b) unable to take important steps forward because of backwards compatibility issues.

Thanks for bringing this API up, Carlos. If J2SE includes the basis for what many of the microkernel packages do, it certainly seems worth a read.

 [1]: http://developer.java.sun.com/developer/technicalArticles/jbeans/BeanContext/
 [2]: http://www.freeroller.net/page/ceperez/20030701#the_forgotten_standard_java_api "::Manageability::"