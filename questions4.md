1. What is type inference in Scala?

The Scala compiler decides data types or result types of elements like variables, expressions, and objects at compile-time.

Scala infers the type for an expression fully or partially. This makes it work even when we don’t declare it explicitly. It also allows for type checking without type annotations. The compiler considers types of atomic values or subexpressions and aggregates it to decide a type for the whole expression.

For more on this, read up on Features of Scala.

2. Is Int in Scala the same as java.lang.Integer in Java?

While the two are similar in some ways, they also differ in other ways:

Differences:

Int does not implement the Comparable interface; java.lang.Integer does.
Similarities:

- They’re both classes
- They are 32-bit signed integers
- They represent integer numbers

3. What is an anonymous function?

An anonymous function in Scala is a function literal. At runtime, Scala instantiates into a function value. Since this is a way to create a function using just one line of code, we can call it lightweight. Here’s an example:
```
scala> val mul=(a:Int,b:Int)=>a*b
mul: (Int, Int) => Int = $$Lambda$1541/400146874@3aca06a3
scala> mul(3,4)
res50: Int = 12
```
4. Explain implicit parameters.

Much like default parameters, implicit parameters help us find default values. To make a parameter implicit, we can pass it to a method or a constructor and label it as implicit. So when we don’t mention the value of a parameter, the compiler searches for an implicit value defined within a scope.

In Part I, we discussed the precedence for implicit parameters.

5. What is a case class?

Scala Case classes let us model immutable data. For object construction, these classes have an apply() method to handle object construction. These classes have all vals, and so prove useful with pattern-matching. Let’s take an example.
```
scala> case class Book(title:String, author:String, ISBN: String)
defined class Book
```
6. What can you tell me about the Scala REPL?

While we often call it ripple, REPL expands to Read Evaluate Print Loop. We can access it from the command prompt by typing ‘scala’:
```
C:\Users\lifei>scala
Welcome to Scala 2.12.5 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_161).

Type in expressions for evaluation. Or try :help.

scala>
```
This is the Command Line Interface(CLI) and command-line shell for Scala, and we can execute Scala code in it as if in an interpreter. We can build and test small pieces of code in it.

7. What is a Map in Scala?

A map is a collection in Scala that holds key-value pairs. A map can only hold unique keys, but values can be repeated. We also call these hash tables. By default, maps are immutable, but we can use the scala.collection.mutable.Map class for a mutable map. This is an example:
```
scala> var m=Map("red"->0,"green"->1,"blue"->2)
m: scala.collection.immutable.Map[String,Int] = Map(red -> 0, green -> 1, blue -> 2)
```
For more on maps, read up on Maps in Scala.

8. Differentiate between arrays and lists in Scala.
```
scala> var m=Map("red"->0,"green"->1,"blue"->2)
```
We have the following differences:

Arrays are mutable; lists are immutable
Arrays are invariants; lists are covariants
In size, arrays are fixed, but lists are variable
We can modify array values later, but that is not the same with lists

9. Is Scala a pure object-oriented language?

Let’s see the object-oriented language.

There are no static members
Scala treats functions and primitives as objects
So, we can conclude that Scala is indeed purely object-oriented as a language.

10. What is a lazy val?

Scala executes a val when we define it, but executes a lazy val only when we access it the first time. We declare it using the keyword lazy:
```
scala> lazy val x=7
x: Int = <lazy>
scala> lazy val x=2+3
x: Int = <lazy>
```
Where eager evaluation is at compile-time, lazy evaluation is at run-time.\

11. How many reserved keywords of Scala can you recall?

Scala has 39 keywords-

- abstract, 
- case, 
- catch, 
- class, 
- def, 
- do, 
- else, 
- extends, 
- false, 
- final, 
- finally, 
- for, 
- forSome, 
- if, 
- implicit, 
- import, 
- lazy, 
- match, 
- new, 
- null, 
- object, 
- override, 
- package, 
- private, 
- protected, 
- return, 
- sealed, 
- super, 
- this, 
- throw, 
- trait, 
- try, 
- true, 
- type, 
- val, 
- var, 
- while, 
- with,
- yield.

Let’s learn Scala Throw Keyword

12. Is it possible to use a Scala keyword as an identifier?

While it might instinctively seem otherwise, you can use a reserved keyword as an identifier in Scala. Use backticks for this. As an example, we can use backticks on the word yield to use Java’s yield method from Thread class instead of Scala’s yield.
```
Thread.`yield`()
```
13. Is an expression the same as a statement in a Scala?

