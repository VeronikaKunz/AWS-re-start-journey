## Challenge Overview

In this challenge, I created and configured an Amazon Linux EC2 instance to host a simple web application. The task required setting up both the infrastructure and the web server, and verifying its functionality.

First I reated a new VPC and subnet, configured networking components (including an internet gateway and route table), and enabled automatic public IPv4 assignment, because the instance needs internet access and must be reachable from a browser.

<img width="500" height="177" alt="Screenshot 2026-03-19 at 11 57 41" src="https://github.com/user-attachments/assets/de9b0e25-df40-4728-89ad-40ad790cbdf2" />

Configured storage using a General Purpose SSD (gp2) volume and set up a security group to allow SSH and HTTP access, because secure remote access and web traffic must be permitted.

Launched an Amazon Linux EC2 instance using the AWS Management Console, selecting a T3 instance type smaller than medium (it meets the lab requirements while remaining cost-efficient)
<img width="500" height="161" alt="Screenshot 2026-03-19 at 12 06 59" src="https://github.com/user-attachments/assets/d5da841b-2303-4ac7-a67c-e02e8bc50559" />

Added user data to install and start the Apache (httpd) web server and configured permissions for the web directory, so the server is automatically ready and users can upload content.

Deployed a sample HTML webpage to the /var/www/html directory and used elevated privileges, because this directory requires administrative permissions.

Accessed the web server via the instance’s public IP address to verify that the application was successfully deployed and accessible.

<img width="339" height="92" alt="Screenshot 2026-03-19 at 12 21 06" src="https://github.com/user-attachments/assets/87aa9280-6180-4aef-a8e0-b6376bb5af1c" />

Accessed the created html file

<img width="527" height="173" alt="Screenshot 2026-03-19 at 12 22 05" src="https://github.com/user-attachments/assets/c8dc9a00-0f8e-4d3c-8362-ac52872e5a6d" />
