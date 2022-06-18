# Install AWS CLI On MacOS

__Category: AWS__

The AWS CLI is used to interact with AWS services from the command line. Installation will require admin rights.

### Install on macOS

Download V2 of the AWS CLI:

```shell
curl https://awscli.amazonaws.com/AWSCLIV2.pkg -o ~/Downloads/AWSCLIV2.pkg
```

Run the installer. You must include sudo on the command to grant write permissions to directories:

```shell
sudo installer -pkg ~/Downloads/AWSCLIV2.pkg -target /
```

Confirm the version:

```shell
aws --version
```

See [Installing or updating the latest version of the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) for more details.
