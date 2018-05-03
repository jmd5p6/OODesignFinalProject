# Lambda expressions, closures, or functions as types

## Does the language utilize lambda expressions, closures, or functions as types?

### Objective C 

Objective C uses lambda expressions, known as blocks.

### Swift

Swift uses closures, which are self-contained blocks of functionality that can be passed around and used in your code.

## If so, how does it utilize these?

### Objective C 

Blocks allow you to create distinct segments of code that can be passed around to methods or functions as if they were values.

### Swift

Closures can capture and store references to any constants and variables from the context in which they are defined. This is known as closing over those constants and variables. Swift handles all of the memory management of capturing for you.

[Back to README.md](/README.md)
