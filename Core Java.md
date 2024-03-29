# Core Java

## Oops

- Object-Oriented Programming System (OOPs) is a programming concept that works on the principles of abstraction, encapsulation, inheritance, and polymorphism.
- The main purpose of Oops is to deal with real world entity using programming language.

## Why is Java said to be platform independent?

- The execution of the code does not depend upon the OS.
- It is said to be platform-independent because the java compiled code(byte code) can run on all operating systems with the help of middleware(i.e.) using JVM.  
   <p align="left">
    <img src="https://user-images.githubusercontent.com/78175168/120521028-1b276280-c3f2-11eb-9de5-a2bcc704d9a9.png"/>
   </p>

## Classes and Objects

- A class can be defined as a template (blueprint) from which objects are created.
- A class has two important things (i.e.) Properties and Methods.
- Example: If we take a car color and numberOfSeats is properties and drive(), break() is Methods.
- Objects are the basic unit of Object Oriented Programming and represents the real life entities.
- Objects is an instance of a class that excutes the class and it takes up space once the object is created.
- Objects have states and behaviors.
- For example, we can take a Car -> Car is an object.

__Creating the Class__

```ruby
class Car {
  
  int numberOfDoors = 5;
  
  void drive(){
    print('wheels start turning');
  }
    
}
```

- Where int numberOfDoors = 5 is the varaible(i.e.) Properties and void drive() is the function(i.e.) Methods

__Creating an Object in the Class__

```ruby
Car myCar = Car();
```
- where int Car = 5 is the type, myCar is the object and Car() is the new version of that class. 

## Constructor

- Constructor is a block of code that initializes the newly created object.
- Constructor resembles an instance method in java but it’s not a method as it doesn’t have a return type.
- It is called when an instance of the class is created. 
- At the time of calling constructor, memory for the object is allocated in the memory.
- It calls a default constructor if there is no constructor available in the class.
- Types -> private, default, parametrized and copy.

__Example__

```ruby
Public class MyClass {
   Int num;
   MyClass() {
      num = 10;
   }
}
```

```ruby
public class Demo {
   public static void main(String args[]) {
      MyClass t1 = new MyClass();
      System.out.println(t1.num);
   }
}
```

## What is Inheritance?

- Inheritance is the process by which objects of one class acquire the properties & methods of another class. 
- It provides code reusability. 
- It is used to achieve runtime polymorphism(i.e.) Method Overriding.
- We use extends keyword to perform inheritance.
- We can't access private members of class through inheritance.
- Types -> Single Inheritance, Mutliple Inheritance, Multiple Inheritance and Hierarchical Inheritance.

```ruby
class Calculation {
   int z;
	
   public void addition(int x, int y) {
      z = x + y;
      System.out.println("The sum of the given numbers:"+z);
   }
}

public class My_Calculation extends Calculation {
   public void multiplication(int x, int y) {
      z = x * y;
      System.out.println("The product of the given numbers:"+z);
   }
	
   public static void main(String args[]) {
      int a = 20, b = 10;
      My_Calculation demo = new My_Calculation();
      demo.addition(a, b);
      demo.multiplication(a, b);
   }
}
```

## Does Java support multiple inheritance?

- Java supports multiple inheritance by interface only since it can implement multiple interfaces but can extend only one class.

## Why Multiple Inheritance is Not Supported in Java?

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
- The whole idea behind encapsulation is to hide the implementation details from users.
- If a data member is private it means it can only be accessed within the same class.
- No outside class can access private data member (variable) of other class.
- We can use setter and getter methods to set and get the data in it.
- By providing only a setter or getter method, you can make the class read-only or write-only.

__Example__

```ruby
public class EncapTest {
   private String name;
   private int age;

   public int getAge() {
      return age;
   }

   public String getName() {
      return name;
   }

   public void setAge( int newAge) {
      age = newAge;
   }

   public void setName(String newName) {
      name = newName;
   }

}
```

```ruby
public class MainClass {

   public static void main(String args[]) {
      EncapTest encap = new EncapTest();
      encap.setName("James");
      encap.setAge(20);

      System.out.print("Name : " + encap.getName() + " Age : " + encap.getAge());
   }
}
```

