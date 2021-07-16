# Make Content Crawlable

__Category: Gatsby__

You can increase visibilty of your Gatsby site and optimise SEO by generating a sitemap and making this accessible through robots.txt.

A robots.txt file tells search engine crawlers which URLs the crawler can access on your site.

### Generate a sitemap

Add `gatsby-plugin-sitemap` to your project:

```shell
yarn add gatsby-plugin-sitemap 
```

Update your `gasby-config.js` file:


```javascript
module.exports = {
  siteMetadata: {
    siteUrl: 'https://www.soundbytes.dev',
  },
  plugins: [`gatsby-plugin-sitemap`]
}
```

### Generate robots.txt

Add `gatsby-plugin-robots-txt` to your project:

```shell
yarn add gatsby-plugin-robots-txt
```

Update your `gatsby-config.js` file:

```javascript
module.exports = {
  siteMetadata: {
    siteUrl: 'https://www.soundbytes.dev'
  },
  plugins: ['gatsby-plugin-robots-txt']
};
```

### Putting it all together

```javascript
module.exports = {
  siteMetadata: {
    siteUrl: 'https://www.soundbytes.dev',
  },
  plugins: [
    'gatsby-plugin-sitemap',
    {
      resolve: 'gatsby-plugin-robots-txt',
      options: {
        host: 'https://www.soundbytes.dev',
        policy: [{ userAgent: '*', allow: '/' }]
      }
    }
  ]
};
```

The sitemap.xml and robots.txt files are not accessible in development mode so you must generate the static content and serve it locally to confirm everything is working as expected.

```shell
gatsby build && gatsby serve
```

You can then view the robots.txt file locally at http://localhost:9000/robots.txt and the sitemap locally at http://localhost:9000/sitemap/sitemap-index.xml


