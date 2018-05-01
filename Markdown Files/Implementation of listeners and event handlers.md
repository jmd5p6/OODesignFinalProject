# Implementation of listeners and event handlers

## How are listeners/event handlers implemented?
### Objective C 
Event handlers in Objective C are implemented through the `NSResponder` class. To create an event handler, override the corresponding method in the `NSResponder`. 
### Swift
Event handlers in Swift are implemented though protocols. In a controller, add a protocol such as `NSWindowDelegate` and implement the methods that trigger on the event you want, such as `windowDidResize`.  
  
[Back to README.md](/README.md)
