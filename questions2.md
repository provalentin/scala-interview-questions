1.      What is ofDim in Scala?

ofDim() is a method in Scala that lets us create multidimensional arrays. Since these let us store data in more than one dimension, we can store data like in a matrix. Let’s take an example.
```bash
scala> import Array.ofDim
import Array.ofDim
scala> var a=ofDim[Int](3,3)
a: Array[Array[Int]] = Array(Array(0, 0, 0), Array(0, 0, 0), Array(0, 0, 0))
scala> var k=1
k: Int = 1
scala> for(i<-0 to 2){
    | for(j<-0 to 2){
    | a(i)(j)={i+k}
    | k+=1
    | }
    | k-=1
    | }
scala> a
res12: Array[Array[Int]] = Array(Array(1, 2, 3), Array(4, 5, 6), Array(7, 8, 9)).
```

2.      What do you have to say about exception propagation in Scala?

When a function experiences an exception, it looks for a handler to deal with it. When it fails to find one, it searches for one in the caller method. Failing there, it looks for yet another in the next caller in the chain. Whenever it does find a handler, it makes it catch the exception. This is exception propagation.

Read Scala Functions

3.      What is a BitSet?

A bitset is a set of non-negative integers depicted as arrays. These arrays are variable in size and packed into 64-bit words. The largest number in a bitset determines its memory footprint. Let’s take an example.

```shell-session
scala> import scala.collection.immutable._
import scala.collection.immutable._
scala> var nums=BitSet(7,2,4,3,1)
nums: scala.collection.immutable.BitSet = BitSet(1, 2, 3, 4, 7)
scala> nums+=9  //Adding an element
scala> nums
res14: scala.collection.immutable.BitSet = BitSet(1, 2, 3, 4, 7, 9)

scala> nums-=4  //Deleting an element
scala> nums
res16: scala.collection.immutable.BitSet = BitSet(1, 2, 3, 7, 9)

scala> nums-=0  //Deleting an element that doesn’t exist
scala> nums
res18: scala.collection.immutable.BitSet = BitSet(1, 2, 3, 7, 9)
```
4.      What is a vector in Scala?

A vector is a general-purpose data structure that is immutable. We can use it when we want to hold a huge number of elements and want random access to them. This data structure extends the trait IndexedSeq and the abstract class AbstractSeq.
```bash
scala> import scala.collection.immutable._
import scala.collection.immutable._
scala> var v1=Vector.empty
v1: scala.collection.immutable.Vector[Nothing] = Vector()
scala> var v2=Vector(7,2,4,3,1)
v2: scala.collection.immutable.Vector[Int] = Vector(7, 2, 4, 3, 1)
scala> var v3:Vector[Int]=Vector(8,2,6,5,9)
v3: scala.collection.immutable.Vector[Int] = Vector(8, 2, 6, 5, 9)
scala> v3=v3 :+7  //Adding a new element
v3: scala.collection.immutable.Vector[Int] = Vector(8, 2, 6, 5, 9, 7)
scala> v2++v3  //Merging two vectors
res19: scala.collection.immutable.Vector[Int] = Vector(7, 2, 4, 3, 1, 8, 2, 6, 5, 9, 7)

scala> v3.reverse  //Reversing a vector
res20: scala.collection.immutable.Vector[Int] = Vector(7, 9, 5, 6, 2, 8)

scala> v3.sorted  //Sorting a vector
res21: scala.collection.immutable.Vector[Int] = Vector(2, 5, 6, 7, 8, 9)
```
In results 20 and 21, we do not assign the expression to any variable, so not that this doesn’t change the original vectors.

5.      Explain streams in Scala.

A stream is a lazy list as it evaluates elements only when it needs to. This lazy computation enhances program performance.
```sh
scala> val stream=177#::199#::69#::Stream.empty
stream: scala.collection.immutable.Stream[Int] = Stream(177, ?)
Since we don’t need the second element yet, Scala doesn’t evaluate it.

scala> val stream1=(1 to 7).toStream
stream1: scala.collection.immutable.Stream[Int] = Stream(1, ?)
scala> stream.head
res22: Int = 177

scala> stream.map{_*2}
res24: scala.collection.immutable.Stream[Int] = Stream(354, ?)
```
Learn Scala Arrays and Multidimensional Arrays in Scala

6.      What are the advantages of Scala?

Among various other benefits of the language, here are a few:

It is highly scalable
It is highly testable
It is highly maintainable and productive
It facilitates concurrent programming
It is both object-oriented and functional
It has no boilerplate code
Singleton objects are a cleaner solution than static
Scala arrays use regular generics
Scala has native tuples and concise code
For a detailed piece on its benefits, read up on Advantages of Scala.

