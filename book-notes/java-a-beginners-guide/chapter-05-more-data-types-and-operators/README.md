# Chapter 5. More Data Types & Operators

### Arrays
Array is a collection of variables of the same type.
You can have multi-dimensional arrays but one dimension are most common. 
Arrays organise data in such a way that it can be easily sorted. 
unlike in other languages, in Java, arrays are implemented as objects.

An advantage of this is that unused arrays can be garbage collected. 

Declaring a one-dimensional array:
```aidl
type array-name[] = new type[size]

int numbers[] = new int[5] // the new operation allocated memory of size x to the array.

```
Type declares the element type of the array. The size determines how many elements it can hold.

To access an element in the array, use its index number.
The first element is always index 0. 

You can also initialize the array with values:
```aidl
type array-name {v1, v2, v3, ...}; 
```

Note: Array boundaries are strictly enforced in Java!

#### Sorting an Array

Arrays are the perfect data structure for sorting elements.

There are different sorting algorithms available, the most common are:

Bubble sort - not very efficient, only suitable for small arrays
Quicksort - general purpose sorting algorithm

#### Length Member 
To know the size of an array, you can use the .length member.
```aidl
array-name.length

```
{% hint style="info" %}
Using .length has nothing to do with the number of elements that are stored, just the number it's capable of storing.
{% endhint %}

### Queue class

Arrays support random access to elements, but are often used to underpin other sophisticated data structures, like Queues.

A queue is a list in which elements can be accessed in a first in, first out order only (FIFO).
Queues are data engines, in which storage and retrieval are provided by the data structure itself, not manually by your program.

#### Basic operations

 * put - puts an element on the end of a queue.
 * get - gets element from front of queue. 
   
Queue operations are ***consumptive*** only. Once an element has been retrieved it cannot be retrieved again.

### For-Each Style Loop

When an operation has to be applied to every element in an array, the enhanced for-each loop is less verbose way to loop through an array.

To use:
```aidl
for (type variable: array) {
    // operations
}
```
The loop will iterate through all elements, but you can stop the loop early with a break statement if required.

### Strings
One of the most important Java data types is the String. Unlike some other programming languages where a string is an array of characters, in Java a string is an 
object.

#### Constructing a String
Two simple ways that you can construct a string:
```aidl
String str = new String("Helloooo");

String str = "Helloooo";

```
The second option is typically preferred.

#### String Operations
The String class contains several methods and here's a few common ones:

- boolean equals(str)
- int length()
- char charAt(index)
- int compareTo(str)
- int indexOf(str)
- int lastIndexOf(str)

#### Immutable
String objects are immutable and so once created they cannot be altered. If you need to make a change, create a new string that contains the changes.

### Type Inferance with Local Variables
Introduced in JDK10, you can let the compiler infer the type of a local variable based on the type of its initializer. For example number = 10. 10 here is the initializing
value that the compiler can use to infer the data type of int.

To use, instead of declaring a type, use the var keyword instead:
```aidl
var number = 10;
var string = "Hello";
```
Advantages:
- Streamlines the code
- Simplifies lengthy declarations
- fits with modern and contempory programming styles

**Note**: It can only be used to declare local variables.

### The ? Operator
The ? operator is known as the ternary operator and can be used to replace standard if-else statements.
For example:

```aidl
if (condition) {
  return "YES";
} else {
  return "NO";
}

Above can be reduced to:

condition ? "OK" : "NO";

```
It's called a ternary operator because it requires three operands, starting with a boolean expression, which returns the first value if true, 
or the second value if false.




