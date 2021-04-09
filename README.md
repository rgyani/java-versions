### Quick Summary

<table>
    <thead>
    <tr>
        <th>Version</th>
        <th>Features</th>
        <th>Example</th>
    </tr>
    </thead>
    <tbody>
    <tr style="background-color:#ddd;">
        <td rowspan=4>Java 8</td>
        <td>Lambdas</td>
        <td>

```
Runnable runnable = () -> System.out.println("Hello world two!");
```

</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td>Arrays.asList</td>
        <td>

```
List <String> list = Arrays.asList("franz", "ferdinand", "fiel", "vom", "pferd");
```

</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td>Streams API</td>
        <td> 

```
list.stream()
   .filter(name -> name.startsWith("f"))
   .map(String::toUpperCase)
   .sorted()
   .forEach(System.out::println);
```

</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td>Default and Static methods in interface</td>
        <td>Default methods in interfaces allow the developers to add new methods to the interfaces without affecting
            the classes that implement these interfaces. <br> Static methods in interfaces are similar to the default
            methods except that we cannot override these methods in the classes that implement these interfaces.
        </td>
    </tr>
    <tr>
        <td rowspan=7>Java 9</td>
        <td>List.of, Set.of, Map.of</td>
        <td>

```
List<String> list = List.of("one", "two", "three");
Set<String> set = Set.of("one", "two","three");
Map<String, String> map = Map.of("foo", "one", "bar", "two");
``` 

</td>
    </tr>
    <tr>
        <td>streams.takeWhile</td>
        <td>

```
Stream<String> stream = Stream.iterate("", s -> s + "s")
                        .takeWhile(s -> s.length() < 10);
```

</td>
    </tr>
    <tr>
        <td>Optionals: ifPresentOrElse</td>
        <td> 

```
user.ifPresentOrElse(this::displayAccount, this::displayLogin);</td>
```

</tr>
    <tr>
        <td>private methods in interfaces</td>
        <td>private methods will improve code re-usability inside interfaces. For example, if two default methods needed
            to share code, a private interface method would allow them to do so, but without exposing that private
            method to it’s implementing classes.
        </td>
    </tr>
    <tr>
        <td>try with resource</td>
        <td></td>
    </tr>
    <tr>
        <td>Jshell: where you can try out simple commands and get immediate results.</td>
        <td>

```
% jshell 
| Welcome to JShell -- Version 9 
| For an introduction type: /help intro 

jshell> int x = 10 
x ==> 10
```

</td>
    </tr>
    <tr>
        <td><b>project jigsaw</b></td>
        <td>single jar containing diff classes for diff JVM versions</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td>Java 10</td>
        <td><b>var</b> keyword</td>
        <td> local-variable type inference, only applies to variables within methods</td>
    </tr>
    <tr>
        <td rowspan=3>Java 11 <b>(LTS)</b></td>
        <td>Strings.isBlank()</td>
        <td></td>
    </tr>
    <tr>
        <td>Run Source Files</td>
        <td>$ java a.java</td>
    </tr>
    <tr>
        <td>var in lambda parameters</td>
        <td>(var firstName, var lastName) -> firstName + lastName</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td rowspan=2>Java 12</td>
        <td>unicode support</td>
        <td></td>
    </tr>
    <tr style="background-color:#ddd;">
        <td>preview of new switch</td>
        <td></td>
    </tr>
    <tr>
        <td rowspan=2>Java 13</td>
        <td><b>multiline strings</b> without + (preview)</td>
        <td>

```
String htmlWithJava13 = """
              <html>
                  <body>
                      <p>Hello, world</p>
                  </body>
              </html>
              """;
```

</td>
    </tr>
    <tr>
        <td><b>Switch Expressions</b> (preview)</td>
        <td>

```text
boolean result = switch (status) {
    case SUBSCRIBER -> true;
    case FREE_TRIAL -> false;
    default -> throw new IllegalArgumentException("something is murky!");
};
```

</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td rowspan=4>Java 14</td>
        <td><b>Switch Expressions</b> (standard)</td>
        <td>

