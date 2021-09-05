# Create A Custom URL Scheme

__Category: Xcode__

A custom URL scheme can be configured in an Xcode project to allow launching of an application which matches the URL and then navigate to a specific screem or perfom an action depending on the URL contents.

Assume you are developing an application for macOS or iOS. You might want to use `myapp://` to launch the application in context through a push notification or a callback (where the callback URL could be from an OAuth redirect).

### Register the URL

Add the custom URL schme to `Info.plist` within the `<dict>` opening and closing tags as follows:

```xml
<key>CFBundleURLTypes</key>
<array>
  <dict>
    <key>CFBundleTypeRole</key>
    <string>Editor</string>
    <key>CFBundleURLName</key>
    <string>dev.soundbytes.MyApp</string>
    <key>CFBundleURLSchemes</key>
    <array>
      <string>myapp</string>
    </array>
  </dict>
</array>
```

### Process an incoming URL event

To handle an incoming call where the application is launched from URL, add the following to your `AppDelegate.swift` file:

```swift
/* Called when the app is launched via a URL */
func handleGetURLEvent(event: NSAppleEventDescriptor, replyEvent: NSAppleEventDescriptor) {
    if let aeEventDescriptor = event.paramDescriptor(forKeyword: AEKeyword(keyDirectObject)) {
        if let urlStr = aeEventDescriptor.stringValue {
            let url = NSURL(string: urlStr)
            // Create a URL from the incoming URL event string
            print("Processing incoming URL event \(urlStr) host \(url?.host) path \(url?.path) ")
            if (url?.host == "launch" && (url?.path!.hasPrefix("/page/dashboard"))!) {
                showDashboard()
            } else {
                // Catch-all
                showHome()
            }
        }
    }
}
```

In the above example, the application will handle an incoming URL which matches `myapp://launch/page/dashboard` and show the dashboard screen. Any other incoming URL for `myapp://` will show the home screen.

__Note: If the application is not running it will be launched when receiving a notification from the APNS.__
