
# Request Device Permissions

__Category: React Native__

Device permissions on iOS or Android should be requested when you need to access capabilities such as the camera, microphone, location, contacts, or photo library. When requesting access, you should ask at the last possible moment needed rather when an application starts for the first time to make the user onboarding process as frictionless as posible.

### Device permissions on iOS

To request device permissions on iOS, add the following to your project's `Info.plist` inside the outermost `<dict>` tag:

```shell
<!-- To capture photos or video: -->
<key>NSCameraUsageDescription</key>
<string>$(PRODUCT_NAME) needs access to your Camera.</string>

<!-- To capture audio: -->
<key>NSMicrophoneUsageDescription</key>
<string>$(PRODUCT_NAME) needs access to your Microphone.</string>
```

### Device permissions on Android

To request device permissions on Android, add the following to your project's `AndroidManifest.xml` inside the `<manifest>` tag:

```shell
<uses-permission android:name="android.permission.CAMERA" />

<!-- optionally, if you want to record audio: -->
<uses-permission android:name="android.permission.RECORD_AUDIO" />
```

The user will then be prompted to approve device permissions if they have not been previously granted when you invoke a method such as `requestCameraPermission()` or `requestMicrophonePermission()` in the library being used by your project.