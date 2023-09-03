# Folder Content Summary
1. ## [`docs`](https://github.com/elokac/EKS-Terraform-Project/tree/master/docs)
This folder contains essential documentation and resources for understanding and reproducing the infrastructure setup.

  - ### [Infra_diagram.png](https://github.com/elokac/EKS-Terraform-Project/blob/master/docs/Infra_diagram.png): 
  An image file representing the infrastructure diagram for visual reference.

  - ### [Infrastructure-setup.md](https://github.com/elokac/EKS-Terraform-Project/blob/master/docs/Infrastructure-setup.md): 
  Detailed documentation explaining the entire infrastructure setup, its components, and their interactions.

  - ### [setup-steps.md](https://github.com/elokac/EKS-Terraform-Project/blob/master/docs/setup-steps.md): 
  A guide providing step-by-step instructions for reproducing the infrastructure setup using Terraform.

2. ## [`tf-project`](https://github.com/elokac/EKS-Terraform-Project/tree/master/tf-project)
The `tf-project` folder contains the Terraform configuration files for defining and provisioning the infrastructure.

- #### 0-provider.tf: 
Terraform provider configuration for AWS.

- #### 1-vpc-test.tf: 
Configuration for setting up the Virtual Private Cloud (VPC) and its components.

- #### 2-eks-cluster.tf: 
Configuration for creating the Amazon Elastic Kubernetes Service (EKS) cluster.

- #### 3-eks-worker.tf: 
Configuration for setting up worker nodes within the EKS cluster.

- #### 4-baston-host.tf: 
Configuration for creating the Bastion Host to securely access resources in private subnets.

- #### 5-db.tf: 
Configuration for provisioning the MySQL Database.

- #### 6-ecr.tf: 
Configuration for setting up the Elastic Container Registry (ECR).

- #### output.tf: 
Defines the Terraform outputs, allowing you to access important information about the provisioned infrastructure.

- #### variables.tf: 
Defines Terraform variables used to parameterize the configurations and customize the infrastructure.

3. ## [`tfstate-store`](https://github.com/elokac/EKS-Terraform-Project/tree/master/tfstate-store)
The `tfstate-store` folder contains the configuration for managing the Terraform state using a remote backend.

  - #### tfstate-store.tf: 
  Terraform configuration for setting up the remote state backend, including an S3 bucket and DynamoDB table.
  
This folder structure and its contents are organized to facilitate infrastructure provisioning, documentation, and state management using Terraform. Refer to the docs folder for detailed instructions on reproducing the infrastructure setup.