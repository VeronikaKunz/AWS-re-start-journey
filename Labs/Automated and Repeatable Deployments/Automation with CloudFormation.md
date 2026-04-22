## Lab Overview:

I explored infrastructure automation with AWS CloudFormation by deploying, modifying, and deleting resources through templates rather than manual configuration. The lab focused on defining infrastructure as code, including a VPC, security groups, an S3 bucket, and EC2 resources managed through CloudFormation stacks.
This experience helped me understand how CloudFormation improves consistency and repeatability in deployments, reduces manual errors, and makes infrastructure changes easier to manage and automate.

### Steps:

1. I deployed a CloudFormation stack from a YAML template that provisioned a VPC and security group automatically. Before launching the stack, I reviewed the template structure, including parameters, resources, and outputs, which helped me understand how infrastructure components are defined declaratively in CloudFormation.
   After uploading the template and creating the stack, I monitored the Events and Resources tabs to observe how CloudFormation built the environment and managed dependencies between resources. This exercise introduced me to infrastructure as code in practice and showed how CloudFormation automates repeatable, consistent deployments.

   <img width="500" height="169" alt="Screenshot 2026-04-22 at 14 08 05" src="https://github.com/user-attachments/assets/fca9725d-9a22-41a5-b27e-5a841180636e" />

2. I modified the CloudFormation template to add an Amazon S3 bucket resource and then updated the existing stack with the revised template. This introduced me to making incremental infrastructure changes through code instead of manually provisioning new resources.
   By reviewing the change set before applying the update, I could see that CloudFormation would add only the new bucket while leaving the existing resources unchanged. This helped me understand how stack updates work, how CloudFormation manages changes safely, and how infrastructure can evolve through controlled template modifications.

   <img width="500" height="149" alt="Screenshot 2026-04-22 at 14 17 04" src="https://github.com/user-attachments/assets/ac8a71ca-34e8-4f5a-9081-7051a9a983ee" />

3. I extended the CloudFormation template by adding a parameter that dynamically retrieves the latest Amazon Linux 2 AMI from Systems Manager Parameter Store, then added an EC2 instance resource that references existing components in the stack, including the security group and public subnet.

   <img width="500" height="110" alt="Screenshot 2026-04-22 at 14 19 37" src="https://github.com/user-attachments/assets/54ba5820-7313-43fc-819d-17f9abd40479" />

4. I deleted the CloudFormation stack and observed how CloudFormation automatically removed all resources that had been provisioned by the template, including the VPC, EC2 instance, and S3 bucket.
   This final step reinforced the full lifecycle approach of infrastructure as code—not only provisioning and updating resources through templates, but also cleanly decommissioning them in a controlled and automated way.

   <img width="500" height="103" alt="Screenshot 2026-04-22 at 14 21 49" src="https://github.com/user-attachments/assets/71af955c-80f4-4e53-ae2f-55cce00d5816" />
