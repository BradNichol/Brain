# Chapter 9. Exception Handling

An exception is an error that happens at run time of your application, and utilising Java's exception handling subsystem 
you can handle these run-time errors in a controlled manner.

Exceptions in Java streamline error handling by allowing your program to define a block of code called _exception handler_
that executes when an error occurs.

## Exception Hierarchy
All exceptions in Java are represented as classes and they are all derived from a class called **Throwable**. Throwable has 
two direct subclasses, **Exception** and **Error*. Error type are related to issue with the JVM itself and not your program.

Any errors can occur in your program are represented by subclasses of Exception.

One key important subclass of Exception is **RuntimeException**, which is used to represent various common types of 
run-time errors.

## Handling Fundamentals
An exception handling block uses five keywords:
 * try
 * catch
 * throw
 * throws
 * finally

These keywords form an interrelated system in which the use of one of them connects to another.

Blocks of code that you want to monitor for exceptions are contained in the **try** block. If an exception occurs, it is
thrown and your code can catch this with the **catch** and handle it in the catch block. If you need to re-throw a new 
exception, you can manually do this with **throw**. 
In cases where an exception is thrown out of a method, this must be specified using the **throws** clause in the method. 
**Finally** is used to execute any code that must happen upon existing from the try block.

### Try Catch Block

```aidl

try {
  //  Block of code to try
}
catch (Exception e) {
  //  Block of code to handle errors
}

```

The above scenario is using the parent Exception class and so any exception type will be caught. If you need to specify 
granular exceptions then you can add multiple catch blocks each specifying a particular exception type so they can be 
handled in different ways.

{% hint style="info" %}
It is the job of your exception handler to remedy the problem that caused the exception so that the program can continue 
normally. 
{% endhint %}

## Consequences of Uncaught Exceptions
Catching an exception and dealing with it prevents abnormal program termination. However, if you don't catch an exception 
when it occurs then it will be caught by the JVM. This can be an issue because the default handler in the JVM terminates 
execution and displays a stack trace. This is useful for debugging purposes but not something that you would want any users 
to see.