# Track Outbound Links

__Category: Gatsby__

Outbound links point from your website to another and help to improve SEO for your site.

Similar to the `<a>` href tag, outbound links are used to direct a reader to another source that provides additional information regarding a specific topic.

To use outbound links, install the `gatsby-plugin-google-gtag` plugin. Substitute the `<a>` element tag for the `<OutboundLink>`.

```javascript
import React from 'react';
import { OutboundLink } from 'gatsby-plugin-google-gtag';

export default () => (
  <div>
    <OutboundLink href='https://www.linkedin.com/in/gregorybsmith'>
      See my LinkedIn profile
    </OutboundLink>
  </div>
);
```

See [Easily add Google Global Site Tag to your Gatsby site](https://www.gatsbyjs.com/plugins/gatsby-plugin-google-gtag/) for more details.
