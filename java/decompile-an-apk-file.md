# Decompile An APK File

__Category: Java__

__Disclaimer: Do not use apktool on an application for unauthorised reasons__

An Android Package Kit (APK) file is a compiled program that runs on an Android device. You can decompile an APK file using `apktool` in order to learn how an app works or assess its vulnerabilities. 

To install APK tool on macOS:

```shell
brew install apktool
```

For other platforms, follow installation instructions at https://ibotpeaches.github.io/Apktool/install/

Decompile the APK file:

```shell
apktool d filename.apk
```

By default, the contents on the APK file will be written to a directory matching the name of the input file (without the .apk extension). Decopiled code might also be obfuscated making it more difficult to understand.

See [Apktool](https://ibotpeaches.github.io/Apktool/) for more details.
