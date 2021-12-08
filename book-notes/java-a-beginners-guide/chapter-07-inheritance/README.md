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

## Using Abstract Classes
To create a superclass that only defines a general form to be shared across all subclasses use an abstract class. 
This is usually the case when the superclass is unable to create a meaningful implementation of a method that can be shared.

An abstract method will have an empty body and must be overridden in the subclass.

```aidl
// Abstract class
abstract class Animal {

  public abstract void animalSound(); - // Abstract method (does not have a body)
}

class Pig extends Animal {
  
  // The method is overidden here.
  public void animalSound() {
    System.out.println("The pig says: oink");
  }
}

```

Couple of points to remember:
1. Abstract methods have no body.
2. If a class declares an abstract method, then it must become an abstract class.
3. Abstract methods can only be applied to instance methods, not statics or constructors.
4. You cannot instantiate an abstract class. You'll receive compilation error.
5. Subclass must override all asbtract methods.
6. The abstract class can contain methods that are not abstract to be shared across subclasses.

### Using Final
If you need to prevent a method from being overridden you can use the final keyword.
To do so, just specify final as the modifier at the start of the declaration.

If you want to prevent inheritance completely then you can declare a class as final, stopping any subclass from being able
to inherit it.

You can also apply ***final*** to variables which creates a named constant. This makes the variable immutable after initialization.
A typical convention is to apply static to final variables so they can be accessed via their class name rather than the through 
an object. final constant variables names are also typically UPPER_CASED.

## The Object Class
There's one special class in Java called Object which is a superclass of all other classes created. So any class that you create 
is a subclass of Object. This also means that you're class always inherits a base set of methods. The most frequently used and 
overridden are hashCode(), equals() and toString().