## Abstraction

- Abstraction is a process of hiding the implementation details and showing only functionality to the user.
- There are two ways to achieve abstraction in java
    - Abstract class (0 to 100%)
    - Interface (100%)
- Example: By using Calculator we can Add, Substract , Multiply and Divide but we don't know what is happening internally.

## Abstract Classes

- A class which is declared with the abstract keyword is known as an abstract class in Java.
- It can have abstract and non-abstract methods (method with the body).
- If a class contain partial impementation then we should declare a class as abstract and it cannot be instantiated.
- We can't create object for abstract class.

__Example__

```ruby
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}

// Subclass (inherit from Animal)
class Elephant extends Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The elephant says: mmmmmaaa");
  }
}

class Main {
  public static void main(String[] args) {
    Elephant myElephant = new Elephant(); // Create a Elephant object
    myElephant.animalSound();
    myElephant.sleep();
  }
}
```
    
## Interfaces

- An Interface can be considered as a fully abstract class.
- It means by default all functions and properties of an interface are abstract.
- An interface in java is a blueprint of a class and is a mechanism to achieve abstraction.
- It is used to achieve abstraction and multiple inheritance in Java.
- Interfaces can have abstract methods and variables.

__Note__  
- To achieve interface in java we will use a keyword called implements.
- By default interface methods are public and abstract.
- By default interface variables are public static final.
- From JDK 1.9 onwards interface can have private methods (i.e.) We can declare private method as a static or non static.

__Example 1__

```ruby
interface A {

  // Before JDK 1.8
  public int a = 10; // public + static final
  public void sleep(); // public + abstract
  
  // From JDK 1.8
  public int a = 10; // public + static final
  public void sleep(); // public + abstract
  default void sleepOne(){}
  static void sleepTwo(){}
  
  // From JDK 1.9
  public int a = 10; // public + static final
  public void sleep(); // public + abstract
  default void sleepOne(){}
  static void sleepTwo(){}
  private void sleepThree(){}
  
}
```

__Example 2__

```ruby
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void sleep(); // interface method (does not have a body)
}

class Elephant implements Animal {
  public void animalSound() {
    System.out.println("The Elephant says: wee wee");
  }
  public void sleep() {
    System.out.println("Zzz");
  }
}

class Main {
  public static void main(String[] args) {
    Elephant myElephant = new Elephant();
    myElephant.animalSound();
    myElephant.sleep();
  }
}
```

## Can an Interface implement another Interface?

- Yes, an interface can implement another interface (and more than one), but it needs to use extends instead of Implement keyword.
- The member variable in a 100% abstract class can have any access qualifier, where in an interface they are implicitly public static final.
- If we try to implement an interface with another interface, it will throw a compile-time error in Java.

## Polymorphism

- Polymorphism is a concept by which we can perform a single action in many ways.
- The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object. 
- In Java, we use method overloading and method overriding to achieve polymorphism.
- Two types of polymorphism in Java: compile-time polymorphism and runtime polymorphism.
- Static Polymorphism also known as compile time polymorphism.
- Dynamic Polymorphism also known as runtime polymorphism

## Compiletime Polymorphism (or Static polymorphism)

- Static Polymorphism also known as compile time polymorphism.
- Static Polymorphism that is resolved during compiler time is known as static polymorphism. 
- Method overloading is an example of compile time polymorphism.

## Runtime Polymorphism (or Dynamic polymorphism)

- It is also known as Dynamic Method Dispatch. 
- Dynamic polymorphism is a process in which a call to an overridden method is resolved at runtime, thats why it is called runtime polymorphism.
- Method overriding is an example of runtime polymorphism.

## Typecasting

- Typcasting is the concept from which conversion of one data type to another data type implicitly or explicitly.

__Example__

```ruby
double myDouble = 1.1;
int myInt = (int) myDouble;
```

__Upcasting__

- If the reference variable of Parent class refers to the object of Child class, it is known as upcasting.
- In other words, Upcasting is the typecasting of a child object to a parent object.
- Upcasting can be done implicitly or explicitly.

__Example__

