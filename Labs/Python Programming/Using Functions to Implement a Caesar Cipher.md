## Lab Overview

This lab introduces user-defined functions in Python by applying them to a practical example: implementing a Caesar cipher.

I created custom functions to structure the program and handle specific tasks, such as shifting letters and processing input. The Caesar cipher works by moving each letter in a message by a fixed number of positions in the alphabet, demonstrating basic encryption.

This lab highlights how functions improve code organization, reusability, and clarity while solving real-world problems.

### Steps:

1. I created a user-defined function called **getDoubleAlphabet** that takes a string as input and returns the string concatenated with itself.
   This function duplicates the provided alphabet, which helps simplify shifting operations later in the Caesar cipher implementation.

2. I created a function called **getMessage** that prompts the user to enter a message for encryption using the **input()** function.
   The function returns the entered string, which will be used later in the Caesar cipher process. This demonstrates how functions can handle user input and pass data to other parts of the program.

3. I created a function called **getCipherKey** to request a shift value from the user using the **input()** function.
   The function returns the entered value, which represents how many positions each letter will be shifted in the Caesar cipher.

4. I created the **encryptMessage** function to implement the core logic of the Caesar cipher.
   The function takes the message, cipher key, and alphabet as inputs. It converts the message to uppercase, then uses a for loop to process each character. For letters found in the alphabet, it calculates a new position based on the cipher key and appends the shifted character to the encrypted message. If a character is not part of the alphabet, it is added unchanged.
   Finally, the function returns the fully encrypted message.

5. I created the **decryptMessage** function by reusing the existing **encryptMessage** function.
   Instead of rewriting the logic, I converted the cipher key into a negative value and passed it to the encryption function. This shifts the characters in the opposite direction, effectively reversing the encryption.
   This demonstrates how functions can be reused to simplify code and avoid duplication.

6. I created the **runCaesarCipherProgram** function to bring together all previously defined functions and implement the full encryption workflow.
   Inside the function, I defined the alphabet, duplicated it for shifting, and collected user input for the message and cipher key. I then used the encryption and decryption functions to process the message and display the results.
   Finally, I called the function to execute the program, demonstrating how individual functions can be combined into a complete, working application.

   <img width="500" height="381" alt="Screenshot 2026-04-14 at 22 15 55" src="https://github.com/user-attachments/assets/f6326ebd-3ae9-4152-988c-e01c83ee6ae4" />