```text
int numLetters = switch (day) {
    case MONDAY, FRIDAY, SUNDAY -> 6;
    case TUESDAY                -> 7;
    default      -> {
      String s = day.toString();
      int result = s.length();
      yield result;
    }
};
````

</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td><b>Records</b> (preview)</td>
        <td>record Point(int x, int y) { }</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td>experimental Z Garbage Collector collector added.</td>
        <td></td>
    </tr>
    <tr style="background-color:#ddd;">
        <td>Pattern Matching Type Checks (preview)</td>
        <td>

```
if (person instanceof Employee employee && employee.getYearsOfService() > 5) {
    Date hireDate = employee.getHireDate();
}
```

</td>
    </tr>
    <tr>
        <td rowspan=2>Java 15</td>
        <td><b>Sealed and Permits</b> (preview)</td>
        <td>

```
public abstract sealed class Person permits Employee, Manager 
{
}
   
public final class Employee extends Person {
}

public non-sealed class Manager extends Person {
}
   
           
```

</td>
    </tr>
    <tr>
        <td>Text-Blocks / Multiline Strings (standard)</td>
        <td>

```text
String text = """
                Lorem ipsum dolor sit amet, consectetur adipiscing \
                elit, sed do eiusmod tempor incididunt ut labore \
                et dolore magna aliqua.\
                """;
```

</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td rowspan=2>Java 16</td>
        <td>Pattern Matching for instanceof</td>
        <td>

```text
if (obj instanceof String s) {
    // Let pattern matching do the work!
    // ... s.substring(1)
}
```

</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td>Records & Pattern Matching (standard)</td>
        <td></td>
    </tr>
    <tr>
        <td rowspan=2>Java 17 <b>(LTS)</b></td>
        <td><b>Pattern Matching for switch</b> (preview)</td>
        <td>

```text
public String test(Object obj) {

    return switch(obj) {

    case Integer i -> "An integer";

    case String s -> "A string";

    case Cat c -> "A Cat";

    default -> "I don't know what it is";

    };

}
```

</td>
    </tr>
    <tr>
        <td>Sealed Classes (Standard)</td>
        <td></td>
    </tr>
    </tbody>
    <tr style="background-color:#ddd;">
        <td rowspan=2>Java 18</td>
        <td><b>Pattern matching for switch</b> (2nd preview)</td>
        <td>

```
switch (obj) {
  case String s && s.length() > 5 -> System.out.println(s.toUpperCase());
  case String s                   -> System.out.println(s.toLowerCase());

  case Integer i                  -> System.out.println(i * i);

  default -> {}
}
```

</td>
    </tr>
    <tr style="background-color:#ddd;">
        <td>UTF-8 by Default</td>
        <td></td>
    </tr>
    <tr>
        <td rowspan=3>Java 19</td>
        <td><b>Virtual Threads</b> (Preview)</td>
        <td>Project Loom</td>
    </tr>
    <tr>
        <td><b>Foreign Function & Memory API</b> (Preview)</td>
        <td>In Project Panama, a replacement for the cumbersome, error-prone, and slow Java Native Interface (JNI) has been in the works for a long time.
    </td>
    <tr>
        <td><b>Structured Concurrency</b> (Incubator)</td>
        <td>
<ul>
<li>Task and subtasks form a self-contained unit in the code – there is no ExecutorService in a higher scope. The threads do not come from a thread pool; instead, each subtask is executed in a new virtual thread.</li>
<li>As soon as an error occurs in one of the subtasks, all other subtasks get canceled.</li>
<li>When the calling thread is canceled, the subtasks are also canceled.</li>
<li>The call hierarchy between the calling thread and the subtask-executing threads is visible in the thread dump.</li>
</ul>
    </td>
    </tr>
</table>

### Java Distributions

There’s a variety of sites offering Java, ie. Java Development Kit (JDK) downloads, and it is unclear "who offers what and with which licensing". Let's shine some light on it.

### The OpenJDK project

In terms of Java source code (read: the source code for your JRE/JDK), there is only one, living at
the [OpenJDK project](http://openjdk.java.net/projects/jdk/) site.  
This is just source code however, not a distributable build (think: your .zip file with the compiled java command for
your specific operating system). In theory, you and I could produce a build from that source code, call it, say,
MarcoJDK and start distributing it. But, our distribution would lack certification, to be able to legally call ourselves
Java SE compatible.

That’s why in practice, there’s a handful of vendors that actually create these builds, get them certified (
see [TCK](https://en.wikipedia.org/wiki/Technology_Compatibility_Kit)) and then distribute them.  
And while vendors cannot, say, remove a method from the String class before producing a new Java build, they can add
branding or add some other (e.g. CLI) utilities they deem useful. But other than that, the original source code is the
same for all Java distributions.

### OpenJDK builds (by Oracle) and OracleJDK builds

One of the vendors who builds Java from source is Oracle. This leads to two different Java distributions, which can be
very confusing at first.

1. [OpenJDK](http://jdk.java.net/) builds by Oracle. These builds are free and unbranded, but Oracle won’t release
   updates for older versions, say Java 15, as soon as Java 16 comes out.
2. [OracleJDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html), which is a branded, commercial
   build starting with the license change in 2019. Which means it can be used for free during development, but **you
   need to pay Oracle if using it in production**. For this, you get longer support, i.e. updates to versions and a
   telephone number you can call if your JVM goes crazy.

Now, historically (pre-Java 8) there were actual source differences between OpenJDK builds and OracleJDK builds, where
you could say that OracleJDK was 'better'. But as of today, both versions are essentially the same,
with [minor differences](https://blogs.oracle.com/java-platform-group/oracle-jdk-releases-for-java-11-and-later).  
It then boils down to you wanting paid, commercial support (a telephone number) for your installed Java version.

### AdoptOpenJDK

In 2017, a group of Java User Group members, developers and vendors (Amazon, Microsoft, Pivotal, Redhat and others)
started a community, called [AdoptOpenJDK](https://adoptopenjdk.net/).  
They provide free, rock-solid OpenJDK builds with longer availability/updates and even offer you the choice of two
different Java virtual machines:

* [HotSpot](https://en.wikipedia.org/wiki/HotSpot) and
* [OpenJ9](https://en.wikipedia.org/wiki/OpenJ9).

Highly recommended if you are looking to install Java.

### Azul Zulu, Amazon Corretto, SAPMachine

You will find a complete list of OpenJDK builds at the [OpenJDK Wikipedia site](https://en.wikipedia.org/wiki/OpenJDK).

Among them are [Azul Zulu](https://www.azul.com/products/zulu-community/)
, [Amazon Corretto](https://aws.amazon.com/de/corretto/) as well as [SapMachine](https://sap.github.io/SapMachine/), to
name a few.  
To oversimplify it boils down to you having different support options/maintenance guarantees.  
But make sure to check out the individual websites to learn about the advantages of each single distribution.


## Why are some Java versions, like 8 also called 1.8?
Java versions **before 9** simply had a different naming scheme. So, Java 8 can also be called 1.8, Java 5 can be called 1.5 etc. When you issued the 'java -version' command, with these versions you got output like this:

```text
c:\Program Files\Java\jdk1.8.0_191\bin>java -version
java version "1.8.0_191" (1)
Java(TM) SE Runtime Environment (build 1.8.0_191-b12)
Java HotSpot(TM) 64-Bit Server VM (build 25.191-b12, mixed mode)
```

Which simply means Java 8. With the switch to time-based releases with Java 9 the naming scheme also changed, and Java versions aren’t prefixed with 1.x anymore. Now the version number looks like this:

```text

