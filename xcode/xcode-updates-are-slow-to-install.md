# Xcode Updates Are Slow To Install

__Category: Xcode__

Downloading and installing Xcode updates can seem to take an extremely long amount of time, often with no indication of progress towards completion other than seeing "Installing..." on  Launchpad even after the app has been updated in App Store. 

In some cases, you will see a dialog when trying to launch Xcode with the message: _You can’t open the application “Xcode” because it is being updated._ 

To check on the update progress for Xcode: 

1. Open the Console app

2. Press the "Start" icon to start logging. 

3. Type "App Store" in the search bar.

You will see messages being logged similar to the following:

```shell
ASDAppQuery.resultsDidChange H:ae8f99a5a4: <NSProgress: 0x6000002cbf00> : Parent: 0x0 (portion: 0) / Fraction completed: 0.8440 / Completed: 844 of 1000
...
ASDAppQuery.resultsDidChange H:ae8f99a5a4: <NSProgress: 0x6000002cbf00> : Parent: 0x0 (portion: 0) / Fraction completed: 0.8550 / Completed: 855 of 1000
```

The Xcode update will finish when logs show: `ASDAppQuery.resultsDidChange H:ae8f99a5a4: <BundleID=com.apple.dt.Xcode, Installed=true, LaunchProhibited=false, IsBeta=false>`.
