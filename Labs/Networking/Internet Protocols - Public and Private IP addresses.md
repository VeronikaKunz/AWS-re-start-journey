## Lab Overview

In this lab, I analyzed a real-world networking scenario involving connectivity issues within an AWS VPC. The focus was on understanding the difference between public and private IP addresses and how they impact internet access for EC2 instances.

I investigated why two instances in the same subnet behaved differently, identifying that internet connectivity depends on proper configuration such as public IP assignment and routing through an internet gateway. I also evaluated the implications of using public IP ranges within a VPC and recognized potential conflicts with external networks.

This lab helped reinforce key networking concepts in AWS, including IP addressing, routing, and troubleshooting connectivity issues.

### Steps:

 1. I reviewed the customer’s environment by examining the configuration of both EC2 instances and comparing their networking settings. Even though both instances were deployed in the same VPC and subnet, I focused on identifying differences at the instance level, such as public and private IP address assignments.
    By analyzing the networking details, I determined that internet connectivity depends not only on the VPC configuration but also on whether an instance has a public IP address assigned. This step helped identify the root cause of the issue and highlighted the importance of instance-level configuration when troubleshooting connectivity problems.

 2. An SSH connection was attempted to both EC2 instances using a key pair. After downloading the .pem file, updating its permissions, and running the SSH command from the terminal, the connectivity results were observed.
    The connection to instance B was successful because it has a public IP address, which allows access from outside the VPC. The connection to instance A was not successful because it only has a private IP address, which cannot be accessed directly from the internet.
    This step demonstrates that external SSH access requires a public IP address or an intermediate solution such as a bastion host. 