c:\Program Files\Java\jdk11\bin>java -version
openjdk version "11" 2018-09-25 (1)
OpenJDK Runtime Environment 18.9 (build 11+28)
OpenJDK 64-Bit Server VM 18.9 (build 11+28, mixed mode)
```

## Java Features 8-19

As mentioned at the very beginning of this guide: Essentially all Java 8 language features also work in Java 14. The
same goes for all other Java versions in between.

Which in turns means that all language features from Java 8 serve as very good Java base knowledge and everything else (
Java 9-14) is pretty much additional features on top of that baseline.

Here’s a quick overview of what the specific versions have to offer:

##### Java 8 Language Features: Lambdas

Before Java 8, whenever you wanted to instantiate, for example, a new Runnable, you had to write an anonymous inner
class like so:

```
Runnable runnable = new Runnable(){ @Override public void run(){ System.out.println("Hello world !"); } };
```

With lambdas, the same code looks like this:

```
Runnable runnable = () -> System.out.println("Hello world two!");
```


##### Java 8 Language Features: Collections & Streams

In Java 8 you also got functional-style operations for collections, also known as the Stream API. A quick example:

```  
List<String> list = Arrays.asList("franz", "ferdinand", "fiel", "vom", "pferd");
```

Now pre-Java 8 you basically had to write for-loops to do something with that list.   
With the Streams API, you can do the following:

``` 
list.stream()
  .filter(name -> name.startsWith("f"))
  .map(String::toUpperCase)
  .sorted()
  .forEach(System.out::println);
