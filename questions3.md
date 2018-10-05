1.      How is a trait different from an abstract class?

A class can inherit from only one abstract class, but from multiple traits
Abstract classes are fully interoperable with Java; traits- only when they hold no implementation code
Abstract classes can have both- constructor parameters and type parameters; traits only have type parameters
2. How does Scala support both- highly scalable and high-performance applications?

Not only does Scala use the Actor Concurrency Model, it also supports multi-paradigm programming(object-oriented and functional). This lets us develop highly scalable and high-performance applications.

3.      Differentiate between a Java future and a Scala future.

There’s one main difference between java.util.concurrent.Future and scala.concurrent.Future. Working with Java’s Future, you must access results using a blocking get() method. With Scala’s future, you can attach callbacks to complete. You can also map it and monadically chain Futures together without blocking. For a Java Future, you can call the method isDone() to confirm whether a Future has completed. This lets you avoid blocking.

4.      Explain the differences between Option, Try, and Either.

Option, Try, and Either are monads. We can use them to represent computations gone awry. But how are they different? Here we go:

Options denote absence of value. We can use them when we want to perform a search. Example- database access
Try wraps runtime exceptions. Hence, we can consider it as a monadic approach to the try-catch block in Java.
Either comes in handy when we must provide more information about the failure of the computation. Eithers have two possible return types- successful/correct/expected and the error case.
5.      List some advantages of functional programming.

Functional programming has the following advantages:

- Modular
- Easier to test
- Easier to understand
- Supports reuse
- Less prone to bugs
- Supports parallelism and generalization
- Read about Scala Functions

6.      What is the equivalent type for java.lang.Object here in Scala?

Where there’s java.lang.Object in Java, we have AnyRef in Scala. This is in context of a Java Runtime Environment (JRE).

Have a look at JRE vs JVM

7.      Mention the equivalent construct for Scala’s Option in Java SE 8.

For Option in Scala, we have Optional in Java. This is a class that lets us represent existing or non-existing values. We can access it using the java.util package.

We can use these constructs to represent optional values. We can also avoid unwanted null checks and NullPointerException.

8.      Define covariance and contravariance.

A generic type is covariant if it has the same subtype relationship as its type parameter T. It is contravariant when its subtype relationship is in the reverse of that of its type parameter.

9.      Explain the Either/Left/Right design pattern in Scala.

Either is an abstract class. With it, we can represent a value of two possible kinds. The two parameters it takes are Either[A, B]. The two subtypes it has are Left and Right. Left is an instance A and Right is an instance B.

10.     Now, explain the Option/Some/None design pattern.

Option, in Scala, is an abstract class with two subclasses Some and None. Bounded collections like these can hold either one element or none. When it holds one element, it is a Some; otherwise, it is a None. While Some represents an existing value, None represents absence of a value. Here, None is an object and Some is a case class. This also lets us use them in pattern matching.

Together, these definitions form an Option/Some/None design pattern in Scala.

11.     List down predefined value types in Scala.

Scala has 9 predefined, non-nullable value types under AnyVal. These are-

Double, Float, Long, Int, Short, Byte, Unit, Boolean, and Char.

Follow the link to learn more about Scala Data Types

12.     Which design pattern does pattern matching follow in Scala?

It follows the Visitor design pattern. It is a behavioral design pattern to help perform an operation on a bunch of similar objects. Another operator that follows this design pattern is Java’s isinstanceof operator.

Learn pattern Matching in Scala 

13.     What is a Guard in a for-comprehension?

When, in a for-comprehension, we want to filter elements, we can use an if-condition. We can call this if-condition a ‘guard’. When a guard is True, Scala adds that element to a new collection. Otherwise, it performs no operation. Let’s take an example.
```
scala> val nums=List(0,1,2,3,4,5,6,7,8,9,10)
nums: List[Int] = List(0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
scala> for(num<-nums if num%3==0) yield num
res0: List[Int] = List(0, 3, 6, 9)
```
This code declares a List and adds to another List only those elements which are divisible by 3.

14.     Explain type-casting in Scala.

We can cast values in an order:

Byte-> Short-> Int-> Long-> Float-> Double

This order is unidirectional; anything else makes the compiler throw an error. It is possible to cast a Char into an Int. It is also possible to cast a reference type to a subtype.\

15.     Explain the Diamond Problem.

This takes us to multiple inheritance. The deadly diamond is when one class extends more than one trait holding the same method.

See Diamond Problem

