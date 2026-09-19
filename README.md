# Terraform AWS EKS Cluster

This project provisions a basic Amazon EKS cluster using Terraform.

## Architecture

```text
                         AWS
                          |
                         VPC
                    /           \
             Public Subnet 1   Public Subnet 2
                    \             /
                     \           /
                       EKS Cluster
                            |
                     Managed Node Group
                            |
                       t3.medium
```

## Resources Created

* AWS VPC
* Two public subnets
* Internet Gateway
* Route table
* EKS cluster
* EKS cluster IAM role
* EKS managed node group
* EKS worker node IAM role

## Terraform Structure

```text
terraform-aws-eks-cluster/
│
├── provider.tf
├── variables.tf
├── main.tf
├── outputs.tf
├── terraform.tfvars
├── .gitignore
└── README.md
```

## Prerequisites

* AWS account
* AWS CLI configured
* Terraform installed
* Appropriate AWS IAM permissions

## How to Use

### Initialize Terraform

```bash
terraform init
```

### Format Terraform files

```bash
terraform fmt
```

### Validate the configuration

```bash
terraform validate
```

### Review the infrastructure plan

```bash
terraform plan
```

### Create the EKS infrastructure

```bash
terraform apply
```

Type `yes` when prompted.

## Verify the EKS Cluster

After deployment, configure kubectl:

```bash
aws eks update-kubeconfig --region ap-south-1 --name devops-eks
```

Check the cluster:

```bash
kubectl get nodes
```

## Destroy the Infrastructure

To remove the resources created by Terraform:

```bash
terraform destroy
```

## Key Terraform Concepts Demonstrated

* Terraform AWS provider
* Variables and outputs
* Data sources
* Resource dependencies
* IAM roles
* Amazon EKS
* Managed node groups
* AWS VPC networking
* Infrastructure as Code (IaC)

## Purpose

The purpose of this project is to demonstrate how an Amazon EKS cluster and its supporting AWS infrastructure can be provisioned using Terraform instead of creating resources manually through the AWS Console.
