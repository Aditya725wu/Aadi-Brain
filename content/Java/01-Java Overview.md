---
title: "01 - Java Overview"
aliases:
  - "Java Overview"
  - "Introduction to Java"
tags:
  - "programming/java"
  - "java/basics"
---

# 01 - Java Overview
# 01 - Java Overview

## 1. What Is Java?

Java is a **high-level, class-based, general-purpose programming language** developed by Sun Microsystems in 1995. It is now maintained by Oracle and the Java community.

Java is used to develop:

- Web applications
    
- Desktop applications
    
- Enterprise software
    
- Android applications
    
- Backend services
    

## 2. Why Do We Need Java?

Java helps developers create applications that can run on different operating systems without rewriting the program for each platform.

Its important features include:

- **Platform independent:** Java bytecode can run on any compatible JVM.
    
- **Object-oriented:** Programs are organized using classes and objects.
    
- **Robust:** Provides exception handling and memory management.
    
- **Secure:** Uses JVM protections and runtime checks.
    
- **Multithreaded:** Supports executing multiple threads.
    
- **Portable:** Java bytecode can be transferred between compatible systems.
    

## 3. How Does Java Work?

Java source code is compiled into bytecode. The JVM executes that bytecode on the target system.

```
flowchart TD
    A["Java Source Code (.java)"] --> B["Java Compiler (javac)"]
    B --> C["Bytecode (.class)"]
    C --> D["JVM"]
    D --> E["Machine Instructions"]
    E --> F["Program Output"]
```

### Example

Create a file named `Hello.java`:

```
class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

Compile the program:

```
javac Hello.java
```

Run the program:

```
java Hello
```

Output:

```
Hello, World!
```

## 4. What Is Platform Independence?

Platform independence means that compiled Java bytecode can run on different operating systems, provided a compatible JVM is available.

For example, the same `.class` file can run on Windows, Linux, or macOS with a suitable JVM.

```
flowchart TD
    A["Java Source Code"] --> B["Compiler"]
    B --> C["Bytecode (.class)"]
    C --> D["Windows JVM"]
    C --> E["Linux JVM"]
    C --> F["macOS JVM"]
    D --> G["Runs on Windows"]
    E --> H["Runs on Linux"]
    F --> I["Runs on macOS"]
```

**Remember:** Java is compiled into bytecode, not directly into one operating system's machine code. The JVM handles execution on the target platform.

## 5. JDK, JRE, and JVM

These three terms are closely related but have different responsibilities.

```
flowchart TD
    A["JDK"] --> B["Development Tools"]
    A --> C["Runtime Components"]
    C --> D["JVM"]
    C --> E["Java Runtime Libraries"]
    B --> F["Compiler: javac"]
```

### JVM — Java Virtual Machine

The JVM executes Java bytecode. It also manages runtime activities such as memory allocation, garbage collection, and execution.

### JRE — Java Runtime Environment

The JRE traditionally refers to the JVM and the libraries required to run Java applications.

### JDK — Java Development Kit

The JDK provides tools for developing Java programs, including the compiler (`javac`), along with the components needed to run them.

|Component|Main purpose|
|---|---|
|JVM|Executes bytecode|
|JRE|Provides the runtime environment|
|JDK|Provides development tools and runtime components|

**Note:** Modern Java distributions do not always provide a separate JRE installation. The conceptual distinction remains useful for learning.

## 6. Java Program Execution — Summary

```
sequenceDiagram
    participant P as Programmer
    participant C as Compiler
    participant J as JVM
    participant O as Output
    P->>C: Write and compile Java source
    C->>J: Generate and provide bytecode
    J->>J: Load and execute bytecode
    J->>O: Produce program output
```

## 7. Quick Revision

- Java is a high-level, class-based programming language.
    
- Java source files use the `.java` extension.
    
- The Java compiler is `javac`.
    
- Compiled Java bytecode typically uses the `.class` extension.
    
- The JVM executes Java bytecode.
    
- The JRE conceptually provides the runtime environment.
    
- The JDK provides development tools and runtime components.
    
- Java's platform independence comes from bytecode and compatible JVM implementations.
    

## Related Notes

- [[02- JDK|Java Development Kit (JDK)]]
    
- [[03- JVM|Java Virtual Machine (JVM)]]