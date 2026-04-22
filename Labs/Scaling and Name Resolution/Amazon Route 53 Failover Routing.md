## Lab overview:

Worked with Amazon Route 53 to set up failover routing for a web application running on two EC2 instances in different Availability Zones. The goal was to ensure that if the primary instance becomes unavailable, traffic is automatically redirected to the secondary instance.

This setup demonstrated how DNS-based failover improves availability and resilience by routing users to a healthy endpoint without manual intervention. It also helped me understand how health checks and routing policies work together to maintain application uptime.

### Steps:

1. I reviewed the two EC2 instances provisioned for the activity and verified that the café application was running successfully on both in different Availability Zones. By accessing the primary and secondary website URLs, I confirmed that each server was active and observed how the application identified the instance and Availability Zone serving the request.
   I also tested the application by placing an order, which confirmed that both environments were functioning correctly. This step was important because it established the healthy primary and backup endpoints needed before configuring failover routing and reinforced how distributing workloads across Availability Zones supports high availability.

   <img width="500" height="488" alt="Screenshot 2026-04-22 at 10 42 39" src="https://github.com/user-attachments/assets/79cdb0f0-a8ae-4367-af9d-5b94b7653b56" />

2. I configured a Route 53 health check to continuously monitor the primary website endpoint and verify whether it remained available. I pointed the health check to the primary EC2 instance, adjusted the check interval and failure threshold for faster detection, and enabled notifications through Amazon SNS.
   This step was important because the failover routing depends on health checks to know when to redirect traffic to the secondary instance. I learned how Route 53 uses endpoint monitoring and health status to support automated failover and improve application resilience.

   <img width="500" height="259" alt="Screenshot 2026-04-22 at 10 57 05" src="https://github.com/user-attachments/assets/fcbf7408-985c-4be8-9b08-f970ed81cd57" />

3. I configured Route 53 failover routing by creating two A records in the hosted zone—one for the primary web server and one for the secondary server. I linked the primary record to the health check and defined it as the primary failover endpoint, while the secondary record served as the standby destination if the primary became unavailable.
   This step was important because it brought the failover design together by combining DNS routing with health monitoring. I learned how Route 53 uses failover policies to redirect traffic automatically to a healthy endpoint and support high availability across Availability Zones.

   <img width="500" height="92" alt="Screenshot 2026-04-22 at 11 01 18" src="https://github.com/user-attachments/assets/0be2ccd0-4744-49fa-acf6-1f8a0f3f2e7b" />

4. I verified the DNS configuration by accessing the Route 53 record in a browser and confirming that traffic resolved to the primary website. By checking the server information displayed in the application, I confirmed that requests were being routed to the instance in the primary Availability Zone.
   This verification showed that the failover records were working as intended before simulating an outage. It also helped me better understand how DNS resolution and routing policies direct users to the correct endpoint.

   <img width="500" height="547" alt="Screenshot 2026-04-22 at 11 03 38" src="https://github.com/user-attachments/assets/a20d50fc-67ec-4ff8-b373-f918e5c06114" />

5. I simulated a failure by stopping the primary EC2 instance and monitored the Route 53 health check until it reported the endpoint as unhealthy. After the health check failed, I refreshed the application and confirmed that traffic was automatically redirected to the secondary instance in the other Availability Zone.
   This exercise demonstrated how Route 53 failover routing responds to outages without manual intervention. I also saw how health checks, DNS propagation, and failover records work together to maintain application availability during a server failure.

   
