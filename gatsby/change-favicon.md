# Change Favicon

__Category: Gatsby__

You can change the default favicon in Gatsby using the packages `gatsby-plugin-sharp` and `gatsby-plugin-manifest`.

### Add Gatsby dependencies

```shell
yarn add gatsby-plugin-sharp
yarn add gatsby-plugin-manifest
```

### Configure project settings

Open the `gatsby-config.js` file and edit the value for `plugins.gatsby-plugin-sharp.options.icon` so that it resolves to the path of your image. Your config file should be similar to the following:

```javascript
plugins: [
  // ...
  {
    `gatsby-plugin-sharp`,
    {
      resolve: `gatsby-plugin-manifest`,
      options: {
        start_url: `/`,
        icon: `src/images/website-icon.png`,
      },
    },
  // ...
],
```

The image you specify will be converted into appropriate favicon, sized for different devices (for example: iOS Retina, and Desktop).