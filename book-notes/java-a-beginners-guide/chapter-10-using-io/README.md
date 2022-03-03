# Chapter 10. Using I/O

The Java I/O system is based upon a hierarchy of classes and is very quite large, utilising many classes. It also has 
two complete systems, one for byte I/O and one for character I/O.

## Java's I/O is Built upon Streams
Java programs perform I/O through streams, which is an abstraction that either produces or consumes information.
All streams behave in the same manner no matter what they're connected to, which means the same I/O classes and methods 
can be applied to different types of input and outputs devices. 

## Byte Streams and Character Streams
Modern versions of Java define two types of I/O streams, byte and character. Byte streams provide a convenient means for 
handling input and output of bytes, typically used for reading/writing binary data and useful when reading/writing files.
Character streams are designed for handling the I/O of characters using Unicode. 
At the lowest level, all I/O is still byte orientated.
