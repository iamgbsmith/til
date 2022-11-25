# Unable To Boot Device In Current State

__Category: React Native__

You might see the error dialog stating "Unable to boot device in current state: Booted" when starting a React Native app in the simulator with the command:

```shell
npx react-native run-ios
```

To prevent this error, from the Simulator menu select Simulator -> Preferences -> Simulator lifetime.

Uncheck the checkbox "When Simulator starts boot the most recently used simulator".