```

##### Java 8 Language Features: Default and Static Methods in Interfaces.

Prior to java 8, interfaces in java can only have abstract methods. All the methods of interfaces are public & abstract
by default. **Java 8 allows the interfaces to have default and static methods.**

The reason we have **default methods in interfaces** is to allow the developers to add new methods to the interfaces
without affecting the classes that implement these interfaces.

**Static methods in interfaces** are similar to the default methods except that we **cannot** override these methods in
the classes that implement these interfaces.

##### Java 9 Language Features: New Helpers Methods in Collections

Collections got a couple of new helper methods, to easily construct Lists, Sets and Maps.

```
List<String> list = List.of("one", "two", "three");
Set<String> set = Set.of("one", "two", "three");
Map<String, String> map = Map.of("foo", "one", "bar", "two");
``` 

##### Java 9 Language Features: New Helpers Methods in Streams

Streams got a couple of additions, in the form of **takeWhile, dropWhile, iterate** methods.

```
Stream<String> stream = Stream.iterate("", s -> s + "s")
.takeWhile(s -> s.length() < 10);
```

##### Java 9 Language Features: Optionals

Optionals got the sorely missed **ifPresentOrElse** method.

```
user.ifPresentOrElse(this::displayAccount, this::displayLogin);
```

##### Java 9 Language Features: Private Methods in Interfaces

Interfaces got private methods:

```
public interface MyInterface {
   private static void myPrivateMethod(){ 
      System.out.println("Yay, I am private!"); 
   } 
}
```

These private methods will improve code re-usability inside interfaces. For example, if two default methods needed to
share code, a private interface method would allow them to do so, but without exposing that private method to it’s
implementing classes.

##### Java 9 Language Features: Other Language Features

And a couple of other improvements, like an improved try-with-resources statement or diamond operator extensions.

##### Java 9: JShell

Finally, Java got a shell where you can try out simple commands and get immediate results.

```
% jshell | Welcome to JShell -- Version 9 | For an introduction type: /help intro
jshell> int x = 10 x ==> 10
```

#### Java 9: HTTPClient

Java 9 brought the initial preview version of a new HttpClient. Up until then, Java’s built-in Http support was rather
low-level, and you had to fall back on using third-party libraries like Apache HttpClient or OkHttp.  

With Java 9, Java got its own, modern client - although in preview mode, which means subject to change in later Java
versions.

#### Java 9 : Project Jigsaw: Java Modules and Multi-Release Jar Files

Java 9 got the [Jigsaw Module System](https://www.oracle.com/corporate/features/understanding-java-9-modules.html),
which somewhat resembles the good old [OSGI specification](https://en.wikipedia.org/wiki/OSGi). It is not in the scope
of this guide to go into full detail on Jigsaw, but have a look at the previous links to learn more.

Multi-Release .jar files made it possible to have one .jar file which contains different classes for different JVM
versions. So your program can behave differently/have different classes used when run on Java 8 vs. Java 10, for
example.

#### Java 10: Local-Variable Type Inference using var-keyword

```
// Pre-Java 10 
String myName = "Marco"; 

// With Java 10 
var myName = "Marco"

```

**It is still strongly typed though, and only applies to variables inside methods.**


#### Java 11 Language Features: Strings & Files

Strings and Files got a couple new methods (not all listed here):

```
"Marco".isBlank();
"Mar\nco".lines();
"Marco  ".strip();

Path path = Files.writeString(Files.createTempFile("helloworld", ".txt"), "Hi, my name is!"); String s =
Files.readString(path);
```

#### Java 11:  Run Source Files

Starting with Java 11, you can run Java source files without having to compile them first. A step towards scripting.

```
ubuntu@pc:~$ java MyScript.java
```

#### Java 11:  Local-Variable Type Inference (var) for lambda parameters


```
var firstName, var lastName) -> firstName + lastName
```



### Java 12

Java 12 got a couple [new features and clean-ups](https://www.oracle.com/technetwork/java/javase/12-relnote-issues-5211422.html), but
the only ones worth mentioning here are Unicode 11 support and a preview of the new switch expression, which you will
see covered in the next section.


### Java 13: Switch Expression (Preview)

Switch expressions can now return a value. And you can use a lambda-style syntax for your expressions, without the
fall-through/break issues:   
Old switch statements looked like this:

```  

switch(status) { 
   case SUBSCRIBER:
      // code block 
      break; 
   case FREE_TRIAL:
      // code block 
      break; 
   default:
      // code block 
}

```  

Whereas with Java 13, switch statements can look like this:

```

