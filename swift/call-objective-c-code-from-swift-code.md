# Call Objective-C Code From Swift Code

__Category: Swift__

You can call Objective-C code from Swift code using a bridging header.

To create a bridging header file in your Swift project, from the Xcode menu select: File -> New -> File -> [operating system] -> Source -> Header File.

Name the file using the product module name followed by `-Bridging-Header.h` (for example `MyApp-Bridging-Header.h`)

Import the Objective-C header file to get access to all methods.

```c
//
//  Use this file to import your target's public headers that you would like to expose to Swift.
//

#import "CoolThing.h"
```

In your Swift code, create an instance of the class and call the Objective-C methods:

```swift
let coolThing = CoolThing()
coolThing.doSomething()
```

See [Importing Objective-C into Swift](https://developer.apple.com/documentation/swift/importing-objective-c-into-swift) for more details.
