# S3 Working With Buckets

__Category: AWS__

An S3 bucket is a container for storing objects. 

* There is no limitation on the number of objects that can be stored in a bucket
* Buckets cannot be nested
* You are charged for objects stored in a bucket
* You are not charged for storage of objects on or after their expiration date

Commands here use the AWS CLI.

List all buckets owned by the current user:

```shell
aws s3 ls
```

List all buckets for a named profile:

```shell
aws --profile [profile_name] s3 ls
```

Create a bucket called `backup-bucket.orbiks.com`:

```shell
bucket=backup-bucket-test-orbiks-com
aws s3 mb s3://$bucket
```

Add an object to a bucket:

```shell
aws s3 cp my-test-file s3://[bucket-name]
```

List objects in the bucket called `backup-bucket-test-orbiks-com` where last modified matches 2022-05-01:

```shell
aws s3api list-objects-v2 --bucket "backup-bucket-test-orbiks-com" --query "Contents[?contains(LastModified, '2022-05-01')].{Key: Key}" --output text
```

List all objects in a bucket in human readable format:

```shell
aws s3 ls --recursive --summarize --human-readable s3://[bucket-name]
```
