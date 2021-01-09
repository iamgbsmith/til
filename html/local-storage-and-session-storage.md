# Local Storage and Session Storage

__Category: HTML__

Local and Session storage are provided by HTML5 Web Storage browser capabilities.

### When to use localStorage and sessionStorage

* `localStorage` should be used for data that needs to be accessed across windows or tabs, across multiple sessions or where large (at least 5MB) volumes of data may need to be stored for performance reasons.

* `sessionStorage` should be used for data that is relevant for one-instance of a workflow, such as details for a ticket booking, but where multiple workflows could be performed in other tabs concurrently. The window/tab bound nature prevents data from leaking between workflows in separate tabs.

### Caveats to using localStorage and sessionStorage

* Sensitive data __should not__ be stored in browser data stores because it could result in information leakage. 

* Data put into `localStorage` or `sessionStorage` is unencrypted at-rest, meaning it may be possible to directly access this data from the file system.

* `sessionStorage` only stores data for the duration of the current browsing session. Once the tab is closed, that data is no longer retrievable.

* Both the key and value must be a string. JSON can be stored by using the `JSON.stringify` method.

### Usage

Store and retrieve from `localStorage` as follows:

```javascript
localStorage.setItem(key, value);
localStorage.getItem(key);
localStorage.removeItem(key);
```

Store and retrieve from `sessionStorage` as follows:

```javascript
sessionStorage.setItem(key, value);
sessionStorage.getItem(key);
sessionStorage.removeItem(key);
```
