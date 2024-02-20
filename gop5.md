# Go Tutorial

## Introduction to Go Programming: Creating a Timely Greeting Tool

Welcome to our Go programming tutorial! Today, we'll make a simple yet interesting program—a tool that says hello in different ways depending on the time of day. This project will help you learn key ideas of Go, like how to organize your code, work with data, make decisions in your program, and group code into reusable parts.

### Writing the Basic Program Structure

Every Go program starts by stating which package it belongs to. For programs that run on their own, we use `package main`. We also need to use some tools from Go's standard library, so we'll include those too. For this project, we need `fmt` to show messages and `time` to figure out the current time.

```go
package main

import (
    "fmt"
    "time"
)
func main() {
    fmt.Println("Hello, World!")
}
```

This basic setup just says "Hello, World!". It's good to run this first to make sure everything is working fine.

## Making It More Interesting With Time Logic

Let's add some cleverness to our program. We want it to say good morning, good afternoon, or good evening, depending on the time. Replace the `main` function with this:

```go
func main() {
    now := time.Now() // Finds out the current time
    hour := now.Hour() // Gets the hour part of the current time

    if hour < 12 {
        fmt.Println("Good morning, World!")
    } else if hour < 18 {
        fmt.Println("Good afternoon, World!")
    } else {
        fmt.Println("Good evening, World!")
    }
}
```

Here, we use `time.Now()` to get the time right now, and `Hour()` to just look at the hour part. Then, we use `if-else` to decide what message to show.

## Improving Our Code With a Function

Our code works, but we can make it nicer by moving the greeting part into its own function. Right below where we import packages, let's add a new function called `greet`:

```go
func greet(hour int) {
    if hour < 12 {
        fmt.Println("Good morning, World!")
    } else if hour < 18 {
        fmt.Println("Good afternoon, World!")
    } else {
        fmt.Println("Good evening, World!")
    }
}
```

Now, change the `main` function to use our new `greet` function:

```go
func main() {
    now := time.Now()
    hour := now.Hour()
    greet(hour)
}
```

This makes our `main` function simpler and puts the greeting logic in one place, making it easier to change later.

### Testing Your Program

Run your program. You'll see a greeting that fits the time of day.

[greet](https://goplay.tools/snippet/edBSFutFghf ':include :type=iframe width=100% height=400px')


### Conclusion

Great job! You've built a straightforward Go program that introduces you to how Go works. You've seen how to organize your code, work with data, use `if-else` for decision-making, and group code into functions for reuse. This is a solid start for tackling more complex projects in Go.

## Understanding Go Syntax and Basic Concepts

After completing our timely greeting tool, let's dive deeper into the syntax and fundamental concepts of Go that we used in our project. This section will provide a clearer understanding of package declarations, importing packages, variables, constants, control structures, and functions.

### Package Declaration

Each Go file begins with a package declaration, which groups related code together. For executable programs, we use `package main`. This is how we start:

```go
package main
```

This line tells Go that the file belongs to the main package, which is special. The `main` package is where the program starts running.

### Importing Packages

To use code from Go's standard library or third-party packages, we need to import them. In our project, we used two packages:

- `fmt`: For printing text to the console.
- `time`: For getting the current time.

```go
import (
    "fmt"
    "time"
)
```

This `import` statement makes the `fmt` and `time` packages available in our program.

### Variables

Variables hold data that our program can use. We declare variables with a type, but Go can also infer the type from the initial value. We used a variable to store the current hour:

```go
hour := now.Hour()
```

Here, `hour` is automatically understood to be an integer because `now.Hour()` returns an integer.

### Constants

Constants are like variables, but their values cannot change. We didn't use constants in our project, but they are useful for values that remain the same throughout a program, like this:

```go
const welcomeMessage = "Hello, World!"
```

This constant holds a greeting message that won't change.

### Control Structures

Control structures guide the flow of the program. We used an `if-else` statement to decide what greeting to show based on the time:

```go
if hour < 12 {
    fmt.Println("Good morning, World!")
} else if hour < 18 {
    fmt.Println("Good afternoon, World!")
} else {
    fmt.Println("Good evening, World!")
}
```

This checks the hour and prints a different message for morning, afternoon, and evening.

### Functions

Functions are blocks of code that do a specific task. We made a `greet` function to organize our greeting logic:

```go
func greet(hour int) {
    // Greeting logic here
}
```

This function takes one parameter, `hour`, and contains the logic to print the correct greeting. We call this function from `main` to show our message.

## Conclusion

In this section, we've taken a closer look at Go's syntax and some key programming concepts. Understanding these basics is important for writing Go programs and will be the foundation for learning more advanced topics.