# Core Java

## Oops

- Object-Oriented Programming System (OOPs) is a programming concept that works on the principles of abstraction, encapsulation, inheritance, and polymorphism.

## Why is Java said to be platform independent?

- The execution of the code does not depend upon the OS.
- It is said to be platform-independent because the java compiled code(byte code) can run on all operating systems.

## Classes and Objects

- A template (blueprint) for creating objects (the real thing) that we're going to showing in our app.
- A class has two important things (i.e.) Properties and Methods.
- Example: If we take a car color and numberOfSeats is properties and drive(), break() is Methods.
- It is a basic unit of Object Oriented Programming and represents the real life entities.
- For example, we can take a Car -> Car is an object.

## Constructor

- Constructor is a block of code that initializes the newly created object.
- Constructor resembles an instance method in java but it’s not a method as it doesn’t have a return type.
- It is called when an instance of the class is created. 
- At the time of calling constructor, memory for the object is allocated in the memory.
- It calls a default constructor if there is no constructor available in the class.

## What is Inheritance?

- Inheritance is the process by which objects of one class acquire the properties & methods of another class. 
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

## Can an Interface implement another Interface?

- Yes, an interface can implement another interface (and more than one), but it needs to use extends, rather than implements keyword and while you can not remove methods from     parent interface, you can add new ones freely to your sub-interface.

## Polymorphism

- Polymorphism is the ability of an object to take on many forms. 
- The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object. 
- In Java, we use method overloading and method overriding to achieve polymorphism.
- Two types of polymorphism in Java: compile-time polymorphism and runtime polymorphism.
- Static Polymorphism also known as compile time polymorphism.
- Dynamic Polymorphism also known as runtime polymorphism

## Compiletime Polymorphism (or Static polymorphism)

- Polymorphism that is resolved during compiler time is known as static polymorphism. 
- Method overloading is an example of compile time polymorphism.

## Runtime Polymorphism (or Dynamic polymorphism)

- It is also known as Dynamic Method Dispatch. 
- Dynamic polymorphism is a process in which a call to an overridden method is resolved at runtime, thats why it is called runtime polymorphism. 

## Upcasting 

- If the reference variable of Parent class refers to the object of Child class, it is known as upcasting.

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

## Differences between abstract classes and interfaces

- __Type of methods:__ Interface can have only abstract methods. Abstract class can have abstract and non-abstract methods. From Java 8, it can have default and static methods   also.
- __Final Variables:__ Variables declared in a Java interface are by default final. An abstract class may contain non-final variables.
- __Type of variables:__ Abstract class can have final, non-final, static and non-static variables. Interface has only static and final variables.
- __Implementation:__ Abstract class can provide the implementation of interface. Interface can’t provide the implementation of abstract class.
- __Inheritance vs Abstraction:__ A Java interface can be implemented using keyword “implements” and abstract class can be extended using keyword “extends”.
- __Multiple implementation:__ An interface can extend another Java interface only, an abstract class can extend another Java class and implement multiple Java interfaces.
- __Accessibility of Data Members:__ Members of a Java interface are public by default. A Java abstract class can have class members like private, protected, etc.

## Super Keyword

- The super keyword in Java is a reference variable which is used to refer immediate parent class object.
- Whenever you create the instance of subclass, an instance of parent class is created implicitly which is referred by super reference variable.

__Usage of Java super Keyword__
- super can be used to refer immediate parent class instance variable.
- super can be used to invoke immediate parent class method.
- super() can be used to invoke immediate parent class constructor.

## Final keyword

- Final is a non-access modifier applicable only to a variable, a method or a class.
- Final Variable -> To create constant Variable.
- Final Methods -> Prevent Method Overriding.
- Final Classes -> Prevent Inheritance

 ## Difference between == and .equals() method in Java?

- We can use == operators for reference comparison (address comparison) and .equals() method for content comparison. 
- In simple words, == checks if both objects point to the same memory location whereas .equals() evaluates to the comparison of values in the objects.

## Why strings are Immutable?

- Once a value is assigned to a string it cannot be changed and if changed, it creates a new object of the String. 
- This is not the case with StringBuffer.

## What is the difference between instantiation, initialization and Declaration of an object?

- __Initialization__ is the process when values are put into the memory that was allocated. 
- This is what the Constructor of a class does when using the new keyword.
- A variable must also be initialized by having the reference to some object in memory passed to it.
- __Instantiation__ is the process when memory is allocated for an object. 
- This is what the new keyword is doing. 
- A reference to the object that was created is returned from the new keyword.
- __Declaration__ is the process when you state to the program that there will be an object of a certain type existing and what the name of that object will be.

## Static variables

- The Variables that have only one copy per class are known as static variables. 
- They are not attached to a particular instance of a class but rather belong to a class as a whole.
- A static variable is associated with the class as a whole rather than with specific instances of a class. 
- Non-static variables take on unique values with each object instance.

