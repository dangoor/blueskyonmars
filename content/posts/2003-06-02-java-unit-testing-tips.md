---
title: Java Unit Testing Tips
author: Kevin Dangoor
type: post
date: 2003-06-02T18:06:50+00:00
url: /2003/06/02/java-unit-testing-tips/
article:
  - 1
categories:
  - Software Development

---
I&#8217;m not going to waste time with an introduction to unit testing. There are plenty of other resources for that. This article is a handful of practical tips for unit testing real world apps.

<!--more-->

This would actually make a great topic for a full-length book, so I think you&#8217;ll see that this article is just a quick set of tips. The questions come up often, so I would expect a publisher to jump on making an advanced unit testing book sometime soon.

## Keep it simple and fast!

Unit test code _has_ to be simple, otherwise you&#8217;ll need tests for your tests. It should be easy to read through a test and know what a given method expects to get as input and what it produces as output.

Your tests should also be _fast_. The faster they run, the more often you&#8217;ll run them, and the better off your code will be for it.

The tips here will help keep your tests small and fast.

## Use loose coupling and small methods

I use the phrase &#8220;loose coupling&#8221; here to denote objects and methods that have as few intertwinings and dependencies as possible.

The smaller and more specific your tests are, the easier your code will be to read and test. I think it was Fowler who made the recommendation that if you&#8217;re tempted to put in a comment for what a piece of code does, make that piece of code a separate method and give the method a descriptive enough name that the comment is unnecessary. Eclipse makes this easy to do with the &#8220;Extract Method&#8221; refactoring.

The fewer inputs that your methods take and the fewer connections you have between your objects, the less code you&#8217;ll need to write to test any given piece of your classes.

## I don&#8217;t want to put test code into my real, production objects

If you&#8217;re really trying to do test driven development, you&#8217;ll sometimes run into something that&#8217;s painful to test and is not likely to break anyhow. You may be tempted to do something like:

<pre>class TheMatrix
{
   private boolean isTest = false;

   public boolean enter()
   {
      if (!isTest)
      {
         Agent smith = doComplicatedThingy();
         return smith.allowIntoMatrix();
      }
      return true;
   }

   protected Agent doComplicatedThingy()
   {
      connectToMainframe();
      manipulateGiantAndComplexDataStructure();
      return new AgentSmithWrittenInPerl(false);
   }
}</pre>

