# Create An ECR Repository

__Category: AWS__

AWS Elastic Container Registry (ECR) is a fully managed container registry service with support for resource-based permissions using IAM. Each account in AWS is provided with an ECR private registry which supports one or more repositories. Container images are pushed or pulled from repositories.

You can create a private repository using the AWS CLI. 

For example, to create a repository called `my-ecr-repo` in us-east-2 with security image scanning on push, use the following command:

```shell
aws ecr create-repository --repository-name my-ecr-repo --image-scanning-configuration scanOnPush=true --region us-east-2
```

Containers hosted in ECR can be deployed to AWS ECS or EKS or on-premise. 

__Note: If using ECR for on-premise container deployments, be mindful of data egress costs from AWS.__

See [Amazon Elastic Container Registry](https://docs.aws.amazon.com/AmazonECR/latest/userguide/getting-started-cli.html) for more details.

