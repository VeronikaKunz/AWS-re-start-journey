## Lab Overview

This lab focuses on composite data types, where multiple data structures are combined into one. The goal was to build a nested structure by placing dictionaries inside a list and working with the contained values.

I practiced using numeric and string data types alongside lists and dictionaries, and applied control flow with for **loops**, **if/else** statements, and the **print()** function. The lab also introduced the use of the import statement to extend functionality.

Overall, this exercise demonstrated how different Python concepts can be combined to create more complex and structured data.

### Steps:

1. I imported the required modules **(csv and copy)** to prepare for working with external data and creating copies in memory.
   I then defined a dictionary to represent a vehicle, initializing it with placeholder values for attributes such as VIN, make, model, and performance details. Using a for loop with the **items()** function, I printed each key-value pair to review the structure.
   Finally, I created an empty list to store multiple vehicle records, which will be populated later.

   <img width="500" height="247" alt="Screenshot 2026-04-14 at 14 42 35" src="https://github.com/user-attachments/assets/2014627e-9c34-49fe-a205-a1505f80cd8d" />

2. I read data from a CSV file using the csv module and the with open statement, which ensures the file is properly opened and closed. The **csv.reader()** function allowed me to iterate through each row of the file.
   Using a for loop with an **if-else** condition, I first printed the column headers and then processed each data row. For every row, I created a deep copy of the vehicle dictionary and updated its values with the corresponding data from the CSV file.
   Each updated dictionary was then added to a list, creating an in-memory collection of vehicles. The use of copy.deepcopy() ensured that each record was stored independently, rather than overwriting previous entries.

   <img width="500" height="296" alt="Screenshot 2026-04-14 at 14 45 31" src="https://github.com/user-attachments/assets/7c605ec4-206d-4744-a7ce-fe1af862f1e8" />

3. I iterated through the list of vehicle records using a for loop. For each vehicle, I used a nested loop to access and print all key-value pairs from the dictionary.
   This displayed the full inventory in a structured format, confirming that the data was correctly read from the CSV file and stored in memory.

   <img width="500" height="502" alt="Screenshot 2026-04-14 at 14 55 26" src="https://github.com/user-attachments/assets/8d239347-8f6e-49e1-a31d-172ec8ca77f0" />
