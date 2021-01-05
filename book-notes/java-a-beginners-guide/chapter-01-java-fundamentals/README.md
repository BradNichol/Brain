# Chapter 1. Java Fundamentals

"this chapter provides a brief overview of several Java features..."

## History & Philosophy 
* Developed by James Gosling, et al, at Sun Microsystems in 1991.
* Initially called Oak, renamed to Java in 1995.
* Platform independent language
* Influenced by C/C++, with similar syntax.

### Java's Magic: The Bytecode
To address issues of portability and security that affected other languages, the output of a Java compiler is
not directly executable code. Instead it's Bytecode, a set of instructions designed to be executed by the 
Java Virtual Machine (JVM).

### Release Schedule
Since JDK 9, the release schedule for major updates occurs approximately every 6 months.
However, a lot of new features are often only experimental at time of release. 
For commercial development, stick to long term support (LTS) versions Java 8, 11 + others when released.

## OOP
Java is an Object Orientated Language and achieves this with three main traits:
* Encapsulation - Binding code and the data it manipulates, together.
    * A Java class is the basic unit of encapsulation to achieve this.
    * Access modifiers allow classes, and their members to be public or private.
    
* Polymorphism - is the quality that allows one interface to access a general class of actions.
    * Polymorphism helps to reduce complexity by allowing the same interface to be used to specify
     general class of actions. This means that it's possible to design a generic interface to a group 
      of related methods.
      
* Inheritance - The process by which one object can use the properties of another object.
    * Think class Fruit (with properties of sweetness etc), inherits properties from class Food
      (with properties of nutrition, edible, type etc).
      
    * Without this mechanism, each individual class would need to explicitly define the same properties
    each time.
      
      
## Java Development Kit
JDK is required on the specific machine to be able to compile and run a Java program.
* There are multiple flavours of the JDK. Oracle and OpenJDK are popular.
* JDK supplies two main programs; javac which is the compiler and java, which is the standard
Java interpreter.
  
* The JDK runs in the command-prompt environment only. To compile and run a Java program you can 
use the command line, however this is typically handled by the IDE now.