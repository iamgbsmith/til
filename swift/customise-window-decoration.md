# Customise Window Decoration

__Category: Swift__

Instances of `NSWindow` can be customised in a number of ways. For example you can remove the title text or make the title bar transparent.

### Hide the window title (text)

```swift
window.titleVisibility = .hidden
```

### Set the window title to use a transparent background

```swift
window.titlebarAppearsTransparent = true
```

### Remove all window decoration

You can remove the close, resize, miniaturise buttons and the title bar.

```swift
window.styleMask.remove(.titled)
```

### Remove specific window buttons

```swift
window.styleMask.remove(.closable)        // close button (red)
window.styleMask.remove(.miniaturizable)  // miniaturise button (yellow)
window.styleMask.remove(.resizable)       // resize button (green)
```

### Use all available space within the window

```swift
window.titlebarAppearsTransparent = true
window.styleMask.insert(.fullSizeContentView)
```
