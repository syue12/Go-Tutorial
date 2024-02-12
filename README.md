# Scheme Tutorial
## Introduction to Scheme
### What is Scheme
Scheme is one of the oldest programming languages. Scheme is a programming language that is a descendant of Lisp, and Lisp is indeed one of the oldest programming languages, dating back to 1958. And Scheme was officially introduced in 1978.
### Why do we want to use Scheme?
Scheme is known for its simplicity and flexibility, as well as its powerful features such as support for functional programming. This makes Scheme an ideal language for exploring and understanding programming language concepts, such as lexical scoping, closures, and macros. In short, Scheme’s popularity and longevity can be attributed to its ability to handle complex data structures.
## Scheme Expressions
### S-expression
An s-expression stands for “symbolic expression.” It is a fundamental notation to represent data and code. In Scheme, all valid expressions are s-expressions.

> Examples
* (+ 7 9 11) returns the sum of the three numbers.
* (add 2 3) represents a function call. The symbol add is followed by two number literals, 2 and 3 serving as the arguments.
* (if (> x 5) "Greater" "Less or equal") represents an if statement. It contains three elements: the if symbol, a condition expression (> x 5), and two result expressions ("Greater" and "Less or equal").
* (+ (* 2 3) 4)performs arithmetic operations. The + symbol is followed by a nested S-expression (* 2 3), representing the multiplication of 2 and 3. The result of that multiplication is added to 4.
* (1 2 3): This represents a list of numbers, and lists are s-expressions.
Note that s-expressions are composed of one or more elements enclosed in parentheses.

> Quiz 1

[filename](_media/qz1.html ':include :type=iframe width=100% height=200px')

### Prefix notation
Scheme uses Prefix notation. In prefix notation, operators are written before their operands.

We use the operators only once because Scheme allows you to provide multiple arguments to arithmetic operators like +, *, -, etc., which makes it easy to add multiple numbers without repeating the operator. As in the (+ 7 9 11) expression, Scheme’s + operator is designed to handle multiple arguments, allowing you to add multiple numbers in one expression.

> Example
* a * ( b + c ) / d  => will be written as (/ (* a (+ b c) ) d)
* (60 * 9 / 5) + 32 => will be written as (+ (* (/ 9 5) 60) 32)

> Example 2
* How can we change (60*(9/5))+32 into a prefix notation?
* First, let's convert the inner-most subexpression (9 / 5). Move the operator to the left.
((60 * (/ 9 5)) + 32)
* Convert the next inner subexpression (60 * (/ 9 5)). Similarly, move the last operator to the left.
* Repeat. The final answer is: (+ (* 60 (/ 9 5)) 32)

### Hello World program
The `display` function is used to output a string to the standard output, usually the console or terminal. Put the string right next to the `display`:
(display “Hello, World”)
> Example
* The following code displays “x is smaller than 10” when x is smaller than 10.
* (if (< x 10) (display "x is smaller than 10"))

## Basic Syntax of Scheme
### Atoms
Basic building blocks in Scheme: atom, list, string
In Scheme, programs will be created using atoms, lists and strings.
An atom is a number or string of contiguous characters. It can have a variety of data types, including symbols, numbers and booleans. Booleans in Scheme are `#t` and `#f.` The term "atom" is used to describe the simplest and indivisible data elements. An atom is a basic unit of data that cannot be divided further into smaller parts within the language's data model.
The name "atom" originates from the atomic theory in physics and chemistry, where atoms are considered the fundamental building blocks of matter, and they cannot be broken down further into smaller constituents. Similarly, in Scheme, atoms are the fundamental building blocks of data, and they represent indivisible data elements.
> Examples
* hello-from-tutorials-point
* name
* 123008907
* hello
* Block#221
* #t
* #f
* Abc123

> Quiz 2

[filename](_media/qz2.html ':include :type=iframe width=100% height=200px')

### Lists
A list is a sequence of atoms and/or other lists enclosed in parentheses. An empty list `()` is considered a valid list in Scheme.
> Examples
* ( i am a list)
* (a ( a b c) d e fgh)
* (father tom ( susan bill joe))
* (sun mon tue wed thur fri sat)
* ( )

#### Difference with S-expressions
In Scheme, a list and an S-expression are related concepts, but they have distinct meanings. A list is a specific data structure in Scheme that represents a sequence of elements. On the other hand, an S-expression is a notation used in Scheme to represent both data and code.

