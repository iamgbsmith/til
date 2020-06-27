# Remove Launch Screen White Flash

iOS apps developed with React Native will momentarily flash a white screen when launching while the bridge is initialising. This can be fixed by creating a custom launch screen and showing it only for as long as required when the app starts.

__Note:__ As announced at WWDC19, starting April 2020, apps submitted to the App Store must use an Xcode storyboard to provide the app’s launch screen and must have an interface that supports any display size.

### Create a custom launch screen

In Xcode, create a new launch screen. 

File | New -> File then from the dialog select iOS User Interface -> Launch Screen. Call the file `LaunchScreen`.

Customise the new launch screen storyboard with the relevant image and text, changing the background colour of screen to match app branding.

Associate this newly created screen to your app in the General settings of your project. Set the value of `Launch Screen File` to the name of your new storyboard called `LaunchScreen`.

### Prevent the white flash when the app starts

Add the `react-native-splash-screen` package and link it to the application.

```bash
yarn add react-native-splash-screen
react-native link react-native-splash-screen
```

In Xcode, open the `AppDelegate.m` file.

Add `#import "RNSplashScreen.h"` immediately below the line `#import <React/RCTRootView.h>` and then add `[SplashScreen show];` immediately above `return YES;` in the `didFinishLaunchingWithOptions` method.

In the main JavaScript view, add `import SplashScreen from 'react-native-splash-screen';` and in the `componentDidMount` method, hide the splash screen.

```JavaScript
componentDidMount() {
  SplashScreen.hide()
}
```

If the background of the custom launch screen uses a dark colour, you may want to set the statusbar color to light when it is shown. 

Open Info.plist in Xcode and add a new row using the key "UIStatusBarStyle" with a string value of "UIStatusBarStyleLightContent".

See [Building Adaptive User Interfaces for iPhone and iPad](https://developer.apple.com/news/?id=01132020b) and [react-native-splash-screen](https://github.com/crazycodeboy/react-native-splash-screen) for more details.