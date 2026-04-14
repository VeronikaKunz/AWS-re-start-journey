## Lab Overview

This lab applies Python flow control concepts to a scientific use case involving human insulin.

I used dictionaries, loops, and basic calculations to determine the net charge of insulin across a pH range from 0 to 14. The lab involved storing pKa values, counting relevant amino acids in the insulin sequence, and using a while loop to calculate how the net charge changes under different pH conditions.

This exercise demonstrated how programming logic can be used to model and analyze biochemical behavior.

### Steps:

1. I defined the preproinsulin sequence and its components (signal peptide, B-chain, C-peptide, and A-chain) as string variables and combined the B-chain and A-chain to form the insulin sequence.
   Next, I created a dictionary to store the pKa values of specific amino acids that contribute to the net charge calculation. Each key represents an amino acid, and its corresponding value represents its pKa.
   This setup prepares the data needed for calculating the net charge of insulin across different pH levels.

   <img width="500" height="149" alt="Screenshot 2026-04-14 at 21 51 27" src="https://github.com/user-attachments/assets/a75d9022-c695-42de-9d82-4bbf9b4fa865" />

2. I used the **count()** method to determine how many times specific amino acids appear in the insulin sequence.
   First, I tested counting a single amino acid and converted the result to a float. Then, using list comprehension, I created a dictionary that counts all relevant amino acids (y, c, k, h, r, d, e) in one step.
   This produced a structured count of amino acids that will be used later in the net charge calculation.

3. I created a variable pH and initialized it to 0, then used a **while** loop to calculate the net charge of insulin across pH values from 0 to 14.
   Inside the loop, I implemented the provided net charge formula, which calculates the contribution of positively and negatively charged amino acids using their pKa values. I then printed the pH alongside the calculated net charge using formatted output for better readability.
   Finally, I incremented the pH value in each iteration to ensure the loop progresses and stops at 14. This step demonstrated how loops and mathematical expressions can be combined to model biochemical behavior.

   <img width="500" height="528" alt="Screenshot 2026-04-14 at 21 59 02" src="https://github.com/user-attachments/assets/1ab9f9ac-b5eb-4c7c-95ac-ff670700258b" />
