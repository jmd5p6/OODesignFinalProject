# Classes

## Defining Classes

### Objective C 

Classes are defined in two different sections: @interface and @implementation

#### @interface
The begining of the class definition. This contains the class name and body, enclosed by a pair of curly braces.
This specifies exactly how a given type of object is intended to be used by other objects.

#### @implementation
This is what attributes the class' behavior to the class that has been defined in the interface. After importing the class, the @implementation tag is used to show exactly how the functions are supposed to opperate.

### Swift
Using the keyword class and the name of the class, a class can be created with their entire definition inside of a pair of braces.

## Creating new instances

### Objective C 
To create an instance of a class, type the name of the class, an asterisks followed immediately by the name that you are assigning to the instance you are creating, followed by equals, then inside a set of brackets add the class name and alloc, finally followed by a semi colon.

#### example
ClassName *example = `[ClassName alloc]`;

### Swift
The simplest form of initializer syntax uses the type name of the class or structure followed by empty parentheses.

#### example
let example = ClassName()

## Constructing/Initializing

### Objective C 
Similar to creating a new instance, to initialize an instance of a class the declaration begins the same, but affter allocing, the space for the instance, still inside the brackets, enter the initial values that are being asked for initialization

#### example
ClassName *example = `[[ClassName alloc] initFunc1:DataValue initFunc2:DataValue2]`;

### Swift
When the class is being written, by adding the function init(), at time of creating a new instance, you can request for information to be added for initialization.

#### example
let example = ClassName(initRequest: DataValue)

## Destructing/De-Initializing

### Objective C 
To deallocate the memory occupied by an instance of a class, simply use the dealloc method.

#### example
(void)dealloc{
  free(example)
}

### Swift
A deinitializer is called immediately before deallocation. Deinitializers are writted with the deinit keyword and are only available in class types. Swift automatically deallocates instances once they are no longer needed.
[Back to README.md](/README.md)
