## Lab Overview

In this lab, I designed and built a custom networking environment using Amazon VPC to meet a customer’s requirements. I created a VPC and configured its core components, including subnets and security settings, to establish a structured and secure network.

I then launched an EC2 instance within this environment and configured it to run a web server. By setting up the appropriate security group rules, I ensured that the server could be accessed over the internet.

This lab helped me understand how to build a VPC from scratch, deploy resources within it, and configure them to deliver a working web application.

### Steps:

1. I created a VPC using the “VPC and more” option with the CIDR block 10.0.0.0/16. I configured one public subnet (10.0.0.0/24) and one private subnet (10.0.1.0/24) in a single Availability Zone.
   The setup also included an Internet Gateway, a NAT Gateway, and separate route tables for each subnet. This created a complete network environment ready for deploying resources.

   <img width="469" height="500" alt="Screenshot 2026-04-05 at 18 00 59" src="https://github.com/user-attachments/assets/387ce42e-7610-44da-8c4c-ad602a14ad21" />

2. To improve availability, I created two additional subnets in a second Availability Zone. I added a public subnet (10.0.2.0/24) and a private subnet (10.0.3.0/24) within the existing Lab VPC.
   This expanded the network across multiple Availability Zones, supporting higher availability and better fault tolerance for deployed resources.

   <img width="500" height="120" alt="Screenshot 2026-04-05 at 18 04 25" src="https://github.com/user-attachments/assets/35e2d82d-e0a7-4953-8526-453dbe289db1" />

3. I associated the newly created subnets with their respective route tables to ensure proper traffic flow. The second public subnet was linked to the Public Route Table, enabling internet access, while the second private subnet was linked to the Private Route Table for controlled outbound connectivity via the NAT Gateway.
   This completed the network setup across multiple Availability Zones, with both public and private subnets properly routed.

4. I created a security group named Web Security Group within the Lab VPC to control access to the EC2 instance. I added an inbound rule to allow HTTP traffic (port 80) from anywhere, enabling web access to the server.

   <img width="500" height="397" alt="Screenshot 2026-04-05 at 18 08 45" src="https://github.com/user-attachments/assets/6e100e56-7981-4cc6-91ed-88fd1a1c64d6" />

5. I launched an EC2 instance named Web Server 1 in the Public Subnet 2 of the Lab VPC and associated it with the Web Security Group. The instance was configured with a public IP address to allow internet access.
   Using user data, I automated the installation of Apache, PHP, and the lab application, and started the web server during instance initialization.
   After the instance passed all status checks, I accessed it via the Public IPv4 DNS in a browser. The successful display of the webpage confirmed that the web server was running correctly and accessible from the internet.

   <img width="500" height="169" alt="Screenshot 2026-04-05 at 18 28 48" src="https://github.com/user-attachments/assets/d83e666d-fed8-45e4-98d3-b47475880b5b" />
