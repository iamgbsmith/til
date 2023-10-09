# No Such Module XCTest

__Category: Xcode__

If you create a test target in Xcode for a Swift project you might see the error `No such module 'XCTest'` when attempting to build for testing.

To fix this, go into the test target and select "Build Settings".

Search for the setting "Enable Testing Search Paths" and change the value to "Yes".

Your test classes which extend from `XCTestCase` should now compile.
