
# Kotlin

## What is Kotlin?

- Kotlin is an open-source statically typed programming language.
- It runs on JVM and can be used anywhere Java is used today.
- It can be used to develop Android apps, server-side apps and much more.
- Kotlin was developed by JetBrains team.
- The project was started in 2010 to develop the language and officially, first released in February 2016.
- Kotlin was developed under the Apache 2.0 license.

## Advantages of Kotlin

- Kotlin allows writing less code.
- Kotlin has a strong community.
- Kotlin is fully compatible with Java.
- Adopting Kotlin is easy.
- Kotlin development offers more safety.
- Kotlin suits for the multi-platform development.

## var & val

- var is like general variable and it's known as a mutable variable in kotlin and can be assigned multiple times.
- val is like Final variable and it's known as immutable in kotlin and can be initialized only single time.

## const vs val

- In kotlin, const and val both represents the immutability and read only values and act as final keyword in java.
- val keyword must be used to declare for run time values and const keyword must be used to declare compile time values.
- const must be used only with primitive data types not for function and constructors.

```ruby
const val fun1 = anyFunctionOrConstructor() // it is not fine
val fun2 = anyFunctionOrConstructor() // it is perfectly fine      
const val a = "My String" // it is perfectly fine
```

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
## Init Keyword

- In Kotlin, the primary constructor cannot contain any code.
- init blocks allows adding code to the primary constructor.
- The init block will execute immediately after the primary constructor.

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
:arrow_up: [__Back to Top__](README.md#flutter-interview-questions)
