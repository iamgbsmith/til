# What Are Core Web Vitals

__Category: Web__

Core Web Vitals are metrics from Google used to improve the quality of user experience on the web. Web vitals can be measured in JavaScript using standard web APIs or with the `web-vitals` npm package.

Key metrics:

* Largest Contentful Paint (LCP) - measures the time it takes a browser to render the element having the largest visible height in the viewport. LCP should occcur within 2.5 seconds or less of when the page starts loading.
* First Input Delay (FID) -  measures the time it takes a browser to respond to the user's first interaction. FID should occur within 100 milliseconds or less.
* Cumulative Layout Shift (CLS) - measures unexpected layout shifts while a user is browsing. CLS on pages should be 0.1 or less.

A good threshold to aim for is 75th percentile for all three metrics.

See [Web Vitals](https://web.dev/vitals/) for more details.