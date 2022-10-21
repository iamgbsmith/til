# Detect Dark Mode For A Browser

__Category: Web__

You can query whether a host operating system is using dark mode using the following JavaScript:

```javascript
const prefersDarkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
console.log(`Prefers dark mode ${prefersDarkMode}`);
```

Use this variable to enable a dark mode theme for your web application.