Sure, that works (don&#8217;t ask me what it does, just take my word for it!). But the thing I don&#8217;t like about it is that it requires your real, production code to know something about test environments. I greatly prefer when the code you&#8217;re testing doesn&#8217;t know about the tests. Here&#8217;s an easy way to accomplish that:

&#8230;in JUnit test&#8230;

<pre>public void testEnter()
{
   TheMatrix m = new TheMatrix() {
      public Agent doComplicatedThingy()
      {
         return new AgentSmith(true);
      }
   };
   assertTrue(m.enter());
}</pre>

By creating an [anonymous class][1] that subclasses TheMatrix, I can override the method that I&#8217;m _not_ testing and just make it return a useful, dummy value that will produce a predictable result. This allows me to focus on just what I&#8217;m trying to test. This technique also provides advantages for&#8230;

## The code I want to test accesses files

Ideally, the data you&#8217;re using for your test will be right there with your test code. That way, anyone working with your code can get the full picture of what the code you&#8217;re testing is trying to accomplish. The very existence of a tool like [xDoclet][2] shows that people are keen on keeping their other related resources close to their code.

Java&#8217;s StringReader and StringWriter classes are awfully convenient for eliminating dependencies on files. Let&#8217;s say you&#8217;re trying to test some code that looks like this:

<pre>...code...
BufferedReader br = new BufferedReader(new FileReader(somefile));
...code...</pre>

That pesky reference to the file is right there in the middle of the method. No problem&#8230; just break out the creation of the reader into a separate method:

<pre>BufferedReader br = new BufferedReader(getReader(file));</pre>

Then, using the technique from the last section, you can just override getReader in an anonymous subclass and return a StringReader. When I did this recently, I ended up creating a subclass that allowed me to easily set and get the StringReader.

&#8230;in JUnit test code&#8230;

<pre>public void testMethod()
{
   ObjectToTest ott = new ObjectToTest() {
      StringWriter output = new StringWriter();

      protected getReader()
      {
            return new StringReader("Here is my test data!");
      }

      protected getWriter()
      {
         return output;
      }
   };
   ott.DoInputAndOutput();
   String outputdata = ott.getWriter().toString();
   assertEquals("This is thenexpected output.", outputdata);
}</pre>

Creating these additional methods and class is not a lot of work, and it made my test code easier to read.

## How do I test my app that uses a database?

There are very few apps that do not involve databases. Many of these apps involve reading and writing data based upon web requests. Though I would strongly recommend against it, there are some apps out there that are Java servlets that suck in some input from the web and update a database, all within the servlet&#8217;s doGet or doPost method. What do you do with that?

Setting aside the numerous design issues there, I think you&#8217;ll find that [Mock Objects][3] can be a great friend in such times. Mock Objects stand in place of the real thing to make your testing easier, and the good folk at MockObjects.com have given us a nice collection of stand-ins.

If you download the package from MockObjects.com, you&#8217;ll find implementations of the javax.servlet and java.sql packages. Unlike the real things, these mocks let you set the values that you want to return and set some conditions that you&#8217;d like to verify. Most people view unit testing as &#8220;white box&#8221; testing, which means that it&#8217;s okay for the test to be aware of what&#8217;s happening in the code.

So, pretend that our hypothetical servlet does the following:

  1. Validates the input in the HttpServletRequest object, sends an error message and returns if validation fails
  2. Updates a database
  3. Sends a success page

Testing this with mocks is pretty straightforward. Set up the input as needed in your mock HttpServletRequest and pass in a mock HttpServetResponse object. Using the mocks you can verify that the validation failed (if that&#8217;s the part you&#8217;re teting) or that the database update was sent to the java.sql mock.

Why deal with java.sql mocks at all? Because you want your unit tests to run quickly and independently of each other. If you&#8217;re constantly reinitializing a database so that it&#8217;s in a state that&#8217;s convenient for testing, your test is not going to run as quickly as you might like. Steve Freeman wrote a nice tutorial about [test first development with JDBC][4].

Which is not to say that you shouldn&#8217;t test your database code. Leaving a part of your code that is responsible for nothing less than loading and saving your data untested is like not checking to see that you&#8217;ve actually grabbed the parachute rather than your backpack.

So, the ideal is to isolate your database handling code as much as possible, so that you can test your database interaction with one series of tests and the rest of your business logic with other tests that don&#8217;t depend on the DB. For testing your database, you might want to check out [DBUnit][5].

## But I don&#8217;t have icky database code!

Life with some kind of object-relational layer ([home-grown][6] or [Hibernate][7] or one of the many others) can certainly make life easier. If you create a data source layer that is responsible for making all of the O-R calls and just returns your handy business objects, it becomes fairly simple to drop in a mock implementation that just returns objects directly without hitting the database.

Here&#8217;s how it can work for your typical contact manager:

  1. Make a DataSourceManager class with a static method called something like getContactsManager
  2. The static initializer for DataSourceManager should set the ContactsManager to be the real, database implementation. That way, nothing special needs to happen when the live system is running
  3. You can use [EasyMock][8] or the MockObjects.com DynaMock to create the mock data sources for you, and set up any test objects you want to return.
  4. Call DataSourceManager.setContactsManager to tell the system to use your mock objects

## But I need to create a hierarchy 500 levels deep to run my test

If you find that you need to create hundreds of objects to test a certain method, it&#8217;s possible that your objects are too tightly coupled. If it&#8217;s just that your method is performing a high-level function, then it helps to have a way to get a useful collection of objects with one or two calls.

Peter Schuh and Stephanie Punke have written a paper on a pattern they call the [ObjectMother][9]. This is distinct from a factory, because a factory is typically responsible for creating a fairly small set of objects. The ObjectMother is useful for testing, because you set it up to create a useful, common graph of objects that you can then tweak for each given test. In a way, the ObjectMother is a logical progression if you follow the &#8220;remove duplication&#8221; step that is listed for test driven development.

## Final Thoughts

When you start off with a pile of software that has no tests, unit testing can seem (and can be!) a fairly daunting task. Unit testing software that is built using test driven development is not so hard once you get used to it. So, if you&#8217;re starting off with a base of code that is test-free, your best bet is to try to make it easily testable step by step. The tricky part of that is just making sure you don&#8217;t break things as you go (and how would you know if you did? There aren&#8217;t any tests!) But, at the end of it all, you&#8217;ll probably be glad you added some tests.

I&#8217;d love to hear of more useful patterns and tips that people have learned.

 [1]: http://www-106.ibm.com/developerworks/java/library/j-mocktest.html
 [2]: http://xdoclet.sourceforge.net/
 [3]: http://www.mockobjects.com
 [4]: http://www.mockobjects.com/wiki/DevelopingJdbcApplicationsTestFirst
 [5]: http://dbunit.sf.net
 [6]: http://www.martinfowler.com/eaaCatalog/
 [7]: http://hibernate.sf.net
 [8]: http://tammofreese.de/easymock/
 [9]: http://www.xpuniverse.com/2001/pdfs/Testing03.pdf