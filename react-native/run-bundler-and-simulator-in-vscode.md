# Run Bundler And Simulator In VSCode

__Category: React Native__

To run the bundler and simulators in VSCode for your React Native project, open a terminal window from the VSCode menu: Terminal -> New Terminal. 

In the first terminal window, from your project directory start the bundler:

```shell
react-native start
```

In the other terminal window(s) from your project directory, launch the simulator:

```shell
react-native run-ios
```

Or:

```shell
react-native run-android
```

Launching simulators may take a few minutes if the application is being run on the simulator for the first time.