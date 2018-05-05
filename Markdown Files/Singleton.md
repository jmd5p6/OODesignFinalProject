# Singleton

## How is a singleton implemented?

### Objective C 
#### MyManager.h
```objective-c
#import <foundation/Foundation.h>

@interface MyManager : NSObject {
    NSString *someProperty;
}

@property (nonatomic, retain) NSString *someProperty;

+ (id)sharedManager;

@end
```
#### MyManager.m  
```objective-c
#import "MyManager.h"

@implementation MyManager

@synthesize someProperty;

#pragma mark Singleton Methods

+ (id)sharedManager {
    static MyManager *sharedMyManager = nil;
    static dispatch_once_t onceToken;
    dispatch_once(&onceToken, ^{
        sharedMyManager = [[self alloc] init];
    });
    return sharedMyManager;
}

- (id)init {
  if (self = [super init]) {
      someProperty = [[NSString alloc] initWithString:@"Default Property Value"];
  }
  return self;
}

- (void)dealloc {
  // Should never be called, but just here for clarity really.
}

@end
```
#### Usage  
```objective-c
[MyManager sharedManager];
```

### Swift
Swift is much simpler:  
#### Implementation  
```swift
class MyManager {
    static let sharedInstance = MyManager()
}
```
#### Usage
```swift
MyManager.sharedInstance
```

## Can it be made thread-safe?
Singletons are thread-safe in both Objective-C and Swift.  

## Can the singleton instance be lazily instantiated?

### Objective C 
The example provided above is a lazy instantiation of a singleton in Objective-C.  
  
### Swift  
  
In Swift, you can simply use a static type property, which is guaranteed to be lazily initialized only once, even when accessed across multiple threads simultaneously.  
  
[Back to README.md](/README.md)
