# Toggle Simulator Between Light And Dark Mode

__Category: React Native__

The following approaches can be used to toggle your simulator between light and dark mode when testing your React Native app on iOS or Android.

### Toggle on iOS simulator

Press `Cmd + Shift + a` to toggle between light and dark mode.

### Toggle on Android emulator

Run the following command to enable dark mode: 

`adb shell "cmd uimode night yes"` 

Run the following command to disable dark mode: 

`adb shell "cmd uimode night no"`
