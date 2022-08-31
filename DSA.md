# DSA

# **Introduction to Programming - Types of Languages, Memory Management**

Three types of languages:

1. Procedural: well structured steps to compose a program
2. Functional: only pure functions ie. functions where no existing variables are modified and only new ones are created
3. Object Oriented: Code + Data (classes and their instances)

^ How we write code etc.

Another classification:

Source code that we write —> code that machine can read : compilation

1. Static:
    1. performs type checking during compile time.
    2. errors will show during compile time
    3. more control
2. Dynamic:
    1. performs type checking during runtime
    2. might not show errors before it is run
    

```jsx
a=10
```

- here a is a reference variable and 10 is an object
- a is stored in **stack**
- b is stored in **heap**
- So a is a variable in stack memory, pointing towards 10 in heap memory

All objects have addresses in the memory 

More than 1 reference variables can point to the same objectP

If any one of the reference variables change the object, it is going to be changed for all

If an object does not have any reference variables, garbage collection takes place and it gets deleted from the heap. Garbage collection is basically Yamraj.

# **Flow of Program - Flowcharts & Pseudocode**

In flowcharts

- parallelogram - input/output
- ellipse- start/stop
- rectangle - processing
- rhombus - condition
- arrow - the flow of the program

### Pseudocode

can be the same for different languages as syntax doesn’t matter here. We’re basically writing down what is to be done in order to explain it to someone.

# **Introduction to Java - Architecture & Installation**

Extension of java files : .java

In languages like C: our code -Compiler→ .exe file , which can be understood by the machine but it is platform dependent. For example if you’ve compiled your C++ code on a Mac you won’t be able to run it on a Windows machine. You’ll have to recompile it. This is because it (the exe) depends on the architecture of the system.

In Java: Our code -Compiler-> Compiler (entire file) —> .class file (byte code, won’t be directly run on a system, we need JVM to run this. This makes Java platform independent) -Interpreter (line by line)→Machine Code

### Platform Independence

The byte code can run in all systems because in any case we have to put this byte code in JVM

JVM stands for Java Virtual Machine

JVM is platform dependent.

JIT : Just-in-time compiler

JVM contains JIT

JRE (Java Runtime Environment) = JVM + Library Classes

JDK (Java Development Kit) = JRE + Development Tools

### JDK

We need JDK for writing our programs. It is a package that provides an environment to develop and run the Java Program

It includes:

- development tools - to provide us an environment to develop our programs
- JRE - to execute our programs
- a compiler (javac)
- archiver (jar)
- docs generator - javadoc
- interpreter / loader

### JRE

It is a package that provides an environment for (only) running the program. It consists of: 

- Deployment technologies
- User interface toolkits
- Integration libraries
- Base libraries
- JVM

After we get the .class file, the next things happen at runtime:

1. class loader loads all the classes needed to execute the program
2. JVM sends the code to the bytecode verifier to check the format of the code 

### How JVM works

Loading

Reads .class file and generates binary data and an object of this class gets stored in the heap

Linking: 

JVM verifies the .class file (are there any errors in there?)

It allocates memory for class variables and default values

Replaces symbolic references from the type with direct references. For example if we have written sum = a+b and a = 10, b=20, this will convert a+b to 10 + 20

Initialization: all static variables ( same for an entire class, not dependent on their object, basically like a global for classes) 

JVM contains stack and heap memory allocations

### JVM Execution

Interpreter

Line by line execution

when one method is called many times, it will interpret again and again. To fix this problem, we have:

JIT (Just in time)

for those methods that are repeated, JIT provides direct machine code so re-interpretation is not required

Makes execution faster

Garbage collection also takes place in this step

Java Source Code —>JDK—>Bytecode—>JVM—>JRE (output)

JRE vs JVM

JRE is like a box 

JVM is the actual content in the box 

JRE contains all the libraries etc.

# First Java Program

Everything is written in classes! Every file is itself a class.

Names of classes should have the first letter capital. It’s a good practice (convention)

class Filename should be public

public, private are **access specifiers**

If there is no main function, you won’t be able to run the program

```java
public class Demo{
//^ for a file named Demo.java 
	public static void main (String args[]){

	}

}

//public (behind Main) specifies that the class can be accessed from anywhere
// class is just a named group of properties and functions 
```

- public (behind class Main) specifies that the class can be accessed from anywhere
- class is just a named group of properties and functions
- Functions inside classes are called methods
- Whenever you run your java file, it will look for the main function.
- public (behind static void main) is required because otherwise the compiler won’t be able to find the main function. It is needed so that it can be found by anywhere.
- static is used because we don’t actually want to create a new object of the class Demo when executing our main function. It is the entry point of the program. It is the entry point of the program so you can’t create objects before it.
- void is the return type of the function
- String[] args is the array of arguments that we give in the command line

```java
//for example
public static void main (String[] args){
	System.out.println(args[0])
}

//in the terminal if we do: java filename 23, output will be 23

System.out.println(args[1])

//now in the terminal if we give 30, Namething, output will be "Namething"

//(arrays start from index 0)
```

```java
//in the terminal
javac -d 

// the -d is for changing the destination where the compiled file is stored

javac -d .. Demo.java
// to store the compiled file one directory above the code file

```

Note: In terminal “where” command to see where some file is

Package is the folder in which our java file lies. It’s important because we may need to provide some rules (this file can be accessed where etc.). Packages help us in doing that

System class is a class in the **lang** package of java. It is inherited by default in all files.

```java
System.out.println("Something")
//System is a class which has a variable out of the type printstream and this out has a method 
//println
// printstream is also a class
```

Scanner is a class that specifies an input stream and using an object of that class we can take input