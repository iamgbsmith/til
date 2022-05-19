# S3 Buckets And Directories

__Category: AWS__

Amazon S3 has a flat structure instead of a file system hierarchy which means directories don't actually exist. However, for the sake of organizational simplicity, the Amazon S3 console supports the folder concept as a means of grouping objects. It does this by using a shared name prefix for objects.

To create the appearance of a heirarchical directory structure in S3, name your files using a slash in the path to group objects. This is achieved by using a shared prefix name for objects. For example `parent-dir/file/sub-dir/` __(Note: You must include a trailing slash in the path).__ A directory in a bucket will be created when uploading a file if it doesn't already exist.

Commands here use the AWS CLI.

To upload a file to a directory in a bucket:

```shell
aws s3 cp my-test-file s3://[bucket-name]/[directory-name]/my-test-file
```

List objects in a specified directory in a bucket:

```shell
aws s3 ls s3://[bucket-name]/[directory-name]/
```

Directories can be nested as deep as necessary.

See [Organizing objects in the Amazon S3 console using folders](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-folders.html) for more details.
