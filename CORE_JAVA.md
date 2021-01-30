# Core Java

## Oops

- Object-Oriented Programming System (OOPs) is a programming concept that works on the principles of abstraction, encapsulation, inheritance, and polymorphism.

## Why is Java said to be platform independent?

- The execution of the code does not depend upon the OS.
- It is said to be platform-independent because the java compiled code(byte code) can run on all operating systems.

## What is Inheritance?

- Inheritance is the process by which objects of one class acquire the properties & objects of another class. 
- It provides code reusability. 
- It is used to achieve runtime polymorphism.

## Does Java support multiple inheritance?

- Java supports multiple inheritance by interface only since it can implement multiple interfaces but can extend only one class.

## Why Multiple Inheritance is Not Supported in Java

- To reduce the complexity and simplify the language, multiple inheritance is not supported in java.
- Consider a case where class A extends class B and Class C and both class B and C have the same method display().
- Now java compiler cannot decide, which display method it should inherit. 
- To prevent such situation, multiple inheritances is not allowed in java.

## Access Modifiers

- Java access modifiers are used to provide access control in java.
- An access modifier restricts the access of a class, constructor, data member and method in another class.
- Java provides access control through default, private, protected and public.
- __Private:__ The access level of a private modifier is only within the class. 
- It cannot be accessed from outside the class.
- __Default:__ The access level of a default modifier is only within the package. 
- It cannot be accessed from outside the package. 
- If you do not specify any access level, it will be the default.
- __Protected:__ The access level of a protected modifier is within the package and outside the package through child class. 
- If you do not make the child class, it cannot be accessed from outside the package.
- __Public:__ The access level of a public modifier is everywhere. 
- It can be accessed from within the class, outside the class, within the package and outside the package.
- There are many non-access modifiers, such as static, abstract, synchronized, native, volatile, transient, etc.

## What is Encapsulation?

- Binding (or wrapping) code and data together into a single unit are known as encapsulation..
-	The whole idea behind encapsulation is to hide the implementation details from users.
-	If a data member is private it means it can only be accessed within the same class.
-	No outside class can access private data member (variable) of other class.
-	We can use setter and getter methods to set and get the data in it.
-	By providing only a setter or getter method, you can make the class read-only or write-only.

## Abstract Classes

- A class which is declared with the abstract keyword is known as an abstract class in Java.
- It can have abstract and non-abstract methods (method with the body).
- Abstraction is a process of hiding the implementation details and showing only functionality to the user.
- There are two ways to achieve abstraction in java
    - Abstract class (0 to 100%)
    - Interface (100%)
    
## Interfaces

- An Interface can be considered as a fully abstract class.
- It means by default all functions and properties of an interface are abstract.
- An interface in java is a blueprint of a class and is a mechanism to achieve abstraction.
- It is used to achieve abstraction and multiple inheritance in Java.
- Interfaces can have abstract methods and variables.

## Polymorphism

- Polymorphism is the ability of an object to take on many forms. 
- The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object. 
- In Java, we use method overloading and method overriding to achieve polymorphism.
- Two types of polymorphism in Java: compile-time polymorphism and runtime polymorphism.

## Method Overloading

- If a class has multiple methods having same name but different in parameters, it is known as Method Overloading.
- Method overloading increases the readability of the program.

__Points to get Rememeber:__
- Overloaded methods must change the argument list
- Overloaded methods can change the return type
- Overloaded methods can change the access modifier
- Overloaded methods can declare new or broader checked exceptions
- A method can be overloaded in the same class or in a subclass

## Method Overriding

- If subclass (child class) has the same method as declared in the parent class, it is known as method overriding in Java.
- Method overriding is used to provide the specific implementation of a method which is already provided by its superclass.
- The method must have the same name and parameters as in the parent class.

__Points to get Rememeber:__
- You can’t override a method marked public and make it protected
- You cannot override a method marked final
- You cannot override a method marked static
- Static methods cannot be overridden. 
- Overloaded methods can still be overridden.


## What is the difference between instantiation and initialization of an object?

- __Initialization__ is the process of the memory allocation, when a new variable is created. 
- Variables should be explicitly given a value, otherwise they may contain a random value that remained from the previous variable that was using the same memory space. 
- To avoid this problem, Java language assigns default values to data types.
- __Instantiation__ is the process of explicitly assigning definitive value to a declared variable.

## Super Keyword

- The super keyword in Java is a reference variable which is used to refer immediate parent class object.
- Whenever you create the instance of subclass, an instance of parent class is created implicitly which is referred by super reference variable.

__Usage of Java super Keyword__
- super can be used to refer immediate parent class instance variable.
- super can be used to invoke immediate parent class method.
- super() can be used to invoke immediate parent class constructor.

## Runtime Polymorphism

- Runtime polymorphism or Dynamic Method Dispatch is a process in which a call to an overridden method is resolved at runtime rather than compile-time.
- The overridden method is called through the reference variable of a superclass.
- __Upcasting__ -> If the reference variable of Parent class refers to the object of Child class, it is known as upcasting.

## Final keyword

- Final is a non-access modifier applicable only to a variable, a method or a class.

## What is a deadlock in Java

- A deadlock occurs when a thread enters a waiting state because a requested system resource is held by another waiting process, which in turn is waiting for another resource     held by another waiting process.
