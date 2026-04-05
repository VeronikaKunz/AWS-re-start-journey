## Lab Overview

In this lab, I analyzed a networking issue where a customer was unable to access an Apache web server hosted on an EC2 instance. The problem included both failed ping requests and the inability to open the server in a browser, indicating a connectivity or configuration issue.

I approached the scenario by systematically troubleshooting the network setup, checking components such as security groups, network ACLs, route tables, and internet gateway configuration. I also considered whether the Apache service was running correctly and listening on the required ports.

By identifying what was blocking the connection and correcting the configuration, I ensured that the EC2 instance became reachable both through ping and via a web browser.

This lab strengthened my ability to diagnose real-world networking issues and apply a structured troubleshooting approach in AWS environments.

### Steps:

1. To begin troubleshooting, I checked the status of the Apache (httpd) service on the EC2 instance. The initial status showed that the service was inactive, meaning it was installed but not running.
   I started the service using the appropriate command and then verified that its status changed to active, confirming that the web server is now running on the instance.

   <img width="500" height="225" alt="Screenshot 2026-04-05 at 17 32 24" src="https://github.com/user-attachments/assets/35dffb94-a38e-44fb-a17c-f8059fa3d65b" />

2. After confirming that the Apache service was running but still not accessible, I moved on to analyze the VPC configuration. I reviewed each networking component, including subnets, route tables, the internet gateway, security groups, and network ACLs.
   I verified that the instance could reach the internet by testing connectivity (for example, using ping), which confirmed that the internet gateway and route table were configured correctly. This indicated that outbound connectivity was working as expected.
   Next, I focused on inbound access. Since Apache serves web traffic over HTTP (port 80) and HTTPS (port 443), I checked the security group rules associated with the EC2 instance. I identified that the necessary inbound rules were missing or incorrectly configured, which prevented access from the browser.
   After correcting the security group to allow HTTP traffic, the Apache test page became accessible via the instance’s public IP address. This confirmed that the issue was related to inbound traffic restrictions rather than the VPC routing or the application itself.

   <img width="500" height="481" alt="Screenshot 2026-04-05 at 17 42 36" src="https://github.com/user-attachments/assets/76e6e2f6-e6d2-48f4-8865-0491b165eef1" />
