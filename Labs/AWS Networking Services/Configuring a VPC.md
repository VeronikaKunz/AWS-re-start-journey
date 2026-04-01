## Lab Overview

In this lab, I worked with Amazon VPC to design and configure a custom virtual network in AWS. The focus was on building a secure and structured networking environment that separates public and private resources.

I created a VPC with both public and private subnets, configured internet and NAT gateways, and set up route tables to control traffic flow. I also deployed a bastion host in the public subnet to securely access resources in the private subnet.

This lab demonstrated how to design secure cloud networking architectures and manage connectivity between internal and external resources.

### Steps: 

 1. I created a new Virtual Private Cloud (VPC) to establish a custom network environment in AWS. The VPC was configured with a defined IPv4 CIDR block, allowing control over the IP address range and overall network structure.
    After creating the VPC, I enabled DNS hostnames to ensure that instances launched within the network can receive public DNS names. This is essential for connectivity and easier access to resources hosted inside the VPC.

    <img width="500" height="313" alt="Screenshot 2026-04-01 at 15 09 11" src="https://github.com/user-attachments/assets/e9c88cb1-1146-46ea-b06e-05c1a35fb825" />


 2. I created both a public and a private subnet within the VPC to organize resources based on their accessibility requirements. The public subnet was configured to automatically assign public IP addresses, enabling instances to be reachable from the internet when combined with additional networking components.
    The private subnet was designed for internal resources that should not be directly exposed to the internet. It was assigned a larger CIDR range to accommodate more instances, reflecting common best practices where most workloads reside in private subnets.
    At this stage, the VPC remained isolated, setting the foundation for adding connectivity components such as an internet gateway in the next steps.

    <img width="500" height="67" alt="Screenshot 2026-04-01 at 15 15 31" src="https://github.com/user-attachments/assets/d8c61ab2-1d03-4e77-a86b-9546ad39f253" />


 3. I created an internet gateway and attached it to the VPC to enable connectivity between resources inside the VPC and the internet. This component is essential for allowing instances in public subnets to send and receive traffic externally.
    Although the gateway establishes a connection to the internet, additional routing configuration is required to direct traffic through it, which is addressed in the next step.

    <img width="500" height="281" alt="Screenshot 2026-04-01 at 15 17 16" src="https://github.com/user-attachments/assets/74b5fe2e-71f2-4d62-bb4e-ab83403d74ea" />


 4. I configured routing within the VPC by creating a dedicated public route table to handle internet-bound traffic. A route was added to direct all external traffic (0.0.0.0/0) to the internet gateway, enabling outbound connectivity.
    The public subnet was then associated with this route table, allowing resources within it to communicate with the internet. Meanwhile, the original route table was retained for internal communication, effectively separating public and private traffic within the VPC.

    <img width="500" height="427" alt="Screenshot 2026-04-01 at 15 23 56" src="https://github.com/user-attachments/assets/6aefa8ea-151e-47b9-9a77-ff834481b9a8" />

 
 5. I launched a bastion server in the public subnet to enable secure access to resources within the private subnet. The instance was configured with a public IP address and an appropriate security group allowing SSH access.
    This bastion host acts as an entry point to the VPC, providing controlled access to internal resources while keeping them isolated from direct internet exposure.

    <img width="500" height="328" alt="Screenshot 2026-04-01 at 15 29 59" src="https://github.com/user-attachments/assets/c65b95f2-6d53-4414-84bd-5656f4ef89c3" />


 6. I created a NAT gateway in the public subnet to enable secure outbound internet access for resources located in the private subnet. An Elastic IP address was assigned to the NAT gateway to allow it to communicate with external services.
    The private route table was then updated to direct internet-bound traffic through the NAT gateway. This configuration allows instances in the private subnet to access the internet while remaining inaccessible from external sources, ensuring both connectivity and security.

    <img width="500" height="424" alt="Screenshot 2026-04-01 at 15 33 33" src="https://github.com/user-attachments/assets/ce893210-d5a9-41cb-81b9-67e3ad536ac4" />
