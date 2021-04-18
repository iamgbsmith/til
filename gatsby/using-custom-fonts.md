# Using Custom Fonts

__Category: Gatsby__

The steps outlined here are based on using the Fontsource library which allows you to load equivalent Google Fonts. 

Fonts available for use are listed in https://github.com/fontsource/fontsource/tree/master/packages

### Install the font

For example, to install the Montserrat font run the following command:

`npm install @fontsource/montserrat`

### Import the package

In your `src/components/layout.js` file import the package:

```javascript
import "@fontsource/montserrat" // Defaults to weight 400
```

Alternatively, you can import italic or bold styles for the font:

```javascript
import "@fontsource/montserrat/700.css" // Weight 700
import "@fontsource/montserrat/italic.css" // Italic variant
```

Once the font is imported, you can reference the font name in a CSS stylesheet, CSS Module, or CSS-in-JS (for example, Styled Component).

```css
body {
  font-family: "Montserrat";
}
```