7.      Who designed Scala? Which is the latest version?

At the time of writing, Scala 2.12.6 is the latest version. The interviewer may ask you this to find out whether you keep yourself updated. Martin Odersky, a German computer scientist, began designing it in 2001 at EPFL, Switzerland.

8.      How is Val different from var in Scala?

In this language, val is a value and var is a variable. These are two different keywords for declaring immutable and mutable entities respectively. This means that you can always reassign a var, but trying to do that to a val makes the compiler throw an error.
```shell
scala> val c=7
c: Int = 7
scala> c=8
<console>:19: error: reassignment to val
      c=8
       ^
scala> var c=7
c: Int = 7
scala> c=8
c: Int = 8
```
9.      Why do we need App in Scala?

App is a helper class that holds the main method. We can have our classes extend App to render executable code:
```console
scala> object Hello extends App{
    | println("Hello")
    | }
defined object Hello
```
With this code, our object Hello inherits the main method from the App trait.

10.     How is a class different from an object?

A class is a blueprint, a definition. In terms of methods and compositions of other types, it defines a type. An object, however, is a singleton. It is a unique instance of a class. Every object in your code has an anonymous class for it. Where in Java, you would use a class with static members, you use an object in Scala.


11.     How do the terms ‘Null’, ‘Nil’, ‘None’, and ‘Nothing’ differ in Scala?

While they appear similar, the mentioned terms are slightly different in their behaviors. Here’s how:

Null represents the absence of value. It depicts the absence of type information for complex types inherited from AnyRef.
Nil denotes the end a List.
None is the value of an Option with no value in it.
Nothing is the lowest type in the entire type system. All values under AnyVal and AnyRef fall under this. A method that throws an exception uses Nothing as a return type.
12.     What is a monad in Scala?

A monad is something to which we can pass functions and manipulate the underlying object’s data. We don’t need to manipulate the object directly. Hence, a monad is an object that wraps another.

13.     Differentiate a Scala function from a Java method.

In Scala, a function is also a value. Unlike in Java, we can assign it to vals and vars, and also return it from another function. Check Higher-Order Functions in Scala. Since Java 8, we can use lambda expressions to use functions as first-class objects. So, we can pass functions to methods.

14.     Explain vararg arguments.

With varargs, we can pass a variable number of arguments to a method.
```
scala> def func(arg:String*)=arg.mkString(", ")
func: (arg: String*)String
scala> func("red","green","blue")
res28: String = red, green, blue
```
15.     What do you know about traits in Scala?

A trait is like a partially implemented interface that can hold abstract and non-abstract methods. They’re like Java interfaces; that is what Scala compiles them into. Let’s take an example.

Learn more about Scala trait
```
scala> trait Hello{
    | def sayhello()
    | }
defined trait Hello
warning: previously defined object Hello is not a companion to trait Hello.
```
Companions must be defined together; you may wish to use: paste mode for this.
```
scala> class A extends Hello{
    | def sayhello(){
    | println("Hello")
    | }
    | }
defined class A
scala> var a=new A()
a: A = A@10e595ed
scala> a.sayhello()
Hello
```
16.     What is an Option in Scala?

A Scala Option is a kind of a container. It can hold zero or one element of a type. When it holds a value, it holds Some[T]; otherwise, it holds a None object, as we discussed in the previous question.
```
scala> val o:Option[Int]=Some(7)
o: Option[Int] = Some(7)
scala> val o1:Option[Int]=None
o1: Option[Int] = None
```
17.     Is a case class the same as a regular class in Scala?

No, these aren’t synonyms. Here are a few important characteristics of a Scala case class:

They support pattern-matching
To create an instance of a case class, you don’t need new
Scala automatically generates methods like equals(), hashcode(), and toString() for case classes
For all constructor arguments for a case class, Scala automatically generates accessor methods
For more on case classes, read up on Case Classes in Scala.

18.     What is tail-recursion in Scala?

Recursion is when a function makes a call to itself. When we place this call as the last action performed in the function, we can call the function tail-recursive.
```
scala> def factorial(n:Int):Int={
    | if(n==1) return 1
    | n*factorial(n-1)
    | }
factorial: (n: Int)Int
scala> factorial(5)
res30: Int = 120
```
19.     What is a higher-order function in Scala?

This is a feature of Scala. A higher-order function is one that takes another as a parameter, or that returns a function.
```
scala> def func1(s:String){
    | println("I love "+s)
    | }
func1: (s: String)Unit
scala> def func2(f:String=>Unit,s:String){
    | f(s)
    | }
func2: (f: String => Unit, s: String)Unit
scala> func2(func1, "pizza")
I love pizza
```
20.    Explain the working of yield in Scala.

