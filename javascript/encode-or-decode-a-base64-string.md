# Encode Or Decode A Base64 String

__Category: JavaScript__

Assume a string:

```javascript
const phrase = "Pack my box with six dozen jugs";
```

Convert to base64:

```javascript
let encodedString = btoa(phrase);
console.log(encodedString); // Output = UGFjayBteSBib3ggd2l0aCBzaXggZG96ZW4ganVncw==
```

Convert from base64:

```javascript
let decodedString = atob(encodedString);
console.log(decodedString); // Output = Pack my box with six dozen jugs
```
