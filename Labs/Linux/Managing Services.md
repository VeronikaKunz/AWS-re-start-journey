## Lab Overview

In this lab, I focused on monitoring services and system performance on an Amazon Linux 2 EC2 instance. The main objective was to verify that the httpd service was running correctly and accessible via a local HTTP connection.

Additionally, I explored different monitoring methods, including using the Linux top command to observe real-time system performance and AWS CloudWatch to monitor instance metrics within the AWS environment.

### Steps:
  1. I checked and managed the status of the Apache (httpd) service on the EC2 instance. Initially, the service was installed but inactive, so I started it using the systemctl command.
     After confirming that the service was running, I verified its functionality by accessing the instance’s public IP address in a browser, which displayed the Apache test page. Finally, I stopped the service to understand how to control its lifecycle.

     <img width="500" height="241" alt="Screenshot 2026-03-23 at 16 36 01" src="https://github.com/user-attachments/assets/910d343d-45fa-4af4-937e-6fc6acb46118" />


     <img width="500" height="476" alt="Screenshot 2026-03-23 at 16 36 38" src="https://github.com/user-attachments/assets/46893062-534f-4435-bb1c-e24a6a776172" />

  2. I monitored the performance of the Amazon Linux 2 EC2 instance using both Linux tools and AWS services. I started by running the top command to view active processes and observe real-time CPU and memory usage.
     To simulate load, I executed a stress script, which increased CPU utilization. Running top again allowed me to clearly see the impact of the workload on system performance.

     <img width="500" height="573" alt="Screenshot 2026-03-23 at 16 40 56" src="https://github.com/user-attachments/assets/e63e49d5-43cc-4f26-9169-7093a189c1c3" />


  3. I then accessed AWS CloudWatch through the AWS Management Console to analyze instance metrics in a more visual way. Using the EC2 dashboard, I observed key metrics such as CPU utilization, disk activity, and network usage. The graphs reflected the spike in CPU usage caused by the stress script, followed by a drop once the process completed.
     This demonstrated how both command-line tools and CloudWatch can be used together to monitor and analyze system performance effectively.

     <img width="475" height="220" alt="Screenshot 2026-03-23 at 16 49 02" src="https://github.com/user-attachments/assets/ee87acdb-be16-4b48-aa29-f1bc19986d6b" />

