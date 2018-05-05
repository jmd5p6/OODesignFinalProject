# Multithreading

## Threads or thread-like abilities
Each process (application) in OS X or iOS is made up of one or more threads, each of which represents a single path of execution through the application's code. Every application starts with a single thread, which runs the application's main function. Applications can spawn additional threads, each of which executes the code of a specific function.  
  
### Objective C 
Creating a thread in Objective-C  
```objective-c
NSThread* myThread = [[NSThread alloc] initWithTarget:self
                                        selector:@selector(myThreadMainMethod:)
                                        object:nil];
[myThread start];  // Actually create the thread
```
### Swift
Creating a thread in Objective-C
```swift

DispatchQueue.global(qos:.userInteractive).async {
    self.doSomeTimeConsumingTask() // takes 5 seconds to respond
    
    DispatchQueue.main.async {
        self.tableView.reloadData()
    }
}
```

## How is multitasking accomplished?

### Objective C 
```objective-c
// 1) Add to bottom of initWithHTML:delegate
backgroundQueue = dispatch_queue_create("com.razeware.imagegrabber.bgqueue", NULL);        

// 2) Add to top of dealloc
dispatch_release(backgroundQueue);

// 3) Modify process to be the following
- (void)process {    
    dispatch_async(backgroundQueue, ^(void) {
        [self processHtml];
    });    
}

// 4) Modify call to processZip inside retrieveZip to be the following
dispatch_async(backgroundQueue, ^(void) {
    [self processZip:data sourceURL:sourceURL];
});

// 5) Modify call to delegate at the end of processHTML **AND** processZip to be the following
dispatch_async(dispatch_get_main_queue(), ^(void) {
    [delegate imageInfosAvailable:imageInfos done:(pendingZips==0)];
});
```
### Swift  
```swift
DispatchQueue.global(qos: .userInitiated).async {  
    // Download file or perform expensive task

    DispatchQueue.main.async {  
        // Update the UI  
    }
}
```  
  
[Back to README.md](/README.md)
