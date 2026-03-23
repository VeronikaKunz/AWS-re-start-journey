## Lab Overview

In this lab, I worked with software management on a Linux system using a package manager. The main focus was on updating system packages, managing software versions, and installing essential tools.
I explored how to upgrade the system, roll back or downgrade packages when needed, and install the AWS Command Line Interface (AWS CLI) to enable interaction with AWS services from the command line.

### Steps:

 1. I updated the Linux system using the **yum** package manager to ensure all software and security patches were up to date. I first checked for available updates, then applied security updates and performed a full system upgrade.
    Additionally, I installed the **httpd** package and reviewed the update history, gaining insight into how package installations and updates are managed on the system.

    <img width="350" height="201" alt="Screenshot 2026-03-23 at 21 58 21" src="https://github.com/user-attachments/assets/d32b9177-196f-4f2b-aa7c-9c52fe9e475d" />

 2.  I explored how to manage package versions using the **yum** package manager by reviewing the update history and identifying recent changes. I examined specific transactions to understand what updates or installations had been performed.
     I then rolled back a selected transaction using the **yum history undo** command, effectively reverting the system to a previous state. This demonstrated how to safely downgrade or undo package changes when needed.

     <img width="500" height="452" alt="Screenshot 2026-03-23 at 22 03 32" src="https://github.com/user-attachments/assets/301bb477-8635-493f-97e4-bbba7e874d99" />

 3.  I installed the **AWS Command Line Interface (AWS CLI)** on the Linux EC2 instance. I first verified that the required dependencies, such as Python, were available and checked whether the **pip package manager** was installed.
     I then downloaded the AWS CLI installation package, extracted it, and completed the installation using elevated privileges. After installation, I confirmed that the AWS CLI was working correctly by accessing its help menu.
     Finally, I retrieved the necessary access credentials to prepare for configuring and using the AWS CLI in subsequent tasks.

     <img width="500" height="179" alt="Screenshot 2026-03-23 at 22 12 01" src="https://github.com/user-attachments/assets/b6e263a2-e8da-43b8-8712-0fa73393941e" />

 4.  I configured the AWS CLI to connect to my AWS account by running the aws configure command and setting the default region and output format. I then manually updated the credentials file with the provided access keys and session token to enable authenticated access.
     After completing the configuration, I verified the setup by retrieving information about the EC2 instance using an AWS CLI command. This confirmed that the CLI was correctly configured and able to interact with AWS resources.

     <img width="500" height="112" alt="Screenshot 2026-03-23 at 22 20 00" src="https://github.com/user-attachments/assets/f583a38d-66b9-455f-9837-c69eeef9f5ae" />
