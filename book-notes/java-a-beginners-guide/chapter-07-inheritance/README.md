# Chapter 7. Inheritance

One of the three foundational principles of OOP, inheritance allows you to create a general class that defines shared 
traits common to a set of other classes which they can inherit from. A class that is inherited is called a **superclass**, 
and the class does the inheriting is called the **subclass**.

## Basics
For a class to inherit from an other, it must extend the superclass by using the **extend** keyword. 

```aidl
public class subclass extends superclass() {
    ////
    Here you can now access properties of the superclass.
}
```

A class can only inherit from a single superclass, but you can create a hierarchy where a subclass becomes a superclass 
for another class.

## Member Access
Inheriting from a superclass does not override any members declared with private. So if the superclass contains private 
methods, the subclass won't be able to access these.