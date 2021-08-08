# CloudFront Request Geo Restrictions

__Category: AWS__

For security reasons you may need to prevent users in certain locations or countries from accessing web content served by a CloudFront distribution. 

To enable CloudFront request geo restrictions, navigate to the [CloudFront console](https://console.aws.amazon.com/cloudfront) and choose the distribution you want to apply the restriction on. 

From the distribution select the Restrictions tab then Edit.

For the Restriction Type: 

* Choose Whitelist to allow access to certain countries
* Choose Blacklist to block access from certain countries

For Countries, select the countries that you want to allow or block. Then, choose Add.

Choose Yes, Edit.

Users who try to access a page from a country that is not permitted will see an error page showing an HTTP 403 status code (Forbidden).

Note: According to AWS - _"CloudFront determines the location of your users by using a third-party GeoIP database. The accuracy of the mapping between IP addresses and countries varies by Region. Based on recent tests, the overall accuracy is 99.8%. If CloudFront can't determine a user's location, CloudFront serves the content that the user has requested."_

See [Using CloudFront Geo Restrictions](https://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-geo-restriction) and [Restricting the Geographic Distribution of Your Content](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/georestrictions.html) for more details.
