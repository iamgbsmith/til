# Read Text File Line By Line

__Category: Nodejs__

Files can be read line by line using the `fs` package.

Assuming a filename of `foobar.txt`, read the file in line by line, printing the line number and line text as follows:

```javascript
fs.readFileSync('foobar.txt').toString().split('\n').forEach(function (line, lineNumber) {
  console.log('Line number ' + ++lineNumber + ' content is ' + line);
});
```
