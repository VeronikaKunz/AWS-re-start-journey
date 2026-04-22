## Lab Overview:

I optimized the AWS resources supporting the Café web application by reducing both storage and compute costs. I removed an unused local database from the EC2 instance to lower storage requirements and resized the instance to a smaller T3 micro type to improve cost efficiency.

I also used the AWS Pricing Calculator to estimate service costs and evaluate the impact of the changes. This activity helped me understand how right-sizing and removing unnecessary components can improve utilization while reducing operational expenses.

### Steps: 

1. I configured the AWS CLI on both the Café instance and the CLI Host by setting the access keys, region, and JSON output format, which allowed me to manage AWS resources from the command line. I also used the instance metadata service to identify the correct region dynamically, which helped ensure the CLI was pointed to the right environment.
   I then connected to the CLI Host in a separate SSH session and removed the unused MariaDB service from the Café instance to reduce unnecessary storage usage. After that, I identified the Café instance ID through the AWS CLI, stopped the instance, changed its type to t3.micro, and started it again.
   Once the instance was back online, I checked its new state, public DNS name, and public IP address, then opened the café website in a browser to confirm that it was still functioning correctly. This part of the activity showed me how to optimize an EC2 instance by removing obsolete components and right-sizing compute capacity without breaking the application.

   <img width="500" height="269" alt="Screenshot 2026-04-22 at 12 03 09" src="https://github.com/user-attachments/assets/7f2ae91d-5e2a-413e-b7e4-ccca8bc37ba9" />

2. I used the AWS Pricing Calculator to compare the estimated monthly cost of the Café environment before and after the optimization. First, I entered the original setup with a t3.small EC2 instance, 40 GB of EBS storage, and a MariaDB RDS instance, then saved and exported the estimate to capture the baseline cost.
   After that, I updated the calculator to reflect the optimized setup by changing the EC2 instance type to t3.micro and reducing EBS storage from 40 GB to 20 GB. This made it possible to compare both versions side by side and calculate the projected monthly savings.
   Through this exercise, I saw how infrastructure changes translate into real cost impact. It also gave me practical experience with the AWS Pricing Calculator and showed how right-sizing compute and removing unnecessary storage can reduce ongoing AWS expenses.
   
