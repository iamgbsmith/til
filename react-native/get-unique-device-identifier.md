# Get Unique Device Identifier

__Category: React Native__

Every mobile device has a unique device identifier (UDID) to differentiate it from other devices. On iOS the UDID is used to send push notifications using the Apple Push Notification Service (APNS).

To determine the UDID for a device add the `react-native-device-info` package to your project:

```shell
yarn add react-native-device-info
```

For iOS, pods are autolinked from React Native 0.60 and above, however for you still need install them:

```shell
cd ios && pod install && cd ..
```

Import the `DeviceInfo` class:

```javascript
import DeviceInfo from 'react-native-device-info';
```

Get the device info:

```javascript
const App = () => {
  const [deviceId, setDeviceId] = useState('Unique Device Identifier Currently Unknown');

  const getdeviceId = () => {
    var uniqueId = DeviceInfo.getUniqueId();
    setDeviceId(uniqueId);
  };

  return (
    <SafeAreaView style={styles.container}>
      <View style={styles.container}>
        <Text style={styles.textStyle}>
          {deviceId}
        </Text>
        <Button style={styles.button}
          onPress={getdeviceId}
          title='Show UDID'
        />
      </View>
    </SafeAreaView>
  );
};

export default App;
```
