## Lab overview: 

I worked with an AWS setup containing two VPCs, EC2 instances, and networking components to diagnose and fix connectivity issues. Created an Amazon S3 bucket and configured VPC Flow Logs to capture all network traffic at the interface level. Used the logs to trace rejected and accepted traffic, identify misconfigurations in routing, security groups, or network ACLs, and restore proper access between resources.

### Steps:

1. I connected to the CLI Host EC2 instance using EC2 Instance Connect to access a terminal inside the AWS environment. This was important because it allowed me to work directly with the AWS CLI, which is essential for automation and deeper troubleshooting compared to the web console.
   I then configured the AWS CLI with access keys and region settings, which helped me understand how authentication and service access work in practice. I learned that correct credentials and region configuration are critical, as any mistake here can prevent all further commands from working.

2. I created an S3 bucket to store VPC Flow Logs and then enabled flow logging for VPC1 to capture all IP traffic between network interfaces. This step was important because it gave me visibility into what is actually happening inside the network, not just what I expect to happen.
   I used the AWS CLI to identify the correct VPC and attach the flow logs to it, which helped me understand how AWS resources are connected and referenced in practice. I learned how to track accepted and rejected traffic, which is essential for troubleshooting issues related to routing, security groups, or network ACLs.

   <img width="500" height="269" alt="Screenshot 2026-04-19 at 10 37 34" src="https://github.com/user-attachments/assets/8257a8c8-c9b4-4b8f-94c1-325d3a6c5945" />

3. I tried to access the web server using its public IP, but the page didn’t load, which immediately showed that something was wrong with the network configuration. This step was important because it helped me confirm the problem from a user perspective before jumping into technical checks.
   I then used the AWS CLI to inspect the EC2 instance details, filtering the output to focus only on relevant information like its state, subnet, and security groups. I learned how to quickly extract useful data from large responses and better understand how instances are configured.
   Finally, I attempted to connect via EC2 Instance Connect, which also failed. This confirmed that the issue wasn’t just with the web service, but likely related to networking or access rules, helping me narrow down where to troubleshoot next.

   <img width="500" height="133" alt="Screenshot 2026-04-19 at 10 43 43" src="https://github.com/user-attachments/assets/a7ee9d27-f803-46da-ab93-563898dc6cc1" />

4. I investigated why the web server was unreachable even though the instance was running by using only the AWS CLI. I started with nmap to check open ports and found that no ports were accessible, which suggested that traffic wasn’t reaching the instance at all, not just being blocked at the application level.
   I then checked the security group configuration and learned that it didn’t allow the necessary inbound traffic (like HTTP or SSH), which explained why connections were failing. After that, I reviewed the route table associated with the public subnet and noticed a misconfiguration — the subnet didn’t have a proper route to an Internet Gateway.
   This step was important because it showed me how multiple layers (security groups and routing) work together in AWS networking. I learned how to systematically isolate issues using CLI tools and understand whether the problem is caused by access rules or network routing.

   <img width="500" height="130" alt="Screenshot 2026-04-19 at 10 58 31" src="https://github.com/user-attachments/assets/d855b72a-fc61-4f23-9b0e-0f26042622bb" />

5. I checked the network ACL linked to the public subnet after confirming that the instance was running, the security group allowed port 22, and the route table had internet access. This step was important because it showed me that even when the main settings look correct, subnet-level rules can still block traffic.
   I found that a network ACL entry was preventing SSH access to the web server, which explained why EC2 Instance Connect was still failing. By removing the blocking rule, I learned how network ACLs add another layer of control in AWS and how they differ from security groups by filtering traffic at the subnet level.

   <img width="500" height="634" alt="Screenshot 2026-04-19 at 11 04 14" src="https://github.com/user-attachments/assets/e3d56747-4170-4b34-8ff9-63e027afc799" />

6. I downloaded the VPC Flow Logs from the S3 bucket to the CLI Host and extracted the files to access their contents. This step was important because it allowed me to work with real network traffic data instead of assumptions.
   I then explored the log structure to understand what each field represents, such as source IP, destination port, timestamps, and whether traffic was accepted or rejected. Using command-line tools like grep, I filtered the logs to find rejected SSH connection attempts on port 22 and matched them with my own IP address.
   This helped me clearly see that my connection attempts were being blocked and confirm that the issue I fixed earlier was accurately captured in the logs. I also learned how to trace specific events, verify network interface details, and interpret timestamps, which showed me how flow logs can be used for real troubleshooting and analysis.

   
