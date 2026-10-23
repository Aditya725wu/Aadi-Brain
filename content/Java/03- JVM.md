---
title: "03 - JVM"
aliases:
  - "Java Virtual Machine"
  - "JVM in Java"
tags:
  - programming/java
  - java/tools
---

# 03 - JVM (Java Virtual Machine)

> [!abstract] Core Idea  
> The **Java Virtual Machine (JVM)** is a runtime engine that executes Java bytecode and allows Java programs to run on different operating systems using compatible JVM implementations.

## 1. Why Do We Need the JVM?

Imagine you write a Java program on Windows but want to run it on Linux.

The JVM makes this possible by providing a platform-specific runtime that can execute the same Java bytecode.

## 2. How Does the JVM Work?


mermaid
```
flowchart TD
    A["Java Source Code"]
    B["Java Compiler"]
    C["Bytecode"]
    D["JVM"]
    E["Program Output"]

    A --> B
    B --> C
    C --> D
    D --> E
```

### Step-by-step

1. Write the program in a `.java` file.
    
2. The Java compiler (`javac`) converts the source code into bytecode.
    
3. Bytecode is stored in a `.class` file.
    
4. The JVM loads and executes the bytecode.
    
5. The program produces its output.
    

## 3. Example

Java source code:

```
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

Compile the program:

```
javac Main.java
```

This generates `Main.class`.

Run the program:

```
java Main
```

Output:

```
Hello, Java!
```

**What happens?** The `java` launcher starts the Java runtime, which uses the JVM to execute the compiled bytecode.

## 4. How Does the JVM Enable Platform Independence?

```
flowchart TD
    A["Main.java"]
    B["Compile Once"]
    C["Main.class"]

    A --> B
    B --> C

    C --> D["Windows JVM"]
    C --> E["Linux JVM"]
    C --> F["macOS JVM"]

    D --> G["Program Runs"]
    E --> G
    F --> G
```

The source code does not need to be recompiled for each platform, provided the bytecode, JVM, and application dependencies are compatible.

This principle is called **Write Once, Run Anywhere (WORA)**.

## 5. JVM vs JDK vs JRE

|Component|Main purpose|
|---|---|
|JVM|Executes Java bytecode.|
|JRE|Traditional term for the environment needed to run Java applications.|
|JDK|Provides tools to develop Java applications and the required runtime components.|

Remember:

- **JVM:** Executes.
    
- **JRE:** Runs applications.
    
- **JDK:** Develops applications.
    

Modern Java distributions do not always provide a separate JRE installation.

## 6. Key Points to Remember

- JVM stands for Java Virtual Machine.
    
- It executes Java bytecode stored in `.class` files.
    
- The `javac` compiler generates bytecode from Java source code.
    
- Compatible JVM implementations allow the same bytecode to run on different platforms.
    
- The JVM is part of Java's runtime architecture.
    

## Navigation

```
name ← Previous: JDK
type link
action 02 - JDK
```

```
name Next → Java Program Structure
type link
action 04 - Java Program Structure
```