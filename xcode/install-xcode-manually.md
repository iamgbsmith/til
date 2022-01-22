# Install Xcode Manually

__Category: Xcode__

In some scenarios, for example where disk space is low, Xcode might not download and install from the App Store on macOS.

If this happens, you can download the binary from https://developer.apple.com/download/all/ and install it manually.

Extract the Xcode archive `.xip` file to disk, ensuring that the destination for Xcode is the /Applications folder. 

__Note:__ If disk space problems persist, delete the contents of the following directories:

```shell
~/Library/Developer/CoreSimulator
~/Library/Developer/XCTestDevices
~/Library/Developer/Xcode
```

Then try reinstalling from the downloaded Xcode xip file.

Delete the downloaded xip file once you have finished installation.
