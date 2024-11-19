# Cloud Computing
## LAB 01  Create and Configure an IAM User in AWS

creating and configuring an IAM user

defining policies to assign permissions

Setting up user Password

setting up access keys

configuring the AWS CLI for seamless access to AWS resources

Change the user password

How to install and test Linux AWS CLI 

## Invoke this lab - prerequisites

To invoke this example code, you must have an AWS account. For more information about creating an account, see [AWS Free Tier](https://aws.amazon.com/free/).

You must also have AWS credentials configured. For steps on using the AWS Command Line Interface (AWS CLI) to configure credentials, see [CLI Configuration basics](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)

# Basic Definitions:
## What is Django Application?
Django is an open-source web application framework written in Python

Due to the built-in features such as an object-relational mapper (ORM), URL routing, authentication system, templating system, and more, it is a popular choice for developing web applications and APIs.

---

## Virtual Private Network (VPN)  
### **Definition**  
A Virtual Private Network (VPN) establishes a secure and encrypted connection between a user and a network over the internet, providing private and secure communication channels.  

### **Key Features**  
- Encrypts data to ensure secure communication.  
- Allows remote users to access internal resources securely.  
- Supports site-to-site or client-to-site configurations.  

### **Advantages**  
- Ensures privacy and security for sensitive data transfers.  
- Facilitates secure remote work and access to corporate resources.  
- Provides a seamless connection across public and private networks.  

### **Use Cases**  
- Securely accessing AWS resources in a Virtual Private Cloud (VPC).  
- Remote workforce connectivity to internal systems.  
- Connecting on-premises networks to cloud environments.  

---

## Amazon Elastic Compute Cloud (EC2)  
### **Definition**  
Amazon EC2 (Elastic Compute Cloud) is a web service that provides scalable compute capacity in the cloud, allowing users to run virtual servers (instances) for various applications.  

### **Key Features**  
- Provides multiple instance types tailored to compute, memory, and storage needs.  
- Offers auto-scaling and elastic load balancing for flexibility.  
- Supports various operating systems and configurations.  

### **Advantages**  
- On-demand provisioning of compute resources.  
- Cost-efficient with a pay-as-you-go pricing model.  
- Highly scalable and reliable for workloads of all sizes.  

### **Use Cases**  
- Hosting web applications and backend servers.  
- Running big data analytics and machine learning workloads.  
- Creating virtual test and development environments.  

---

## AWS Identity and Access Management (IAM)  
### **Definition**  
IAM (Identity and Access Management) is a service that allows you to securely manage access to AWS resources by creating and managing users, groups, roles, and permissions.  

### **Key Features**  
- Granular control over user access with policies.  
- Supports multi-factor authentication (MFA) for enhanced security.  
- Provides role-based access for applications and services.  

### **Advantages**  
- Ensures secure access to AWS resources.  
- Facilitates compliance with security standards and regulations.  
- Centralized management of user identities and permissions.  

### **Use Cases**  
- Controlling access to AWS resources based on roles (e.g., developers, admins).  
- Enforcing least-privilege policies.  
- Granting temporary access to external applications or users.
  
## Docker Containerization  
### **Definition**  
Docker containerization is the process of achieving operating system virtualization to run applications and their dependencies in isolated environments.  

### **Key Features**  
- Containers act as building blocks to improve operational efficiency, version control, and environmental stability.  
- Enhances infrastructure by providing granular control over resources.  
- Supports cloud computing storage with enhanced data security, elasticity, and availability.  

### **Advantages**  
- Provides a steady runtime environment.  
- Can run virtually anywhere (cloud, on-premises, etc.).  
- Low overhead compared to virtual machines.  

### **Use Cases**  
- Simplifying application deployment.  
- Supporting microservices architectures.  
- Enabling consistent environments across development, testing, and production.
- 
---

## Amazon Elastic Container Registry (ECR)  
### **Definition**  
Amazon Elastic Container Registry (ECR) is a fully managed container image registry that allows you to store, manage, and deploy Docker container images securely.  

### **Key Features**  
- Fully integrated with AWS services like **EKS**, **ECS**, and **AWS Lambda**.  
- Provides high availability and secure, encrypted image storage.  
- Supports both private and public repositories.  

### **Use Cases**  
- Hosting Docker container images for deployments.  
- Storing container images for microservices architectures.  

### **Example Workflow**  
1. Build a Docker image locally.  
2. Push the image to ECR.  
3. Deploy the image using **EKS** or **ECS**.  

# Amazon Elastic Container Service (ECS)  

## **Definition**  
Amazon Elastic Container Service (ECS) is a fully managed container orchestration service that allows you to run, manage, and scale containerized applications on AWS.  

---

## **Key Features**  
- **Fully Managed Service**: ECS handles the orchestration of containers, so you can focus on your application.  
- **Support for Multiple Compute Options**: Run containers on Amazon EC2, AWS Fargate (serverless), or on-premises with ECS Anywhere.  
- **Seamless AWS Integration**: Easily integrates with AWS services like IAM, VPC, CloudWatch, and ECR.  
- **High Performance**: Optimized for high availability and low-latency container orchestration.  
- **Flexible Networking**: Provides granular control over networking with VPC integration.  

---

## **Advantages**  
- **Scalability**: Automatically scales containerized applications to handle varying workloads.  
- **Cost-Effective**: Pay only for the resources you use with EC2 or opt for Fargate for serverless compute.  
- **Simplified Management**: Abstracts the complexity of deploying and scaling containers.  
- **High Security**: Integrated with AWS Identity and Access Management (IAM) and other AWS security tools.  

---

## **Use Cases**  
- **Microservices Architecture**: Deploy and manage containerized microservices easily.  
- **Batch Processing**: Run jobs and batch tasks in isolated containers.  
- **Web Applications**: Host scalable web applications with containers.  
- **Hybrid Deployments**: Use ECS Anywhere to run containers on-premises and in the cloud.  

---

## **Example Workflow**  
1. **Define a Task Definition**:  
   Specify the container image, resources, and configurations in a task definition.  
2. **Create a Cluster**:  
   Set up an ECS cluster to organize and manage your containers.  
3. **Deploy a Service**:  
   Run the defined tasks as services, enabling load balancing and scaling.  
4. **Monitor**:  
   Use CloudWatch for metrics and logs to monitor your container performance.  

---

## What is DevOps?  
### **Definition**  
DevOps is a combination of "Development" and "Operations," aimed at bridging the gap between development and operations teams for faster, seamless, and more efficient delivery of applications.  

### **Key Features**  
- Enables **Continuous Delivery**, **Continuous Integration**, and **Continuous Deployment**.  
- Reduces the boundaries between development and operations teams.  
- Utilizes cloud tools to build, test, and deploy applications rapidly.  

### **Advantages**  
- Eliminates manual, labor-intensive configuration for heavy applications.  
- Offers cost efficiency by allowing resources to be customized and discarded as needed.  
- Makes the development process faster, more agile, and more collaborative.  

### **Use Cases**  
- Automating application deployment pipelines.  
- Monitoring and managing applications in real-time.  
- Scaling infrastructure dynamically to meet changing demands.  

---

## Amazon Elastic Kubernetes Service (EKS)  
### **Definition**  
Amazon Elastic Kubernetes Service (EKS) is a managed Kubernetes service that simplifies running containerized applications at scale.  

### **Key Features**  
- Fully compatible with open-source Kubernetes.  
- Manages the Kubernetes control plane for high availability.  
- Integrates seamlessly with AWS services like **ECR**, **IAM**, and **CloudWatch**.  

### **Use Cases**  
- Deploying microservices-based architectures.  
- Running large-scale, distributed container workloads.  
- Utilizing Kubernetes’ orchestration without managing infrastructure.  

### **Example Workflow**  
1. Set up an EKS cluster.  
2. Deploy containerized applications using Kubernetes YAML files.  
3. Use an ELB for ingress and connect services to the cluster.  

---

## AWS Lambda  
### **Definition**  
AWS Lambda is a serverless compute service that runs your code in response to events and automatically manages the underlying infrastructure.  

### **Key Features**  
- Automatically scales based on the number of requests.  
- Supports multiple programming languages (e.g., Python, Node.js, Java, Go).  
- Seamlessly integrates with AWS services like S3, DynamoDB, and API Gateway.  

### **Use Cases**  
- Building event-driven architectures.  
- Real-time file processing (e.g., resizing images uploaded to S3).  
- Backend logic for mobile and web applications.  

### **Example Workflow**  
1. Upload your function code to Lambda.  
2. Trigger the function via an event (e.g., S3 upload, DynamoDB change).  
3. Lambda runs the code and scales as needed.

---

## Cloud Load Balancing  
### **Definition**  
Cloud Load Balancing is the process of distributing incoming traffic across multiple servers, ensuring no single server is overwhelmed.  

### **Key Features**  
- Splits and redistributes incoming loads to servers for optimal resource utilization.  
- Monitors and manages traffic to reduce outages and server crashes.  
- Provides enhanced security and better performance.  

### **Advantages**  
- Improves application performance and availability.  
- Enhances scalability and elasticity of server resources.  
- Ensures continuous service with minimal downtime.  

### **Use Cases**  
- Managing high-traffic applications and websites.  
- Distributing workloads in cloud-based server farms.  
- Providing failover support and disaster recovery.  






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
- Select *Add Permissions > Create Customer Managed Policy* to attach new permissions, open the *JSON* editor and paste in the below example policy:
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
- Select *Add Permissions > Create Customer Managed Policy* to attach new permissions, open the *JSON* editor and paste in the below example policy:
Policy Name: **Sufficient-treasure-access-For-StudentUser01**
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "iam:UpdateAssumeRolePolicy",
                "iam:GetPolicyVersion",
                "iam:TagRole",
                "application-autoscaling:*",
                "cloudsearch:*",
                "logs:*",
                "iam:UpdateOpenIDConnectProviderThumbprint",
                "dynamodb:*",
                "iam:CreateRole",
                "iam:AttachRolePolicy",
                "iam:PutRolePolicy",
                "iam:AddRoleToInstanceProfile",
                "codebuild:*",
                "servicediscovery:*",
                "cloudfront:*",
                "iam:ListSSHPublicKeys",
                "iam:SimulateCustomPolicy",
                "iam:SimulatePrincipalPolicy",
                "route53domains:*",
                "secretsmanager:*",
                "iam:ListAttachedRolePolicies",
                "iam:ListOpenIDConnectProviderTags",
                "iam:UploadSSHPublicKey",
                "iam:ListRolePolicies",
                "iam:DeleteOpenIDConnectProvider",
                "events:*",
                "sns:*",
                "iam:GetRole",
                "iam:GetPolicy",
                "apigateway:*",
                "iam:RemoveClientIDFromOpenIDConnectProvider",
                "cloudformation:*",
                "iam:UpdateSSHPublicKey",
                "autoscaling-plans:*",
                "iam:GetUserPolicy",
                "cloudwatch:*",
                "servicequotas:*",
                "ecs:*",
                "ec2:*",
                "iam:GetGroupPolicy",
                "eks:*",
                "iam:GetOpenIDConnectProvider",
                "ce:*",
                "iam:GetRolePolicy",
                "iam:CreateInstanceProfile",
                "cloudtrail:*",
                "iam:DeleteSSHPublicKey",
                "sqs:*",
                "pricing:GetProducts",
                "iam:PassRole",
                "sagemaker:*",
                "access-analyzer:ValidatePolicy",
                "iam:GetInstanceProfile",
                "s3:*",
                "s3:GetBucketPolicy",
                "s3:PutBucketPolicy",
                "iam:GetSSHPublicKey",
                "iam:ListRoles",
                "sts:*",
                "elasticloadbalancing:*",
                "iam:ListInstanceProfiles",
                "support:*",
                "iam:CreateOpenIDConnectProvider",
                "iam:CreatePolicy",
                "es:*",
                "iam:CreateServiceLinkedRole",
                "iam:ListOpenIDConnectProviders",
                "iam:AttachGroupPolicy",
                "ssm:*",
                "route53:*",
                "lambda:*",
                "ecr:*",
                "iam:UntagOpenIDConnectProvider",
                "iam:AddClientIDToOpenIDConnectProvider",
                "iam:TagOpenIDConnectProvider",
                "iam:DeletePolicyVersion",
                "acm:*",
                "autoscaling:DescribeAutoScalingGroups",
                "autoscaling:UpdateAutoScalingGroup",
                "compute-optimizer:GetEnrollmentStatus"
            ],
            "Resource": "*"
        }
    ]
}

