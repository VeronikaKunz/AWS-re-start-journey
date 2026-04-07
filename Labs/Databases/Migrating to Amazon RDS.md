## Lab Overview

In this lab, I migrated a café web application from a local database running on an Amazon EC2 instance to a fully managed Amazon RDS database. Initially, the application and its MariaDB database were hosted together on a single EC2 instance within a public subnet.

As part of the migration process, I created the required infrastructure, including private subnets across multiple Availability Zones, a dedicated security group, and an Amazon RDS MariaDB instance. I then transferred the existing database data from the EC2 instance to the RDS instance.

I also reconfigured the café application to connect to the new RDS database instead of the local database and monitored the database performance using Amazon CloudWatch.

### Steps:

1. In the beginning, I accessed the café web application using the provided URL and placed multiple orders by selecting items from the menu and submitting them. After placing the orders, I navigated to the Order History page to verify that they were successfully recorded and noted the total number of orders created for later comparison.

   <img width="500" height="235" alt="Screenshot 2026-04-07 at 21 47 02" src="https://github.com/user-attachments/assets/8dd06ced-fbf2-4fbc-9911-914f251a5bcb" />

2. In this task, I connected to the pre-configured CLI Host instance using EC2 Instance Connect to access the AWS CLI. I configured the AWS CLI environment and used it to create the required infrastructure for the database deployment. This included setting up a security group for the RDS instance, creating two private subnets across different Availability Zones, and configuring a database subnet group. Finally, I launched an Amazon RDS MariaDB instance using the AWS CLI.

   <img width="500" height="168" alt="Screenshot 2026-04-07 at 22 30 29" src="https://github.com/user-attachments/assets/a0ab4370-08e9-46f4-904c-58bd72543a29" />

3. Now, I connected to the Café EC2 instance by using EC2 Instance Connect and used the mysqldump utility to create a backup of the existing local cafe_db database. After generating the backup file, I restored its contents to the Amazon RDS instance by connecting to the database endpoint with the mysql command.
   To validate the migration, I opened an interactive MySQL session to the RDS instance and queried the product table in the cafe_db database. This confirmed that the database schema and data had been successfully migrated and that the records matched the data previously generated in the café application.

   <img width="500" height="399" alt="Screenshot 2026-04-07 at 23 02 53" src="https://github.com/user-attachments/assets/77effffe-bf29-4453-a870-0694f235a059" />

4. I updated the café application to use the Amazon RDS database by changing the /cafe/dbUrl parameter in AWS Systems Manager Parameter Store to the RDS endpoint. After saving the changes, I opened the website to verify that it was working correctly.
   I then checked the Order History page and confirmed that the number of orders matched the data recorded before the migration, which verified that the application was successfully connected to the new database.

   <img width="500" height="496" alt="Screenshot 2026-04-07 at 23 16 04" src="https://github.com/user-attachments/assets/d2bbb494-2cc7-44e9-abb1-9cf65a42c4a9" />
