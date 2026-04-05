## Lab Overview

In this lab, I supported a customer who needed help designing a VPC with specific IP address requirements. The customer wanted approximately 15,000 private IP addresses within the VPC and at least 50 IP addresses for a public subnet, while also ensuring the use of a valid private IPv4 range in the 192.x.x.x space.

I analyzed the available private CIDR ranges and confirmed that 192.168.0.0/16 is part of the private IP space. Based on the requirement for around 15,000 IPs, I selected an appropriate CIDR block that provides sufficient capacity and allows for subnetting.

I then designed the VPC structure, including subnets and IP allocation, ensuring that the public subnet meets the required size while maintaining efficient IP distribution across the network.

This lab strengthened my understanding of CIDR calculations, subnet planning, and how to design scalable and well-structured VPC architectures in AWS.

### Steps:

 1. Based on the customer’s request, I defined the appropriate IP addressing and subnet structure before creating the VPC. The requirement of approximately 15,000 IP addresses means that a CIDR block of /18 (16,384 IPs) is the closest suitable option above the requested size. Since the customer prefers a 192.x.x.x private range, I selected 192.168.0.0/18, which is part of the valid private IP space.

    For the public subnet, the requirement was at least 50 IP addresses. I chose a /26 subnet (64 IPs), which satisfies this need while maintaining efficient IP allocation. This resulted in a subnet such as 192.168.1.0/26.

    After defining the addressing plan, I created a VPC with a single public subnet, ensuring that it aligns with the customer’s architecture. This setup allows resources within the subnet to communicate with the internet while keeping the overall network structured and scalable.

    This step ensured that the VPC design meets both capacity and networking requirements before proceeding with further configuration.
