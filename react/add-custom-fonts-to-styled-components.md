# Add Custom Fonts To Styled Components

__Category: React__

Custom fonts can be added to styled components by loading the font face in a global style. 

Before referencing the font, download it and add to the project as static content. Ideally, use `.woff2` format as this provides a balance between good performance and browser compatibility.

This example assumes the use of TypeScript.

### Import the font from a URL

Do not attempt to create a custom global style which uses an `@import` statement as this generates the following JavaScript error:

_Please do not use @import CSS syntax in createGlobalStyle at this time, as the CSSOM APIs we use in production do not handle it well. Instead, we recommend using a library such as react-helmet to inject a typical <link> meta tag to the stylesheet, or simply embedding it manually in your index.html <head> section for a simpler app._

### Serve the font as static content

Create a file called `fonts.d.ts` in `/src` and include the font extensions you need to support:

```javascript
declare module '*.ttf';
declare module '*.woff2';
```

Create a file called `fontStyles.ts` for a global style containing the font face declaration.

```javascript
import { createGlobalStyle } from 'styled-components';

import RobotoTtf from './assets/fonts/roboto-regular.ttf';
import RobotoWoff2 from './assets/fonts/roboto-regular.woff2';

export const FontStyles = createGlobalStyle`
  @font-face {
    font-family: 'Roboto Condensed';
    font-style: normal;
    src: url(${RobotoTtf}) format('ttf'),
         url(${RobotoWoff2}) format('woff2');
    font-display: swap;
  }
`;
```

Including `font-display: swap;` will temporarily uses a system font and avoid showing invisible text while custom fonts are loading.

If you want a specific component to use the font:

```javascript
const BannerHeadline = styled.h1`
    font-family: 'Roboto Condensed';
`;

export default BannerHeadline;
```

If you want all components to use the font add the following to global styles:

```javascript
* {
  font-family: 'Roboto Condensed', ...
}
```
