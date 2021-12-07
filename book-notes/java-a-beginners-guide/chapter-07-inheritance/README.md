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

## Constructors and Inheritance
In an inheritance hierarchy when multiple constructors are involved, which constructor is in charge of building the object?
The super or subclass? 
It's actually both. Each constructor becomes responsible for creating the class it belongs too.

## Using super() and super

### super() for Superclass Constructors
If you need to instantiate the parent class while creating the subclass object, you can use the super() constructor call
in the subclass. 

```aidl

class Animal {
 
    // Constructor of superclass
    Animal()
    {
        System.out.println("Animal class Constructor");
    }
}

class Dog extends Animal {
    Dog()
    {
        super();
        System.out.println("Dog class Constructor");
    }
}

When executed, output will be:
Animal class Constructor
Dog class Constructor
```
***Note:*** when calling super(), it must always be the first statement executed inside a subclass constructor.

### super for Accessing Superclass Members
You can use the keyword ***super***, in a similar way as this, except in the super case it refers to the superclass and 
allows you to access the members of a superclass using dot notation.

super._member_

Member can be either a method or variable.
