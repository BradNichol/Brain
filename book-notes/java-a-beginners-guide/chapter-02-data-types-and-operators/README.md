# Chapter 2. Introducing Data Types and Operators

## The Importance of Data Types in Java
Java is a strongly typed language, which under the hood means that all operations are type-checked by the
compiler for type compatibility. A string value cannot be stored in a variable of type Integer, this would be
considered an Illegal operation. Strong type checking helps prevent these sort of errors, especially in large
applications. 

## Java Primitive's
There are two categories of built-in data types in Java. 
* Object-orientated
* Non object-orientated

The non objected-orientated types are the primitives, and there are 8 of them. The term primitive
is used to indicate that these types are not objects. 

| Type    | Meaning                         | Width in Bits |    
| ---     | ------------                    | ----------    |
| boolean | true/false                      | 1             |
| byte    | 8-bit integer                   | 8             |
| char    | Character                       | 16            |
| double  | Double-precision floating point | 64            |
| float   | Single-precision floating point | 32            |
| int     | Integer                         | 32            |
| long    | Long integer                    | 64            |
| short   | Short integer                   | 16            |

### Integers
There are four integer types, byte, short, int and long. All of these integer types can be assigned
either positive or negative values. Java does not support unsigned (positive-only) integers like some
other languages do.

For most cases you'll typically use an int.

{% hint style="info" %}
The smallest integer type is a byte, which is typically useful for when working with raw binary data.
{% endhint %}

### Floating-point Types

