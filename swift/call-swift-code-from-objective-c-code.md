# Call Swift Code From Objective-C Code

__Category: Swift__

This TIL shows how to call Swift code from Objective-C code in the same project without creating a circular dependency.

Add a forward reference in your Objective-C header file:

```c
@class YourSwiftClass; // Forward reference to Swift class

@interface YourObjectiveC : NSObject
{
    YourSwiftClass* yourSwiftClass;
}

@end
```

In your Objective-C implementation file, call the Swift method:

```c
#import "ProjectName-Swift.h"
#import "YourObjectiveC.h"

@implementation YourObjectiveC

// Implement methods or properties that use YourSwiftClass
[yourSwiftClass someMethod];

@end
```
