# Go Tutorial
## Introduction to Go
### What is Go
Go, also known as Golang, is a programming language created by Google. It's designed to be simple and efficient, perfect for beginners like you! Imagine Go as a tool that helps build large projects easily, like constructing a building with advanced yet easy-to-use tools.

## First Steps in Go
### Your First Go Program: Hello World 
When you start learning a new language, you usually begin with a simple program that says "Hello World". In Go, this looks like this:

[helloworld](https://goplay.tools/snippet/mHIEl2BLCxl ':include :type=iframe width=100% height=400px')

> Exercise: Try changing "Hello World!" to a different message and see what happens.

If you run the code, it will print out "Hello World!" to the terminal.

### Understanding Packages and Imports
Think of a package in Go as a folder on your computer that holds related files. The import "fmt" line is like getting a tool from a toolbox - in this case, fmt is used to print text to the screen.

### Playing with Variables and Constants
Variables are like labels on jars; they can hold different things (values). Constants are similar but once you fill the jar, you can't change what's inside.

```go
var age int = 19
const name = "Alex"
```
> Exercise: Create a variable for your favorite color and a constant for your birth year.

[website](https://goplay.tools/snippet/2UfhdQeuphV ':include :type=iframe width=100% height=400px')

### Simple Operations and Functions
Functions in Go are like recipes. They take ingredients (inputs), do something with them, and sometimes give back a result.

> Example
```go
func addNumbers(a int, b int) int {
    return a + b
}
```
> Exercise: Write a function that subtracts one number from another.

[website](https://goplay.tools/snippet/aRrVK6l1tFE ':include :type=iframe width=100% height=400px')

### Making Decisions: If Statements
In programming, sometimes you need to make decisions. Go uses 'if' statements for this, like a crossroad where you take different paths based on a condition.

```go
if temperature > 30 {
    fmt.Println("It's hot outside!")
} else {
    fmt.Println("It's not that hot.")
}
```
> Exercise: Create an 'if' statement that checks if a number is greater than 10.

[website](https://goplay.tools/snippet/aRrVK6l1tFE ':include :type=iframe width=100% height=400px')

### Repeating Tasks: Loops
Loops in Go are like telling your computer to repeat a task several times, like running around a track.
> Example
 ```go
 for i := 0; i < 5; i++ {
    fmt.Println("Loop iteration", i)
}
 ```
> Exercise: Write a loop that counts from 1 to 10.

[website](https://goplay.tools/snippet/aRrVK6l1tFE ':include :type=iframe width=100% height=400px')