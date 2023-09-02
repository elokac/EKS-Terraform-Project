# Steps to Reproduce Infrastructure Setup

## Prerequisites:
1. AWS CLI is installed and configured with appropriate IAM credentials.
1. Terraform is installed on your local machine.

## Step 1: Set up the State Store
1. Navigate to the tfstate-store directory.

1. Initialize the Terraform configuration:
```
terraform init
```
1. Review and modify the `tfstate-store.tf` file as needed, including the S3 bucket and DynamoDB table settings.

1. Create the backend resources for storing Terraform state:
```
terraform apply
```
1. Note down the S3 bucket name and DynamoDB table name as they will be required in the `tf-project` configuration.

## Step 2: Provision the Infrastructure
1. Navigate to the `tf-project` directory.
1. Initialize the Terraform configuration:
```
terraform init
```
1. Review and modify the `variables.tf` file to ensure all variables are correctly set, including the state store settings obtained from Step 1.
Review and modify the Terraform configuration files (`1-vpc-test.tf`, `2-eks-cluster.tf`, `3-eks-worker.tf`, `4-baston-host.tf`, `5-db.tf`, `6-ecr.tf`) to match your desired infrastructure settings.
1. Create an execution plan to preview the changes:
```
terraform plan
```
1. Confirm that the execution plan matches your expectations.

1. Apply the Terraform configuration to create the infrastructure:
```
terraform apply
```

## Step 3: Access and Test the Infrastructure
1. Wait for Terraform to finish provisioning the infrastructure. This may take several minutes.
1. After successful provisioning, check the Terraform output for important information, such as instance IPs, endpoint URLs, and other relevant details.
1. Access the infrastructure components as needed, following the documented architecture:
 - EKS Cluster: Access the EKS cluster from the Bastion Host or other trusted sources.
 - MySQL Database: Connect to the MySQL database securely via the Bastion Host or application instances.
 - Elastic Container Registry (ECR): Use ECR to store and manage Docker images.
1. Verify the functionality and security of the infrastructure.

## Step 4: Cleanup (Optional)

If you want to tear down the infrastructure:
1. Navigate to the `tf-project` directory.
1. Run the following command to destroy the resources:
```
terraform destroy
```
1. Confirm the destruction of resources when prompted.

## Step 5: State Store Cleanup (Optional)

If you no longer need the state store resources:
1. Navigate to the `tfstate-store` directory.
1. Run the following command to destroy the backend resources:
```
terraform destroy
```
1. Confirm the destruction of backend resources when prompted.

Following these steps will allow you to reproduce the infrastructure setup using Terraform. Be cautious when performing destroy operations to avoid accidental data loss or resource removal.