```ruby
class  Parent{  
   void PrintData() {  
      System.out.println("method of parent class");  
   }  
}  
  
class Child extends Parent {  
   void PrintData() {  
      System.out.println("method of child class");  
   }  
}  
class UpcastingExample{  
   public static void main(String args[]) {  
        
      Parent obj = (Parent) new Child();    
      obj.PrintData();   
   }  
}
```

__Downcasting__

- Similarly downcasting means the typecasting of a parent object to a child object.
- Downcasting cannot be done implicitly but can be done explicitly.

## Method Overloading

- If a class has multiple methods having same name but different in parameters, it is known as Method Overloading.
- There are two ways to overload the method in java -> By changing number of arguments, By changing the data type.
- Method overloading increases the readability of the program.

__Example__

```ruby
class Adder{  
static int add(int a,int b){return a+b;}  
static int add(int a,int b,int c){return a+b+c;}  
}  

class TestOverloading{  
public static void main(String[] args){  
System.out.println(Adder.add(1,1));  
System.out.println(Adder.add(1,1,1));  
}
}  
```

## Method Overriding

- If subclass (child class) has the same method as declared in the parent class, it is known as method overriding in Java.
- Method overriding is used to provide the specific implementation of a method which is already provided by its superclass.
- The method must have the same name and parameters as in the parent class.
- Method overriding is used for runtime polymorphism

__Example__

```ruby
class Vehicle{  
  void move(){
  System.out.println("Vehicle is moving");
  }  
} 

class Cycle extends Vehicle{  
  void move(){
  System.out.println("Bike is running safely");
  }  
}

class Bike extends Vehicle{  
  public static void main(String args[]){  
  Bike obj = new Bike();  
  obj.move();  
  }  
}
```

## Differences between abstract classes and interfaces

- __Type of methods:__ Interface can have only abstract methods. Abstract class can have abstract and non-abstract methods. From Java 8, it can have default and static methods   also.
- __Final Variables:__ Variables declared in a Java interface are by default final. An abstract class may contain non-final variables.
- __Type of variables:__ Abstract class can have final, non-final, static and non-static variables. Interface has only static and final variables.
- __Implementation:__ Abstract class can provide the implementation of interface. Interface can’t provide the implementation of abstract class.
- __Inheritance vs Abstraction:__ A Java interface can be implemented using keyword “implements” and abstract class can be extended using keyword “extends”.
- __Multiple implementation:__ An interface can extend another Java interface only, an abstract class can extend another Java class and implement multiple Java interfaces.
- __Accessibility of Data Members:__ Members of a Java interface are public by default. A Java abstract class can have class members like private, protected, etc.

## Super Keyword

- The super keyword in Java is a reference variable which is used to refer immediate parent class object which is applicable for variables, method and constructor.
- It is used to call superclass methods, superclass methods and superclass constructor.

__Extra points__  

- In other words, super keyword refers to the objects of super class, it is used when we want to call the superclass variables, methods and constructor through                                                     subclass objects.
- Whenever you create the instance of subclass, an instance of parent class is created implicitly which is referred by super reference variable.  

__Example__

```ruby
class Animal {

  int a = 10;
	
  public void animalSound() {
    System.out.println("The animal makes a sound");
  }
}

class Dog extends Animal {

  int a = 20;
  
  public void animalSound() {
    super.animalSound(); // using method
    System.out.println(a);
    System.out.println(super.a); // using variable
    System.out.println("The dog says: bow");
  }
}

class Cat extends Animal { 
  
  Cat() {
    super(); // using Constructor
    System.out.println("The cat says: Meowww");
  }
}

public class Main {
   public static void main(String[] args) {
      Dog myDog = new Dog(); 
      myDog.animalSound();
      Cat myCat = new Cat(); 
    
   }
}
```

## Final Keyword

- Final keyword is a non-access modifier applicable only to a variable, a method or a class.
- Final Variable -> To create constant Variable.
- Final Methods -> To Prevent Method Overriding.
- Final Classes -> To Prevent Inheritance.  

## Finally keyword

- Finally is a block of code which is used to place important code, it will be executed at the end of a try catch block regardless of whether or not an exception occurs.
- It is mainly used for closing files or a database connection.

