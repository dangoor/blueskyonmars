---
title: Velocity whitespace handling is not as written
author: Kevin Dangoor
type: post
date: 2003-10-29T22:17:22+00:00
url: /2003/10/29/velocity-whitespace-handling-is-not-as-written/
categories:
  - Software Development

---
In the [Velocity User Guide][1], it says that &#8220;Velocity&#8217;s behaviour is to gobble up excess whitespace.&#8221; and gives some examples that it says will produce the same output. That&#8217;s not the way it works for me:

<pre>public void testVelocityWhitespace()
{
  VelocityEngine ve = new VelocityEngine();
  try
  {
    ve.init();
    VelocityContext context = new VelocityContext();
    String test1 = "Send me #set($foo = ["$10 and ","a cake"])#foreach($a in $foo)$a #end please.";
    String test2 = "Send me\n" +
      "#set( $foo = ["$10 and ","a cake"] )\n" +
      "#foreach( $a in $foo )\n" +
      "$a\n" +
      "#end\n" +
      "please.";
    String test3 = "Send me\n" +
      "			#set($foo       = ["$10 and ","a cake"])\n" 
      "							 #foreach           ($a in $foo )$a\n" +
      "					 #end please.";
    StringWriter sw = new StringWriter();
    ve.evaluate(context, sw, "test", test1);
    String output1 = sw.toString();
    sw = new StringWriter();
    ve.evaluate(context, sw, "test", test2);
    String output2 = sw.toString();
    sw = new StringWriter();
    ve.evaluate(context, sw, "test", test3);
    String output3 = sw.toString();
    System.out.println(output1);
    System.out.println(output2);
    System.out.println(output3);
    assertEquals(output1, output2);
    assertEquals(output1, output3);
  }
  catch (Exception e)
  {
    e.printStackTrace();
    fail("Template didn't work correctly.");
  }
}
</pre>

Perhaps there&#8217;s a property that controls it. Either way, the documentation should probably change to reflect what Velocity really does. (By the way, this is not at all a knock on Velocity. I think it&#8217;s a very nice templating system.)

 [1]: http://jakarta.apache.org/velocity/user-guide.html#VTL:%20Formatting%20Issues "Velocity - Velocity User Guide"