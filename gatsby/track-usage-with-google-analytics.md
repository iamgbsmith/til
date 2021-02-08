# Track Usage With Google Analytics

__Category: Gatsby__

__Note:__ This TIL assumes you have registered for Google Analytics at <a href="https://analytics.google.com" target="_blank" rel="noopener noreferrer">https://analytics.google.com</a>

Google Analytics can provide you with details on which pages in your site are the most popular, how many people view your site, and where your site visitors are from.

You can incorporate Google Analytics into your Gatsby site using the `gatsby-plugin-google-gtag` plugin. Google Analytics 4  uses a Measurement ID in the format of `G-XXXXXXXXXX` and also supports the legacy `UA-XXXXXX-X` format. This plugin will only work in production mode once you have deployed your site.

### Add the Google Analytics plugin

```shell
yarn add gatsby-plugin-google-gtag
```

The Global Site Tag plugin (gtag.js) is designed to combine multiple Google tagging systems and replace older ones such as analytics.js.

### Update your gatsby-config file

In your `gasby-config.js` file add and configure the relevant tracking IDs:

```javascript
plugins: [
  // ...
  {
    resolve: `gatsby-plugin-google-gtag`,
    options: {
      // You can add multiple tracking ids and a pageview event will be fired for all of them.
      trackingIds: [
        "GA-TRACKING_ID",   // Google Analytics / GA (in the format of G-XXXXXXXXXX)
        "AW-CONVERSION_ID", // Google Ads / Adwords / AW (if applicable)
        "DC-FLOODIGHT_ID",  // Marketing Platform advertising products (Display & Video 360, Search Ads 360, and Campaign Manager) (if applicable)
      ],
      // This object gets passed directly to the gtag config command
      // This config will be shared across all trackingIds
      gtagConfig: {
        optimize_id: "OPT_CONTAINER_ID",
        anonymize_ip: true,
        cookie_expires: 0,
      },
      // This object is used for configuration specific to this plugin
      pluginConfig: {
        // Puts tracking script in the head instead of the body
        head: false,
        // Setting this parameter is also optional
        respectDNT: true,
        // Avoids sending pageview hits from custom paths
        exclude: ["/preview/**", "/do-not-track/me/too/"],
      },
    },
  },
  // ...
],

```

Google Analytics requires a tracking ID to associate data with your site’s traffic. Each web site you are monitoring will need a different tracking ID.

Once the analytics has been configured, deploy your site and test it by navigating to the homepage of Google Analytics to monitor tracking information.