All lists are s-expressions, but s-expressions can have different forms other than lists, like (+ 2 3 4). In summary, a list is a specific data structure in Scheme that represents an ordered sequence of elements, while an s-expression is a notation used to represent data or code, which can include lists as a specific type of structure.

### Strings
A string is a group of characters enclosed in double quotation marks.
> Examples
* " I am a string"
* "a ba c d efg #$%^&!"
* "Please enter the following details :"
* "Hello from 'Tutorials Point'! “

#### Difference between an atom and a string
Having double quotation marks or not is not the only difference between an atom and a string. Strings are a specific data type in Scheme that represents a sequence of characters and it can be decomposed. Namely, strings can be accessed or modified character by character. On the other hand, atoms are basic, indivisible data elements in Scheme.

### Adding Comments in Scheme
The purpose of using comments:

Comments are very useful in providing human-readable explanations or annotations within the source code. They are non-executable lines of text that are ignored by the compiler or interpreter, serving as notes. We use comments to help those who are reading code.

> Example
* In Scheme, we use semicolon symbol to indicate a comment line:
```
`(display "Hello World")`` ; greet the world
; tell them your whereabouts
(display "I am at 'Tutorials Point'! Learning Scheme")
Anything after the ; will be ignored.
```

> Example (2)
```
(define (is-positive x)
  (if (> x 0)     ; checks x is bigger than 0
      (display "Positive")
      (display "Non-positive")))
(is-positive 7)                  
(is-positive -3)
```                
Note: `define` allows you to declare a function.

### Use of Single Quotation
Single quotations are used when you want a piece of code to be considered as literal expressions rather than having it evaluated as usual. For example, you want to use the `display` function to print the expression `(+ 2 3)` as it is, rather than printing the answer 5.

> Examples
* (display[7] "single quote used, it inhibits evaluation")
* (display '(* 2 3))
* (display " ")
* (display "single quote not used, so expression evaluated")
* (display (* 2 3))
When we execute this code, the printed value will be:
* single quote used, it inhibits evaluation
* (* 2 3)
* single quote not used, so expression evaluated
* 6

## Functions
Functions in Scheme are used to perform specific tasks or operations. They allow you to organize your code, make it more modular, and reuse code blocks.
With functions, you can:
* Perform mathematical calculations
* Manipulate strings
* Control program flow with conditional statements
* Create loops and iterate over lists or other data structures
* Define your own custom operations
Overall, functions are an essential part of programming in Scheme as they help in creating efficient and organized code.

### How to define functions
We can define a function by using `define`. The `define` procedure needs two arguments:
* Name of the function / Parameter of the function
* Body of the function

> Example (1)
```
(define (average 1st-number 2nd-number)
        (/ (+ 1st-number 2nd-number) 2))
```
`average` is the name of the function. The first line defines the function using `define`.
Parameters
The parameters, `(1st-number 2nd-number)` follow the function name `average`. These are symbols representing the numbers we are going to refer to later in the function.
Body of the function
The body of the function tells Scheme what it should do. `(/ (+ 1st-number 2nd-number) 2)`, which is the body in this function, calculates the average of the two numbers by summing them and dividing by 2.

> Example (2)

`square` function returns the square root of `x`. In order to do this, we need to provide `x`, which is the number we will square in this function. We will return the square root in the body of the function. The function will look like this:
```
(define (square x)
    (* x x))
```
> Example (3)

A function named `area-circle`:
```
        (define (area-circle rad)
                (newline)
                (display “Area: “)
        )
```

Should calculate the area of a circle when the radius of the circle `rad` is given.

The newline procedure is used to insert a newline character (line break) in the output. It is commonly used to add a new line after printing some content to the screen. The newline procedure does not take any arguments; it simply adds a newline character to the output stream.

We will use the format function to print `Area: `. The format function in Scheme is used to format and generate strings based on a format string and optional arguments. It provides a way to create custom string output with specific formatting for different types of data. The format function is quite versatile and allows you to control how data is presented in the output string.

Also, in Scheme, `~a` is a format control directive used within the format function for general formatting, including floating-point numbers. The completed area-circle function will be:
```scheme
(define (area-circle rad)
         (newline)
           (format "Area: ~a" (* 3.14 rad rad))
)
```


