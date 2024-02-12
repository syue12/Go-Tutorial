# Scheme Tutorial
## Introduction to Scheme
### What is Scheme
Scheme, a descendant of Lisp, one of the oldest programming languages, was introduced in 1978. It's known for its simplicity, flexibility, and powerful features like functional programming support.
### Why do we want to use Scheme?
Scheme's simplicity and flexibility make it ideal for understanding programming concepts like lexical scoping, closures, and macros. It excels in handling complex data structures, contributing to its popularity and longevity.
## Scheme Expressions
### S-expression
S-expressions or "symbolic expressions" represent data and code in Scheme. Every valid expression in Scheme is an S-expression.

> Examples
* `(+ 7 9 11)` calculates the sum of three numbers. Try modifying this to add four numbers.
* `(if (> x 5)` "Greater" "Less or equal") is a conditional statement. Experiment by changing the condition to (< x 5).

> Quiz 1

[filename](_media/qz1.html ':include :type=iframe width=100% height=200px')

### Prefix notation
Scheme uses prefix notation where operators precede their operands.

> Step-by-Step Conversion Example:
> Convert a * (b + c) / d to prefix notation:
* Start with the innermost expression: b + c becomes (+ b c).
* Then, a * (b + c) becomes (* a (+ b c)).
* Finally, a * (b + c) / d is (/ (* a (+ b c)) d).

### Hello World program
To output text, Scheme uses the display function.

> Exercise
* Try modifying the below code to display a different message:
```scheme
(display "Hello, World")
```
## Basic Syntax of Scheme
### Atoms
Atoms in Scheme are indivisible data elements like symbols, numbers, and booleans (#t for true, #f for false).
> Examples and Exercise:
* hello-from-tutorials-point
* #t
> Try to create your own atom using your name

> Quiz 2

[filename](_media/qz2.html ':include :type=iframe width=100% height=200px')

### Lists
Lists are sequences of atoms and/or other lists, enclosed in parentheses.
> Examples
* ( i am a list)
> Exercise
* Create a list that represents your favorite hobbies.

### Strings
Strings are sequences of characters enclosed in double quotes.

> Difference between an atom and a string
* While atoms are indivisible, strings can be decomposed and manipulated character by character.

> Exercise: 
* Write a string describing your favorite book or movie.

### Comments in Scheme
Comments, indicated by the semicolon ;, provide explanations within the code and are ignored during execution.

> Example:
```
; This is a comment
(display "Hello World") ; This displays a greeting
```

### Use of Single Quotation
Single quotations prevent the evaluation of code, treating it as a literal expression.

> Exercise:
* Display the expression (+ 2 3) as is, without evaluating it.

## Functions in Scheme
Functions perform specific tasks and improve code modularity and reusability.

### Defining Functions
Use define to create functions.

> Step-by-Step Example:
* Define a function to calculate the average of two numbers:
1. Name the function average.
2. Specify parameters: 1st-number, 2nd-number.
3. Write the body to calculate the average.
```
(define (average 1st-number 2nd-number)
        (/ (+ 1st-number 2nd-number) 2))
```

> Exercises:
* Modify the average function to calculate the average of three numbers.
* Create a function named square that returns the square of a number.

### The `area-circle` Function
This function calculates the area of a circle given its radius.

> Step-by-Step Walkthrough:
1. Name the function area-circle.
2. The parameter is the radius rad.
3. Use (* 3.14 rad rad) to calculate the area.
```scheme
(define (area-circle rad)
         (newline)
           (format "Area: ~a" (* 3.14 rad rad))
)
```
> Exercise:
* Modify area-circle to use a variable for π (pi) instead of 3.14.