__Example__

```ruby
public class Main { 
   public static void main(String []args) { 
      try { 
         int data = 25/5; 
         System.out.println(data);
      } catch(NullPointerException e) { 
         System.out.println(e);
      } finally { 
         System.out.println("finally block is always executed"); 
      } 
   }
}
```

## Finalize() method

- Finalize method is to clear garbage value.
- Before removing the unused object by Garbage collector it release all the connections associated with the object.
- The purpose of finalize() method is to release the resources like Database Connection and  Network Connection that is allocated by unused objects.
- By default it is the protected finalize method and it is the object class. 
- The finally block is a key tool for preventing resource leaks.

## Static Keyword

- Static means that you don't have to create an instance of the class to use the methods or variables associated with the class.
- Static is a non-access modifier applicable only to a blocks, variables, methods and nested classes.
- Static Keyword in Java is used for memory management mainly.

__Example__

```ruby
class Test {
    public static void method() {
      System.out.println("Static Keyword");
    }
}

class Main {
    public static void main(String args[]){  
       Test.method();
   }  
}
```

## Synchronized keyword

- When we start two or more threads within a program, there may be a situation when multiple threads try to access the same resource and finally they can produce unforeseen result.
- By using Synchronization keyword in a method which will allow only one thread to access the shared resource.  
- It is classified in to two categories -> Method Level Synchronization and Block Level Synchronization
- Advantage -> We can resolve data inconsistency problems
- Disadvantage -> It increases the waiting time of the thread and effects performance of the system.

 ## Difference between == and .equals() method in Java?

- Main difference between .equals() method and == operator is that one is method and other is operator.
- We can use == operators for reference comparison (address comparison) and .equals() method for content comparison. 
- In simple words, == checks if both objects point to the same memory location whereas .equals() evaluates to the comparison of values in the objects.

## Why strings are Immutable?

- Once a value is assigned to a string it cannot be changed and if changed, it creates a new object of the String. 
- This is not the case with StringBuffer.

## Instantiation, Initialization, Declaration and Assigning of an object?

- __Initialization__ is the process when values are put into the memory that was allocated. 
- This is what the Constructor of a class does when using the new keyword.
- A variable must also be initialized by having the reference to some object in memory passed to it.
- In simple terms, The new operator is followed by a call to a constructor, which initializes the new object.

```ruby
int a; //a is declared
int a = 0; //a is declared AND initialized to 0
MyObject x = new MyObject(); //x is declared and initialized with an instance of MyObject
```

- __Instantiating__ a class means to create a new instance of the class.
- It is the process when memory is allocated for an object. 
- This is what the new keyword is doing. 
- A reference to the object that was created is returned from the new keyword.

```ruby
MyObject x = new MyObject(); //we are making a new instance of the class MyObject
```
- __Declaration__ a variable means to introduce a new variable to the program and define its type and its name.

```ruby
int a; //a is declared
```
- __Assigning__ to a variable means to provide the variable with a value.

```ruby
int a = 0; //we are assigning to a; yes, initializing a variable means you assign it a value, so they do overlap!
a = 1; //we are assigning to a
```

## Serialization and De-serialization
 
- Serialization is a mechanism to convert an object into byte stream so that it can be written into a file, transported through a network or stored into database.
- De-serialization is a mechanism of converting bytes back to an object (Deserialization). 
- A class must implement java.io.Serializable interface to be eligible for serialization.
- Realtime Example -> When the account holder tries to withdraw money from the server through ATM, the account holder information like withdrawal details will be serialized and   sent to the server where the details are deserialized and used to perform operations.

## What are anonymous classes?

- An anonymous class is just as its name implies it has no name. 
- It should be used if you have to override method of class or interface.

```ruby
MyButton.setOnClickListener(new Button.OnClickListener {
       @override
          public void onClick(View view){
              //some code
          }
   });
```

## What is a singleton class in Android?

- A singleton class is a class that can have only one object(an instance of the class) at a time that can be shared all other classes.
- In other words, Singleton class in Java allows only one instance to be created and provides global access to all other classes through this single object or instance.

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


