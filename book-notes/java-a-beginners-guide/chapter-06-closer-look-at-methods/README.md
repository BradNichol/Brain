# Chapter 6. A Closer Look At Methods & Classes

This chapter goes back to methods and classes and explains features like access control, among other features of using 
classes and objects in Java.

## Access Control

### Controlling Access For Classes
To support encapsulation, a Java class links data with with code, but also provides the means of access 
with the use of two basic class members.

1. public - can be access freely from any other code in the application
2. private - can only be access from within the class itself

Restricting access is fundamental to achieve aspects of OOP and when correctly used, a class should be a 'black box' that
can be used without knowing or understanding the inner workings.

### Access Modifiers
Member (properties and methods) access control is achieved via three access modifiers:
1. public
2. private
3. protected

If no modifier is used, the default that Java applies is public. If using packages to structure code, default access will differ.

## Passing Objects
Objects can be passed to a method parameter just like primitive types can be, but there are some nuances to be aware of.
There are two ways in which an argument is passed to a subroutine:
1. call-by-value
2. call-by-reference

For call-by-value, the value of the argument is copied and so any changes made in the method will have no effect on the
argument in the call. This applied to primitives.

For call-by-reference which is how objects are passed, call-by-reference is used (think memory pointers) and so inside 
the method any changes made will effect/mutate the original object being called.

## Overloading 

### Method Overloading
One of the ways to achieve polymorphism on class methods is to use method overloading. This is the process of creating 
two methods that use the same name, but have a different number of parameters. They are said to have different signatures.

The value of this is that it allows related methods to be accessed by the use of a common name.

### Constructor Overloading
Constructors can also be overloading in a similar manner, which doing so allows you to construct objects in a variety of 
ways.

## Understanding Static
If you need to define a class member that can be accessed independently of any object of that class, you can use a static 
declaration.
Use the keyword **static** at the start of the method or variable declaration. When you do this, the member can be accessed before 
any object of the class is created which makes these properties global as they can be accessed throughout the application.

To access the static property, use the class name followed by the dot operator to select the static.

```aidl
public class StaticExample() {
 
 static String name = 'This is a static string';
 
}

To access:

StaticExample.name

```

When an object is declared, no copy of static is made, instead all instances of the class share the same static variable.

Methods declared as static have some restrictions:
1. They can only call other static methods in their class
2. They can only directly access other static variables in their class
3. They do not have a **this**

### Static Blocks
If your class requires pre-initialization before it's ready to create objects, such as initializing static variables you 
can declare a static block, which is executed when the class is first loaded. Meaning any initialization happens before 
it will be used.

```aidl
public class StaticBlockExample() {
    
    static int number;

    static {
        number = 5;
     }
}

```
