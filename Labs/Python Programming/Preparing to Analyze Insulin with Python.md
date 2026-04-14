## Lab Overview

This lab focuses on using Python for basic scientific data manipulation, specifically working with biological sequences.

I worked with a protein sequence related to human insulin, extracting the insulin sequence from a larger preproinsulin sequence. This demonstrated how Python can be used to process and manipulate real-world scientific data.

### Steps: 

1. I accessed the National Center for Biotechnology Information to search for the human insulin protein sequence.
   After selecting the correct result **(insulin [Homo sapiens])**, I copied the sequence starting from ORIGIN to // and saved it into a new file named **preproinsulin-seq.txt** in the Cloud9 environment.
   This step provided the raw biological data that will be used for further processing and analysis in the lab.
   I cleaned the **preproinsulin-seq.txt** file programmatically using Python and regular expressions. The goal was to remove unnecessary elements such as the ORIGIN label, numbers, slashes (//), spaces, and line breaks, leaving only the protein sequence.
   After processing the file, I verified the result by checking the total number of characters using the **len()** function, confirming that the cleaned sequence contains 110 characters. This step demonstrates how raw data can be prepared for analysis using code.

   <img width="500" height="401" alt="Screenshot 2026-04-14 at 21 12 14" src="https://github.com/user-attachments/assets/e993de4b-288b-4606-b0a2-ef89a3cba4a6" />

2. I then divided the sequence into its functional parts based on amino acid positions and saved each segment into separate files:
   **lsinsulin-seq-clean.txt → amino acids 1–24 (24 characters)
   binsulin-seq-clean.txt → amino acids 25–54 (30 characters)
   cinsulin-seq-clean.txt → amino acids 55–89 (35 characters)
   ainsulin-seq-clean.txt → amino acids 90–110 (21 characters)**

   This step demonstrated how biological data can be programmatically processed and segmented for further analysis.

   <img width="500" height="357" alt="Screenshot 2026-04-14 at 21 21 44" src="https://github.com/user-attachments/assets/52a1fa77-06aa-4021-9bbc-da57887adc4b" />
