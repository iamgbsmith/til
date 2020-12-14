# Hide The Dock Icon And Main Window For Your Application

You might want to hide the dock icon and main window when developing macOS menubar applications.

To do this, open `Info.plist` in your Xcode project. Add a new key `Application is agent (UIElement)` and set its value to `YES`.