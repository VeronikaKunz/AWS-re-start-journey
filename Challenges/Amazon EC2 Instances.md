## Challenge Overview

In this challenge, I created and configured an Amazon Linux EC2 instance to host a simple web application. The task required setting up both the infrastructure and the web server, and verifying its functionality.

Launched an Amazon Linux EC2 instance using the AWS Management Console, selecting a T3 instance type smaller than medium, because it meets the lab requirements while remaining cost-efficient.

Created a new VPC and subnet, configured networking components (including an internet gateway and route table), and enabled automatic public IPv4 assignment, because the instance needs internet access and must be reachable from a browser.

Configured storage using a General Purpose SSD (gp2) volume and set up a security group to allow SSH and HTTP access, because secure remote access and web traffic must be permitted.

Added user data to install and start the Apache (httpd) web server and configured permissions for the web directory, so the server is automatically ready and users can upload content.

Connected to the EC2 instance using EC2 Instance Connect over SSH, because direct access to the instance is required to manage files and verify configuration.

Deployed a sample HTML webpage to the /var/www/html directory and used elevated privileges, because this directory requires administrative permissions.

Accessed the web server via the instance’s public IP address to verify that the application was successfully deployed and accessible.

Captured the required screenshots, including the system log and the displayed webpage, to provide evidence that the setup was completed correctly.
