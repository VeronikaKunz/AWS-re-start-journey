## Challenge Overview

In this challenge, I deployed and configured a relational database using Amazon RDS with the MySQL engine within the provided lab environment. I ensured that all configurations met the required constraints, including instance type, storage, networking, and security settings.

I then connected to a Linux server via SSH, installed a MySQL client, and established a connection to the database. Using SQL, I created tables, inserted sample data, and executed queries to validate the results. Finally, I performed an inner join to combine data from multiple tables, demonstrating an understanding of relational database concepts.

### Tasks and Steps

**Task 1: Launch and Configure RDS Database**
 - Created an Amazon RDS instance using the MySQL engine.
 - Configured the instance with a burstable class (db.t3.micro), General Purpose SSD storage, and deployed it within the Lab VPC.
 - Set up database credentials and ensured proper security group configuration to allow access from the Linux server (port 3306).
   
   <img width="500" height="184" alt="Screenshot 2026-04-07 at 18 24 58" src="https://github.com/user-attachments/assets/b7b89894-595d-42bd-ba7e-7202b2417372" />

**Task 2: Connect to Linux Server and Database**
 - Downloaded the PEM key and connected to the Linux server via SSH.
 - Installed the MySQL client on the EC2 instance.
 - Connected to the RDS database using the endpoint, username, and password.

**Task 3: Create and Populate RESTART Table**
 - Created a new database and selected it for use.
 - Created the RESTART table with columns: StudentID, StudentName, RestartCity, and GraduationDate.
 - Inserted 10 sample rows into the RESTART table.
 - Queried all records from the table to verify the data.
   
   <img width="482" height="232" alt="Screenshot 2026-04-07 at 19 59 07" src="https://github.com/user-attachments/assets/a1ae3151-96de-441e-83e3-2c9f50ca9584" />

**Task 4: Create and Populate CLOUD_PRACTITIONER Table**
 - Created the CLOUD_PRACTITIONER table with columns: StudentID and CertificationDate.
 - Inserted 5 sample rows into the table.
 - Queried all records to verify the data.

   <img width="290" height="162" alt="Screenshot 2026-04-07 at 20 02 43" src="https://github.com/user-attachments/assets/39aab4d8-c88e-42b4-807c-13a6761ad670" />


**Task 5: Perform INNER JOIN**
 - Executed an INNER JOIN between the RESTART and CLOUD_PRACTITIONER tables using StudentID.
 - Retrieved StudentID, StudentName, and CertificationDate from both tables.

  <img width="376" height="247" alt="Screenshot 2026-04-07 at 20 04 34" src="https://github.com/user-attachments/assets/53167585-5180-4d6e-8d48-6525f34e8395" />


## Conclusion

This challenge provided hands-on experience in deploying and configuring an RDS database, connecting securely via a Linux environment, and performing SQL operations such as table creation, data insertion, querying, and joining datasets. It reinforced key concepts of cloud-based database management and relational data handling.