```
## Create a cutom ROLE (type: Cutom trust policy)
My-role-prod-mfa-For-StudentUser01

Assign it **Sufficient-treasure-access-For-StudentUser01** policy

Make a trusted relationship to the user
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::528383356345:user/StudentUser01"
            },
            "Action": "sts:AssumeRole",
            "Condition": {
                "Bool": {
                    "aws:MultiFactorAuthPresent": "true"
                }
            }
        }
    ]
}
```
## Create an inline policy in the user
STS-Custom-policy-For-StudentUser01
```
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Effect": "Allow",
			"Action": [
				"sts:AssumeRole"
			],
			"Resource": [
				"arn:aws:iam::528383356345:role/StudentUser01"
			]
		}
	]
}
```
Notedown user credentials and access keys

User name	Password	Console sign-in URL

StudentUser90	****k	https://528383356345.signin.aws.amazon.com/console

Access key ID	Secret access key

AKIAXWBQ2FW4ZG****	IMS5fkDQ****

-- login and check the user from web console - see its permissions:
user can view EC2 service resources
user cannot view IAM service 

-- login usign Linux AWS CLI (Ubumtu 42.04 LTS OS)
CLI client:>> 
```
aws configure
```
```
aws sts get-caller-identity
```

 
## Pert 2: Django Application in VSCode

