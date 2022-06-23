# Install And Start LocalStack

__Category: DevOps__

LocalStack is a cloud service emulator that runs in a single container on your laptop or in your CI environment. It can be used to mock AWS services and it supports running Lambda expressions on a local machine. 

You can run Localstack in two ways: using Python or from within a Docker container.

### Run using Python

Requirements:

* python (Python 3.6 up to 3.9 supported)
* pip (Python package manager)
* Docker

When installing Localstack, __do not install it using a root or admin user.__ 

Install Localstack as follows:

```shell
pip install localstack
```

If you face permissions problems on MacOS install as follows:

```shell
pip install --user localstack
```

Start Localstack inside a Docker container:

```shell
localstack start -d
```

The default behavior of LocalStack is to spin up all the supported services with each of them listening on port 4566.

Show services running on Localstack:

```shell
localstack status services
```

Output:

```shell
┌──────────────────────────┬─────────────┐
│ Service                  │ Status      │
├──────────────────────────┼─────────────┤
│ acm                      │ ✔ available │
│ apigateway               │ ✔ available │
│ cloudformation           │ ✔ available │
│ cloudwatch               │ ✔ available │
│ config                   │ ✔ available │
│ dynamodb                 │ ✔ available │
│ dynamodbstreams          │ ✔ available │
│ ec2                      │ ✔ available │
│ es                       │ ✔ available │
│ events                   │ ✔ available │
│ firehose                 │ ✔ available │
│ iam                      │ ✔ available │
│ kinesis                  │ ✔ available │
│ kms                      │ ✔ available │
│ lambda                   │ ✔ available │
│ logs                     │ ✔ available │
│ opensearch               │ ✔ available │
│ redshift                 │ ✔ available │
│ resource-groups          │ ✔ available │
│ resourcegroupstaggingapi │ ✔ available │
│ route53                  │ ✔ available │
│ route53resolver          │ ✔ available │
│ s3                       │ ✔ available │
│ s3control                │ ✔ available │
│ secretsmanager           │ ✔ available │
│ ses                      │ ✔ available │
│ sns                      │ ✔ available │
│ sqs                      │ ✔ available │
│ ssm                      │ ✔ available │
│ stepfunctions            │ ✔ available │
│ sts                      │ ✔ available │
│ support                  │ ✔ available │
│ swf                      │ ✔ available │
└──────────────────────────┴─────────────┘
```

To stop Localstack, use the following command:

```shellooo
localstack stop
```

### Run using Docker

You can get started using the Docker image or with `docker-compose`.

Using the sample compose file at https://github.com/localstack/localstack/blob/master/docker-compose.yml to get started with default configuration or customise it as required.

On macOS:

__Note: On macOS you should set the tmp directory when starting__

```shell
TMPDIR=/private$TMPDIR docker-compose up
```

On Windows:

```shell
docker-compose up
```
