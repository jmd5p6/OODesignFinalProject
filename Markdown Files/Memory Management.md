# Memory Management

## How is it handled?

### Objective C 
Objective-C provides two methods of application memory management:  
  
1. MRR, or Manual Retain-Release (Manual Management)
2. ARC, or Automatic Reference Counting (Automatic Management)  
  
It is recommended by Apple that you should use ARC for new projects, as it is simpler. Objective-C previously only had MRR, but Apple later implemented ARC.    

### Swift  
Swift also utilizes ARC, as it is a high-level language. In most cases, memory management "just works" in Swift.  

## How does it work?

### Objective C (MRR) 
With MRR, you must, as the name implies, explicitly track any objects that you "own" or are using. This is implemented using reference counting, similar to *malloc* or *dealloc* in C, although the Cocoa framework utilizes *retain* and *release*.  
  
By calling release, you tell the object you are letting go of it, and its reference count is decremented. If, after calling release, the reference count is now zero, then that object's memory is freed by the system.  

### ARC  
According to Apple, as a part of their Swift documentation, "Using ARC in Swift is very similar to the approach described in 'Transitioning to ARC Release Notes' for using ARC with Objective-C." Subsequently, their category has been combined.  
  
  
Everytime you create a new instance of a class, ARC allocates memory to store that instance and information about that instance. It also automatically deallocates these chuns of memory once they are no longer needed. To prevent deallocating an instance still in use, ARC will not deallocate an instance as long as at least one active reference to that instance still exists.

## Garbage Collection?

### Objective C 
After its transition to ARC, Objective-C's Garbage Collection system was deprecated, as it became automated.  

### Swift  
Because Swift solely utilizes ARC, garbage collection is completely automated.

## Automatic reference counting?

### Objective C   
Objective-C began using MRR, but transitioned to ARC.  

### Swift  
Swift utilizes ARC.  

[Back to README.md](/README.md)
