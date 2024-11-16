# Cloud Computing
## LAB 01  Create and Configure an IAM User in AWS

creating and configuring an IAM user

defining policies to assign permissions

Setting up user Password

setting up access keys

configuring the AWS CLI for seamless access to AWS resources

Change the user password

How to install and test Linux AWS CLI 


# Creating an IAM User (StudentUser01)
Log in to the AWS Management Console as the **root** user.

We don't use the root user (bad practice)

We need a user who should have 
- right builtin policies to access EC2 machines
- right custom policy to access Kubernetes services
- right custom policy to start a load balancer 

**Steps**
- Go to IAM service (Identity and Access Management).
- Select Users and click Add user.
- Enter the username as 'TestUser_0x’.
- Select Programmatic access to enable the generation of an Access key ID and Secret access key.
- Proceed to permissions.

**Assigning Policies**
- Under the permissions section, assign both built-in and custom policies:
a. Built-in Policies: Choose following relevant built-in policies:
	- AmazonEC2FullAccess
	- AmazonS3FullAccess
b. Custom Policies: Write the JSON of following policy:
- Select *Add Permissions > Create Customer Policy* to attach new permissions, open the *JSON* editor and paste in the below example policy:
Policy Name: **Full-Access-to-EKS-For-StudentUser01**
```
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "VisualEditor0",
			"Effect": "Allow",
			"Action": "eks:*",
			"Resource": "*"
		}
	]
}
```
):
- Select *Add Permissions > Create Customer Policy* to attach new permissions, open the *JSON* editor and paste in the below example policy:
Policy Name: **Sufficient-Access-For-StudentUser01**
```
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "VisualEditor0",
			"Effect": "Allow",
			"Action": "eks:*",
			"Resource": "*"
		}
	]
}
```

 
 
## Invoke example code

To invoke this example code, you must have an AWS account. For more information about creating an account, see [AWS Free Tier](https://aws.amazon.com/free/).

You must also have AWS credentials configured. For steps on using the AWS Command Line Interface (AWS CLI) to configure credentials, see [CLI Configuration basics](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)

## Getting Started

To get started with the code examples, ensure you have access to [Amazon Bedrock](https://aws.amazon.com/bedrock/). Then clone this repo and navigate to one of the folders above. Detailed instructions are provided in each folder's README.

### Enable AWS IAM permissions for Bedrock

The AWS identity you assume from your environment (which is the [*Studio/notebook Execution Role*](https://docs.aws.amazon.com/sagemaker/latest/dg/sagemaker-roles.html) from SageMaker, or could be a role or IAM User for self-managed notebooks or other use-cases), must have sufficient [AWS IAM permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) to call the Amazon Bedrock service.

To grant Bedrock access to your identity, you can:

- Open the [AWS IAM Console](https://us-east-1.console.aws.amazon.com/iam/home?#)
- Find your [Role](https://us-east-1.console.aws.amazon.com/iamv2/home?#/roles) (if using SageMaker or otherwise assuming an IAM Role), or else [User](https://us-east-1.console.aws.amazon.com/iamv2/home?#/users)
- Select *Add Permissions > Create Inline Policy* to attach new inline permissions, open the *JSON* editor and paste in the below example policy:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "BedrockFullAccess",
            "Effect": "Allow",
            "Action": ["bedrock:*"],
            "Resource": "*"
        }
    ]
}
```

> ⚠️ **Note 1:** With Amazon SageMaker, your notebook execution role will typically be *separate* from the user or role that you log in to the AWS Console with. If you'd like to explore the AWS Console for Amazon Bedrock, you'll need to grant permissions to your Console user/role too.
