## Lab Overview

Worked with Elastic Load Balancing and Auto Scaling to build a more resilient and scalable AWS setup. I distributed traffic across multiple EC2 instances using a load balancer and automated capacity management by creating a launch template and an Auto Scaling group.

I also created an AMI to reuse a configured instance, placed new instances in private subnets, and used CloudWatch alarms to trigger scaling based on demand. This helped me understand how to maintain availability, handle traffic spikes, and optimize costs by scaling resources dynamically.

### Steps:

1. I created an AMI from the existing Web Server 1 instance to capture its full configuration, including the operating system, installed software, and web server setup. This step was important because it allows me to launch identical instances automatically without repeating manual setup.
   By doing this, I learned how AMIs are used as templates in Auto Scaling, ensuring consistency across instances and enabling quick scaling when demand increases.

   <img width="500" height="299" alt="Screenshot 2026-04-20 at 15 40 51" src="https://github.com/user-attachments/assets/39586e48-6bcf-490e-a1a4-bc5aa197c2f1" />

2. I created an Application Load Balancer to distribute incoming traffic across multiple EC2 instances and Availability Zones, which improves availability and fault tolerance. I configured it to run in the Lab VPC, mapped it to public subnets in two Availability Zones, and attached a security group that allows HTTP access.
   I also created a target group and linked it to the load balancer, which defines where the traffic should be routed. This step helped me understand how load balancers route requests, how target groups connect instances to the load balancer, and how traffic is distributed to keep applications reliable.

   <img width="500" height="355" alt="Screenshot 2026-04-20 at 15 47 06" src="https://github.com/user-attachments/assets/e4762871-2481-41a2-a236-37fc8b836a9a" />

3. I created a launch template based on the AMI from the web server to define how new instances should be configured in Auto Scaling. This included selecting the instance type, security group, and other settings needed to launch identical instances automatically.
   This step was important because it standardizes instance configuration and ensures consistency when scaling. I learned how launch templates act as blueprints for Auto Scaling, allowing new instances to be created quickly and reliably without manual setup.

   <img width="500" height="147" alt="Screenshot 2026-04-20 at 15 51 52" src="https://github.com/user-attachments/assets/44a288f5-597c-4ffd-8066-88b14578a9cb" />

4. I set up an Auto Scaling group based on the launch template to automatically manage EC2 capacity depending on demand. I configured it to run across two Availability Zones in private subnets and connected it to the load balancer target group so that traffic is routed only to healthy instances.
   I also defined scaling rules based on CPU utilization, which allows the system to add or remove instances dynamically to maintain performance. Through this, I learned how Auto Scaling and load balancing work together to ensure high availability, handle traffic fluctuations, and optimize resource usage efficiently.

   <img width="500" height="232" alt="Screenshot 2026-04-20 at 16 01 28" src="https://github.com/user-attachments/assets/349a1f2b-3858-40d4-b422-d00065969cae" />

5. I verified that Auto Scaling launched new EC2 instances and confirmed that they were registered in the target group. I monitored their health status until both instances became healthy, which showed that the load balancer was ready to route traffic to them.
   I then tested the setup by accessing the application through the load balancer’s DNS name and confirmed that the request was successfully handled by one of the instances. This step helped me understand how health checks control traffic flow and how load balancing ensures availability across multiple instances.

   <img width="500" height="214" alt="Screenshot 2026-04-20 at 16 03 53" src="https://github.com/user-attachments/assets/69360b27-a62e-4448-a042-cc9f680040f7" />

6. I tested the Auto Scaling setup by generating load on the application and monitoring how the system reacted. I observed the CloudWatch alarms and saw how CPU utilization increased, which triggered the scaling policy once it passed the defined threshold.
   As a result, additional EC2 instances were launched automatically, confirming that the Auto Scaling group responds correctly to demand. This step helped me understand how CloudWatch alarms drive scaling decisions and how the system maintains performance by adjusting capacity in real time.

   <img width="500" height="263" alt="Screenshot 2026-04-20 at 16 19 39" src="https://github.com/user-attachments/assets/19d0ef12-fca9-4fe7-81a0-e7b4f8c91812" />