Scala resolves this by following rules called Class Linearization. Let’s take an example.
```
scala> trait A{
    | def show(){
    | println("A's show")
    | }
    | }
defined trait A
scala> trait B extends A{
    | override def show(){
    | println("B's show")
    | }
    | }
defined trait B
scala> trait C extends A{
    | override def show(){
    | println("C's show")
    | }
    | }
defined trait C
scala> class D extends B with C{}
defined class D
scala> val d=new D()
d: D = D@72d4d9ac
scala> d.show()
C’s show
```
As you can see, the compiler prints C’s message. The compiler reads “class D extends B with C” and reads it right to left. It takes the show() method from the left-most trait, which, to it, is C.

16.     What is a Range?

Range is a kind of a collection in Scala. It is a lazy collection and we can use it to denote an ordered sequence of Integer values. To use it, we can use the class scala.Range. Here’s an example.
```
scala> 1 to 7
res4: scala.collection.immutable.Range.Inclusive = Range 1 to 7

scala> 1 until 7
res5: scala.collection.immutable.Range = Range 1 until 7

scala> for(i<-1 to 7) println(i)
1

2

3

4

5

6

7
```

17.     Is it possible to set default values for class parameters?

When a caller omits a few parameters, Scala will take in the default values if we have provided them. It then becomes optional to include these parameters in a call. It is also possible to provide default values to method parameters.
```
scala> class A(name:String="Ayushi"){}
defined class A
```

18.     What do you think is a pure function?

A pure function has no side-effects. But what does that mean? Well, even if you call it a thousand times, it will return the same outputs for respective inputs.

* is a pure function with Scala. Let’s see if this always gives us the same result.
```
scala> 3*4
res8: Int = 12

scala> 3*4
res9: Int = 12

scala> 3*4
res10: Int = 12

scala> 1*2
res11: Int = 2

scala> 3*4
res12: Int = 12
```
It does. Hence, we conclude what a pure function is.

Learn about Scala Currying Functions

19.     What are some rules for Scala named arguments?

There are two rules-

You can reorder named arguments
For a parameter list with both named and unnamed arguments, the latter must appear first. These should be in order of their parameters in the method signature.
```
scala> def show(name:String,surname:String):Unit={
    | println(name+" "+surname)
    | }
show: (name: String, surname: String)Unit
scala> show("Ayushi",surname="Sharma")
Ayushi Sharma
```

20.     How is a function different from a procedure?

A function is a computation unit and has no side effects. A procedure is a computation unit too, but has side effects.

However, both help with computation; this is how they’re similar.

21.     It is impossible to mark constructor parameters as private in Scala?

No, it isn’t. We can declare a parameter to be private if we declare it without a var or a val keyword. Then, we can only access these values within the class.

Read more about Scala constructor

22.     We have seen that traits let us implement multiple inheritance. Can traits extend other traits, though?

Yes, they can. We can extend a trait using the extends keyword. And if we make a class extend it, we can use the keyword override to implement its abstract members.

23.     Mention a way to import all classes from a package.

While we can import a single class from a package using the dot operator and the name of that class. But to avoid having to name each class that we want to import, we can rather import all classes at once. We use the underscore for this.
```
import sound._
```
This imports all classes. But we can also import some certain classes at once.
```
import sound.(Treble, Soprano, Bass}
```
24.     Can classes in Scala extend more than one class?

A class can extend only one class. So, no, a class cannot extend more than one class. However, it can have many mixins.

25.     Can you Subtype using a trait?

Absolutely. We can use a subtype of a trait where we need that trait.

26.     So, what is a mixin?

A mixin, in Scala, is a trait that we can use to compose a class. It is also true that a class can have more than one mixin. To add a mixin to a class, we use the with keyword as we have seen earlier in our tutorials.

27.     How is nesting functions helpful in Scala?

When we nest functions, it lets us structure code. This also promotes readability.

28.     What is an abstract type?

We can use the type keyword to define an abstract type in Scala. This describes element type, but only its implementation defines its actual type.

29.     Explain sealed classes in Scala.

When we mark a trait or a class as sealed, we must declare all subtypes in the same file. This way, we can make sure that we know all subtypes.
```
scala> sealed abstract class Transport
defined class Transport
scala> case class Scooter() extends Transport
defined class Scooter
scala> case class Car() extends Transport
defined class Car
scala> def show(vehicle:Transport):String=vehicle match{
    | case a: Scooter=>"Two wheels"
    | case b: Car=>"Four wheels"
    | }
show: (vehicle: Transport)String
```
30.     Can you reassign parameters for case classes?

No, we cannot, since case classes help model immutable data. Its parameters are implicitly public val. We could use vars here, but Scala discourages doing so.
