# Calculate Seconds Between Dates

__Category: JavaScript__

Calculate the difference in seconds between two dates with the following code:

```javascript
let startDate = new Date();
// Execute a function or call a remote endpoint...
let endDate = new Date();
let duration = ((endDate.getTime() - startDate.getTime()) / 1000;
console.log("Difference between the dates is", duration);
```
