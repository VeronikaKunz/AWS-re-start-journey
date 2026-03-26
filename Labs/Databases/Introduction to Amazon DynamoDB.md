## Lab Overview

In this lab, I worked with **Amazon DynamoDB**, a fully managed NoSQL database service designed for high performance and scalability. I created a table to store data for a music library, which demonstrates how DynamoDB can handle flexible data structures using key-value and document models.
I then added data to the table and performed queries to retrieve specific information, showing how data can be accessed efficiently with low latency. Finally, I deleted the table to complete the lifecycle of managing a DynamoDB resource, reinforcing best practices for resource cleanup.

### Steps:

   1. I created a new DynamoDB table named **Music** to store data for a music library. The table was designed with a partition key (Artist) and a sort key (Song), which together uniquely identify each record and ensure efficient data organization and retrieval.
      This structure allows DynamoDB to distribute data across servers for scalability while also enabling precise queries based on both artist and song.

      <img width="500" height="187" alt="Screenshot 2026-03-26 at 14 22 03" src="https://github.com/user-attachments/assets/e72938f0-aa56-4ac9-b696-fa3568ebedcb" />

   2. I added multiple items to the Music DynamoDB table to populate it with sample data. Each item included the required partition and sort keys (Artist and Song), along with additional attributes such as album, year, and genre to enrich the data.
        This demonstrated DynamoDB’s flexible schema, where each item can have different attributes without needing a predefined structure. By adding varied records, I was able to see how NoSQL databases allow for dynamic and scalable data storage depending on the needs of each entry.

      <img width="500" height="256" alt="Screenshot 2026-03-26 at 14 32 02" src="https://github.com/user-attachments/assets/8591e806-0f57-44b1-a836-2caf55a41401" />

   3. I modified an existing item in the Music table to correct inaccurate data, demonstrating how easily records can be updated in DynamoDB without impacting other items. This highlights the flexibility of managing data in a NoSQL database.
      I then explored how to retrieve data using both query and scan operations. By using a query based on the primary key, I was able to quickly locate a specific item, showing the efficiency of indexed access. I also used a scan with filters to find records based on attributes, which demonstrated a broader but less efficient way of searching through the entire table.

   4. I deleted the Music DynamoDB table to complete the lifecycle of managing a database resource. This action removed both the table structure and all stored data, emphasizing the importance of careful resource management.
      This step reinforced how DynamoDB resources can be quickly created and removed, which is especially useful in lab environments or when cleaning up unused resources to avoid unnecessary costs.   
       
