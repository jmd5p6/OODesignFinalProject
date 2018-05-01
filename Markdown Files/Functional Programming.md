# Functional Programming

## Does the language support functional programming?

### Objective C 
...Kinda You have to implement a lot of work arounds yourself through for the lack of primative functions, multiple returns, and generic types other than lightweight generic types. 
### Swift
Yes it is. It is even used in `.sorted()` where you have to implement your own comparison function. Functions are first class citizens and can be passed as parameters. As an example here is a quicksort algorithm programmed functionally from [Swift Algorithm Club](https://github.com/raywenderlich/swift-algorithm-club/tree/master/Quicksort)
```swift
func quicksort<T: Comparable>(_ a: [T]) -> [T] {
  guard a.count > 1 else { return a }

  let pivot = a[a.count/2]
  let less = a.filter { $0 < pivot }
  let equal = a.filter { $0 == pivot }
  let greater = a.filter { $0 > pivot }

  return quicksort(less) + equal + quicksort(greater)
}
```
Copyrighted and licensed with [MIT License](https://github.com/raywenderlich/swift-algorithm-club/blob/master/LICENSE.txt)

[Back to README.md](/README.md)
