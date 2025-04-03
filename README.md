# Terraform State Management with S3 Backend

## Objective
This lab demonstrates how to configure Terraform to store its state remotely in an AWS S3 bucket with state locking enabled using DynamoDB.

## Prerequisites
- AWS account with IAM permissions to manage S3, DynamoDB, and EC2.
- Terraform installed.
- AWS CLI installed and configured (`aws configure`).

## Part 1: Create an S3 Bucket for Terraform State
1. Go to the AWS S3 Console.
2. Click **Create bucket**.


## Part 2: Create a DynamoDB Table for State Locking
1. Go to the AWS DynamoDB Console.
2. Click **Create table**.
3. Set **Table name**: `terraform-lock`.
4. Set **Partition key**: `LockID` (String).
5. Click **Create table**.

## Part 3: Configure Terraform Backend
terraform init
terraform apply -auto-approve


## Part 4: Verify Terraform State & Locking
Check Remote State File
Go to the S3 Console → Open your bucket → Navigate to terraform/state.tfstate.

Check Locking in DynamoDB
Go to DynamoDB Console → Explore items → Select your table

terraform destroy -auto-approve