Used with a loop, yield produces a value for each iteration. Another way to do is to use map/flatMap and filter with nomads.
```
scala> for(i<-1 to 4) yield i*3
res35: scala.collection.immutable.IndexedSeq[Int] = Vector(3, 6, 9, 12)
```

21.     Prove that Scala is a language statically/strongly typed.

Since the compiler performs type checking at compile time instead of runtime, it lets the developer notice and resolve errors at the compile time itself. Hence, we can say that it is strongly and statically typed. Read up on type inference in Features of Scala.

Learn Scala Map 

22.     How do you use Scala to append to a List?

For this purpose, we use the single value ‘:+’.
```
scala> var a=List.empty[String]
a: List[String] = List()
scala> a :+="red"
scala> a :+="green"
scala> a :+="blue"
scala> a
res40: List[String] = List(red, green, blue)

//And now, appending a List to this
scala> a++=List("golden","bronze")
scala> a
res42: List[String] = List(red, green, blue, golden, bronze)
```


23.     Are concurrency and parallelism the same thing? Explain.

When we take a task and break it into subtasks to execute at one time by multiple threads, we call it parallelism. Concurrency, however, is when multiple computations execute sequentially; this is during overlapping time periods. When we avoid access to a mutable state by multiple threads at a time, it is concurrency. Sometimes, actors can concurrent as well as parallel. Node.js is a single-threaded implementation yet is concurrent because of its event loop. An example of parallelism is parallel collections.

24.     Explain different types of identifiers in Scala.

We have four kinds of identifiers in Scala.

- Alphanumeric Identifiers

These contain letters, underscores, and digits, but only begin with a letter or with an underscore. We name them in camel case. Here are a few examples: ab12, myVal, Pi.

- Operator Identifiers

These contain operator characters except these- ( ) [ ] { } ‘ ” _ . , ; , `. Some valid examples are: +  => <?> ::: .

- Mixed Identifiers

These contain an alphanumeric identifier, an underscore, and also an operator identifier. Here are some valid examples: myVar_=, unary_+.

- Literal Identifiers

These contain an arbitrary string enclosed in backticks(`). Some valid examples are: `class`, `Hello, World!`.

25.     Is Scala compatible with Java? Explain.

We’ve seen that both Scala and Java work on the JVM on the backend. Well, Scala classes are Java classes and Java classes are Scala classes too. So you can call a Java method from a Scala method, and vice-versa. You can also extend classes from one language in another. However, features like traits in Scala have no equivalents in Java.

Have a look at Scala vs Java

26.     What is a closure in Scala?

A closure in Scala is a function whose value depends on variables declared outside of it. Let’s take an example.
```
scala> var c=5
c: Int = 5
scala> val mul2=(a:Int,b:Int)=>(a+b)*c
mul2: (Int, Int) => Int = $$Lambda$1533/239864031@6d90e705
scala> mul2(2,3)
res45: Int = 25

scala> c=7
c: Int = 7
scala> mul2(2,3)
res46: Int = 35
```
In this example, mul2 reads the new value of ‘c’ when we call it a second time.

For more on closures, refer to Closures in Scala.

27.     Explain implicit parameter precedence.

The compiler doesn’t randomly look for implicits in your code; it follows the following precedence:

- Locally declared implicits
- Imported implicits
- Outer scope (ex- a class for a method)
- Inheritance
- Package object
- Implicit scope like companion objects

28.     What is a lens in Scala?

A lens is an abstraction from functional programming. It makes updating complex immutable nested objects easier for us.

For lenses, we have three kinds of available implementations:

- scalaz.Lens
- Quicklens- Has more functionality than a Sauron
- Sauron

29.     Consider for-comprehensions in Scala. What are they syntactic sugars for?

A for-comprehension is one way to carry out the composition of operations on monads. We can replace it with a foreach or a map/flatMap and filter.

30.     What is function currying in Scala?

With Scala currying, we can take a function that takes multiple arguments and turn it into a series of functions that take single arguments each. These come in handy working with higher-order functions. With this, we can also fill in only the arguments we have yet.
```
scala> def mul(a:Int,b:Int)=a*b
mul: (a: Int, b: Int)Int
scala> mul(3,4)
res48: Int = 12
```
We can define it as follows:
```
scala> def mul(a:Int)(b:Int)=a*b
mul: (a: Int)(b: Int)Int
scala> val mid=mul(3)(_)
mid: Int => Int = $$Lambda$1540/90644757@43fe3f7
scala> mid(4)
res49: Int = 12
```
