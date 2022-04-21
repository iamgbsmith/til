# S3 Object Expiry

__Category: AWS__

### Default and minimum object expiration

By default, an object stored in S3 does not have a expiration date. If you don't specify a lifecycle rule, it will be there forever.

It is not possible to specify an object expiration of less than 1 day.

### Specifying object expiration

S3’s Object Expiration function allows you to define rules to schedule the removal of your objects after a pre-defined time period. The rules are specified in the Lifecycle Configuration policy that you apply to a bucket and can be set through the S3 API or Management Console.

To set an expiry of 1 day for a bucket use the following command:

```shell
bucket=leaky-bucket.orbiks.com
aws s3 mb s3://$bucket
aws s3api put-bucket-lifecycle --bucket $bucket --lifecycle-configuration '{"Rules":[{"Status":"Enabled","Prefix":"","Expiration":{"Days":1}}]}'
```

Amazon S3 deletes expired objects on your behalf. The built in Object Expiration is 1 day (plus "not before" the time to next midnight UTC). 

For example, with expiration of 1 day, an object created at 01:00:00 today would persist for 47 hours minimum before being queued for deletion.

Lifecycle rules allow you to sepcify a date for when S3 will perform an action. The date value must be in ISO 8601 format and the time is always midnight UTC.