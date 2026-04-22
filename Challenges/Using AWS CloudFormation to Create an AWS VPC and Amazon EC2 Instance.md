## Lab Overview

In this challenge lab, I built AWS infrastructure by writing and deploying an AWS CloudFormation template instead of creating resources manually in the console. The goal was to provision a complete environment that included an Amazon VPC, an internet gateway attached to the VPC, a security group allowing SSH access, a private subnet, and a t3.micro EC2 instance launched inside that subnet.

### Steps:

1. I started by checking that my AWS CLI was installed and properly configured. I verified my setup with aws --version and aws sts get-caller-identity, which confirmed that I was authenticated and working in the correct AWS account.

2. Next, I created a CloudFormation template in YAML format. In the template, I defined each required resource step by step. I added a VPC with DNS support enabled, then created an internet gateway and attached it to the VPC. After that, I defined a security group that allows SSH traffic on port 22 from anywhere. I also created a private subnet inside the VPC and configured an EC2 instance to launch in that subnet.

3. To make the template more flexible, I used a Systems Manager parameter to dynamically retrieve the latest Amazon Linux 2 AMI instead of hardcoding an AMI ID. This is useful because it makes the template easier to reuse in different regions and avoids manually updating AMI values.

4. Before deploying, I validated the template with the AWS CLI to catch syntax issues early. Once the template passed validation, I launched the CloudFormation stack and monitored the deployment by checking stack events in real time. This allowed me to see how CloudFormation created each resource and whether any dependencies or errors appeared during the process.

5. The lab was iterative, so the idea was to test, review, and adjust the template until all required components built successfully without errors. By the end, I had a working stack that automatically created the full environment from code. This lab gave me practical experience with infrastructure as code, template structure, resource dependencies, validation, and stack deployment through CloudFormation. It also showed me how automation improves consistency and reduces the risk of manual configuration mistakes.

   <img width="500" height="217" alt="Screenshot 2026-04-22 at 15 25 43" src="https://github.com/user-attachments/assets/36f0a19b-0517-465e-8825-4c77e3205d3b" />
