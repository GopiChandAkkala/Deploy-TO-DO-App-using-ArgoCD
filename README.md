# Deploy-TO-DO-App-using-ArgoCD

First create a EKS cluster either by using Terraform or by AWS console or just by EKSctl

# Setting up an EKS Cluster

## Using Terraform:

Find the source code for the terraform configuration [here](https://github.com/GopiChandAkkala/AWS-EKS-using-Terraform-Modules.git)
```bash
# Use Terraform to define your EKS cluster configuration.

terraform init
terraform apply
```

## Using AWS Console:

```bash
# Navigate to the AWS Management Console.
# Go to the EKS service and create a new cluster.
# Follow the on-screen instructions to configure and create your cluster.
```

## Using EKSctl:


Install EKSctl AWS.

Run the following command to create an EKS cluster:
```bash
eksctl create cluster --name your-cluster-name --region your-region
```
