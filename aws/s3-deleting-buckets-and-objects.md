# S3 Deleting Buckets and Objects

__Category: AWS__

The steps outlined here use the AWS CLI.

### Deleting objects from a bucket

Delete an object from a bucket where the s3 url is in the format of `s3://$bucket-name/$file-name` as follows:

```shell
aws s3 rm s3://backup-bucket-test-orbiks-com/my-test-file
```

### Deleting a bucket

You cannot delete a versioning enabled bucket using the AWS CLI. You must remove all of the objects first.

Delete an empty, non-versioned bucket called `backup-bucket-test-orbiks-com` with the following command:

```shell
aws s3 rb s3://backup-bucket-test-orbiks-com
```

Force delete a non-empty, non-versioned bucket called `backup-bucket-test-orbiks-com` with the following command:

```shell
aws s3 rb s3://backup-bucket-test-orbiks-com --force
```

__Note:__ If you delete a bucket, another AWS account or user will be able claim the bucket name. If you want to continue to use the same bucket name, empty the bucket without deleting it.
