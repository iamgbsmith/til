# Use SwiftUI With UIKit Or Cocoa

__Category: Swift__

When developing Swift applications that use storyboards, it is possible to incorporate SwiftUI views with a `UIViewController` (UIKit for iOS) or `NSViewController` (Cocoa for macOS) by wrapping the view in either a `UIHostingController` or `NSHostingController`.

The example here is for a Swift app running on maOS with a SwiftUI view called `DashboardView`.

### Create a view controller

In the view controller, wrap the SwiftUI view in an NSHostingController. 

Ensure the view uses all available space from the parent container by setting up constraints.

```swift
import Cocoa
import SwiftUI

class DashboardViewController: NSViewController {

    private var dashboardView: DashboardView!
    private var dashboardViewHostingController: NSHostingController<DashboardView>!

    override func loadView() {
        dashboardView = DashboardView()
        dashboardViewHostingController = NSHostingController(rootView: dashboardView)
        
        let frame = NSRect(
            x: 0,
            y: 0,
            width: 800,
            height: 300
        )

        view = NSView()
        view.frame = frame
        view.wantsLayer = true
    }
    
    override func viewDidLoad() {
        super.viewDidLoad()
        view.addSubview(dashboardViewHostingController.view)
        setupConstraints()
    }
    
    fileprivate func setupConstraints() {
        dashboardViewHostingController.view.translatesAutoresizingMaskIntoConstraints = false
        dashboardViewHostingController.view.topAnchor.constraint(equalTo: view.topAnchor).isActive = true
        dashboardViewHostingController.view.leftAnchor.constraint(equalTo: view.leftAnchor).isActive = true
        dashboardViewHostingController.view.bottomAnchor.constraint(equalTo: view.bottomAnchor).isActive = true
        dashboardViewHostingController.view.rightAnchor.constraint(equalTo: view.rightAnchor).isActive = true
    }
    
}
```

### Show the SwiftUI view

If the SwiftUI view needs to be displayed in a window, embed as follows:

```swift
private func setupWindow() {
    window = NSWindow()
    window.backingType = .buffered
    window.contentViewController = self.dashboardViewController
    window.isOpaque = false
    windowController = NSWindowController()
    window.center()
    dashboardViewController.view.wantsLayer = true
    window.makeKeyAndOrderFront(nil)
    window.titlebarAppearsTransparent = true    
    windowController.showWindow(self)
}
```
