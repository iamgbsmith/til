# Render An SVG

__Category: React Native__

React Native does not provide support out-of-the-box for rendering SVG images. You need to use the additional package dependencies `react-native-svg` and `react-native-svg-transformer`.

This TIL will configure a React Native TypeScript project for use with SVG files.

Install the dependencies:

```shell
yarn add react-native-svg
yarn add --dev react-native-svg-transformer
```

On iOS, install the pods by navigating to the iOS directory and run the following:

```shell
pod install
```

Restart Xcode.

Update your Metro config:

```javascript
const {getDefaultConfig} = require('@expo/metro-config');

module.exports = (async () => {
  const {
    resolver: {sourceExts, assetExts},
  } = await getDefaultConfig(__dirname);
  return {
    transformer: {
      babelTransformerPath: require.resolve('react-native-svg-transformer'),
    },
    resolver: {
      assetExts: assetExts.filter(ext => ext !== 'svg'),
      sourceExts: [...sourceExts, 'svg'],
    },
  };
})();
```

Restart the Metro bundler.

To import SVG files, create a `declarations.d.ts` file in `/src/types`.

```javascript
declare module '*.svg' {
  import {SvgProps} from 'react-native-svg';
  const content: React.FC<SvgProps>;
  export default content;
}
```

Import the SVG in your component:

```javascript
import CalendarIcon from '../assets/icons/calendar.svg';

//...

<View style={[styles.header]}>
  <CalendarIcon height={24} width={24} fill="red" />
<View>
```
