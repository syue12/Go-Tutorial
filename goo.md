# Go Tutorial
## Introduction to Go
### What is Go
Go, also known as Golang, is an open-source programming language developed by Google. It was created to address the needs of developers working on large-scale projects. 

When Go was designed in 2007, Java and C++ were the most commonly used languages for writing servers. These languages required too much bookkeeping and repetition. Some programmers reacted by moving towards more dynamic, fluid languages like Python, at the cost of efficiency and type safety. In this case, there needs to be a single language that has the efficiency, the safety, and the fluidity.

Go is expressive, concise, clean, and efficient. Its concurrency mechanisms make it easy to write programs that get the most out of multicore and networked machines, while its novel type system enables flexible and modular program construction. Go compiles quickly to machine code yet has the convenience of garbage collection and the power of run-time reflection. It's a fast, statically typed, compiled language that feels like a dynamically typed, interpreted language.
### Where is Go used?
**Web Development**: Go is commonly used for building web servers, RESTful APIs, and microservices due to its strong support for concurrency and networked operations.

**Cloud Computing**: Go is popular in cloud computing and is used by companies like Google, AWS, and Dropbox. It's efficient for building scalable cloud applications.

**DevOps and Site Reliability Engineering**: With its fast compilation and execution, Go is ideal for DevOps and SRE tools. Kubernetes, a popular container orchestration system, is written in Go.

**Command-Line Tools**: Go's simplicity and compilation of a single binary make it a great choice for developing command-line tools.

Go's performance is comparable to C++, making it suitable for high-performance applications. On the other hand, Go's simplicity makes it easy to learn, especially for those familiar with C or C++. Go also offers excellent resources for learning and problem-solving.
popularity and longevity.
## Syntax
### Hello World Program
In Go, every program is part of a package. Programs start running in package main. A Go program consists of the following parts:
- Package declaration
- Import packages
- Functions
- Statements and expressions

Let’s start with an example. When learning a new language, we often write a little program that prints the text “Hello, world!” to the screen, so let’s do it here!

