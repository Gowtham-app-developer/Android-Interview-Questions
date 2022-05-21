
# Kotlin

## Kotlin

- It is a Statically Typed Programming Language.
- It is Officially announced for Android Development.
- It is Powerful and Easy to Use.
- It Uses JVM to execute its byte code.

:arrow_up: [__Back to Top__](README.md#kotlin)

## Why Kotlin

- To Avoid NullPointer Exception.
- It Supports Immutability (i.e.) We can use val and var.
- It Supports Oops concepts.
- Write only Less Code (i.e.) Reduces a lot of Boilerplate Code.
- It Supports Functional Programming (i.e.) Can pass Function as parameter to another function or Function can return another function.

:arrow_up: [__Back to Top__](README.md#kotlin)

## var & val

- Var is mutable and Values of the variable can be changed later.
- Val is immutable and Values of the variable cannot be changed later.
- __Note:__ DataTypes in Kotlin all are objects so it must be initialized.
- __Note:__ Try to use Float instead of Double because it consumes more memory size.

:arrow_up: [__Back to Top__](README.md#kotlin)  

## Interoperability

- We Can Call Java Functions from Kotlin and Kotlin Functions from Java using some annotations.
- We Can have both Java and Kotlin files in the same Application.
- __Example:__ Java doesn’t support default Functions but we can achieve using @JVMOverloads in Kotlin.

:arrow_up: [__Back to Top__](README.md#kotlin)

## const vs val

- In kotlin, const and val both represents the immutability and read only values and act as final keyword in java.
- val keyword must be used to declare for run time values and const keyword must be used to declare compile time values.
- const must be used only with primitive data types not for function and constructors.

```ruby
const val fun1 = anyFunctionOrConstructor() // it is not fine
val fun2 = anyFunctionOrConstructor() // it is perfectly fine      
const val a = "My String" // it is perfectly fine
```

## Tailrec [Recursive] Function

- It is mainly used to prevent Stack Overflow Exception due to the limit of Stack Memory.
- Uses Recursion in a more Optimized way. [ Recursion  means calling your own function within the function ]
- We can print countless numbers without exception.
- Prefix of tailrec keyword is used.
- Example: Fibonacci type of Applications.

__Example__

```ruby
 fun main(args: Array<String>) {

        println(getFibonacciNumber(1000, BigInteger("1"), BigInteger("0")))
    }

    private tailrec fun getFibonacciNumber(n: Int, a: BigInteger, b: BigInteger): BigInteger {

        return if (n == 0)
            b
        else
            getFibonacciNumber(n - 1, a + b, a)
    }
```

:arrow_up: [__Back to Top__](README.md#kotlin)

## Init Keyword

- In Kotlin, the primary constructor cannot contain any code.
- init blocks allows adding code to the primary constructor.
- The init block will execute immediately after the primary constructor.
- Unlike the Primary Constructor, the Secondary constructor has its own body and the primary constructor call is expected.
- We can’t declare the properties (i.e.) Val or Var in the Secondary Constructor.

__Example using Primary Constructor__

```ruby
fun main() {	
  
    var mValue = Employee ("Raja")
    mValue.mName = "Gowtham"
    
    println("The Sum is ${mValue.mName}")
    
}

class Employee(mName:String){
    
  var mName:String = "Gokul"
    
    init{
        print("The Sum is ${mName}")
    }
    
}
```
__Example using Secondary Constructor__

```ruby
fun main() {	
  
    var mValueOne = Employee ("Kholi")
    
    var mValueTwo = Employee ("Raja", 16)
    mValueTwo.mName = "Gowtham"
    
    println("The Sum is ${mValueTwo.mName}")
    
}

class Employee(var mName:String){
    
  var mVarName:String = "Ganesh"
    
    init{
        println("The Sum is ${mName}")
    }
    
    constructor(_mName:String, mAge:Int):this(_mName){
        println("The Sum is ${_mName} and ${mAge}")
    }
   
}
```
:arrow_up: [__Back to Top__](README.md#kotlin)

## Visibility Modifiers

- It Supports Public, Protected, internal and Private.
- By Default all the Classes and Functions are public in nature.
- __Public:__  We can access it anywhere (inside and even outside) the Class.
- __Private:__  We can access it only inside the Class.
- __Internal:__  We can access it only inside our module.
- __Protected:__  The Modifier Protected is not applicable for top level Function and Classes (i.e) It can be accessible only within a class or Subclass not     outside the Class.

__Example__

```ruby
fun main() {	
  
   var mPerson = Employee()
   
   var mStudent = Student()
   println(mStudent.mValueOne)
   // println(mStudent.mValueTwo)
   // println(mStudent.mValueThree)
   println(mStudent.mValueFour)
    
}

open class Person{
  
    public var mValueOne: String = "Data_1"
    private var mValueTwo: String = "Data_2"
    protected var mValueThree: String = "Data_3"
    internal var mValueFour: String = "Data_4"
   
}

class Employee : Person() {
    
    init{
        println(mValueOne)
        // println(mValueTwo)
        println(mValueThree)
        println(mValueFour)
    }
   
}

class Student {
    
    public var mValueOne: String = "StuData_1"
    private var mValueTwo: String = "StuData_2"
    protected var mValueThree: String = "StuData_3"
    internal var mValueFour: String = "StuData_4"
   
}
```  
:arrow_up: [__Back to Top__](README.md#kotlin)  

## Abstract Class

- By default all the abstract Properties are "open" in nature.
- Abstract Classes are partially defined classes which are declared using abstract keywords.
- It can have both abstract and non-abstract methods (method with the body).
- If a class contains partial implementation then we should declare a class as abstract and it cannot be instantiated.
- If we define any properties or methods in abstract class then we must override that properties or methods in the sub class.

__Example__

```ruby
fun main() {	
  
  var mStudent = Student()
	mStudent.myabstractMethod()
    
}

abstract class Person{
  
    abstract fun myabstractMethod()
   
}

class Student: Person(){
    
   override
   fun myabstractMethod(){
       println("Printed")
   }
   
}
```  
:arrow_up: [__Back to Top__](README.md#kotlin) 

## Null safety in Kotlin

- Kotlin's type system is aimed at eliminating the danger of null references from code.
- Types -> Nullable Types and Non-Nullable Types

__Nullable Types__

- Nullable types are declared by putting a ? behind the String.

```ruby
var name: String? = "Android"  
name = null
```

__Non Nullable Types__

- Non nullable types are normal strings which are declared as String.

```ruby
val name: String = null // compile error  
```

__Null checks(!!)__

- The null check operator !! is used to inform the compiler that the property or variable is null or not. 
- If it is null then it will throw some NullPointerException.

```ruby
studentA!!.giveGoodies() //works fine if studentA is not null
```

__Safe call (?.)__

- In the below example, If any of the value is null i.e. if either of studentA, courseName, instructor is null then the whole expression will return null.

```ruby
studentA?.courseName?.instructor?.name 
```

__Safe call (?.) vs Null checks(!!)__

- The basic difference between the Safe call and Null check is that we use Null checks (!!) only when we are confident that the property can’t have a null value. 
- If we are not sure that the value of the property is null or not then we prefer to use Safe calls(?.).

__Elvis Operator (?:)__

- Elvis operator (?:) is used to return the not null value even the conditional expression is null. 
- It is also used to check the null safety of values.

```ruby
var name: String? = null  
var company: String? = "May be declare nullable string"  
var nameLength:  Int = name ?.length ?: -1  
var companyLength:  Int = company ?.length ?:  -1  
```

