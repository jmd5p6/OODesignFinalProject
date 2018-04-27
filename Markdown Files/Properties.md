# Properties

## Getters and Setters (Write your own or built in?)

### Objective C 
Getters: 
```objective-c
- (int)someNumber {
    return 42;
}
```  
Setters:  
```objective-c
- (void)setSomeNumber: (int)newValue { 
  _someNumber = newValue;
}
```  
### Swift  
Getters and Setters:
```swift
class Point {
  private var _x: Int = 0
  var x: Int {
    set { _x = 2 * newValue }
    get { return _x / 2 }
  }
}
```

## Backing Variables?

### Objective C 
Backing variables are created automatically when yo ucreate a property in Objective-C, named _yourPropertyName
### Swift  
Backing variables are supported in the case of computed properties in Swift. An example can be seen below in the swift Computed Properties Section. 

## Computed Properties?

### Objective C 
Computed Properties are supported in Objective-C
```objective-c
-(NSDate*)nsDate{
 return [Conversion toNSDate:date];
}
```

### Swift  
Computed Properties are supported, as seen here: 
```swift
struct Point {
    var x = 0.0, y = 0.0
} 
struct Size {
    var width = 0.0, height = 0.0
}
struct Rect {
    var origin = Point()
    var size = Size()
    var center: Point {
        get {
            let centerX = origin.x + (size.width / 2)
            let centerY = origin.y + (size.height / 2)
            return Point(x: centerX, y: centerY)
        }
        set(newCenter) {
            origin.x = newCenter.x - (size.width / 2)
            origin.y = newCenter.y - (size.height / 2)
        }
    }
}
```  
This also shows the use of backing variables.  

  
[Back to README.md](/README.md)
