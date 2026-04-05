## Lab Overview

In this lab, I investigated a networking issue where an EC2 instance’s public IP address changes every time it is stopped and started. This behavior caused connectivity problems for the customer, as their setup requires a consistent, static IP address.

I analyzed the difference between dynamically assigned public IPs and persistent IP addresses in AWS, and identified why the IP address was changing. Based on this, I implemented a solution by assigning an Elastic IP address to the instance, ensuring that it retains the same public IP across restarts.

Through this process, I gained practical experience in troubleshooting AWS networking issues and applying a reliable solution to maintain stable and predictable access to cloud resources.

### Steps:

 1. To understand the customer’s issue, I launched a new EC2 instance with a configuration similar to the one described. After the instance was running, I reviewed its networking details and noted both the public and private IPv4 addresses.
    I then stopped and started the instance to observe how the IP addresses behaved. After restarting, I noticed that the public IP address changed, while the private IP address remained the same. This confirmed that the public IP assigned by default is dynamic, whereas the private IP is persistent within the VPC.
    To resolve this behavior, I allocated an Elastic IP address and associated it with the instance. After repeating the stop/start process, I observed that the public IP no longer changed. This verified that the Elastic IP provides a static public IP address, ensuring consistent connectivity.
    This step confirmed the root cause of the customer’s issue and demonstrated how assigning an Elastic IP resolves it.