## Serialization and De-serialization
 
- It is a mechanism to convert an object into byte stream so that it can be written into a file, transported through a network or stored into database.
- De-serialization is just a vice versa.
- In simple words serialization is converting an object to stream of bytes and de-serialization is rebuilding the object from stream of bytes. 
- Java Serialiation API provides the features to perform seralization & de-serialization.
- A class must implement java.io.Serializable interface to be eligible for serialization.

## Final modifier

- Final modifiers - once declared cannot be modified.
- A blank final variable in Java is a final variable that is not initialized during declaration.
    - final Classes- A final class cannot have subclasses.
    - final Variables- A final variable cannot be changed once it is initialized.
    - final Methods- A final method cannot be overridden by subclasses.
    
## Finalize keyword

- Finalize is a method used to perform clean up processing just before object is garbage collected.

## Finally keyword

- Finally is a code block and is used to place important code, it will be executed whether exception is handled or not.


## Difference between Encapsulation & Abstraction?

- Abstraction focuses on the outside view of an object (i.e. the interface)
- Encapsulation (information hiding) prevents clients from seeing it’s inside view.
- Abstraction solves the problem in the design side while Encapsulation is the Implementation.


## Constructors vs Methods?

- Constructors must have the name as the class name and does not have a return type. 
- It can be used to instantiate any objects in the class whereas methods have no such rule and is another member of the class. Constructors cannot be inherited but a derived - - class can call the super constructor of parent class.
- this(): Constructors use this to refer to another constructor in the same class with a different parameter list.
- super(): Constructors use super to invoke the superclass's constructor.
- Methods: Instance methods on the other hand require an instance of the class to exist before they can be called, so an instance of a class needs to be created by using the     new keyword. 
- Class methods are methods which are declared as static. The method can be called without creating an instance of the class

## What is a deadlock in Java

- A deadlock occurs when a thread enters a waiting state because a requested system resource is held by another waiting process, which in turn is waiting for another resource     held by another waiting process.

## What are anonymous classes?

- An anonymous class is just what its name implies -- it has no name. 
- It combines the class declaration and the creation of an instance of the class in one step. 
- Since anonymous classes have no name, objects can not be instantiated from outside the class in which the anonymous class is defined. 
- In fact, an anonymous object can only be instantiated from within the same scope in which it is defined.

__Rules:__

- An anonymous class must always extend a super class or implement an interface but it cannot have an explicit extends or implements clause.
- An anonymous class must implement all the abstract methods in the super class or the interface.
- An anonymous class always uses the default constructor from the super class to create an instance.

```ruby
MyButton.setOnClickListener(new Button.OnClickListener {
       @override
          public void onClick(View view){
              //some code
          }
   });
```


## What is String.intern()? When and why should it be used?

- String.intern() is used to mange memory in Java code. 
- It is used when we have duplicates value in different strings. When you call the String.intern(), then if in the String pool that string is present then the equals() method     will return true and it will return that string only.

## Garbage Collector

- Garbage collection is the process by which Android programs perform automatic memory management using several GC algorithm e.g. Mark and Sweep.
- If our app creates a lot of objects, then the Android run time (ART) environment will trigger garbage collection (GC) frequently.
- Android garbage collection is an automatic process which removes unused objects from memory.
- However, frequent garbage collection consumes a lot of CPU, and it will also pause the app.

## What is Memory Leak?

- A Memory Leak is a situation when there are objects present in the heap that are no longer used, but the garbage collector is unable to remove them from memory and, thus they are unnecessarily maintained.

## What is a singleton class in Android?

A singleton class is a class which can create only an object that can be shared all other classes.

```ruby
private static volatile RESTService instance;
 protected RESTService(Context context) {
     super(context);
 }
 
 public static RESTService getInstance(Context context) {
 if (instance == null) {
    synchronized (RESTService.class) {
       if (instance == null) instance = new RESTService(context);
         }
     }
     return instance;
 }
 ```
 
 ## What is Java PriorityQueue? 
 
 - In Priority Queue, each element is having some priority and all the elements are present in a queue. 
 - The operations are performed based on the priority.
 
 ## Enum in Java
 
- While developing an application, there may arise a situation where we want a variable to have a value out of a given set of allowed values only.
- for example, if we have a variable DressSize, then it should have following values: small, medium and large.
- In Kotlin, and in Java too, Enums help us achieve this.
- In Kotlin we can create an enum class with the help of enum keyword.
- Kotlin enums can have properties, functions, can implement interfaces, etc.
- The enum data type (also known as Enumerated Data Type) is used to define an enum in Kotlin.

 ## Exception Handling
 
 ## ArrayList vs HashMap in Java
 ## Annotation
 ## Ternary Operator
 ## Hash Map
 ## List and Array
 ## Linked List
 ## Generics
## Type cast
## Difference between stack memory & heap memory?
## Design Pattern

