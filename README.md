# Preface

This is a practical guide on kotlin language. This one file can be used as your pocket reference if you had already mastered the language or a life savior for the newbies who are looking for a short and simple tutorial.


I will try to update it frequently, but you can feel free to add examples in `codes/` directory or commit changes in readme file

**NOTE:** This is exported from jupyter notebook. If you want that, mail me tbhaxor@gmail.com

# Introduction

Kotlin is a **cross-platform, statically typed, general-purpose programming** language with type inference

Every kotlin program starts from the [main function](https://kotlinlang.org/docs/reference/basic-syntax.html#program-entry-point), as demonstrated below
```kotlin
fun main(args: Array<String>) {
        // your code
}
```

**NOTE :** Since this is an interactive notebook, the `main` function part will be skipped.

# Basics

## Printing on the console

Documentation: [https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.io/println.html#println](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.io/println.html#println)


```kotlin
println("Hello World")
```

    Hello World


## Variables

Variables are used to store the value of specific type, the types supported by kotlin there in documentation

Documentation: [https://kotlinlang.org/docs/reference/basic-types.html, https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/](https://kotlinlang.org/docs/reference/basic-types.html, https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/)


```kotlin
var age: Int = 22
age
```




    22



Changing value of the variable


```kotlin
age = 30
age
```




    30



Kotlin support three types of variables
+ `var` &rarr; mutable variables, values of such variables can be changed during the program set
+ `val` &rarr; immutable variables, values of such variables can be initialized only single time


```kotlin
val i = 10
i
```




    10




```kotlin
i = 20
```

    Val cannot be reassigned


```kotlin
i
```




    10



Using underscored number literal


```kotlin
val oneMillion = 1_000_000
oneMillion
```




    1000000



### Floating Numbers

Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-float/


```kotlin
// the f means to use floating number, otherwise it will use the double and then type cast it into float
val price: Float = 44.77f;
price
```




    44.77



### Strings

Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/


```kotlin
var name: String = "Gurkirat Singh"
name
```




    Gurkirat Singh



Length of string


```kotlin
name.length
```




    14



Getting one character


```kotlin
name[0] == name.get(0)
```




    true



Comparing two strings


```kotlin
val name2 = "Gurkirat Singh"
name2
```




    Gurkirat Singh




```kotlin
name == name2
```




    true




```kotlin
name.compareTo(name2)
```




    0



Here `0` means both strings are identical

Concatenating two strings


```kotlin
name.plus(name2)
```




    Gurkirat SinghGurkirat Singh




```kotlin
name + name2
```




    Gurkirat SinghGurkirat Singh



### Arrays

Collection of similar type of data

Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-array/


```kotlin
var numbers = arrayOf(1, 2, 3, 4, 5, 6)
numbers
```




    [Ljava.lang.Integer;@728561a2



To get the value, use the index number


```kotlin
numbers[0]
```




    1




```kotlin
numbers[4]
```




    5



Getting the length of array


```kotlin
numbers.size
```




    6



Empty array of specific type


```kotlin
val emptyArray = arrayOf<Int>()
emptyArray
```




    [Ljava.lang.Integer;@303524fb




```kotlin
emptyArray.size
```




    0



## Type Conversion


```kotlin
val num1 = 1
val num2 = "2"
```

Both look identical (numbers), but the type of both the variables are not same


```kotlin
num1 + num2
```

    None of the following functions can be called with the arguments supplied: 
    public final operator fun plus(other: Byte): Int defined in kotlin.Int
    public final operator fun plus(other: Double): Double defined in kotlin.Int
    public final operator fun plus(other: Float): Float defined in kotlin.Int
    public final operator fun plus(other: Int): Int defined in kotlin.Int
    public final operator fun plus(other: Long): Long defined in kotlin.Int
    public final operator fun plus(other: Short): Int defined in kotlin.Int


```kotlin
num1 + num2.toInt()
```




    3



## Operators and Operands

Documentation: https://kotlinlang.org/docs/reference/keyword-reference.html#operators-and-special-symbols

### Arithmatic Operators


```kotlin
val num1 = 20
val num2 = 30
```

Addition


```kotlin
num1 + num2
```




    50



Subtraction


```kotlin
num2 - num1
```




    10



Multiplication


```kotlin
num1 * num2
```




    600



Division


```kotlin
num2 / num1
```




    1




```kotlin
num2.toFloat() / num1.toFloat()
```




    1.5



Finding remainder


```kotlin
num2 % num1
```




    10



### Relation Operators


```kotlin
val num1 = 20
val num2 = 30
```

Equality


```kotlin
num1 == num2
```




    false



**NOTE:** Don't misunderstand `==` with `=`. First one is called equal to operator and another is called assignment operator (evaluates and assigns the RHS value to LHS)

Less than


```kotlin
num1 < num2
```




    true




```kotlin
num2 < num2
```




    false



Greater than


```kotlin
num1 > num2
```




    false



Greater than equal to


```kotlin
num1 >= num1
```




    true



Less than equal to


```kotlin
num1 <= num1
```




    true



Not equal to


```kotlin
num1 != num2
```




    true



### Unary Operators


```kotlin
var num1 = 10
num1
```




    10



Post increment


```kotlin
num1++
num1
```




    11



Pre increment


```kotlin
++num1
num1
```




    12



Post decrement


```kotlin
num1--
num1
```




    11



Pre decrement


```kotlin
--num1
num1
```




    10



### Bitwise Operator


```kotlin
var num1 = 10
var num2 = 20
```


```kotlin
num1.toString(2)
```




    1010




```kotlin
num2.toString(2)
```




    10100



Shift left by one bit


```kotlin
num1 = num1.shl(1)
num1.toString(2)
```




    10100



Shift right by one bit


```kotlin
num1 = num1.shr(1)
num1.toString(2)
```




    1010



Bitwise or


```kotlin
num1.or(num2).toString(2)
```




    11110



Bitwise and


```kotlin
num1.and(num2).toString(2)
```




    0



Bitwise xor


```kotlin
num1.xor(num2).toString(2)
```




    11110




```kotlin
num1.and(num1).toString(2)
```




    1010



Bitwise inverse


```kotlin
num1.inv().toString(2)
```




    -1011




```kotlin
num1.inv()
```




    -11



### Logical Operators

AND operator


```kotlin
true && true
```




    true




```kotlin
false && true
```




    false




```kotlin
true && false
```




    false




```kotlin
false && false
```




    false



OR  operator


```kotlin
true || true
```




    true




```kotlin
true || false
```




    true




```kotlin
false || true
```




    true




```kotlin
false || false
```




    false



NOT Operator


```kotlin
true && !false
```




    true



# Conditionals

## IF - ELSE
Documentation: https://kotlinlang.org/docs/reference/control-flow.html#if-expression


```kotlin
var age = 18
var age2 = 14
```


```kotlin
if (age >= 18) {
    println("You are an adult")
}
else {
    println("Hey kiddo")
}
```

    You are an adult



```kotlin
if (age2 >= 18) {
    println("You are an adult")
}
else {
    println("Hey kiddo")
}
```

    Hey kiddo


## WHEN

Documentation: https://kotlinlang.org/docs/reference/control-flow.html#when-expression


```kotlin
var num = 4
```


```kotlin
when(num) {
    1 -> println("Sunday")
    2 -> println("Monday")
    3 -> println("Tuesday")
    4 -> println("Wednesday")
    5 -> println("Thursday")
    6 -> println("Friday")
    7 -> println("Saturday")
    else -> println("Number should be in between 1 and 7") // will be executed if no value matches
}
```

    Wednesday


To run same lines of code for multiple choices
```kotlin
when(variable) {
    1, 2, 3 -> println("your input is either 1 or 2 or 2")
    else -> {
        // running multiple lines
        println("This is not a joke")
        println("Enter number 1, 2, 3 only")
    }
}
```

To run same lines of code for a **range of numbers**
```kotlin
when(variable) {
    in 1..3 -> println("your input is either 1 or 2 or 2")
    else -> {
        // running multiple lines
        println("This is not a joke")
        println("Enter number 1, 2, 3 only")
    }
}
```

## FOR Loop

Documentation: https://kotlinlang.org/docs/reference/control-flow.html#for-loops


```kotlin
var numbers = arrayOf<Int>(1, 2, 3, 4, 5, 6)
```

Simple demonstration


```kotlin
for (number in numbers){
    println(number)
}
```

    1
    2
    3
    4
    5
    6


With indices


```kotlin
for ((idx, number) in numbers.withIndex()) {
    println("number '$number' is at index '$idx' in the array")
}
```

    number '1' is at index '0' in the array
    number '2' is at index '1' in the array
    number '3' is at index '2' in the array
    number '4' is at index '3' in the array
    number '5' is at index '4' in the array
    number '6' is at index '5' in the array


Range based loop


```kotlin
for (i in 1..5)
{
    println(i)
}
```

    1
    2
    3
    4
    5


Range based loop with step


```kotlin
for (i in 1..5 step 2)
{
    println(i)
}
```

    1
    3
    5


Reverse loop with step


```kotlin
for (i in 6 downTo 0 step 2)
{
    println(i)
}
```

    6
    4
    2
    0


## WHILE and DO-WHILE Loop

Documentation: https://kotlinlang.org/docs/reference/control-flow.html#while-loops


```kotlin
var num = 5
```

### While Loop


```kotlin
while (num > 0)
{
    println(num--)
}
```

    5
    4
    3
    2
    1


### Do While Loop


```kotlin
do {
    println(num--)
} while (num > 0)
```

    0


Difference between while and do-while loop: https://stackoverflow.com/a/3347010/10362396

Jump statements like `break` and `continue` are used to end and skip the following loop body.

Documentation: https://kotlinlang.org/docs/reference/returns.html#returns-and-jumps

# Functions

A function is a unit of code that performs a special task. In programming, function is used to break the code into smaller modules which makes the program more manageable.

## Declaring a function

Documentation: https://kotlinlang.org/docs/reference/functions.html#function-declarations

### Simple function


```kotlin
fun greet() {
    println("Hello User")
}
```


```kotlin
greet()
```

    Hello User


### Receiving parameters


```kotlin
fun sum(x: Int, y: Int) {
    println(x+y)
}
```


```kotlin
sum(10, 11)
```

    21


Calling function with wrong type


```kotlin
sum(10.4f, 11)
```

    The floating-point literal does not conform to the expected type Int

### Return statements


```kotlin
fun say_hello(name: String) : String {
    return "Hello, " + name
}
```


```kotlin
say_hello("John")
```




    Hello, John




```kotlin
say_hello("Dale")
```




    Hello, Dale



### Recursion

A function which **calls itself** is called as recursive function and this process of repetition is called recursion.


```kotlin
fun factorial(num: Int): Int {
    // base condition
    if (num <= 1) {
        return 1
    }
    
    // function calling itself
    return num * factorial(num - 1)
}
```


```kotlin
factorial(5)
```




    120



### Default arguments
Documentation: https://kotlinlang.org/docs/reference/functions.html#default-arguments


```kotlin
fun say_hello_default(name: String = "Guest"): String {
    return "Hello, " + name
}
```


```kotlin
say_hello_default()
```




    Hello, Guest




```kotlin
say_hello_default("Sheldon")
```




    Hello, Sheldon



### Named arguments
Documentation: https://kotlinlang.org/docs/reference/functions.html#named-arguments


```kotlin
fun say_hello_default_name(name: String = "Guest", robot: String): String {
    return "Hello, " + name + ". I am " + robot
}
```


```kotlin
say_hello_default_name(robot = "Alex")
```




    Hello, Guest. I am Alex




```kotlin
say_hello_default_name("Dale", robot = "Alice")
```




    Hello, Dale. I am Alice



## Lambda Functions

The lambda functions are the functions that are not declared, but passed immediately as an expression

Documentation: https://kotlinlang.org/docs/reference/lambdas.html#lambda-expressions-and-anonymous-functions


```kotlin
fun multiply(x: Int, y: Int, callback: (Int) -> Unit)
{
    callback(x * y)
}
```


```kotlin
var cb: (Int) -> Unit = {p -> println("The product is $p") } // lambda function
multiply(10, 20, cb)
```

    The product is 200


## Higher order functions
Function that accept functions as the parameters and can return function as a value. This is basically **implemented by the lambda functions**

Documentation: https://kotlinlang.org/docs/reference/lambdas.html#higher-order-functions

### Accepting function


```kotlin
var fn:(Int, Int) -> Int = {x, y-> x + y};

fun adder(num1: Int, num2: Int, callback: (Int, Int) -> Int): Int {
    return callback(num1, num2)
}
```


```kotlin
adder(10, 20, fn)
```




    30



## Inline function
Documentation: https://kotlinlang.org/docs/reference/inline-functions.html


```kotlin
inline fun inlineFunc(myFunc: () -> Unit): Unit {
    myFunc()
}
```


```kotlin
inlineFunc({println("Printing inside inline function")})
```

    Printing inside inline function


# Exception Handling

## Try Catch

Documentation: https://kotlinlang.org/docs/tutorials/kotlin-for-py/exceptions.html#throwing-and-catching


```kotlin
var num1 = 100
var num2 = 0
```


```kotlin
try {
    num1 / num2
} catch (e: ArithmeticException) {
    println("Attempeted divide by zero")
}
```

    Attempeted divide by zero


### Try-Catch as an Expression


```kotlin
fun toInt(v: String): Int {
    return try {
        Integer.parseInt(v)
    } catch (e: NumberFormatException) {
        0
    }
}
```


```kotlin
toInt("10")
```




    10




```kotlin
toInt("hello")
```




    0



The finally blocks runs regardless of the successful or failed execution
```kotlin
try {
    // some code
} catch (e: Exception) {
    //some execption
} finally {
    // this will run after try or catch block execution
}
```

## Throwing Exception


```kotlin
fun divMe(x: Int, y: Int): Int {
    if (y < 0){
        throw IllegalArgumentException("y should be strictly greater than 0")
    }
    
    return x / y
}
```


```kotlin
try {
    divMe(10, 0)
} catch (e: ArithmeticException) {
    print("Aborted: ")
    println(e)
} catch (e: IllegalArgumentException) {
    print("Aborted: ")
    println(e)
}
```

    Aborted: java.lang.ArithmeticException: / by zero



```kotlin
try {
    divMe(10, -20)
} catch (e: ArithmeticException) {
    print("Aborted: ")
    println(e)
} catch (e: IllegalArgumentException) {
    print("Aborted: ")
    println(e)
}
```

    Aborted: java.lang.IllegalArgumentException: y should be strictly greater than 0


# NULL Safety

Documentation: https://kotlinlang.org/docs/reference/null-safety.html#nullable-types-and-non-null-types


```kotlin
var myVar: Int = 7
myVar
```




    7




```kotlin
myVar = 10
myVar
```




    10




```kotlin
myVar = null
```

    Null can not be a value of a non-null type Int

Use `Int?` while defining the variable, so as to accept null values


```kotlin
var myVar: Int? = 7
myVar
```




    7




```kotlin
myVar = 10
myVar
```




    10




```kotlin
myVar = null
myVar
```

## Safe Casting

Documentation: https://kotlinlang.org/docs/reference/null-safety.html#safe-casts


```kotlin
var num: Int? = 19
num = null
```


```kotlin
var num2: Int? = num as? Int
num2
```


```kotlin
num = 10
```


```kotlin
var num2: Int? = num as? Int
num2
```




    10



## Elvis Operator

Documentation: https://kotlinlang.org/docs/reference/null-safety.html#elvis-operator


```kotlin
val s1: String? = null;
val s2: String? = "Hello World";
```


```kotlin
var l1: Int = if (s1 != null) s1.length else -1
l1
```




    -1




```kotlin
var l2: Int = if (s2 != null) s2.length else -1
l2
```




    11



Simplifying the above with elvis operator


```kotlin
var l1: Int = s1 ?.length ?: -1
l1
```




    -1




```kotlin
var l2: Int = s2 ?.length ?: -1
l2
```




    11



# Collections

<img src="https://kotlinlang.org/assets/images/reference/collections-overview/collections-diagram.png" style="height: 350px; width: 500px;">

## Lists

Documentation:https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-list/

### Immutable List: listOf

Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/list-of.html


```kotlin
var numbers = listOf(1, 2, "3", 4, 5)

for (number: Any in numbers) {
    println(number)
}
```

    1
    2
    3
    4
    5


List with type specification


```kotlin
var numbers = listOf<Int>(1, 2, 3, 4, 5)

for (number: Int in numbers) {
    println(number)
}
```

    1
    2
    3
    4
    5


### Mutable List: mutableListOf

Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/mutable-list-of.html


```kotlin
var list = mutableListOf<Int>()
```


```kotlin
list.isEmpty()
```




    true




```kotlin
list.size
```




    0



Adding an element


```kotlin
list.add(10)
list.size
```




    1




```kotlin
list[0]
```




    10



Adding multiple elements


```kotlin
list.addAll(listOf(20, 30, 40))
list.size
```




    4



### Arrays: arrayListOf

Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/array-list-of.html


```kotlin
var array = arrayListOf<Int>(10, 20, 30)
for(element in array) {
    println(element)
}
```

    10
    20
    30



```kotlin
array.add(100)
for(element in array) {
    println(element)
}
```

    10
    20
    30
    100



```kotlin
array[2] = -100
for(element in array) {
    println(element)
}
```

    10
    20
    -100
    100


Inserting at specific location


```kotlin
array.add(1, -200)
for(element in array) {
    println(element)
}
```

    10
    -200
    20
    -100
    100


## Map

Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-map/

### Immutable Map: mapOf 

Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/map-of.html


```kotlin
var map: Map<String, Int> = mapOf<String, Int>("ONE" to 1, "TWO" to 2)
```


```kotlin
map["ONE"]
```




    1




```kotlin
map.keys
```




    [ONE, TWO]




```kotlin
for (key in map.keys) {
    println(map[key])
}
```

    1
    2


### Mutable Map: mutableMapOf
Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/mutable-map-of.html


```kotlin
var map = mutableMapOf<Int, String>(10 to "TEN", 20 to "TWENTY")
map
```




    {10=TEN, 20=TWENTY}




```kotlin
map[10]
```




    TEN




```kotlin
map[30] = "THIRTY"
```


```kotlin
for(key in map.keys) {
    println(map[key])
}
```

    TEN
    TWENTY
    THIRTY


### HashMap

It is an implementation of the interface MutableMap

Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-hash-map/


```kotlin
var hmap: HashMap<Int, String> = HashMap<Int, String>();
// HashMap<Int, String>(initalCapacity) use this to reserve the memory while initilization
// you can add more keys later on
```


```kotlin
hmap.put(1, "Spiderman")
hmap.put(2, "Ironman")
hmap.put(3, "Black Widow")
hmap.put(4, "Ant Man")
```


```kotlin
hmap[1]
```




    Spiderman




```kotlin
hmap.get(2)
```




    Ironman




```kotlin
hmap.keys
```




    [1, 2, 3, 4]




```kotlin
for(key in hmap.keys) {
    println(hmap[key])
}
```

    Spiderman
    Ironman
    Black Widow
    Ant Man


### hashMapOf
Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/hash-map-of.html


```kotlin
var hmap = hashMapOf<Int, Int>(1 to 10, 2 to 20)
hmap.size
```




    2




```kotlin
for(key in hmap.keys) {
    println(hmap[key])
}
```

    10
    20


## Sets

Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-set/#kotlin.collections.Set

### Immutable Set: setOf
Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/set-of.html


```kotlin
var set1 = setOf(1, 2, 3, 4, 4, 2, 3)
set1
```




    [1, 2, 3, 4]




```kotlin
for(element in set1){
    println(element)
}
```

    1
    2
    3
    4



```kotlin
set1.contains(1)
```




    true




```kotlin
set1.contains(10)
```




    false



### Mutable Set: mutableSetOf
Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/mutable-set-of.html


```kotlin
val set2 = mutableSetOf<Int>()
```


```kotlin
set2.add(1)
set2.add(1)
set2.add(2)
set2.add(2)
set2.add(3)
```




    true




```kotlin
set2
```




    [1, 2, 3]




```kotlin
for(element in set2) {
    println(element)
}
```

    1
    2
    3



```kotlin
set2.remove(1)
```




    true




```kotlin
set2.remove(5)
```




    false




```kotlin
for(element in set2) {
    println(element)
}
```

    2
    3


### Hashset: hashSetOf
Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/hash-set-of.html


```kotlin
val set3 = hashSetOf<Int>(1, 2, 3, 5)
set3
```




    [1, 2, 3, 5]




```kotlin
for(el in set3) {
    println(el)
}
```

    1
    2
    3
    5


# Classes

## Basic Example
Documentation: https://kotlinlang.org/docs/tutorials/kotlin-for-py/classes.html#declaration-and-instantiation


```kotlin
class Vehicle {
    // class properties
    var speed: Int = 0
    var wheels: Int = 0
    var model: String = ""
        
    // class methods
    fun SetModel(m: String) {
        model = m
    }
    
    fun SetSpeed(s: Int) {
        speed = s
    }
}
```


```kotlin
var vehicle1 = Vehicle()
```


```kotlin
vehicle1
```




    Line_166_jupyter$Vehicle@6400abd0




```kotlin
vehicle1.model
```




    




```kotlin
vehicle1.SetModel("BMW")
```


```kotlin
vehicle1.model
```




    BMW




```kotlin
vehicle1.wheels
```




    0




```kotlin
vehicle1.wheels = 4
vehicle1.wheels
```




    4



## Nested Classes

Documentation: https://kotlinlang.org/docs/reference/nested-classes.html#nested-and-inner-classes


```kotlin
class C1 {
    
    fun ShowMe() {
        println("From Outer Class C1")
    }   
    
    class C2 {
        fun ShowMe() {
            println("From Inner Class C2")
        }
    }
}
```


```kotlin
var c1 = C1()
c1.ShowMe()
```

    From Outer Class C1



```kotlin
var c2 = C1.C2()
c2.ShowMe()
```

    From Inner Class C2


## Constructor

Documentation: https://kotlinlang.org/docs/reference/classes.html#constructors

### Primary Constructor: Default


```kotlin
class Car {
    var wheels: Int
    var model: String
    
    init {
        println("Starting the car")
        wheels = 4
        model = "BMW"
    }
    
    fun Stop() {
        println("Stopping the car")
    }
}
```


```kotlin
var car = Car()
```

    Starting the car



```kotlin
car.wheels
```




    4




```kotlin
car.Stop()
```

    Stopping the car


### Primary Constructor: Parameterized


```kotlin
class Vehicle(_wheels: Int, _model: String) {
    var wheels: Int
    var model: String
    
    init {
        println("starting")
        wheels = _wheels
        model = _model
    }
    
    fun Stop() {
        println("stopping")
    }
}
```


```kotlin
var v1 = Vehicle(4, "BMW")
var v2 = Vehicle(2, "Kawasaki Ninka")
```

    starting
    starting



```kotlin
v1.wheels
```




    4




```kotlin
v2.wheels
```




    2




```kotlin
v1.Stop()
v2.Stop()
```

    stopping
    stopping


**NOTE:** Keyword `init` can be used multiple times


```kotlin
class InitOrderDemo(name: String) {
    val firstProperty = "First property: $name"
    
    init {
        println("First initializer block that prints ${name}")
    }
    
    val secondProperty = "Second property: ${name.length}"
    
    init {
        println("Second initializer block that prints ${name.length}")
    }
}

InitOrderDemo("hello")
```

    First initializer block that prints hello
    Second initializer block that prints 5





    Line_186_jupyter$InitOrderDemo@7435796a



### Secondary Constructor

Documentation: https://kotlinlang.org/docs/reference/classes.html#secondary-constructors


```kotlin
class Person {
    var name: String;
    var age: Int;
    
    constructor(name: String, age: Int) {
        this.name = name;
        this.age = age;
    }
    
    fun whoami() {
        println("I am $name and I am $age years old.")
    }
}
```


```kotlin
var p1 = Person("John", 23)
var p2 = Person("Sarrah", 44)
```


```kotlin
p1.whoami()
```

    I am John and I am 23 years old.



```kotlin
p2.whoami()
```

    I am Sarrah and I am 44 years old.


## Visibility Modifiers

Documentation: https://kotlinlang.org/docs/reference/visibility-modifiers.html#classes-and-interfaces


```kotlin
class Person {
    private var name: String;
    
    constructor(name: String) {
        this.name = name
    }
    
    fun whoami(): String {
        return "I am $name"
    }
}
```


```kotlin
var p1 = Person("Joel")
```


```kotlin
p1.whoami()
```




    I am Joel




```kotlin
p1.name
```

    Cannot access 'name': it is private in 'Person'

## Inheritance
Documentation: https://kotlinlang.org/docs/reference/classes.html#inheritance


```kotlin
open class Vehicle {
    
    public var wheels: Int = 0;
    public var model: String = "";
    
    fun Start() {
        println("Starting")
    }
    
    fun Stop() {
        println("Stop")
    }
}
```


```kotlin
class Car: Vehicle {
    constructor(model: String, wheels: Int) {
        this.wheels = wheels
        this.model = model
    }
}
```


```kotlin
var car = Car("BMW", 4)
```


```kotlin
car.Start()
```

    Starting



```kotlin
car.model
```




    BMW




```kotlin
car.Stop()
```

    Stop


## Method Overriding
Documentation: https://kotlinlang.org/docs/reference/classes.html#overriding-methods


```kotlin
open class Vehicle {
    
    public var wheels: Int
    
    constructor(wheels: Int) {
        this.wheels = wheels
    }
    
    open fun Start() {
        println("Starting the vehicle")
    }
    
    open fun Stop() {
        println("Stopping the vehicle")
    }
}
```


```kotlin
class Car(_wheels: Int): Vehicle(_wheels) {
    
    init {
        this.wheels = _wheels;
    }
    
    override fun Start() {
        println("Starting the car")
    }
    
    override fun Stop() {
        println("Stopping the car")
    }
}
```


```kotlin
var car = Car(4)
car.wheels
```




    4




```kotlin
car.Start()
```

    Starting the car



```kotlin
car.Stop()
```

    Stopping the car


## Property Overriding
Documentation: https://kotlinlang.org/docs/reference/classes.html#overriding-properties


```kotlin
open class Shape {
    open protected val ndims: Int = 0
    
    fun getDims(): Int {
        return this.ndims
    }
}
```


```kotlin
class Rectangle : Shape() {
    override protected val ndims = 4
}
```


```kotlin
var rect = Rectangle()
```


```kotlin
rect.getDims()
```




    4




```kotlin
rect.ndims
```

    Cannot access 'ndims': it is protected in 'Rectangle'

## Abstract Class

Documentation: https://kotlinlang.org/docs/reference/classes.html#abstract-classes


```kotlin
abstract class Shape(_n: Int) {
    protected var ndims: Int
    
    init {
        this.ndims = _n
    }
    
    public fun getDims(): Int {
        return this.ndims
    }
}
```


```kotlin
class Rect: Shape(4) {
}
```


```kotlin
var rect = Rect()
rect.getDims()
```




    4



### Accessing super class from base class


```kotlin
open class Person {
    open fun sayHello() {
        println("Hello from super class")
    }
}

class Student: Person {
    constructor() : super() {}
    override fun sayHello() {
        println("Hello from sub class")
        super.sayHello()
    }
}
```


```kotlin
var student = Student()
```


```kotlin
student.sayHello()
```

    Hello from sub class
    Hello from super class


## Data Class
Documentation: https://kotlinlang.org/docs/reference/data-classes.html#data-classes


```kotlin
data class Student(var name: String, var age: Int);
```


```kotlin
var student: Student = Student("John", 22)
student
```




    Student(name=John, age=22)




```kotlin
student.name
```




    John




```kotlin
student.age
```




    22



## Sealed Class
Documentation: https://kotlinlang.org/docs/reference/whatsnew11.html#sealed-and-data-classes


```kotlin
sealed class Shape {
    data class Circle (var radius: Int)
    data class Rectangle (var width: Int, var height: Int)
    data class Square (var side: Int)
}
```


```kotlin
var c = Shape.Circle(20)
c
```




    Circle(radius=20)




```kotlin
var r = Shape.Rectangle(20, 10)
r
```




    Rectangle(width=20, height=10)




```kotlin
var s = Shape.Square(20)
s
```




    Square(side=20)



## Extension Function
Documentation: https://kotlinlang.org/docs/reference/extensions.html#extension-functions


```kotlin
class Person {}

fun Person.sayHello(): String {
    return "Hello"
}
```


```kotlin
var p = Person()
p.sayHello()
```




    Hello



## Generic Functions
Documentation: https://kotlinlang.org/docs/reference/functions.html#generic-functions


```kotlin
fun <T> Return(x: T): T {
    return x
}
```


```kotlin
Return<Int>(5)
```




    5




```kotlin
Return<String>("Hello")
```




    Hello



# Misc

## Regex
Documentation: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/-regex/


```kotlin
var str = "Hello world at 10:22!!"
```


```kotlin
var pattern = Regex("[0-9]{2}:[0-9]{2}")
```


```kotlin
pattern
```




    [0-9]{2}:[0-9]{2}




```kotlin
pattern.containsMatchIn(str)
```




    true




```kotlin
pattern.findAll(str)
```




    kotlin.sequences.GeneratorSequence@53db2a04



## Call Java from Kotlin
Documentation: https://kotlinlang.org/docs/reference/java-interop.html


```kotlin
System.out.println("Hello")
```

    Hello


Like Java, it also supports imports

## Call Kotlin from Java

Documentation: https://kotlinlang.org/docs/reference/java-to-kotlin-interop.html

_filename: main.kt_
```kotlin
fun main() {
}

fun Print() {
    println("Calling from kotlin file")
}
```

_filename: app.java_
```java
public class app
{
    public static void main() {
        MainKt.Print()
    }
}
```
