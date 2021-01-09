# Functional Components

__Category: React Native__

There are two approaches to writing components in React and React Native:

* Class Components (ES6)
* Functional Components (also referred to as Function Components)

It is now commonly accepted that Functional Components should be used in preference to Class Components as code is easier to read and test. Functional Components do not have any React lifecycle methods and always implement the render lifecycle method without using the `render` keyword.

Functional Components can be enhanced using React Hooks which let you use state and lifecycle methods inside functional components.

### Functional component example

The following is an example of a stateless functional component written using TypeScript. In the props object, there is a read-only string property called title.

```javascript
import React from 'react';
import {StyleSheet, Text, View} from 'react-native';

interface TitleBarProps {
  readonly title: string;
}

const TitleBar: React.FunctionComponent<TitleBarProps> = (props: TitleBarProps) => {
  return (
    <View style={styles.titleBar}>
      <View>
        <View>
          <Text style={styles.title}>{props.title}</Text>
        </View>
      </View>
    </View>
  );
};

export default TitleBar;

var styles = StyleSheet.create({
  titleBar: {
    paddingTop: 20,
    paddingLeft: 15,
    backgroundColor: '#FFFFFF',
  },
  title: {
    fontSize: 28,
    fontWeight: 'bold',
  },
});
```

Use this component as follows:

```javascript
<TitleBar title={'Scores'} />
```
