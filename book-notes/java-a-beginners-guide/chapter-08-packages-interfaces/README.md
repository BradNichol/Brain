# Chapter 8. Packages & Interfaces

Packages are groups of related classes and using them help to organize code and provide another layer of encapsulation.

Interfaces define a set of methods that must be implemented by a class that implements it. In this way an interface specifies 
what a class will do (the contract), but not how it should do it. 

## Packages
Packages serve two purposes:
1. organization
2. access control

Packages utilise Java's access control features so classes defined within a package can be made private to that package 
only and cannot be accessed outside, to do this do not apply an access modifier to the class member. This applies the default 
access which is public within the package but private outside.

Another access modifier that is used within packages is ***protected***. Using this, allows a member to be public within the 
package, private outside but also accessible to subclasses of it that are outside the package.

### Java Class Library Packages
The Java class library defines a large number of standard classes that are available to all programs. This library is 
referred to as the Java API, which is stored in packages. The top level being Java, which several subpackages below:


| Subpackage | Description                                         |    
|------------|-----------------------------------------------------|
| java.lang  | Contains general purpose classes                    |   
| java.io    | Contains I/O classes                                |
| java.net   | Contains classes for networking                     |
| java.util  | Contains utility classes, inc Collections framework |
| java.awt   | Contains classes for Abstract Window Toolkit        |


## Interfaces
If you want to be able to instruct what a class must do, but not how it should do it, then you can use an interface to 
enforce whichever class implements it must do. This is similar to an abstract method, which defines the signature of 
the method but provides no implementation. In this way, an abstract method specifies the interface to the method but not the 
implementation. In a similar way, an interface can be used to define methods with no body. The difference with using an 
interface is that it fully seperates a class interface from its implementation.

This means that an interface can only specify asbtract methods, whereas asbtract classes can define both asbtract and non 
abstract methods.

Interfaces can also only have static and final variables.

An interface allows you to utilise the 'one interface, multiple methods' aspect of polymorphism.

```aidl
// Interface
interface Shape {
 
    // Abstract methods
    void draw();
    double area();
}
 
// Class 1
class Rectangle implements Shape {
 
    int length, width;
 
    Rectangle(int length, int width)
    {
        this.length = length;
        this.width = width;
    }
 
    @Override 
    public void draw()
    {
        System.out.println("Rectangle has been drawn ");
    }
 
    @Override 
    public double area()
    {
        return (double)(length * width);
    }
}

```

### Variables in Interfaces

{% hint style="info" %}
The following info is considered controversial and should be considered before implementing.
{% endhint %}

In large programs, a convenient way to share constant values is to create an interface without any methods and only contains 
these shared constants. Any class that requires these values can then implement the interface. 

### Extending
Interfaces can be extended by inheriting other interfaces. This means that a class must provide implementations for all methods 
in the interface chain.

### Default Interface Methods
Starting with JDK 8, interfaces can define some default behaviour using the _default method_.
One of the reasons for the reasons for the introduction of default method was to allow interfaces to be expanded without
breaking existing code.
As a general rule, default methods are a special purpose feature and should be used only if required. 

### Private Interface Methods
An interface can include a private method, but it can only be called by a default method or another private method defined 
in that interface.
The primary purpose is to allow default methods to share a common piece of code, and so avoid duplication.
