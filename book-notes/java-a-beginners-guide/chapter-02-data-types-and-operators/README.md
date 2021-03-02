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

There are two floating-point types to represent fractional numbers.
1. float - single precision - 32 bits wide
2. double - double precision - 64 bits wide

Double is the most commonly used type and many of the Java class library math functions will return a double.

### Char
In Java a char is an unsigned 16-bit type that can be used to represent the characters found in all human
langages. This is Unicode. This is why a Java char is 16-bit and not 8-bit like a lot of other programming languages 
that use ASCII.

{% hint style="info" %}
ASCII character set is a subset of Unicode and as such can still be used in Java.
{% endhint %}

{% hint style="warning" %}
As char is an unsigned type, it is possible to perform arithmetic functions on a variable.
For example:
```
char letter = 'X';
letter++
System.out.println(letter);
Y

```
{% endhint %}

### Boolean Type
The boolean type can be one of two values, true or false.

{% hint style="info" %}
A boolean variable can control a conditional if statement without explicit code. 
For example:
```
boolean isAllowed == true;

if (isAllowed) { .... this is OK

if (isAllowed == true) { ....  this will compile but it is not neccessary

```

A relational operator will return a boolean value, and does not require explicit code either.
For example:
```aidl
return 5 > 2;
```
{% endhint %}

## Literals

Literals refer to fixed values, for example 100 is a literal and are also known as constants. Literals can be any of the primitive types.
char literals are specified with single quotes, whereas string literals with double quotes.

Long and float primitives can also be specified by adding a character to the end of value.
For example:
```aidl
long longNumber = 12345678910L
float floatNumber = 1234.56F
```
To make ***integers*** and ***floating-point*** literals easier to read, you can embed underscores which are removed at compile time.
```aidl
int number = 123_456_789
==> 123456768 
```
This is typically useful for numbers such as customer IDs and parts numbers.

### Hexadecimal & Octal literals
Number systems such as octal and hexadecimal can be represented in Java.

The system based on 8 is octal and base 16 system is hexadecimal.
Octal uses numbers 0 to 7, and hexadecimal uses digits 0 to 9, and letters A to F, which stand for 10, 11, 12, 13, 14, 15.
```aidl
int hexNumber = 0xFF; // 255 in decimal
int octNumber = 011; // 9 in decimal
```

### Escape Sequences
Some characters in Java can pose an issue when used in certain situations. For example, single and double quotes are used to enclose strings,
but what if you need to display a quote mark? That's where escape sequences can help.
Also referred as backlash character constants.

| Escape Sequence   | Description          |    
| ----------------  | -----------------    |
| \'                | Single quote         |
| \"                | Double quote         |
| \\                | Backslash            |
| \r                | Carriage return ↵    |
| \n                | New line             |
| \f                | Form feed            |
| \t                | Horizontal tab       |
| \b                | Backspace            |
| \ddd              | Octal constant (ddd is the octal value)   |
| \uxxxx            | Hexadecimal contstant (xxxx is the value) |

If I wanted to assign a backslash to a variable, it would be the following char backSlash = '\\';

### String Literals
A string literal is a set of characters enclosed by double quotes. (single quotes will not work).

A string literal can contain one or more of the escaoe sequences from above.

{% hint style="info" %}
A string literal that contains a single character is not the same as a single letter of type char.
{% endhint %}







