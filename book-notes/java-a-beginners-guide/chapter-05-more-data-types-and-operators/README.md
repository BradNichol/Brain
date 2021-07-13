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




