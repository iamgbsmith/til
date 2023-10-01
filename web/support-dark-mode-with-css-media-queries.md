# Support Dark Mode With CSS Media Queries

__Category: Web__

You can support dark mode using CSS media queries. For example, to change the colour of a background from light to dark, use the `prefers-color-scheme` media query. 

The following CSS swaps the background colour and text color for content on your site when your system is using a dark colour scheme:

```css
body {
  background-color: #fff;
  color: #000;
}

@media (prefers-color-scheme: dark) {
  body {
    background-color: #000;
    color: #fff;
  }
}
```
