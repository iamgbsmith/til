# S3 Bucket Naming Conventions

__Category: AWS__

Amazon S3 bucket names must adhere to the following rules:

* Bucket names must be globally unique 
* Bucket names must be between 3 and 63 characters long
* Bucket names can only contain either lowercse letters, numbers, dots (.), and hyphens (-)
* Bucket names must begin and end with a letter or number
* Bucket names must not be formatted as an IP address (for example, 10.10.1.5)
* Bucket names must not start with the prefix xn--

### Examples of valid bucket names

* backup-bucket-test-orbiks-com
* somestoragebucket
* logbucket-14

### Examples of invalid bucket names

* web_image_bucket (contains underscores)
* some-test-bucket- (ends with a hypen)
* CoolBucket (contains uppercase characters)

__Note:__ It is best to avoid using dots in bucket names as this prevents virtual host addressing over HTTPS.
