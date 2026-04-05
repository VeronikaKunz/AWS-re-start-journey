## Lab Overview

In this lab, I worked on resolving a networking issue where a customer was unable to reach the internet (ping outside the VPC) from their EC2 instance. The customer had already created a VPC and related components but was missing or misconfiguring key networking elements required for connectivity.

I reviewed the architecture and identified that successful internet access in AWS depends on several components working together, including an Internet Gateway, route tables, security groups, and network access control lists (NACLs). I then created and configured these resources to ensure proper routing and access.

By correctly attaching the Internet Gateway, updating route tables to allow outbound traffic, and verifying security settings, I enabled the EC2 instance to successfully communicate outside the VPC.

This lab helped me strengthen my understanding of how AWS networking components interact and how to troubleshoot connectivity issues to ensure a fully functional and routable network environment.

### Steps:

 1. Based on the customer’s request, I created a VPC with the CIDR block 192.168.0.0/18 and designed a public subnet (192.168.1.0/28) to support internet-facing resources. I followed a structured approach by creating and configuring each networking component in sequence to ensure proper connectivity.

    <img width="500" height="378" alt="Screenshot 2026-04-05 at 16 26 50" src="https://github.com/user-attachments/assets/bb870a84-4808-4d23-bd3b-6b9dcd5f686a" />

 
 2. I created and attached an Internet Gateway (IGW) to enable internet access, then configured a route table with a default route (0.0.0.0/0) pointing to the IGW. After that, I associated the route table with the public subnet so that traffic from the subnet could reach the internet.

    <img width="500" height="375" alt="Screenshot 2026-04-05 at 16 31 54" src="https://github.com/user-attachments/assets/16fa0210-928a-473f-969f-61f8f0a36dc8" />


3.  To control traffic, I configured both a Network ACL (allowing inbound and outbound traffic) and a security group that permits SSH, HTTP, and HTTPS access. These settings ensure that the instance can communicate both within the VPC and externally.

    <img width="500" height="375" alt="Screenshot 2026-04-05 at 16 31 54" src="https://github.com/user-attachments/assets/ab53e408-7c24-43c1-b35f-5d51837edbd1" />

    This step established a fully configured and routable VPC environment, ready for launching an EC2 instance and validating connectivity using ping.

4. To verify that the VPC configuration is working correctly, I launched an EC2 instance within the Public Subnet using the Test VPC and the previously created security group. The instance was configured with a public IP address to allow external access.
   After the instance reached the running state, I connected to it using SSH with the selected key pair. Once connected, I tested network connectivity by running the ping command to an external address.
   The successful response confirmed that the Internet Gateway is correctly attached, the route table directs traffic to the internet, and both the security group and Network ACL allow traffic. This validated that the VPC is fully routable and functioning as expected.

   <img width="500" height="168" alt="Screenshot 2026-04-05 at 16 50 51" src="https://github.com/user-attachments/assets/ee6ddcde-ce2d-4352-b1c0-f51036449af8" />