## Threads

- Threads allows a program to operate more efficiently by doing multiple things at the same time.
- Threads can be used to perform complicated tasks in the background without interrupting the main program.

## Constructors vs Methods

- Constructor does not return any value where the method may/may not return a value.
- In case constructor is not present, a default constructor is provided by java compilerand in the case of a method, no default method is provided.
- Constructor should be of the same name as that of class and Method name should not be of the same name as that of class.
- Constructor is used to initialize an object whereas method is used to exhibits functionality of an object.

## What is a deadlock in Java

- Deadlock in java is a part of multithreading.
- Deadlock describes a situation where two or more threads are blocked forever and waiting for each other.
- Deadlock can occur in a situation when a thread is waiting for an object lock, that is acquired by another thread and second thread is waiting for an object lock that is       acquired by first thread.
- A Java multithreaded program may suffer from the deadlock condition because the synchronized keyword causes the executing thread to block while waiting for the lock, or         monitor, associated with the specified object.

## What is String.intern()? When and why should it be used?

- String.intern() is used to mange memory in Java code. 
- It is used when we have duplicates value in different strings. When you call the String.intern(), then if in the String pool that string is present then the equals() method     will return true and it will return that string only.

## Garbage Collector

- Garbage collection is the process by which Android programs perform automatic memory management using several GC algorithm e.g. Mark and Sweep.
- In other words, Android garbage collection is an automatic process which removes unused objects from memory.
- If our app creates a lot of objects, then the Android run time (ART) environment will trigger garbage collection (GC) frequently.
- However, frequent garbage collection consumes a lot of CPU, and it will also pause the app.

## What is Memory Leak?

- A Memory Leak is a situation  when objects are no longer being used by the application, but the Garbage Collector is unable to remove them from working memory – because they’re still being referenced. 
- As a result, the application consumes more and more resources – which eventually leads to a fatal OutOfMemoryError.
 
 ## What is Java PriorityQueue? 
 
 - In Priority Queue, each element is having some priority and all the elements are present in a queue. 
 - The operations are performed based on the priority.
 
 ## Enum in Java

- The enum is a special "class" that represents a fixed set of constants (unchangeable variables, like final variables). 
- In Java we can create an enum class with the help of enum keyword.
- for example, if we have a variable DressSize, then it should have following values: small, medium and large.
- Java enums can have properties, functions, can implement interfaces, etc.
- The enum data type (also known as Enumerated Data Type) is used to define an enum in Java.

 ## Exception Handling

- The Exception Handling is a mechanism to handle the runtime errors so that normal flow of the application can be maintained.
- In Java, all exception classes are descendants of class Throwable.
- four keyword Types -> try, catch, finally and throw
- Types -> Checked Exception, Unchecked Exception and Errors

__Checked Exception__

- Checked exception is checked at compile time. 
- This exception type extends the Throwable class.
- Example: IOException, SQLException, FileNotFoundException, ClassNotFoundException etc.

__Unchecked Exception__

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

- Makes the code understandable.
- Makes the code maintainable for Long run.
- Makes the Project loosely coupled.
- Makes the code Testable.
- Making Changes, new Features are Easy.

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

## Event Handling

- When you press a button in your program or Android application the state of the button changes from ‘Unclicked’ to ‘Clicked’.
- This change in the state of our button is called an Event.
- The button you press is an object too (i.e.) Source is the object which generates an event. 
- In other words, a source is an object which undergoes state change.
- Listeners are also called as event handlers as they are the ones responsible to handle events occurring at the source. 
- Listeners are interfaces and different types of listeners are used according to the event.

## What is the difference between iterator and enumeration in java?

- In Enumeration we have remove() method and we can only read and traverse through a collection.
- Iterators can be applied to any collection. 
- In Iterator, we can read and remove items from a collection.

## Event Handling

- It is Changing the state of an object is known as an event. 
- Example: click on button. 
- Event handling has three main components,
- __Events__ : An event is a change in state of an object.
- __Events Source__ : Event source is an object that generates an event.
- __Listeners__ : A listener is an object that listens to the event and gets notified when an event occurs.