To get started with the code examples, ensure you have VSCode, Python installed on Ubuntu

## ---------------Install VSCode ----------------
VS Code
Go to 'Preferences > Keyboard Shortcuts'

Set the 'Terminal: Copy Selection' keybindings to Ctrl-C.

Set the 'Terminal: Paste into Active Terminal' keybinding to Ctrl-V.

sudo systemctl restart gdm3

## ---------------DJango App-------------------
**Step 1: APP Start Commands**
Create an Empty Folder: StudentUser90_App
```
python -m venv .venv
```
```
ls -a
```
activate the environment
```
. .venv/bin/activate
```
```
pip install django
```
```
django-admin startproject student_project
cd student_project
```
```
python manage.py startapp studentApp
```
In student_project/settings.py>> 'studentApp' to the INSTALLED_APPS  

**Step 2: Define the Student Model**
1. In students/models.py>> 
```
from django.db import models

class Student(models.Model):
       first_name = models.CharField(max_length=50)
       last_name = models.CharField(max_length=50)
       age = models.IntegerField()

       def __str__(self):
           return f"{self.first_name} {self.last_name}
```
2. Create SQLLITE Database Tables by migration commands:
```
python manage.py makemigrations studentApp
python manage.py migrate
```
4. Run the server for now:
```
python manage.py runserver
```

