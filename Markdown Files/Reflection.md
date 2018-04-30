# Reflection

## What reflection abilites are supported?

### Objective C 
Objective C objects can give you their type, fields, and method signatures. You can also access the same information about the superclass as well as check if an object conforms to a protocol.  
### Swift
Swift objects can give you their type, fields, and method signatures. You can also access the same information about the superclass as well as check if an object conforms to a protocol.  

## How is reflection used?

### Objective C 
There are standard library functions for getting and modifying properties of an object at at runtime such as 
```objective-c 
- (BOOL)conformsToProtocol:(Protocol *)aProtocol;
``` 

### Swift
Swift uses the `Mirror` struct for reflection, which contains a number of members such as `DisplayType` and `AncestorRepresentation` to represent all the attributes for an object.
[Back to README.md](/README.md)
