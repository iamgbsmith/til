# S3 Configure Bucket Object Expiry

__Category: AWS__

S3’s Object Expiration function allows you to define rules to schedule the removal of objects from a bucket after a pre-defined time period. The rules are specified in the Lifecycle Configuration policy that you apply to a bucket and can be set through the S3 API or Management Console. It is good practice to configure an object expiry as part of information lifecycle governence and to also ensure storage costs on S3 are optimised.

Use the following AWS CLI command to set an expiry of 30 days on an S3 Standard bucket called `backup-bucket-dev-orbiks-com`:

### Set object expiry to a specific number of days

```shell
aws s3api put-bucket-lifecycle --bucket "backup-bucket-dev-orbiks-com" --lifecycle-configuration '{"Rules":[{"Status":"Enabled","Prefix":"","Expiration":{"Days":30}}]}'
```

When an object reaches the end of its lifetime based on its lifecycle policy, S3 queues it for asynchronous removal. Delays may occur between the expiration date and the date at which Amazon S3 removes an object.
