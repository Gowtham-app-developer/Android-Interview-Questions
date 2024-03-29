# Android System

## Garbage Collector

- Garbage collection is the process by which Android programs perform automatic memory management using several GC algorithm e.g. Mark and Sweep.
- If our app creates a lot of objects, then the Android run time (ART) environment will trigger garbage collection (GC) frequently.
- Android garbage collection is an automatic process which removes unused objects from memory.
- However, frequent garbage collection consumes a lot of CPU, and it will also pause the app.

## What is JVM?

- Java Virtual Machine (JVM) is an engine that provides runtime environment to drive the Java Code or applications. 
- It converts Java bytecode into machines language. 
- JVM is a part of Java Run Environment (JRE).
- JVM in Java is responsible for allocating memory space.

   
## What is DVM?

- The Dalvik Virtual Machine (DVM) is an android virtual machine optimized for mobile devices. 
- It optimizes the virtual machine for memory, battery life and performance.
- The Java Compiler(javac) converts the Java Source Code into Java Byte-Code(.class). 
- Then DEX Compiler converts this (.class) file into in Dalvik Byte Code i.e. “.dex” file.
- Advantages – Execution is Faster, Applications are given on their own instances.

![image](https://user-images.githubusercontent.com/78175168/123641566-034fcc80-d840-11eb-9da3-fed79b6abecd.png)
    
## What is ART?

- Android Apps, written in Java, converted to byte code, packaged as apk and run on Runtime. 
- That runtime can be either DVM or ART. 
- Dalvik Virtual Machine(DVM) was the default runtime till Kitkat. 
- From Lollipop onwards, Android Runtime is the default platform for the android applications to run. 
- ART is claimed to be the fastest runtime than DVM, since ART does ahead-of-compilation which converts Android apks to odex to improve Application performance.

## What is runtime?

- In a simplest term it is a system used by operating system which takes care of converting the code that you write in a high level language like Java to machine code and understand by CPU/Processor.

## What is DEX file?

- DEX  file is a file that is executed on the Dalvik VM.
- It is the Compiled Android application code file.
- Android programs are compiled into .dex (Dalvik Executable) files, which are in turn zipped into a single .apk file on the device. 
- .dex files can be created automatically by Android, by translating the compiled applications written in the Java programming language.

## Difference between ART and Dalvik

- Approach: ART uses AOT(Ahead Of Time) approach and compiles the whole code during the installation time but the Dalvik uses JIT(Just In Time) approach and complies only a       part of the code during installation and rest of the code will be compiled dynamically.
- Booting time: As compare to Dalvik, ART takes more time to reboot because the cache is built at the first time. So, the booting is slow.
- Space: Since ART uses the AOT approach, so it needs more space during installation. While Dalvik uses the JIT approach, so for mobile phones having less storage can use the     Dalvik.
- Battery: ART increases battery performance to a large extent because of the AOT approach. While the Dalvik uses the JIT approach and this results in more battery utilization.
- Garbage Collection: ART has better garbage collection than Dalvik.
- So, DVM uses JIT and have a lot of drawbacks that were replaced by ART. So, from Android 4.4(Kitkat) ART was introduced as runtime and finally from Android 5.0(Lollipop), the   Dalvik was completely replaced by ART by Android.

## Drawbacks of ART

- Since the compilation of the code is done once, ART requires more space or storage during installation.
- The booting time is more as compared to Dalvik because it uses the concept of AOT.

## What is Multidex

- Android application (APK) files contain executable bytecode files in the form of Dalvik Executable (DEX) files, which contain the compiled code used to run your app. 
- The Dalvik Executable specification limits the total number of methods that can be referenced within a single DEX file to 65,536, including Android framework methods, 
  library methods, and methods in your own code. 
- Getting past this limit requires that you configure your app build process to generate more than one DEX file, known as a multidex configuration.

## How to reduce APK size?

- Enable proguard in your project by adding following lines to your release build type.
- Enable shrinkResources.
- Strip down all the unused locale resources by adding required resources name in “resConfigs”.
- Convert all the images to the webp or vector drawables

## What is multiple apks?

- Generating the multiple number of apks for a single application, by splitting a single apk into multiple apks, where each apk is specific for some sort of devices. 
- Multiple apk is mainly used to generate specific apks for different screen densities and different CPU architecture.

## What is ProGuard?

- ProGuard is a free java tool in Android, which helps us to do the following,
- Shrink(Minify) the code: Remove unused code in the project.
- Obfuscate the code: Rename the names of class, fields, etc.
- Optimize the code: Do things like inlining the functions.
- In short, ProGuard makes the following impact on our project,  
    - It reduces the size of the application.
    - It removes the unused classes and methods that contribute to the 64K method counts limit of an Android application.
    - It makes the application difficult to reverse engineer by obfuscating the code.
    
## What is Gradle?

- Gradle is a build system (open source) which is used to automate building, testing, deployment etc. 
- “Build.gradle” are scripts where one can automate the tasks. 
- For example, the simple task to copy some files from one directory to another can be performed by Gradle build script before the actual build process happens.

## What is Git?

- Git is an Open Source Distributed Version Control System tool designed to handle everything from small to very large projects with speed and efficiency.

## Distributed Version Control System

- Git has a remote repository which is stored in a server and a local repository which is stored in the computer of each developer.
- This means that the code is not just stored in a central server, but the full copy of the code is present in all the developers’ computers.
- Git is a Distributed Version Control System since the code is present in every developer’s computer.

## What is Firebase?

- Firebase is a NoSQL type database that makes use of sockets, which allows the client to receive information live - without having to make GET requests to the server.

## What is Lint?

- Lint is a code scanning tool provided by the Android Studio to identify, suggest and correct the wrong or the risky code present in the project.
- That errors or warnings can be of:
   - Unused variables
   - Unhanded exceptions
   - Imports that are not used in the project, and many more..
   
## DDMS 

- DDMS stands for Dalvik debug monitor server, that provide many services on the device.
- The service could include message formation, call spoofing, capturing screenshot, exploring internal threads and file systems e.t.c
- Running DDMS -> From Android studio click on Tools>Android>Android device Monitor.

## What is ADB?

- The Android Debug Bridge (ADB) is a client-server program used in Android application development. 
- The Android Debug-Bridge is part of the Android SDK and is made up of three components: a client, a daemon, and a server. 
- It is used to manage either an emulator instance or an actual Android device.

# Android Unit Testing

## Unit Testing

- Unit Testing is done to ensure that the developer would be unable to write low quality/erroneous code. 
- It makes sense to write Unit Tests before writing the actual app as then you wouldn’t have a bias towards the success of your tests, you will write tests beforehand and the     actual code will have to adhere to the design guidelines laid out by the test.

## Junit

- It is a “Unit Testing” framework for Java Applications. 
- It is an automation framework for Unit as well as UI Testing. 
- It contains annotations such as @Test, @Before, @After etc.

## Mockito

- Mockito mocks (or fakes) the dependencies required by the class being tested. 
- It provides annotations such as @Mock.
