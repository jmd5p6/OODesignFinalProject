# Implementation of listeners and event handlers

## How are listeners/event handlers implemented?
### Objective C 
UI event handlers in Objective C are implemented through the `NSResponder` class. To create an event handler, override the corresponding method in the `NSResponder`. In a more broad context, event handlers are implemented through delegate protocols, where you declare the event handlers and implement them in a class.
### Swift
Event handlers in Swift are implemented though delegate protocols. In a controller, add a protocol such as `NSWindowDelegate` and implement the methods that trigger on the event you want, such as `windowDidResize`. Also, there are `IBActions` which connect functions to UI elements so that the triggeron certain events.
  
[Back to README.md](/README.md)
