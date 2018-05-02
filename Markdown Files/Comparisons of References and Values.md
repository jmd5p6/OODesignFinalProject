# Comparisons of References and Values

## How are values compared?

### Objective C 
Compound data types are represented using @class instances, which are handled using reference semantics. Therefore values are compared by references.

### Swift
Objects of the class type are treated as a reference and objects of the struct type are treated by value. Both references and values are used for comparison in Swift depending on if they are structs or classes.
[Back to README.md](/README.md)
