
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
