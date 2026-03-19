## Lab Overview

In this lab, I worked with Amazon EC2 to explore different methods of launching and managing instances. The focus was on using both the AWS Management Console and the AWS Command Line Interface (AWS CLI).

An EC2 instance was launched and configured as a bastion host, which provided secure access to resources inside the VPC. Using EC2 Instance Connect, I established a connection to the bastion host and then used the AWS CLI to launch an additional EC2 instance that served as a web server.

Overall, the lab demonstrated how to build a simple, secure architecture and manage EC2 instances using both graphical and command-line tools.
### Launching an EC2 Instance by Using the AWS Management Console
1.  Entered a name for the instance and applied tags to identify it as the **bastion host**.
 <img width="500" height="259" alt="Screenshot 2026-03-19 at 10 52 38" src="https://github.com/user-attachments/assets/077927ca-149b-47f6-bd47-e0a2795a4771" />

2.  Selected the **Amazon Linux 2 AMI** as the operating system for the instance.
 <img width="500" height="300" alt="Screenshot 2026-03-19 at 10 52 48" src="https://github.com/user-attachments/assets/b76eb22f-8d1e-40c8-b77f-3a00bd651c83" />

3.  Chose the **t3.micro** instance type to provide the required compute resources.


4.  Configured login settings and proceeded without a key pair because EC2 Instance Connect was used for access.
 
5.  Configured the network by selecting the **Lab VPC**, keeping the **public subnet** and **public IP** assignment, and creating a **security group** to allow SSH access.
<img width="500" height="355" alt="Screenshot 2026-03-19 at 10 53 12" src="https://github.com/user-attachments/assets/ad9269e2-5bdf-4530-a3a6-3ee41fd41772" />
<img width="500" height="304" alt="Screenshot 2026-03-19 at 10 53 24" src="https://github.com/user-attachments/assets/0051b53f-abcb-4a95-a479-cf9385014902" />


6.  Kept the **default storage** configuration for the root volume.
<img width="500" height="196" alt="Screenshot 2026-03-19 at 10 53 39" src="https://github.com/user-attachments/assets/5f38b444-93c6-44dd-8027-042277426814" />
  
7.  Selected the Bastion-Role IAM instance profile to grant the required permissions for AWS CLI access.
 <img width="500" height="228" alt="Screenshot 2026-03-19 at 10 54 10" src="https://github.com/user-attachments/assets/e0fadb34-e06e-42b0-af53-bd77cdd51610" />

8.  Reviewed the configuration and launched the bastion host EC2 instance.
## Launching an EC2 Instance by Using the AWS CLI

1. Retrieved the latest Amazon Linux 2 AMI ID from AWS Systems Manager Parameter Store and stored it in an environment variable.
<img width="500" height="198" alt="Screenshot 2026-03-19 at 10 56 40" src="https://github.com/user-attachments/assets/1bd2b5ed-8213-4354-a9c2-6a7f33d8ca9d" />

2.  Retrieved the subnet ID for the public subnet by using an AWS CLI command.
<img width="500" height="78" alt="Screenshot 2026-03-19 at 10 57 08" src="https://github.com/user-attachments/assets/1fe891c7-968e-460a-ae2a-4e7541b62524" />

3.  Retrieved the security group ID for the web server security group.
<img width="500" height="72" alt="Screenshot 2026-03-19 at 10 57 35" src="https://github.com/user-attachments/assets/03606481-59ca-43c1-9598-4ce8f4c3faff" />

4.  Downloaded and reviewed the user data script used to automatically install and configure the Apache web server.
<img width="500" height="268" alt="Screenshot 2026-03-19 at 10 57 56" src="https://github.com/user-attachments/assets/134362c6-8554-4ee2-aa3c-55d86104ec3f" />

5. Launched a second EC2 instance as a web server by using the AWS CLI with the AMI, subnet, security group, instance type, tags, and user data script.
<img width="500" height="263" alt="Screenshot 2026-03-19 at 10 59 01" src="https://github.com/user-attachments/assets/00f247e5-959e-424a-87c1-6397388ae19b" />

6.  Checked the instance status until it changed from pending to running.
<img width="500" height="241" alt="Screenshot 2026-03-19 at 11 02 19" src="https://github.com/user-attachments/assets/50334af1-fee1-4f7c-815f-945c17480d2d" />

7.  Retrieved the public DNS name of the web server instance and opened it in a browser to confirm that the website was running successfully.
<img width="500" height="474" alt="Screenshot 2026-03-19 at 11 01 29" src="https://github.com/user-attachments/assets/d89d963c-5003-41cc-a477-1473fa2cbe80" />

  