A statement is one or more operation, but an expression is a value. This means we can assign an expression to a variable, but we can’t assign a statement to the same. Examples of expressions- Scala’s if-condition, Java’s ternary operator. Examples of statements- Java’s if-condition.

Let’s revise Scala Regular expression

14. Differentiate between equals() and == in Scala. Is the latter the same as == in Java?

When we try to compare two instances with the == operator, Scala calls the object’s equals() method. We use it to check instance equality. However, in Java, we use it to check reference equality. This tells us whether two references point to the same object.

15. Explain the differences between the if-else statements for Scala and Java.

There is one main difference. This statement is an expression in Scala, but not in Java. There, we cannot assign it to a variable because it doesn’t return a value.

Scala:
```
scala> val x=3
x: Int = 3
scala> val kind= if(x%2==0) "even" else "odd"
kind: String = odd
```
Java:
```
int x=3;
String kind;
if(x%2==0)
kind=”even”;
else
kind=”odd”;
```
Learn more about Scala If-else Statements

16. How are Scala’s inner classes different from those of Java?

In Scala, an inner class is associated with the outer class’ object. In Java, however, an inner class is associated with the outer class; the inner class is a member of the outer class.

17. Is Scala expression-based or statement-based? What about Java?

Yes, Scala is expression-based. You already know everything is a value in Scala. This means all expressions and statements evaluate to a value. So, we can assign expressions, functions, closures, objects, and other entities to variables. But things aren’t the same with Java. Hence, Java is statement-based.

18. Why doesn’t Scala have the keyword ‘static’?

The team made this decision to maintain the nature of Scala as a pure object-oriented language. If they included it, we could access class members without having to create an object. That would violate the principles of OOP. Note that this means Java isn’t a purely object-oriented language.

19. Between Scala and Java, what are some features only one of them supports?

Operator overloading- Scala
Static members- Java
Primitive data types- Java
Implicits and traits- Scala
Explicit type casting- Java
break and continue statements- Java
Checked and unchecked exceptions- Java
Pattern matching- Scala
++ and — operators- Java
Let’s revise Features of Java

20. Can companion objects access private members of their companion classes?

Yes. A companion object can access its companion class’ private members, but the vice-versa is true as well.

21. How do you implement interfaces in Scala?

This is a trick question to throw you off. Scala has no interfaces. Here, we have traits instead. Refer to Traits and Trait Mixins in Scala.

22. Functions and methods are the same in Scala. Is that true?

No. While we use the same syntax to define both, there is a difference:

Methods associated with an object. So we can call it on an instance of a class, but cannot call it directly without an object. We can define it in a class or in a trait.
A function, however, doesn’t associate with a class or with a trait. We can access it without an object, and we define it in a Scala package.
Let’s learn Scala String Method

23. What are some popular MVC frameworks for developing web applications with Scala?

Here are a few names:

+ Play
+ Spray
+ Lift
+ Scalatra
24. How many public class files can you define in a Scala source file? Not more than one?

While that would be the case with Java, Scala actually lets us have as many as we want.

25. What are some default imports in Scala?

Some names:

+ java.lang package
+ scala package
+ scala.PreDef
In Java, the JVM automatically imports java.lang as the default package into each program so we don’t have to do it manually.

26. Between Java and Scala, what are some OOP concepts that only one of the languages supports?

Scala has the following OOP constructs that Java lacks:

Traits
It solves the inheritance diamond problem
And Java has these:

Interfaces
Enum
27. How many operators does Scala have?

Only one- The ‘=’ operator. No, we’re not forgetting +, -, and other such ones. Those are methods, not Scala operators. You can attribute this to operator overloading.

Let’s take an example. For the expression 5+6, + is a method in the Int class. The compiler knows that these are integers, and looks for the + method in Int. It makes a call on the object 5 as: 5.+(6), and returns 11. This is some syntactic sugar.

28. Name some IDEs that support Play and Scala-based Application Development.

Two popular IDEs that help us with our purpose are:

+ IntelliJ IDEA
+ Eclipse IDE
These IDEs have plugins for Scala. To find out how to download and install IntelliJ, read up on Scala Environment Setup.

29. Have you heard of SBT?

Yes. SBT expands to Scala Build Tool. Using this simple build tool, we can easily develop Scala-based applications. We can also use it to develop for Play and Scala applications. IntelliJ uses SBT as a build tool for its Scala plugin.

30. Okay, so what are some other tools available for this purpose?

While SBT is very popular, other common tools are Maven and Gradle.
