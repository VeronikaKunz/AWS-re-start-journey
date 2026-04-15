## Challenge Overview

I created a Python script that iterates through numbers from 1 to 250 and checks whether each number is prime. For each number, I used a loop to test if it is divisible by any number other than 1 and itself. If no divisors were found, the number was identified as a prime number.

I stored all prime numbers in a list and printed them to the console. Then, I opened a file called results.txt in write mode and saved the list of prime numbers into it.

Finally, I ran the script using Python 3 in the terminal and verified that the results.txt file contained the correct output.

<img width="500" height="236" alt="Screenshot 2026-04-15 at 16 01 25" src="https://github.com/user-attachments/assets/419b0cc6-fac2-456e-9538-67986d6c3a27" />


### Logic explained: 

I used a **for** loop to go through numbers from 2 to 250 and check each one. Inside it, another loop checks if the number can be divided by anything else.

The **if** statement helps decide if a number is not prime, and **break** stops the loop early when a divisor is found. I used a simple **True/False** flag (**is_prime**) to keep track of that.

All prime numbers are stored in a list, and then written to a file using **with open(...)**. Finally, **print()** just confirms that everything worked.


Overall, it’s a simple combination of loops, conditions, and file writing.

<img width="448" height="306" alt="Screenshot 2026-04-15 at 16 01 48" src="https://github.com/user-attachments/assets/f8606b95-806f-4e79-95dc-591b54e20870" />
