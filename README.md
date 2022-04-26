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
    <tr>
        <td rowspan=4>Java 8</td>
        <td>Lambdas</td>
        <td> Runnable runnable = () -> System.out.println("Hello world two!");</td>
    </tr>
    <tr>
        <td>Arrays.asList</td>
        <td>List &lt;String&gt; list = Arrays.asList("franz", "ferdinand", "fiel", "vom", "pferd");</td>
    </tr>
    <tr>
        <td>Streams API</td>
        <td> list.stream()<br>&nbsp;.filter(name -> name.startsWith("f"))<br>&nbsp;.map(String::toUpperCase)<br>&nbsp;.sorted()
            <br/>&nbsp;.forEach(System.out::println);
        </td>
    </tr>
    <tr>
        <td>Default and Static methods in interface</td>
        <td>Default methods in interfaces allow the developers to add new methods to the interfaces without affecting
            the classes that implement these interfaces. <br> Static methods in interfaces are similar to the default
            methods except that we cannot override these methods in the classes that implement these interfaces.
        </td>
    </tr>
    <tr>
        <td rowspan=7>Java 9</td>
        <td>List.of, Set.of, Map.of</td>
        <td>List&lt;String&gt; list = List.of("one", "two", "three");<br>Set&lt;String&gt; set = Set.of("one", "two",
            "three");<br>Map&lt;String, String&gt; map = Map.of("foo", "one", "bar", "two");
        </td>
    </tr>
    <tr>
        <td>streams.takeWhile</td>
        <td>Stream&lt;String&gt; stream = Stream.iterate("", s -> s + "s")<br/>&nbsp;.takeWhile(s -> s.length() < 10);
        </td>
    </tr>
    <tr>
        <td>Optionals: ifPresentOrElse</td>
        <td> user.ifPresentOrElse(this::displayAccount, this::displayLogin);</td>
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
        <td>% jshell <br> | Welcome to JShell -- Version 9 <br> | For an introduction type: /help intro <br><br> jshell>
            int x = 10 <br> x ==> 10
        </td>
    </tr>
    <tr>
        <td><b>project jigsaw</b></td>
        <td>single jar containing diff classes for diff JVM versions</td>
    </tr>
    <tr>
        <td>Java 10</td>
        <td><b>var</b> keyword</td>
        <td> local-variable type inference, only applies to variables within methods</td>
    </tr>
    <tr>
        <td rowspan=3>Java 11</td>
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
    <tr>
        <td rowspan=2>Java 12</td>
        <td>unicode support</td>
        <td></td>
    </tr>
    <tr>
        <td>preview of new switch</td>
        <td></td>
    </tr>
    <tr>
        <td rowspan=2>Java 13</td>
        <td>multiline strings without +</td>
        <td>String htmlWithJava13 = """<br>&lt;html&gt;<br>&lt;body&gt;<br>&lt;p&gt;Hello, world&lt;/p&gt;<br>&lt;/body&gt;<br>&lt;/html&gt;<br>""";
        </td>
    </tr>
    <tr>
        <td>Switch Expressions</td>
        <td> boolean result = switch (status) {<br>&nbsp;case SUBSCRIBER -> true;<br>&nbsp; case FREE_TRIAL ->
            false;<br>&nbsp; default -> throw new IllegalArgumentException("something is murky!"); <br> };
        </td>
    </tr>
    <tr>
        <td rowspan=4>Java 14</td>
        <td>Switch Expressions Standard</td>
        <td></td>
    </tr>
    <tr>
        <td>Records Preview</td>
        <td>record Point(int x, int y) { }</td>
    </tr>
    <tr>
        <td>experimental Z Garbage Collector collector added.</td>
        <td></td>
    </tr>
    <tr>
        <td>Pattern Matching Type Checks</td>
        <td>if (person instanceof Employee employee && employee.getYearsOfService() > 5) {<br>&nbsp;    Date hireDate = employee.getHireDate();<br>}</td>
    </tr>
    <tr>
        <td rowspan=2>Java 15</td>
        <td>sealed and permits</td>
        <td>public abstract sealed class Person<br>&nbsp; permits Employee, Manager {<br>}<br><br>public final class
            Employee extends Person {<br>}<br><br>public non-sealed class Manager extends Person {<br>}<br></td>
    </tr>
    </tbody>
</table>

### Java Distributions

