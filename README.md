# Terraform AWS Web Server Project

This project uses Terraform to provision a basic web server infrastructure on AWS. It sets up a VPC, subnet, internet gateway, route table, security group, and an EC2 instance running Apache2.

## Resources Created

- VPC
- Internet Gateway
- Custom Route Table
- Subnet
- Security Group (allowing ports 22, 80, 443)
- Network Interface
- Elastic IP
- EC2 Instance (Ubuntu with Apache2)

## Prerequisites

- AWS Account
- Terraform installed
- AWS CLI installed and configured

## Implementation Instructions

1. Clone this repository to your local machine.

2. Create a file named `terraform.tfvars` in the project directory and add your AWS credentials:

   ```
   access_key = "your_access_key"
   secret_key = "your_secret_key"
   ```

   Replace `your_access_key` and `your_secret_key` with your actual AWS credentials.

3. Generate an SSH key pair:
   ```
   ssh-keygen -t rsa -b 2048 -f terraform_key
   ```
   This will create `terraform_key` (private key) and `terraform_key.pub` (public key) files.

4. Initialize Terraform:
   ```
   terraform init
   ```

5. Review the planned changes:
   ```
   terraform plan
   ```

6. Apply the Terraform configuration:
   ```
   terraform apply
   ```

7. After the apply completes successfully, Terraform will output the public IP of your web server.

8. Open a web browser and navigate to `http://<public_ip>`. You should see the message:
   ```
   this is your very first web server yotam
   ```

## Clean Up

To avoid incurring unnecessary costs, remember to destroy the resources when you're done:

```
terraform destroy
```

## Note

This configuration is for demonstration purposes and may not be suitable for production use without further security enhancements.