boolean result = switch (status) { 
   case SUBSCRIBER -> true; 
   case FREE_TRIAL -> false; 
   default -> throw new IllegalArgumentException("something is wrong!"); 
};

```

#### Java 13 Language Features: Multiline Strings (Preview)

You can finally do this in Java:

```

String htmlBeforeJava13 = "<html>\n" +
"    <body>\n" +
"        <p>Hello, world</p>\n" +
"    </body>\n" +
"</html>\n";

String htmlWithJava13 = """
  <html>
  <body>
  <p>Hello, world</p>
  </body>
  </html>
  """;
```

#### Java 14 Language Features: Switch Expression (Standard)

The switch expressions that were “in preview” in versions 12 and 13, are now standardized.

```
int numLetters = switch (day) {
    case MONDAY, FRIDAY, SUNDAY  -> 6;
    case TUESDAY                 -> 7;
    default                      -> {
        String s = day.toString();
        int result = s.length();
        yield result;
    }
};
```

#### Java 14 Language Features: Records (Preview)

There are now record classes, which help alleviate the pain of writing a lot of boilerplate with Java. Have a look at
this pre Java 14 class, which only contains data, (potentially) getters/setters, equals/hashcode, toString.

```
final class Point {
    public final int x;
    public final int y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}

// state-based implementations of equals, hashCode, toString
// nothing else
```

With records, it can now be written like this:

```
record Point(int x, int y) { }
```



#### Java 14 Language Features: Helpful NullPointerExceptions

Finally, NullPointerExceptions describe exactly which variable was null.

```
author.age = 35;
---
Exception in thread "main" java.lang.NullPointerException:
Cannot assign field "age" because "author" is null
```

#### Java 14 Language Features: Pattern Matching For InstanceOf (Preview)

Whereas previously you had to (cast) your objects inside an instanceof like this:

```
if (obj instanceof String) {
    String s = (String) obj;
    // use s
}
```

You can now do this, effectively dropping the cast.

```
if (obj instanceof String s) {
    System.out.println(s.contains("hello"));
}
```

#### Java 14 Language Features: Packaging Tool (Incubator)

There’s an incubating **jpackage** tool, which allows you to package your Java application into platform-specific packages,
including all necessary dependencies.

* Linux: deb and rpm
* macOS: pkg and dmg
* Windows: msi and exe

#### Java 14 Language Features: Garbage Collectors

The Concurrent Mark Sweep (CMS) Garbage Collector has been removed, and **the experimental Z Garbage Collector has been added.**


#### Java 15 Language Features: Sealed Classes

The goal of sealed classes is to allow individual classes to declare which types may be used as sub-types. This also
applies to interfaces and determining which types can implement them.

Sealed classes involve two new keywords — sealed and permits:

```
public abstract sealed class Person
    permits Employee, Manager {
 
    //...
}
```

In this example, we've declared an abstract class named Person. We've also specified that the only classes that can
extend it are Employee and Manager. Extending the sealed class is done just as it is today in Java, using the extends
keyword:

```
public final class Employee extends Person {
}

public non-sealed class Manager extends Person {
}
```

It's important to note that any class that extends a sealed class must itself be declared sealed, non-sealed, or final.
This ensures the class hierarchy remains finite and known by the compiler.

This finite and exhaustive hierarchy is one of the great benefits of using sealed classes. Let's see an example of this
in action:

```
if (person instanceof Employee) {
    return ((Employee) person).getEmployeeId();
} 
else if (person instanceof Manager) {
    return ((Manager) person).getSupervisorId();
}
```

Without a sealed class, the compiler can't reasonably determine that all possible sub-classes are covered with our
if-else statements. Without an else clause at the end, the compiler would likely issue a warning indicating our logic
doesn't cover every case.

#### Java 16 Language Features: Pattern Matching for instanceof

Instead of:

```
if (obj instanceof String) {
    String s = (String) obj;
    // e.g. s.substring(1)
}
```

You can now do this:

```
if (obj instanceof String s) {
    // Let pattern matching do the work!
    // ... s.substring(1)
}
```

#### Java 16 Language Features:  Unix-Domain Socket Channels

You can now connect to Unix domain sockets (also supported by macOS and Windows (10+).

```
 socket.connect(UnixDomainSocketAddress.of(
        "/var/run/postgresql/.s.PGSQL.5432"));