[helloworld](https://goplay.tools/snippet/mHIEl2BLCxl ':include :type=iframe width=100% height=500px')

If you run the code, it will print out "Hello World!" to the terminal.

Let’s focus on the first line package main. This line is called a package declaration and it tells the Go compiler to which package this ‘.go’ file belongs. If this package declaration is `package main`, then this program will be compiled into an executable.

Then we have an import statement, import `fmt`. The import keyword allows us to use code from other packages, in this case the Println function from the fmt package. Note how the package name is enclosed with double quotes `"`.

Then we use the `func` keyword to declare a function. The `func` keyword denotes the start of a function declaration, and it’s followed by the name of the function: `main`.
After the name there follows a pair of parentheses `()` and a set of curly braces `{}`.
The function code is written inside the set of curly braces.

The code inside a function is indented. The code here invokes the `Println` function in the `fmt` package (that we imported earlier) to print the message `"Hello World"`.

When we have a `main` function in the main package, this is special to Go. When compiled and run, it uses the `main` function as the starting point.

### Importing Packages
To import multiple packages, we can add multiple import statements:
```go
import "package1"
import "package2"
```
Or use a single import with parentheses:
```go
import (
  "package1"
  "package2"
)
```
We can also provide an alias to a package by specifying an alias name before the package name.
```go
import (
  p1 "package1"
  "package2"
)
```
In the example above we’ve aliased package1 as p1 and now we can call functions from package1 by using p1 like:

```go
p1.SampleFunc()
```

Instead of:

```go
package1.SampleFunc() 
```


### Exported Names
In Go, a name is exported if it begins with a **capital letter**. For example, Println is an exported name, which is exported from the `fmt` package. `Pi` is an exported name from the `math` package.

The code below will report an error as the exported name is incorrect. You should be able to fix it.

[exportedname](https://goplay.tools/snippet/Jcp1fMKMbr3 ':include :type=iframe width=100% height=400px')

`math.pi` should be `math.Pi`.

### Go Comments
A comment is a text that is ignored upon execution. Comments can be used to explain the code, and to make it more readable. Comments can also be used to prevent code execution when testing an alternative code. Go supports single-line or multi-line comments.

[comments](https://goplay.tools/snippet/SLtC3iLYyZC ':include :type=iframe width=100% height=400px')

## Constants and Variables
Naming a value in Go means creating a word that will represent that value. One example of named values are constants, which cannot be updated while the program is running. Another example of named values are variables which we can update their value.

### Variable Types
In Go, there are different types of variables, for example:

- int- stores integers (whole numbers), such as 123 or -123
- float32- stores floating point numbers, with decimals, such as 19.99 or -19.99
- string - stores text, such as "Hello World". String values are surrounded by double quotes
- bool- stores values with two states: true or false

Go is a **statically** typed language, which means data types in Go are bound to variables rather than values. If you define a variable as an int, it can only be an int; you can’t assign a string to it without converting the data type of the variable.

### Declare a variable
Variables are placeholder names that we use to refer to values that we intend to update over the course of our program. Updating our variable is also called assigning a value to a variable. In order to assign values to variables, we can use the assignment operator `=` followed by a value.

In Go, there are two ways to declare a variable:
#### With the var keyword:
Use the var keyword, followed by variable name and type:
Syntax
```go
var variablename type = value
```
Note: You always have to specify **either type or value (or both)**.

#### With the := sign:
Inside a function, the := short assignment statement can be used in place of a var declaration with implicit type. Outside a function, every statement begins with a keyword (var, func, and so on) and so the := construct is not available.
Syntax
```go
variablename := value
```
Note: In this case, the type of the variable is inferred from the value (means that the compiler decides the type of the variable, based on the value).

When we declare a Go variable without specifying its data type and assign the variable (using ``:=`` or `var =`) to a whole number, the Go compiler automatically infers the variable data type as an int. 

For example:
```go
score := 85
var temperature = 60
```

#### Multiple Go variables 
Variables can be declared and initialized on the same line delimited with a comma. If they are of the same type, the type can be optionally declared after the variable names before the assignment operator. For example:
```go
var x, y int = -1, 5
a, b := 7, 2
fmt.Println(x, y, a, b)
// -1, 5, 7, 2
```
If the variables are of different types, they can also be declared on the same line without the type designation.
```go
found, answer := true, "yes"
var name, age = "Steve", 35
fmt.Println(found, answer, name, age)
// true, "yes", "Steve", 35
```

### Constant
If a variable should have a fixed value that cannot be changed, you can use the const keyword.

The const keyword declares the variable as "constant", which means that it is **unchangeable** and **read-only**.

We use the `const` keyword to create a constant. We immediately assign a value to the constant using a literal.

```go
const CONSTNAME type = value

const pi = 3.1415926
```
Multiple constants can be grouped together into a block for readability:
```go
const (
  A int = 1
  B = 3.14
  C = "Hi!"
)
```

### Output
#### Go Fmt .Print() and .Println()
The Go fmt package supports two closely-related functions for formatting a string to be displayed on the terminal. .Print() accepts strings as arguments and concatenates them without any spacing. .Println(), on the other hand, adds a space between strings and appends a new line to the concatenated output string.
```go
fmt.Print("I", "am", "cool")
// Iamcool
fmt.Println("I", "am", "cool")
// I am cool
```
#### Go Fmt .Printf() Function
The Go .Printf() function in fmt provides custom formatting of a string using one or more verbs. A verb is a placeholder for a named value (constant or variable) to be formatted according to these conventions:

- %v represents the named value in its default format
- %d expects the named value to be an integer type
- %f expects the named value to be a float type
- %T represents the type for the named value

The first argument for `.Printf()` is the string with verb(s) followed by one or more named values corresponding to the verb(s). Unlike `.Println()`, `.Printf()` does not append a newline to the formatted string.

## Go If Statement
Functions perform specific tasks and improve code modularity and reusability.

A Go if statement evaluates a condition and executes a statement block enclosed in curly braces {..} if the evaluation returns true. The condition may be optionally enclosed inside a pair of parentheses (...).
```go
if healthy {
  fmt.Println("Work.")
}
if sick {
  fmt.Println("Stay home.")
}
```
### Go else Statement
A Go else statement can succeed an if or if else-if statement block and its code executed if the conditions in the preceding if or if else-if statements evaluate to false.
```go
sick := false
if sick {
  fmt.Println("Call the doctor.")
} else {
  fmt.Println("Enjoy your day.")
}
```
### Go Else If Statement
The Go else if statement provides an additional condition to evaluate besides the first if conditional. It can only appear after the if statement and before an else statement if it exists. For example:
```go
if temperature < 60 {
  fmt.Println("Put on a jacket.")
} else if (temperature >= 60 && temperature < 75) {
  fmt.Println("Put on a light sweater.")
} else {
  fmt.Println("Wear summer clothes.")
}
```
[if](https://goplay.tools/snippet/oI3EK3_FGqy ':include :type=iframe width=100% height=400px')

Multiple else if statements can exist alongside the if statement. The if else if statements are scanned from top to bottom and only the code block associated with a true condition is executed. If none of the conditions are satisfied, the else code block is executed if it exists.


## Functions
### Create a Function
To create (often referred to as declare) a function, do the following:
1. Use the func keyword.
2. Specify a name for the function, followed by parentheses ().
3. Finally, add code that defines what the function should do, inside curly braces {}.

Functions are not executed immediately. They are "saved for later use", and will be executed when they are called.

### Naming Rules for Go Functions
A function name must start with a letter. A function name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ ). Function names are case-sensitive. A function name cannot contain spaces

### Parameters and Arguments
Information can be passed to functions as a parameter. Parameters act as variables inside the function.

Parameters and **their types** are specified after the function name, inside the parentheses. You can add as many parameters as you want, just separate them with a comma:

```go
package main
import ("fmt")

func familyName(fname string) {
  fmt.Println("Hello", fname, "Harry")
}

func main() {
  familyName("Potter")
}
```
### Return Values
If you want the function to return a value, you need to define the data type of the return value (such as int, string, etc), and also use the return keyword inside the function:
```go
package main
import ("fmt")

func myFunction(x int, y int) int {
  return x + y
}

func main() {
  fmt.Println(myFunction(1, 2))
}
```
[fuc](https://goplay.tools/snippet/LnOY1uYq7-Q ':include :type=iframe width=100% height=400px')
