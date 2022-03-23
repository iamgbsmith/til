# Address Bar And Mobile Viewport Sizing

__Category: HTML__

Mobile devices present challenges with setting the correct viewport height. Specifying a value of 100% on iOS can result in the address bar covering page content, requiring the user to scroll up or down. Furthermore, it is difficult to hide the address bar using code unless deploying as a Progressive Web Applicaton (PWA).

Page content can be shown without the address bar obscuring it by calculating the viewport height, multiplying it by 0.01 and storing it in a variable for use in CSS. The value should be recalculated when the window is resized.

### Calculate viewport height

In `index.html` add the following JavaScript to calculate viewport height on page load and when window resize events are triggered.

```javascript
const calculateViewportHeight = () => {
  let vh = window.innerHeight * 0.01;
  document.documentElement.style.setProperty('--vh', `${vh}px`);
}

calculateViewportHeight();  

window.addEventListener('resize', () => {
  calculateViewportHeight();
});
```

### Set value for height using a variable

Height is calculated in your CSS using the value for `vh` obtained using JavaScript.

```css
body {
  /* Other values... */
  height: calc(var(--vh, 1vh) * 100);
}
```

This approach should work for Android and iOS.
