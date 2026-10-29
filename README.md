# Terraform AWS ECS Fargate

Terraform configuration for an AWS ECS cluster and Fargate task definition, an ECR repository, and the task execution IAM role.

The provider is configured for `eu-north-1`. The current configuration creates the cluster, repository, IAM role, and task definition; it does not create an ECS service or run a task.

## Requirements

- Terraform 1.0 or later
- AWS credentials configured for an account with permission to manage ECS, ECR, and IAM resources

## Usage

```sh
terraform init
terraform plan
terraform apply
```

The ECR repository URL is printed as the `repository_url` output. The task definition references the `latest` image tag, so push an image to that repository before launching a task.

Terraform state and local working files are excluded from Git. Keep the `.terraform.lock.hcl` provider lock file committed.