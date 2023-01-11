# capstone

In this project I used the below tools

AWS

-- CloudFormation

-- EKS

CircleCI

Docker

Application
My application is a simple “Hello World” application. I used the below sequence to deploy my application

1- CloudFormation to create infrastructure. This infrastructure is created only one time.

a.	Network infrastructure including: VPC, 1 public subnet, 2 private subnets and internet gateway (InfrastructureCreation/Network.yml)

b.	Servers infrastructure including: 1 EKS cluster and 1 bastion host to test and administrate my EKS cluster (InfrastructureCreation/Servers.yml)
