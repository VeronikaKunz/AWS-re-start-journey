## Lab Overview

This lab applies fundamental Python concepts to a real-world example involving human insulin.

I worked with the protein sequence of preproinsulin by storing it in a string variable and extracting the insulin sequence through string manipulation. I also used numeric variables to represent molecular weights and performed basic calculations.

Throughout the lab, I added comments to explain the logic, used print() for output, and handled simple exceptions. This exercise demonstrated how core Python skills can be used to process and analyze scientific data.

### Steps:

1. I began the script by adding comments to define the Python version and file encoding, following best practices for readability.
   Next, I stored the full preproinsulin sequence in a variable, splitting the string across two lines using a backslash to comply with line length recommendations.
   I then created separate variables for each part of the sequence (signal peptide, B-chain, C-peptide, and A-chain) by assigning the corresponding string values.
   Finally, I combined the B-chain and A-chain to form the insulin sequence using string concatenation, storing the result in a new variable.

   <img width="500" height="166" alt="Screenshot 2026-04-14 at 21 38 18" src="https://github.com/user-attachments/assets/7d4412e5-2a4f-4ad7-9657-4e955f74dd00" />

2. I used the **print()** function to display the preproinsulin sequence and its components in the console.
   First, I printed a descriptive message followed by the full sequence stored in a variable. Then, I demonstrated string concatenation by combining text with the A-chain sequence in a single line of output.
   This step showed how to present data clearly in the console using both direct printing and concatenation.

   <img width="500" height="236" alt="Screenshot 2026-04-14 at 21 40 57" src="https://github.com/user-attachments/assets/4bb393be-7b54-420d-955e-07bdf8a74da5" />


3. I calculated the rough molecular weight of insulin by using a predefined dictionary of amino acid weights and counting their occurrences in the insulin sequence.
   The script converts the sequence to uppercase, counts each amino acid, and multiplies the count by its corresponding weight. The total molecular weight is then calculated using the **sum()** function and printed to the console.
   To evaluate accuracy, I compared the calculated result with the known molecular weight of insulin and computed the error percentage. This demonstrated how Python can be used to perform scientific calculations and analyze results, including handling data types through casting.

   <img width="500" height="177" alt="Screenshot 2026-04-14 at 21 44 06" src="https://github.com/user-attachments/assets/4b4f5c04-410c-4616-8454-c2f33f060f7d" />
