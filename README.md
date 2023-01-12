# capstone

In this project I used the AWS Cloudformation, AWS EKS, CircleCI and Docker


Application

My application is a simple “Hello World” application. I used the below sequence to deploy my application

1- CloudFormation to create infrastructure. This infrastructure is created only one time.

a.	Network infrastructure including: VPC, 1 public subnet, 2 private subnets and internet gateway (InfrastructureCreation/Network.yml)

aws cloudformation create-stack  --stack-name CapstoneNetwork --region us-east-1 --template-body file://Network.yml  --parameters file://Network-parameters.json

b.	Servers infrastructure including: 1 EKS cluster and 1 bastion host to test and administrate my EKS cluster (InfrastructureCreation/Servers.yml)

aws cloudformation create-stack  --stack-name CapstoneServers --region us-east-1 --template-body file://Servers.yml  --parameters file://Servers-parameters.json --capabilities CAPABILITY_NAMED_IAM

2- CircleCI CI/CD to auto deploy my application if any change done using the following sequence

a.	code linting

b.	docker code building

c.	docker code uploading to docker hub

d.	deploy new image from docker hub to my EKS cluster

Output

I can use my cluster endpoint to check the running application.


