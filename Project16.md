# Documentation for Project 16: AUTOMATE INFRASTRUCTURE WITH IAC USING TERRAFORM PART 1

## Prerequisites before you begin writing Terraform code

You must have completed Terraform course from the Learning dashboard.

Create an IAM user, name it terraform (ensure that the user has only programatic access to your AWS account) and grant this user AdministratorAccess permissions.

Copy the secret access key and access key ID. Save them in a notepad temporarily.

Configure programmatic access from your workstation to connect to AWS using the access keys copied above and a Python SDK (boto3). You must have Python 3.6 or higher on your workstation.

If you are on Windows, use gitbash, if you are on a Mac, you can simply open a terminal. Read here to configure the Python SDK properly.

- Download AWS CLI

- Create an S3 bucket to store Terraform state file. You can name it something like <yourname>-dev-terraform-bucket (Note: S3 bucket names must be unique unique within a region partition, you can read about S3 bucken naming in this article). We will use this bucket from Project-17 onwards.
When you have configured authentication and installed boto3, make sure you can programmatically access your AWS account by running following commands in >python:

[Create S3 Bucket](./images/create-S3-bucket1.PNG)

[Create S3 Bucket](./images/create-S3-bucket2.PNG)

[Create S3 Bucket](./images/create-S3-bucket3.PNG)

[Create S3 Bucket](./images/create-S3-bucket4.PNG)

[Create S3 Bucket](./images/create-S3-bucket5.PNG)

[Create S3 Bucket](./images/create-S3-bucket-success.PNG)

- Run the command below in the CLI:

`aws s3 ls`

- The output below should display:

[AWS S3 Ls](./images/aws-S3-ls-output.PNG)

- The secrets of writing quality Terraform code
The secret recipe of a successful Terraform projects consists of:

Your understanding of your goal (desired AWS infrastructure end state)
Your knowledge of the IaC technology used (in this case – Terraform)
Your ability to effectively use up to date Terraform documentation here

- Make sure you understand them and know when to use each of them.

Another concept you must know is data type. This is a general programing concept, it refers to how data represented in a programming language and defines how a compiler or interpreter can use the data. Common data types are:

Integer
Float
String
Boolean, etc.
Best practices
Ensure that every resource is tagged using multiple key-value pairs. You will see this in action as we go along.
Try to write reusable code, avoid hard coding values wherever possible. (For learning purpose, we will start by hard coding, but gradually refactor our work to follow best practices).

## VPC | SUBNETS | SECURITY GROUPS

- Let us create a directory structure
Open your Visual Studio Code and:

Create a folder called PBL
Create a file in the folder, name it main.tf

- Provider and VPC resource section
Set up Terraform CLI as per this instruction.

Add AWS as a provider, and a resource to create a VPC in the main.tf file.
Provider block informs Terraform that we intend to build infrastructure within AWS.
Resource block will create a VPC.

- Note: You can change the configuration above to create your VPC in other region that is closer to you. The same applies to all configuration snippets that will follow.

The next thing we need to do, is to download necessary plugins for Terraform to work. These plugins are used by providers and provisioners. At this stage, we only have provider in our main.tf file. So, Terraform will just download plugin for AWS provider.
Lets accomplish this with terraform init command as seen in the below demonstration.
