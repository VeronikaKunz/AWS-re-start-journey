## Lab Overview

In this lab, I worked with **Amazon RDS** to deploy and manage a relational database in the AWS cloud. The focus was on setting up a highly available database instance and integrating it with a web application.
I explored how to configure connectivity between the database and a web server, and interacted with the database through an application. This demonstrated how AWS-managed database services can be used to support scalable and efficient application architectures.

### Steps:

   1. I created a security group to control access to the RDS database instance. The configuration allowed inbound database traffic on port **3306** specifically from the web server’s security group, ensuring that only authorized resources could connect.
      This setup established secure communication between the web application and the database while restricting access from other sources.

      <img width="500" height="202" alt="Screenshot 2026-03-24 at 21 57 47" src="https://github.com/user-attachments/assets/0de48f89-04ba-4b58-a43e-b58c18921a56" />

   2. I created a DB subnet group to define which subnets the RDS database instance could use. The configuration included subnets from two different Availability Zones, ensuring high availability and fault tolerance.
      By selecting private subnets within the VPC, I ensured that the database would be deployed securely and isolated from direct public access.

      <img width="500" height="445" alt="Screenshot 2026-03-24 at 22 02 00" src="https://github.com/user-attachments/assets/2f5a7314-5c32-4bd2-bb5c-5bc66ca4c7f8" />

   3. I built an Amazon RDS MySQL database instance configured for high availability using a Multi-AZ deployment. This setup ensured data replication across multiple Availability Zones, improving reliability and fault tolerance.
      I configured the instance with appropriate compute, storage, networking, and security settings, including attaching the previously created security group. After launching the database, I monitored its status and retrieved the endpoint required for connecting the application to the database.

      <img width="500" height="210" alt="Screenshot 2026-03-24 at 22 21 11" src="https://github.com/user-attachments/assets/dd43188c-a03a-472e-ba1e-87360fa9b63d" />

   4. I connected a web application to the Amazon RDS database by configuring the application with the database endpoint and credentials. After establishing the connection, the application was able to interact with the database and store data.
      I verified the integration by using the application to add, update, and delete records, confirming that the data was successfully persisted and replicated across the Multi-AZ database setup.

      <img width="500" height="437" alt="Screenshot 2026-03-24 at 22 27 35" src="https://github.com/user-attachments/assets/6cede803-392d-4705-b677-f91c0ec6242c" />
