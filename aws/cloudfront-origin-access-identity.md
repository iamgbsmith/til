# CloudFront Origin Access Identity

__Category: AWS__

CloudFront Origin Access Identities (OAI) secure and restrict public access to S3 buckets behind a CloudFront distribution.

Using an Amazon S3 bucket without OAI as the origin of an Amazon CloudFront distribution gives everyone public access and permission to read files in the bucket.

OAI prevents users from viewing S3 files using the direct URL and should be enabled when selecting S3 buckets as the origin.Authorised users are only able to access content using the URL of the CloudFront distribution.

Benefits of OAI include:

* Data is more secure and it is easier to monitor who has accessed it.
* Accessing files via CloudFront results in better performance because objects are cached by edge servers.
* Data transfer cost for accessing files is reduced because data is served via CloudFront as opposed to directly via S3.
