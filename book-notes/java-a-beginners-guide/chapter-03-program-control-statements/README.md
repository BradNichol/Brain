# Chapter 3. Program Control Statements

## Overview

The program control statements in Java are as follows:

### Selection Statements
* if
* switch

### Iteration Statements
* for
* while
* do-while

### Jump Statements
* break
* continue
* return

## The if Statement

```aidl
if (condition) {
    statement
} else {
    statement
};

```
The conditional expression controlling the if must produce a boolean result.

### Nested ifs
Very common usage of using an if statement within an if/else statement block. Note, the an else statement
always refers to the nearest if statement that is within the same block. 
Example:
```aidl
if (i == 1) {
    if (j > 10) statement;
    if (k < 10) statement;
    else statement; // this else refers to if (k < 10)
} else {
    statement // this else refers to if (i == 1)
};

```

### if-else-if ladder
A common construct in programming is the if-else-if ladder. The conditional expressions are evaluated from 
the top down. As soon as a true condition is met, the statement block executes and the rest of the ladder is 
bypassed.

If the ladder has a final else statement, if no true condition is met, this final else block will execute.
```aidl
if (condition) {
    statement
} else if {
    statement
} else if {
    statement
} else if {
    statement
} else {
    statement
};

```

## Switch Statement
The second type of selection statement is a switch statement. Similar to creating an if-else-ladder,
the switch provides multiway branching allowing a program to select among several alternatives.
The switch is typically a more efficient approach than writing ladders.

The value of an expression is tested against a list of constants and executed when a match is found.
```aidl
switch (expression) {
    case *constant1*:
      _statement sequence_
      break; K 

```