```

#### Java 16 Language Features:  Foreign Linker API - Preview

A planned replacement for JNI (Java Native Interface), allowing you to bind to native libraries (think C).


### Java 17 is the new long-term support (LTS) release of Java, after Java 11.

#### Java 17 Language Features: Pattern Matching for switch (Preview)

Already available in many other languages:

```
public String test(Object obj) {

    return switch(obj) {

    case Integer i -> "An integer";

    case String s -> "A string";

    case Cat c -> "A Cat";

    default -> "I don't know what it is";

    };

}
```

Now you can pass Objects to switch functions and check for a particular type.

#### Java 17 Features:  Foreign Function & Memory API (Incubator)

A replacement for the Java Native Interface (JNI). Allows you to call native functions and access memory outside the
JVM. Think C calls for now, but with plans for supporting additional languages (like C++, Fortran) over time.

#### Java 18: UTF-8 by default

If you tried reading in files without specifying an explicit character ending, the operating system encoding was used in previous Java versions (e.g. UTF-8 on Linux and macOS, and Windows-1252 on Windows). 
With Java 18 this changed to UTF-8 by default.


#### Java 19: Virtual Threads 

This is one of the most exciting feature and demands a [separate article](https://github.com/rgyani/java19-virtual-threads/#readme)

#### Java 19 Language Features: Structured Concurrency (Preview)
If a task consists of different subtasks that can be done in parallel (e.g., accessing data from a database, calling a remote API, and loading a file), we could so far use the Java executable framework for this.

This could then look like this, for example:

```
private final ExecutorService executor = Executors.newCachedThreadPool();

public Invoice createInvoice(int orderId, int customerId, String language)
    throws ExecutionException, InterruptedException {
  Future<Order> orderFuture =
      executor.submit(() -> loadOrderFromOrderService(orderId));

  Future<Customer> customerFuture =
      executor.submit(() -> loadCustomerFromDatabase(customerId));

  Future<String> invoiceTemplateFuture =
      executor.submit(() -> loadInvoiceTemplateFromFile(language));

  Order order = orderFuture.get();
  Customer customer = customerFuture.get();
  String invoiceTemplate = invoiceTemplateFuture.get();

  return Invoice.generate(order, customer, invoiceTemplate);
}

```

We pass the three subtasks to the executor and wait for the partial results. The happy path is quickly implemented. But how do we handle exceptions?

* If an error occurs in one subtask – how can we cancel the others?
* How can we cancel the subtasks if the entire invoice is no longer needed?
* Both are possible but require pretty complex and difficult-to-maintain code.

And what if we want to debug code of this kind? A thread dump, for example, would give us a bunch of threads named "pool-X-thread-Y" – but we wouldn't know which pool thread belongs to which calling threads since all calling threads share the executor's thread pool.

JDK Enhancement Proposal 428 introduces an API for so-called "structured concurrency", a concept intended to improve the implementation, readability, and maintainability of code for requirements of this type.

Using a StructuredTaskScope, we can rewrite the example as follows:

```
Invoice createInvoice(int orderId, int customerId, String language)
    throws ExecutionException, InterruptedException {
  try (var scope = new StructuredTaskScope.ShutdownOnFailure()) {
    Future<Order> orderFuture =
        scope.fork(() -> loadOrderFromOrderService(orderId));

    Future<Customer> customerFuture =
        scope.fork(() -> loadCustomerFromDatabase(customerId));

    Future<String> invoiceTemplateFuture =
        scope.fork(() -> loadInvoiceTemplateFromFile(language));

    scope.join();
    scope.throwIfFailed();

    Order order = orderFuture.resultNow();
    Customer customer = customerFuture.resultNow();
    String invoiceTemplate = invoiceTemplateFuture.resultNow();

    return new Invoice(order, customer, invoiceTemplate);
  }
}
```

So we replace the ExecutorService in the scope of the class with a StructuredTaskScope located in the method's scope – and executor.submit() with scope.fork().

Using scope.join(), we wait for all tasks to be completed – or at least one to fail or be canceled. In the latter two cases, the subsequent throwIfFailed() throws an ExecutionException or a CancellationException.

The new approach brings the following improvements over the old one:

Task and subtasks form a self-contained unit in the code – there is no ExecutorService in a higher scope. The threads do not come from a thread pool; instead, each subtask is executed in a new virtual thread.
As soon as an error occurs in one of the subtasks, all other subtasks get canceled.
When the calling thread is canceled, the subtasks are also canceled.
The call hierarchy between the calling thread and the subtask-executing threads is visible in the thread dump.


