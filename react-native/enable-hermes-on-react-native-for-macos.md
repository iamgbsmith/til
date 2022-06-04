# Enable Hermes On React Native For MacOS

__Category: React Native__

You can enable Hermes on a React Native for macOS app. This will only work if using RN version 0.62 or higher. 

Add the Hermes package:

```shell
yarn add hermes-engine-darwin
```

Edit `macos/Podfile` and uncomment the following line:

```text
:hermes_enabled => true
```

Regenerate the Pods:

```shell
cd macos && pod install
```

When Hermes is installed and activated, you will see the message "Engine: Hermes" (with a version, for example, 0.9.0) in the welcome view.
