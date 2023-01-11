# capstone

In this project I used the AWS Cloudformation, AWS EKS, CircleCI and Docker


Application

My application is a simple “Hello World” application. I used the below sequence to deploy my application

1- CloudFormation to create infrastructure. This infrastructure is created only one time.

a.	Network infrastructure including: VPC, 1 public subnet, 2 private subnets and internet gateway (InfrastructureCreation/Network.yml)

aws cloudformation create-stack  --stack-name FinalProjectmyNetwork --region us-east-1 --template-body file://Network.yml  --parameters file://Network-parameters.json

b.	Servers infrastructure including: 1 EKS cluster and 1 bastion host to test and administrate my EKS cluster (InfrastructureCreation/Servers.yml)

aws cloudformation create-stack  --stack-name FinalProjectmyServers --region us-east-1 --template-body file://Servers.yml  --parameters file://Servers-parameters.json --capabilities CAPABILITY_NAMED_IAM
