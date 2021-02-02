# Change Page Title

__Category: React__

The default title for pages in applications built using `create-react-app` is "React App".

From React 16.8 onwards, you can change the page title with `useEffect` in your component:

```javascript
useEffect(() => {
  document.title = "My Page Title"
}, []);
```  