----------Adding forms Student List and Add --------
**Step 3: Create a Form for the Student Model**
1. In studentApp/forms.py (create this file if it doesn't exist):
```
from django import forms
from .models import Student

class StudentForm(forms.ModelForm):
    class Meta:
        model = Student
        fields = ['first_name', 'last_name', 'age']

```
**Step 4: Create a View to Handle the Form**
In students/views.py:
```
from django.shortcuts import render, redirect
from .forms import StudentForm
from .models import Student

def student_add_view(request):
       if request.method == 'POST':
           form = StudentForm(request.POST)
           if form.is_valid():
               form.save()
               return redirect('student_success')
       else:
           form = StudentForm()
       return render(request, 'students/student_add.html', {'form': form})

def student_add_success_view (request):
    return render(request, 'students/student_add_success.html')

def student_list_view(request):
    students = Student.objects.all()
    return render(request, 'students/student_list.html', {'students': students})
```
----
**Step 5: Create Templates for the Form**
1. Inside your students app directory, create a new folder named templates. Inside this, create another folder named students (to organize templates related to the students app).
2. Create  students/templates/students/student_add.html:
```
<h2>Enter Student Details</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Submit</button>
</form>
```
3. Create students/student_add_success.html:
```
<h2>Student has been added successfully!</h2>
```
4. Create the Template for listing students in `students/templates/students/student_list.html`:
```
   <h2>Student List</h2>
<table>
    <tr><th>First Name</th><th>Last Name</th><th>Age</th><th>Actions</th></tr>
    {% for student in students %}
    <tr>
        <td>{{ student.first_name }}</td>
        <td>{{ student.last_name }}</td>
        <td>{{ student.age }}</td>
   
    </tr>
    {% endfor %}
</table>
<a href="{% url 'student_add' %}">Add New Student</a>
```

----
Step 9: Configure URLs
1. In students/urls.py (create this file if it doesn't exist):
```
from django.urls import path
from .views import student_add_view, student_add_success_view

urlpatterns = [
    path('add/', student_add_view, name='student_add'),
    path('success/', student_add_success_view, name='student_success'),
]
```
2. Include the students URLs in the main urls.py of student_project:
```
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
path('admin/', admin.site.urls),
path('students/', include('studentApp.urls')),
]
```
3. Update the URLs in `students/urls.py`:
```
from .views import student_list_view

urlpatterns = [
path('add/', student_add_view, name='student_add'),
path('success/', student_add_success_view, name='student_success'),
path('list/', student_list_view, name='student_list'),
]
```
---


## ------------------Github -------------------
Click on the New repository button.
Enter a repository name "StudentUser90_App_Repo", and make it public or private.
Click Create repository (do not initialize with a README).

**# Initialize a Git Repository (if haven’t already)**
```
git init
```
```
(.venv) (base) zak@zak-VirtualBox:~/_src/03_CloudPractice_01/studentuser90_app01/student_project$ 
git status
```
```
git remote add origin https://github.com/basharatphd/StudentUser90_App_Repo.git
```
**# Add all files to staging**
```
git add .
```

```
git config --global user.email "basharat.phd.2023@gmail.com"
git config --global user.name "Basharat Hussain"
```

**# Commit your changes**
```
git commit -m "Initial commit"
```
**# Push your code to GitHub**
```
git push -u origin main  
```


 # ---------------DOCKER-------------------
create a file named **`Dockerfile`** at the root location in django application (where manage.py exists)

```
# Use the official Python image as a base
FROM python:3.10-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements file and install dependencies
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code
COPY . /app/

# Expose the port on which Django runs
EXPOSE 8000

# Start the Django server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
```

** Run the following command to generate dependency requirement file **
```
pip freeze > requirements.txt
```
```
docker build -t studentuser90_my_app01:v1 .
```
```
docker images
```
```
docker run -p 8001:8000 studentuser90_my_app01:v1
```
```
http://localhost:8001
```
```
docker ps -a
```


# ----------------ECR Push-----------------

AWS CLI client:>> 
```
aws configure
```
```
aws sts get-caller-identity
```
```
aws ecr describe-repositories
```
```
aws ecr create-repository --repository-name studentuser90_my_app01_4_ecr
```
 
<read 'repositoryuri'> for eaxmaple 

528383356345.dkr.ecr.us-east-1.amazonaws.com/studentuser90_my_app01_4_ecr
 
```
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 528383356345.dkr.ecr.us-east-1.amazonaws.com/studentuser90_my_app01_4_ecr 
```
```
docker tag studentuser90_my_app01:v1    528383356345.dkr.ecr.us-east-1.amazonaws.com/studentuser90_my_app01_4_ecr:v1
```
```
docker push 528383356345.dkr.ecr.us-east-1.amazonaws.com/studentuser90_my_app01_4_ecr:v1
```
```
docker images
```
 
to check and run this ecr image:
```
docker run -p 8002:8000 528383356345.dkr.ecr.us-east-1.amazonaws.com/studentuser90_my_app01_4_ecr:v1 
```

