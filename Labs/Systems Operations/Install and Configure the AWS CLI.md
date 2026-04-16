## Lab Overview

This lab focuses on using the AWS Command Line Interface (AWS CLI) to interact with AWS services.

I installed and configured the AWS CLI on a Red Hat Linux EC2 instance, which required manual setup. After connecting to the instance via SSH, I configured access using credentials and practiced running commands to interact with IAM.

The lab shows how the AWS CLI can be used as an alternative to the console for managing AWS resources.

### Steps:

1. I installed the **AWS CLI** by downloading the installer with **curl**, extracting it with **unzip**, and running the install script with **sudo**.
   After installation, I verified it using **aws --version** and tested it with **aws help** to confirm it was working.
   This shows how to manually install and validate the AWS CLI on systems where it is not pre-installed.

   <img width="500" height="259" alt="Screenshot 2026-04-16 at 20 33 34" src="https://github.com/user-attachments/assets/13a424d1-2c79-4364-bbdb-03a682e84614" />

2. I explored the IAM configuration for the awsstudent user in the AWS Management Console.
   I reviewed the attached policy in **JSON** format to see what permissions were granted and checked the security credentials to locate the access key details.
   This shows how IAM policies define access to AWS services and how credentials are used for authentication.

   <img width="500" height="375" alt="Screenshot 2026-04-16 at 20 37 05" src="https://github.com/user-attachments/assets/83a41f09-ed7c-495f-a8d8-54f0f0c7fb22" />

3. I explored the IAM configuration for the awsstudent user in the AWS Management Console by reviewing the attached policy in **JSON** format and checking the security credentials, which showed how permissions are defined and how access keys are used for authentication.

   <img width="500" height="163" alt="Screenshot 2026-04-16 at 20 44 11" src="https://github.com/user-attachments/assets/beef78c9-9d4a-4cad-91b4-93c4577cba84" />
