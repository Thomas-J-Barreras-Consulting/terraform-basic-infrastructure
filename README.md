# Terraform Basic Infrastructure

A simple Terraform project that provisions an AWS S3 bucket. Built as a learning exercise and demonstration of Terraform fundamentals.

## Architecture

This project creates a single S3 bucket in AWS using the AWS provider. It demonstrates core Terraform concepts:

- **Provider configuration** with a parameterized AWS region
- **Input variables** for flexible, reusable configuration
- **Output values** to expose resource attributes
- **Resource tagging** for organization and identification

## Resources Created

| Resource | Type | Description |
|----------|------|-------------|
| `aws_s3_bucket.example` | S3 Bucket | A general-purpose S3 bucket tagged for the Dev environment |

## Prerequisites

- [Terraform](https://developer.hashicorp.com/terraform/install) >= 1.0
- An AWS account with credentials configured (via `aws configure`, environment variables, or an IAM role)

## Usage

1. **Clone the repository**

   ```sh
   git clone https://github.com/chrisbarreras/terraform-basic-infrastructure.git
   cd terraform-basic-infrastructure
   ```

2. **Set your variables**

   Edit `terraform.tfvars` to provide a globally unique bucket name:

   ```hcl
   bucket_name = "my-unique-bucket-name"
   ```

3. **Initialize Terraform**

   ```sh
   terraform init
   ```

4. **Preview the changes**

   ```sh
   terraform plan
   ```

5. **Apply the configuration**

   ```sh
   terraform apply
   ```

6. **Destroy resources when finished**

   ```sh
   terraform destroy
   ```

## Variables

| Name | Type | Description | Default | Required |
|------|------|-------------|---------|----------|
| `region` | `string` | AWS region to deploy into | `us-west-2` | No |
| `bucket_name` | `string` | Name of the S3 bucket | — | Yes |

## Outputs

| Name | Description |
|------|-------------|
| `bucket_name` | The name of the created S3 bucket |

## Project Structure

```
.
├── main.tf            # Provider and resource definitions
├── variables.tf       # Input variable declarations
├── outputs.tf         # Output value declarations
├── terraform.tfvars   # Variable values
└── README.md
```
