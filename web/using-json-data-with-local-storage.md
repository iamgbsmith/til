# Using JSON Data With Local Storage

__Category: Web__

You might need to store and load JSON data from local storage. For example, if you application is a Progressive Web App and does not require a server backend.

Prefix the name of the data using your reverse FQDN name to differentiate it from other items in local storage.

Save JSON object to localStorage:

```javascript
const data = '{ foo: 12, bar: 18, baz: 33, wibble: 42 }';
localStorage.setItem('com.orbiks.data.guesses', JSON.stringify(data));
```

Load JSON object from localStorage:

```javascript
const data = JSON.parse(localStorage.getItem('com.orbiks.data.guesses'));
```

__Note: Do not store personally identifiable or private information in local storage.__