There’s a variety of sites offering Java (read: JDK) downloads and it is unclear "who offers what and with which
licensing". This section will shed some light on this.

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

You will find a complete list of OpenJDK builds at the [OpenJDK Wikipedia site](https://en.wikipedia.org/wiki/OpenJDK)
.  
Among them are [Azul Zulu](https://www.azul.com/products/zulu-community/)
, [Amazon Corretto](https://aws.amazon.com/de/corretto/) as well as [SapMachine](https://sap.github.io/SapMachine/), to
name a few.  
To oversimplify it boils down to you having different support options/maintenance guarantees.  
But make sure to check out the individual websites to learn about the advantages of each single distribution.

## Java Features 8-14

As mentioned at the very beginning of this guide: Essentially all Java 8 language features also work in Java 14. The
same goes for all other Java versions in between.

Which in turns means that all language features from Java 8 serve as very good Java base knowledge and everything else (
Java 9-14) is pretty much additional features on top of that baseline.

Here’s a quick overview of what the specific versions have to offer:

### Java 8

Java 8 was a massive release and you can find a list of all features at
the [Oracle website](https://www.oracle.com/technetwork/java/javase/8-whats-new-2157071.html).  
There’s two main feature sets I’d like to mention here, though:

##### Language Features: Lambdas etc.

Before Java 8, whenever you wanted to instantiate, for example, a new Runnable, you had to write an anonymous inner
class like so:

```
  Runnable runnable = new Runnable(){
      @Override
      public void run(){
          System.out.println("Hello world !");
      }
  };
```

With lambdas, the same code looks like this:

```
  Runnable runnable = () -> System.out.println("Hello world two!");
```

You also got method references, repeating annotations, default methods for interfaces and a few other language features.

##### Collections & Streams

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

##### Default and Static Methods in Interfaces.

Prior to java 8, interfaces in java can only have abstract methods. All the methods of interfaces are public & abstract
by default. **Java 8 allows the interfaces to have default and static methods.**

The reason we have **default methods in interfaces** is to allow the developers to add new methods to the interfaces
without affecting the classes that implement these interfaces.

**Static methods in interfaces** are similar to the default methods except that we **cannot** override these methods in
the classes that implement these interfaces.

### Java 9

Java 9 also was a fairly big release, with a couple of additions:

#### Collections

Collections got a couple of new helper methods, to easily construct Lists, Sets and Maps.

```
  List<String> list = List.of("one", "two", "three");
  
  Set<String> set = Set.of("one", "two", "three");
  
  Map<String, String> map = Map.of("foo", "one", "bar", "two");
``` 

#### Streams

Streams got a couple of additions, in the form of **takeWhile, dropWhile, iterate** methods.

```
  Stream<String> stream = Stream.iterate("", s -> s + "s")
      .takeWhile(s -> s.length() < 10);
```

#### Optionals

Optionals got the sorely missed **ifPresentOrElse** method.

```
  user.ifPresentOrElse(this::displayAccount, this::displayLogin);
```

#### Interfaces

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

#### Other Language Features

And a couple of other improvements, like an improved try-with-resources statement or diamond operator extensions.

#### JShell

Finally, Java got a shell where you can try out simple commands and get immediate results.

```
  % jshell
  |  Welcome to JShell -- Version 9
  |  For an introduction type: /help intro

  jshell> int x = 10
  x ==> 10
```

#### HTTPClient

Java 9 brought the initial preview version of a new HttpClient. Up until then, Java’s built-in Http support was rather
low-level, and you had to fall back on using third-party libraries like Apache HttpClient or OkHttp (which are great
libraries, btw!).  
With Java 9, Java got its own, modern client - although in preview mode, which means subject to change in later Java
versions.

#### Project Jigsaw: Java Modules and Multi-Release Jar Files

Java 9 got the [Jigsaw Module System](https://www.oracle.com/corporate/features/understanding-java-9-modules.html),
which somewhat resembles the good old [OSGI specification](https://en.wikipedia.org/wiki/OSGi). It is not in the scope
of this guide to go into full detail on Jigsaw, but have a look at the previous links to learn more.

Multi-Release .jar files made it possible to have one .jar file which contains different classes for different JVM
versions. So your program can behave differently/have different classes used when run on Java 8 vs. Java 10, for
example.

### Java 10

There have been a few changes to Java 10, like Garbage Collection etc. But the only real change you as a developer will
likely see is the introduction of the "var"-keyword, also called local-variable type inference.

#### Local-Variable Type Inference: var-keyword

```
  // Pre-Java 10
  String myName = "Marco";
  // With Java 10
  var myName = "Marco"
```

Feels Javascript-y, doesn’t it? It is still strongly typed, though, and only applies to variables inside methods.

### Java 11

Java 11 was also a somewhat smaller release, from a developer perspective.

#### Strings & Files

Strings and Files got a couple new methods (not all listed here):

```
  "Marco".isBlank();
  "Mar\nco".lines();
  "Marco  ".strip();

  Path path = Files.writeString(Files.createTempFile("helloworld", ".txt"), "Hi, my name is!");
  String s = Files.readString(path);
```

#### Run Source Files

Starting with Java 10, you can run Java source files without having to compile them first. A step towards scripting.

```
ubuntu@DESKTOP-168M0IF:~$ java MyScript.java
```

#### Local-Variable Type Inference (var) for lambda parameters

The header says it all:

```
var firstName, var lastName) -> firstName + lastName
```

#### HttpClient

The HttpClient from Java 9 in its final, non-preview version.

#### Other stuff

Flight Recorder, No-Op Garbage Collector, Nashorn-Javascript-Engine deprecated etc.

### Java 12

Java 12 got a
couple [new features and clean-ups](https://www.oracle.com/technetwork/java/javase/12-relnote-issues-5211422.html), but
the only ones worth mentioning here are Unicode 11 support and a preview of the new switch expression, which you will
see covered in the next section.

### Java 13

You can find a complete feature list [here](https://www.oracle.com/technetwork/java/13-relnote-issues-5460548.html), but
essentially you are getting Unicode 12.1 support, as well as two new or improved preview features (subject to change in
the future):

#### Switch Expression (Preview)

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
      default -> throw new IllegalArgumentException("something is murky!");
  };
```

#### Multiline Strings (Preview)

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

### Java 14

#### Switch Expression (Standard)

The switch expressions that were “in preview” in versions 12 and 13, are now standardized.

```
int numLetters = switch (day) {
    case MONDAY, FRIDAY, SUNDAY -> 6;
    case TUESDAY                -> 7;
    default      -> {
        String s = day.toString();
        int result = s.length();
        yield result;
    }
};
```

#### Records (Preview)

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

Again, this is a preview feature and subject to change in future releases.

#### Helpful NullPointerExceptions

Finally NullPointerExceptions describe exactly which variable was null.

```
author.age = 35;
---
Exception in thread "main" java.lang.NullPointerException:
Cannot assign field "age" because "author" is null
```

#### Pattern Matching For InstanceOf (Preview)

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

#### Packaging Tool (Incubator)

There’s an incubating jpackage tool, which allows you to package your Java application into platform-specific packages,
including all necessary dependencies.

* Linux: deb and rpm
* macOS: pkg and dmg
* Windows: msi and exe

#### Garbage Collectors

The Concurrent Mark Sweep (CMS) Garbage Collector has been removed, and the experimental Z Garbage Collector collector
has been added.
 


### Java 15

#### Sealed Classes

The goal of sealed classes is to allow individual classes to declare which types may be used as sub-types. This also applies to interfaces and determining which types can implement them.

Sealed classes involve two new keywords — sealed and permits:

```
public abstract sealed class Person
    permits Employee, Manager {
 
    //...
}
```
In this example, we've declared an abstract class named Person. We've also specified that the only classes that can extend it are Employee and Manager. Extending the sealed class is done just as it is today in Java, using the extends keyword:
```
public final class Employee extends Person {
}

public non-sealed class Manager extends Person {
}
```

It's important to note that any class that extends a sealed class must itself be declared sealed, non-sealed, or final. This ensures the class hierarchy remains finite and known by the compiler.

This finite and exhaustive hierarchy is one of the great benefits of using sealed classes. Let's see an example of this in action:

```
if (person instanceof Employee) {
    return ((Employee) person).getEmployeeId();
} 
else if (person instanceof Manager) {
    return ((Manager) person).getSupervisorId();
}
```

Without a sealed class, the compiler can't reasonably determine that all possible sub-classes are covered with our if-else statements. Without an else clause at the end, the compiler would likely issue a warning indicating our logic doesn't cover every case.

