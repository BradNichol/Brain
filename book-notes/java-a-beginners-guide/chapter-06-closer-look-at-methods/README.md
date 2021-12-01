# Chapter 6. A Closer Look At Methods & Classes

This chapter goes back to methods and classes and explains features like access control, among other features of using 
classes and objects in Java.

### Access Control

#### Controlling Access For Classes
To support encapsulation, a Java class links data with with code, but also provides the means of access 
with the use of two basic class members.

1. public - can be access freely from any other code in the application
2. private - can only be access from within the class itself

Restricting access is fundamental to achieve aspects of OOP and when correctly used, a class should be a 'black box' that
can be used without knowing or understanding the inner workings.

#### Access Modifiers
Member (properties and methods) access control is achieved via three access modifiers:
1. public
2. private
3. protected

If no modifier is used, the default that Java applies is public. If using packages to structure code, default access will differ.

### Passing Objects
Objects can be passed to a method parameter just like primitive types can be, but there are some nuances to be aware of.
There are two ways in which an argument is passed to a subroutine:
1. call-by-value
2. call-by-reference

For call-by-value, the value of the argument is copied and so any changes made in the method will have no effect on the
argument in the call. This applied to primitives.

For call-by-reference which is how objects are passed, call-by-reference is used (think memory pointers) and so inside 
the method any changes made will effect/mutate the original object being called.

### Method Overloading
One of the ways to achieve polymorphism on class methods is to use method overloading. This is the process of creating 
two methods that use the same name, but have a different number of parameters. They are said to have different signatures.

The value of this is that it allows related methods to be accessed by the use of a common name.

### Constructor Overloading
Constructors can also be overloading in a similar manner, which doing so allows you to construct objects in a variety of 
ways.

