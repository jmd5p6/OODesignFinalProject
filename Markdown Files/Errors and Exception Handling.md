# Errors and Exception Handling

## How are errors handled?

### Objective C 
In Objective-C, exceptions should only be used for programmer errors, such as an out-of-bounds exception. Most errors should use NSError.  

#### Errors
Some delegate methods alert you to errors:  
```objective-c
- (void)connection:(NSURLConnection *)connection didFailWithError:(NSError *)error;
```
This will provide you with an NSError object to describe the problem.  
  
Some Methods will pass errors by reference:  
```objective-c
  NSError *anyError;
    BOOL success = [receivedData writeToURL:someLocalFileURL
                                    options:0
                                      error:&anyError];
    if (!success) {
        NSLog(@"Write failed with error: %@", anyError);
        // present error to user
    }
```
#### Exceptions
```objective-c
@try {
        // do something that might throw an exception
    }
    @catch (NSException *exception) {
        // deal with the exception
    }
    @finally {
        // optional block of clean-up code
        // executed whether or not an exception occurred
    }
```
  
### Swift  
In Swift, errors are represented by values of types that conform to the Error protocol. This empty protocol indicates that a type can be used for error handling.  
#### Catching and Throwing Errors
```swift
enum VendingMachineError: Error {
    case invalidSelection
    case insufficientFunds(coinsNeeded: Int)
    case outOfStock
}

throw VendingMachineError.insufficientFunds(coinsNeeded: 5)
```
#### Handling Errors  
There are 4 ways to handle errors in Swift:  
1. Propagate the error from a function to the code that calls that function
A function can either throw or not throw an error, as demonstrated below
```swift
func canThrowErrors() throws -> String
 
func cannotThrowErrors() -> String
```
2. Handle the error using a do-catch statement
```swift
var vendingMachine = VendingMachine()
vendingMachine.coinsDeposited = 8
do {
    try buyFavoriteSnack(person: "Alice", vendingMachine: vendingMachine)
    print("Success! Yum.")
} catch VendingMachineError.invalidSelection {
    print("Invalid Selection.")
} catch VendingMachineError.outOfStock {
    print("Out of Stock.")
} catch VendingMachineError.insufficientFunds(let coinsNeeded) {
    print("Insufficient funds. Please insert an additional \(coinsNeeded) coins.")
} catch {
    print("Unexpected error: \(error).")
}
```
3. Handle the error as an optional value
```swift
func someThrowingFunction() throws -> Int {
    // ...
}
 
let x = try? someThrowingFunction()
 
let y: Int?
do {
    y = try someThrowingFunction()
} catch {
    y = nil
}
```
4. Or, assert that the error will not occur
  
  
[Back to README.md](/README.md)
