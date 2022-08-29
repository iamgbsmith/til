# Render Markdown

__Category: React__

Markdown can be rendered using the `react-markdown` package.

Assume you have a file resource which contains markdown, render it as follows:

```javascript
import React, { useEffect, useState } from 'react'
import ReactMarkdown from 'react-markdown';

import MarkdownFile from '/assets/markdown/some-markdown-file.md';

export default MarkdownComponent = () => {
  const [markdownText, setMarkdownText] = useState('');

  useEffect(() => {
    fetch(MarkdownFile).then(res => res.text()).then(text => setMarkdownText(text))
  })
  
  return (
    <div>
      <ReactMarkdown children={markdownText} />
    </div>
  );
}
```

In the above code, the value for `children` could also be a string.
