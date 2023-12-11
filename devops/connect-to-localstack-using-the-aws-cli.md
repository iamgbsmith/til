# Connect To Localstack Using The AWS CLI

__Category: DevOps__

Before connecting to a running Localstack instance you must setup a profile using the `aws configure` command.

Create an AWS profile called `localstack`. 


```shell
aws configure --profile localstack
```

When prompted: 

* Specify a value for `AWS Access Key ID`
* Specify a value for `AWS Secret Access Key`
* Specify the `Default region name` as `us-east-1`
* Use the default value for `Default output format`

For example, to list kinesis streams for a running Localstack instance:

```shell
aws --endpoint-url=http://localhost:4566 kinesis list-streams --profile localstack
```

To create an S3 bucket called `my-test-bucket`:

```shell
aws --endpoint-url=http://localhost:4566 s3api create-bucket --bucket some-test-bucket --profile localstack
```

List S3 buckets:

```shell
aws --endpoint-url=http://localhost:4566 s3api list-buckets --profile localstack
```

You can also set the AWS profile using an environment variable.
