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

## Selection Statements
The selection statements are also known as decision making statements or branching statements

### The if Statement

```aidl
if (condition) {
    statement
} else {
    statement
};

```
The conditional expression controlling the if must produce a boolean result.

#### Nested ifs
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

#### if-else-if ladder
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

### The Switch Statement
The second type of selection statement is a switch statement. Similar to creating an if-else-ladder,
the switch provides multiway branching allowing a program to select among several alternatives.
The switch is typically a more efficient approach than writing ladders.

The value of an expression is tested against a list of constants and executed when a match is found.
```aidl
switch (expression) {
    case constant1:
      statement sequence
      break; 
    case constant2:
      statment sequence
      break;
    default:
      statement sequence
}

```
Each of the case constants must be unique. Duplicates are not allowed.
The default case is optional.
The break statement causes the program flow to exit. If it is not specified, all statements at and
following the match case will continue to be executed until a break statement is hit.

**Nested switch statements are also allowed.**

## Iteration Statements
Iteration statements create loops in the program that repeat until the condition for termination 
is met. 

### The for Loop

The general form of a for loop is: 
```aidl
for (initialization; condition; iteration) {
     statement sequence;
}
```
The initialization sets the initial value of the loop, which acts as the counter. The condition us a Boolean expression that determines
if the loop will repeat and the iteration defines the amount by which the loop control variable will change each time the loop is repeated.
The for loop will continue to execute while the condition test is true.

A loop iteration control variable can either increment or decrement.

You can also use multiple loop control variables if need be.
```aidl
int i, j, k;

for (i =0; i < 10; i++, j++, k--) {
     System.out.println("i is: " + i + " " + "j is: " + j + " " + "k is: " + k)
}

Output:
i is: 0 j is: 0 k is: 0
i is: 1 j is: 1 k is: -1
i is: 2 j is: 2 k is: -2
i is: 3 j is: 3 k is: -3
i is: 4 j is: 4 k is: -4
i is: 5 j is: 5 k is: -5
i is: 6 j is: 6 k is: -6
i is: 7 j is: 7 k is: -7
i is: 8 j is: 8 k is: -8
i is: 9 j is: 9 k is: -9
```

