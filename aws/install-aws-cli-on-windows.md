# Install AWS CLI On Windows

__Category: AWS__

The AWS CLI is used to interact with AWS services from the command line. Installation will require admin rights.

### Install on Windows

Install V2 of the AWS CLI by downloading and launching the installer. 

```shell
msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi
```

Follow the prompts in the wizard to complete installation. You will need to restart your command shell for path updates to take effect.

Confirm the version:

```shell
aws --version
```

See [Installing or updating the latest version of the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) for more details.
