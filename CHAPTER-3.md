# Android System Internal

# Garbage Collector

- Garbage collection is the process by which Android programs perform automatic memory management using several GC algorithm e.g. Mark and Sweep.
- Android garbage collection is an automatic process which removes unused objects from memory. However, frequent garbage collection consumes a lot of CPU, and it will also       pause the app.

# What is JVM?

- Java Virtual Machine (JVM) is an engine that provides runtime environment to drive the Java Code or applications. 
- It converts Java bytecode into machines language. 
- JVM is a part of Java Run Environment (JRE).
- JVM in Java is responsible for allocating memory space.

   
# What is DVM?

- The Dalvik Virtual Machine (DVM) is an android virtual machine optimized for mobile devices. It optimizes the virtual machine for memory, battery life and performance.
- The Java Compiler(javac) converts the Java Source Code into Java Byte-Code(.class). Then DEX Compiler converts this (.class) file into in Dalvik Byte Code i.e. “.dex” file.
- Advantages – Execution is Faster, Applications are given on their own instances.
     
# What is ART?

- ART is the new Android Runtime. 
- Android Runtime has replaced DVM since Android Lollipop. 
- ART uses Ahead of Time Approach (AOT) instead of JIT.
- Using AOT, the dex files are compiled before they are needed. 
- Usually, they are done at installation time only and then stored in phone storage.

# What is runtime?

- In a simplest term it is a system used by operating system which takes care of converting the code that you write in a high level language like Java to machine code and understand by CPU/Processor.

# What is DEX file?

- DEX  file is a file that is executed on the Dalvik VM.
- It is the Compiled Android application code file.
- Android programs are compiled into .dex (Dalvik Executable) files, which are in turn zipped into a single .apk file on the device. 
- .dex files can be created automatically by Android, by translating the compiled applications written in the Java programming language.

# Difference between ART and Dalvik

- Approach: ART uses AOT(Ahead Of Time) approach and compiles the whole code during the installation time but the Dalvik uses JIT(Just In Time) approach and complies only a       part of the code during installation and rest of the code will be compiled dynamically.
- Booting time: As compare to Dalvik, ART takes more time to reboot because the cache is built at the first time. So, the booting is slow.
- Space: Since ART uses the AOT approach, so it needs more space during installation. While Dalvik uses the JIT approach, so for mobile phones having less storage can use the     Dalvik.
- Battery: ART increases battery performance to a large extent because of the AOT approach. While the Dalvik uses the JIT approach and this results in more battery utilization.
- Garbage Collection: ART has better garbage collection than Dalvik.
- So, DVM uses JIT and have a lot of drawbacks that were replaced by ART. So, from Android 4.4(Kitkat) ART was introduced as runtime and finally from Android 5.0(Lollipop), the   Dalvik was completely replaced by ART by Android.

# Drawbacks of ART
- Since the compilation of the code is done once, ART requires more space or storage during installation.
- The booting time is more as compared to Dalvik because it uses the concept of AOT.
