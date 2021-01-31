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

## What is a singleton class in Android?

- A singleton class is a class which can create only an object that can be shared all other classes.

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
- It can be used to instantiate any objects in the class whereas methods have no such rule and is another member of the class. 
- Constructors cannot be inherited but a derived class can call the super constructor of parent class.
- this(): Constructors use this to refer to another constructor in the same class with a different parameter list.
- super(): Constructors use super to invoke the superclass's constructor.
- Methods: Instance methods on the other hand require an instance of the class to exist before they can be called, so an instance of a class needs to be created by using the     new keyword. 
- Class methods are methods which are declared as static. The method can be called without creating an instance of the class

## What is a deadlock in Java

- A deadlock occurs when a thread enters a waiting state because a requested system resource is held by another waiting process, which in turn is waiting for another resource     held by another waiting process.

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
 
 ## What is Java PriorityQueue? 
 
 - In Priority Queue, each element is having some priority and all the elements are present in a queue. 
 - The operations are performed based on the priority.
 
 ## Enum in Java
 
- While developing an application, there may arise a situation where we want a variable to have a value out of a given set of allowed values only.
- for example, if we have a variable DressSize, then it should have following values: small, medium and large.
- In Java, and in Java too, Enums help us achieve this.
- In Java we can create an enum class with the help of enum keyword.
- Java enums can have properties, functions, can implement interfaces, etc.
- The enum data type (also known as Enumerated Data Type) is used to define an enum in Java.

 ## Exception Handling

- The Exception Handling in Java is one of the powerful technique to handle the runtime errors so that normal flow of the application can be maintained.
- In other words, Exception Handling is a mechanism to handle runtime errors such as ClassNotFoundException, IOException, SQLException, RemoteException, etc.
- In Java, all exception classes are descendants of class Throwable.
- four keyword Types -> try, catch, finally and throw
- Types -> Checked Exception, Unchecked Exception and Errors

__Checked Exception__

- Checked exception is checked at compile time. 
- This exception type extends the Throwable class.
- Example: IOException, SQLException, FileNotFoundException, ClassNotFoundException etc.

__Unchecked Exception__

- The classes which inherit RuntimeException are known as unchecked exceptions.
- Unchecked exceptions are not checked at compile-time, but they are checked at runtime.
- Example:  ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException etc.

__Error__

- Error is irrecoverable.
- Example: OutOfMemoryError, VirtualMachineError, AssertionError etc.

## Type cast

- The process of converting the value of one data type (int, float, double, etc.) to another data type is known as typecasting.

```ruby
int x = 10;
byte y = (byte)x;
```

## Event-driven programming

- In Java GUI applications, a user's interaction with a component is called an event. 
- As a programmer, you can write code to do something after these events. 
- This is why Java is referred to as being event-driven.
- An application can listen for updates and changes via event listeners.

## Stack Memory

- The stack memory is a physical space (in RAM) allocated to each thread at run time. 
- It is created when a thread creates. 
- Memory management in the stack follows LIFO (Last-In-First-Out) order because it is accessible globally. 
- It stores the variables, references to objects, and partial results. 
- When Memory allocated to stack lives until the function returns. 
- If there is no space for creating the new objects, it throws the java.lang.StackOverFlowError. 
- The scope of the elements is limited to their threads. 
- The JVM creates a separate stack for each thread.

## Heap Memory

- It is created when the JVM starts up and used by the application as long as the application runs. 
- It stores objects and JRE classes.
- Whenever we create objects it occupies space in the heap memory while the reference of that object creates in the stack. 
- It does not follow any order like the stack. It dynamically handles the memory blocks. 
- It means, we need not to handle the memory manually. 
- For managing the memory automatically, Java provides the garbage collector that deletes the objects which are no longer being used. 
- Memory allocated to heap lives until any one event, either program terminated or memory free does not occur. 
- The elements are globally accessible in the application.
- It is a common memory space shared with all the threads. 
- If the heap space is full, it throws the java.lang.OutOfMemoryError. 
- The heap memory is further divided into the following memory areas:
 
