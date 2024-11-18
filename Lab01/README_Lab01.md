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
StudentUser90	aUKU81|k	https://528383356345.signin.aws.amazon.com/console

Access key ID	Secret access key
AKIAXWBQ2FW4ZG6UFYHH	IMS5fkDQbZksOEYk0Mn/gDW8Nlz7T744xYk40j2U

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


 
