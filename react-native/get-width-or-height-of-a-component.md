# Get Width Or Height Of A Component

__Category: React Native__

React Native provides the ability to get the width of the screen using `Dimensions.get('screen').width` and window using `Dimensions.get('window').width` methods. Height can be obtained using `.height`.

`Dimensions` does not provide the ability to get the width or height of an individual component however it is possible to get these values using the `onLayout` callback. 

The following example obtains the component width and height, storing the values in the component state for future use.

Store the width in the state for the component.

```javascript
state = {
  width: 0,
  height: 0,
};
```

Obtain the width of the component using the `onLayout` event.

```javascript
<View
  style={styles.container}
  onLayout={event => {
    this.setState({
      width: event.nativeEvent.layout.width, 
      height: event.nativeEvent.layout.height
    });
    console.log('Layout event', event.nativeEvent.layout);
  }}
>
</View>
```

Use the values as required.

```javascript
<View style={[styles.box, {width: this.state.width - 20}]}>
  <Text>Hello World!<Text>
</View>
```

