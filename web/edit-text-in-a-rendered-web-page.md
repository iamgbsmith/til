# Edit Text In A Rendered Web Page

__Category: Web__

You can edit text in a rendered web page which by changing the JavaScript DOM setting for `designMode` to "on".

For the web page you want to edit, load Developer Tools and open the JavaScript console.

In the JavaScript console type the following and hit enter:

```javascript
document.designMode = "on";
```

Double click on text elements in the web page to change them.

To disable editing, set design mode to "off".
