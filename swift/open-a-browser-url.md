# Open A Browser URL

__Category: Swift__

You can open the default system browser for a given URL using Swift.

To open on iOS:

```swift
if let url = URL(string: "https://www.soundbytes.dev"), UIApplication.shared.open(url) {
    // On success
    print("Browser opened")
}
```

To open on macOS:

```swift
if let url = URL(string: "https://www.soundbytes.dev"), NSWorkspace.shared.open(url) {
    // On success
    print("Browser opened")
}
```
