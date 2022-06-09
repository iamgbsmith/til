# Convert Markdown To HTML

__Category: Nodejs__

You can convert Markdown to HTML in Node.js using the `markdown-it` parser. 

Add the package to your project:

```shell
yarn add markdown-it
```

Convert from Markdown to HTML and print to the console:

```javascript
const md = require('markdown-it')();
const markdown = '# Heading 1';

const htmlOutput = md.render(markdown);
console.log('HTML from Markdown', htmlOutput);
```

Enable all features for Markdown conversion:

```javascript
var md = require('markdown-it')({
  html: true,
  linkify: true,
  typographer: true
});
```

See [markdown-it on Github](https://github.com/markdown-it/markdown-it) for more details.
