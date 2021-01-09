# Set Badge Icon In The Dock

__Category: Swift__

Set the badge icon for applications running in the dock on macOS in Swift code as follows:

```swift
NSApp.dockTile.badgeLabel = "7";
```

Clear the badge icon by setting the value to an empty string.

```swift
NSApp.dockTile.badgeLabel = "";
```

Do not set the value in the string to a non-numeric value. Apple Human User Interface guidelines also suggest using badging to supplement notifications, not to denote critical information.