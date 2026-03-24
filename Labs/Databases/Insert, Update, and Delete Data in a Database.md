## Lab Overview

In this lab, I worked with a pre-configured relational database to practice data manipulation using SQL. The focus was on managing data within existing tables by performing INSERT, UPDATE, and DELETE operations.
Using the provided environment, I also explored how to import data from a backup file and validate changes within the database. This lab highlighted how data can be added, modified, and maintained effectively within a database system.

### Steps:

   1. I inserted sample data into the country table using **SQL INSERT** statements, ensuring that the values matched the table schema. I then verified the successful insertion by querying the table and filtering for the newly added records.
      This demonstrated how to add new data to a database table and validate that the data was stored correctly.

      <img width="500" height="237" alt="Screenshot 2026-03-24 at 14 45 25" src="https://github.com/user-attachments/assets/b95496a4-8247-48da-81a7-14d8a88affeb" />

   2. I updated existing records in the country table using **SQL UPDATE** statements. By applying changes without a WHERE clause, I modified all rows in the table at once.
      I then verified the updates by querying the table, confirming that the specified columns were successfully changed. This demonstrated how to modify existing data and highlighted the importance of using conditions when targeting specific rows.

      <img width="500" height="542" alt="Screenshot 2026-03-24 at 14 49 00" src="https://github.com/user-attachments/assets/5be0c11d-82ab-4643-8407-eaf4c3474fa6" />

   3. I imported data into the database using an **SQL script file** to efficiently load multiple records and tables at once. After exiting the database client, I executed the script from the terminal, which populated the database with additional tables and data.
      I then reconnected to the database to verify that the import was successful by checking the available tables and querying their contents. This demonstrated how to quickly load and validate large datasets using SQL files.

      <img width="500" height="272" alt="Screenshot 2026-03-24 at 14 52 39" src="https://github.com/user-attachments/assets/5b912609-f273-4c02-891a-7d1508f6b46b" />

