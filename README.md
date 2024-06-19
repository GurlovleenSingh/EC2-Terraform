# EC2-Terraform
AWS instance launch with Terraform
To run an EC2 instance using Terraform, you need to follow these basic steps:
Prerequisites:
*******************************************
Install Terraform: Ensure that Terraform is installed on your local machine or on the system where you plan to execute Terraform commands. You can download Terraform from terraform.io and follow the installation instructions for your operating system.

AWS Account: You need an AWS account with appropriate permissions to create EC2 instances. Obtain your AWS Access Key ID and Secret Access Key for authentication.

Steps to Create an EC2 Instance using Terraform
1. Set up your Terraform Configuration
Create a new directory for your Terraform configuration files and create a .tf file, typically named main.tf, to define your infrastructure.
Below code will set the aws provider and the resource block for the EC2 with Amazon Linux AMI and t2.micro as instance type
CODE:
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
provider "aws" {
  region     = "us-east-1"
  access_key = "provide keys here"
  secret_key = "provide secret keys here"
}
resource "aws_instance" "ubuntu_server" {
  ami           = "ami-08a0d1e16fc3f61ea"
  instance_type = "t2.micro"

  tags = {
    Name = "HelloWorld"
  }
}

2. Initialize Terraform

Navigate to your Terraform configuration directory in your terminal and initialize Terraform. This step downloads the necessary provider plugins.
terraform init

3. Review and Plan

Before applying changes, it's a good practice to review what Terraform plans to do.
terraform plan

4. Apply Changes

If the plan looks good, apply your configuration to create the EC2 instance
terraform apply

6. Clean Up (Optional)

If you want to delete the resources created by Terraform, you can use:
terraform destroy


