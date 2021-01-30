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
