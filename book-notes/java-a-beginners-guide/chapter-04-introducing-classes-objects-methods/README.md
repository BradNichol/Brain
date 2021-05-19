# Chapter 4. Introducing Classes, Objects, and Methods

*"the class is the essence of Java. it is the foundation upon which the entire Java language is built because the class defines the nature 
of an object. As such, the class forms the basis for object-orientated programming in Java."*

## Class Fundamentals
All activity within a Java program occurs within a class. 
The class is a template or blueprint for the form of an object. Java uses a class specification to contruct objects. Objects are instances of a class.

Note, until an object is instantiated, a physical representation of the class does not exist in memory.

Basic class form:
```aidl
class className {
    
    // instance variable(s)
    type var1;
    
    // method(s)
    type method1 (params) {
        // method body
    }   
}
```
* A class definition created a new data type. I.e. class Person, will create a data type of Person.
* Each time you create a new instance of a class, a new object is created with its own copy of each instance variable defined. This means each object of the
same class will only ever contain its own data.
  
### Object Creation
An object can be instantiated in the following way using a class of Employee as an example:
```aidl
Employee bill = new Employee(); 
```
Two processes are happening here:

1. a variable is declared of type Employee.
2. An instance of the object is created and assigned as a reference to the variable name.

The new operator dynamically allocates memory for an object at runtime and returns an address reference for it. The reference is its location in memory, and
this is what is stored in the variable.

{% hint style="info" %}
The way an object is assigned to another variable reference is different to when you do the same with primitive types.
When you assign a primitive type variable to another, the new variable receives a copy of the value.

However, when you assign an object reference to another variable, you are only assigning the same address pointer to the new variable, and as such 
these two variable reference link to the same object. Updating either of the variables, will result in the same change for both references.
{% endhint %}

Example:
```aidl
Primitives
int number1 = 1;
int number2 = number1; // contains 1;
number1 = 5; // number2 is unaffected and still contains 1

Objects
Employee bill = new Employee();
bill.age = 28;
Employee ted = bill; // points to the same object. println(ted.age) = 28
ted.age = 30; // println(bill.age) = 30;

```

### Methods
Typically, methods are used in two ways inside a class:
* To manipulate data.
* To provide access to that data

In well-written Java code, a method performs a single task. 
The general form of a method is:
```aidl
return-type name(parameter-list) { 
    // body of method
}
```

The return type can be any valid class type. If the method doesn't return data, the return type must be void. 
To exit from a method, use the keyword *return value*.
The return keyword is not required if using void, unless you want to break out early. 

#### Using Parameters
You can pass one or more values to a method when it is called. This data is called arguments, and the receiving variables 
are the parameters, which are declared inside a method's parenthesis'.

Quick Note: Each class must represent a single fictional unit.

### Constructors
A constructor initializes an object when it is created, and uses the same name as the class itself. 
Syntactically, it looks similar to a method.
A constructor is typically used to give initial state to the instance variables.

If a constructor is not defined, Java automatically creates one for you at initialization, and any instance variables are defaulted
to their base values.

### Garbage Collection
when objects are created, they are allocated memory from a pool of free memory by using the new keyword. 
Java automatically reclaims memory from objects when they are no longer referenced.

Garbace collection typically runs when:
* there are objects to recycle
* there is a reason to recycle

Garbage collection takes time, so the Java run-time system does it only when appropriate.