## Generics 
 
- Java Generic methods and generic classes enable programmers to specify, with a single method declaration, a set of related methods, or with a single class declaration, a set    of related types, respectively.
- Generics also provide compile-time type safety that allows programmers to catch invalid types at compile time.

## Array vs ArrayList

- __Array__ is a simple fixed-size data structure which requires a size at the time of creation.
- An Array can contain both primitive data types or objects of a class depending on the definition of the array but it has a fixed size.
- __ArrayList__ is a dynamic sized data structure which doesn’t require a specific size at the time of initialization.
- An ArrayList can’t be created for primitive data types. 
- It only contains an object and it has the ability to grow and shrink dynamically.

## HashMap

- HashMap in Java in a collection class which implements Map interface. 
- It is used to store key & value pairs. Each key is mapped to a single value in the map.
- Keys are unique. 
- It means we can insert a key ‘K’ only once in a map. Duplicate keys are not allowed. 
- Though a value 'V' can be mapped to multiple keys.

## Java Annotation

- Java Annotation is a tag that represents the metadata i.e. attached with class, interface, methods or fields to indicate some additional information which can be used by java compiler and JVM.
- Annotations in Java are used to provide additional information, so it is an alternative option for XML and Java marker interfaces.
- There are several built-in annotations in Java. Some annotations are applied to Java code and some to other annotations.
- Built-In Java Annotations used in Java code -> @Override, @SuppressWarnings and @Deprecated
- Built-In Java Annotations used in other annotations -> @Target, @Retention, @Inherited and @Documented

## Difference between stack memory & heap memory?

- Heap memory is used by all the parts of the application whereas stack memory is used only by one thread of execution.
- Whenever an object is created, it’s always stored in the Heap space and stack memory contains the reference to it. 
- Stack memory only contains local primitive variables and reference variables to objects in heap space.
- Objects stored in the heap are globally accessible whereas stack memory can’t be accessed by other threads.
- Heap memory is divided into Young-Generation, Old-Generation etc, more details at Java Garbage Collection.
- Stack memory is short-lived whereas heap memory lives from the start till the end of application execution.
- When stack memory is full, Java runtime throws java.lang.StackOverFlowError whereas if heap memory is full, it throws java.lang.OutOfMemoryError: Java Heap Space error.
- Stack memory size is very less when compared to Heap memory. Because of simplicity in memory allocation (LIFO), stack memory is very fast when compared to heap memory.

## Design Pattern

- Design Patterns are already defined and provides industry standard approach to solve a recurring problem, so it saves time if we sensibly use the design pattern. 
- There are many java design patterns that we can use in our java based projects.
- Using design patterns promotes reusability that leads to more robust and highly maintainable code. 
- It helps in reducing total cost of ownership (TCO) of the software product.
- Since design patterns are already defined, it makes our code easy to understand and debug. 
- It leads to faster development and new members of team understand it easily.

## Singleton design Pattern

- The singleton design pattern is used to restrict the instantiation of a class and ensures that only one instance of the class exists in the JVM. 
- In other words, a singleton class is a class that can have only one object (an instance of the class) at a time per JVM instance.

## Linked List

- The LinkedList class of the Java collections framework provides the functionality of the linked list data structure (doubly linkedlist).
- A single node of doubly linkedlist that has 3 fields Prev, Data, and Next.
- Java Doubly LinkedList
- Each element in a linked list is known as a node. It consists of 3 fields:
    - Prev - stores an address of the previous element in the list. It is null for the first element
    - Next - stores an address of the next element in the list. It is null for the last element
    - Data - stores the actual data

## ArrayList vs LinkedList

- The LinkedList class is a collection which can contain many objects of the same type, just like the ArrayList.
- The LinkedList class has all of the same methods as the ArrayList class because they both implement the List interface.
- This means that you can add items, change items, remove items and clear the list in the same way.
- However, while the ArrayList class and the LinkedList class can be used in the same way, they are built very differently.

