## Lab Overview

In this lab, I worked with Amazon Aurora to understand how managed relational databases are deployed and used in AWS. The focus was on creating an Aurora database instance and establishing a connection from an EC2 instance.
I explored how to configure connectivity between compute and database resources, and used SQL queries to interact with the database. This lab provided a practical introduction to working with highly available and scalable database solutions in the cloud.

### Steps:

   1. I created an Amazon Aurora (MySQL-compatible) database instance using the AWS Management Console. The configuration included defining database credentials, selecting an appropriate instance type, and setting up networking within the VPC using a predefined subnet group and security group.
      To ensure a secure setup, the database was deployed without public access and restricted to specific network resources. I also configured basic database settings, such as the initial database name, and adjusted monitoring and maintenance options to suit the lab environment.
      Finally, I launched the Aurora instance and monitored its status until it was successfully created and ready for use.

      <img width="500" height="220" alt="Screenshot 2026-03-26 at 12 08 54" src="https://github.com/user-attachments/assets/871f67cf-9404-4f11-aaa4-60603a6410d3" />

  2. I configured the Amazon EC2 Linux instance to connect to the Aurora database by installing the MariaDB client using the package manager. This provided the necessary tools to interact with the database from the command line.
     I then retrieved the database endpoint from the AWS Management Console and used it, along with the database credentials, to establish a connection. After connecting successfully, I verified access to the database through the MariaDB client, confirming that the EC2 instance could communicate with the Aurora cluster.

     <img width="500" height="165" alt="Screenshot 2026-03-26 at 12 17 59" src="https://github.com/user-attachments/assets/f65d3028-853c-4017-b625-6d6011435b9e" />

  3. I created a new table in the Aurora database to store structured country data, defining columns and data types to ensure consistency and proper organization of information. This allows the database to store and manage records in a reliable and scalable way.
     I then inserted multiple records into the table to populate it with sample data, making it possible to work with real entries. Finally, I queried the table using filtering conditions to retrieve only specific records based on defined criteria, demonstrating how to extract meaningful insights from the data.

     <img width="500" height="234" alt="Screenshot 2026-03-26 at 12 21 55" src="https://github.com/user-attachments/assets/0d250f39-17b0-4d84-85e4-59b905ab8bf8" />
