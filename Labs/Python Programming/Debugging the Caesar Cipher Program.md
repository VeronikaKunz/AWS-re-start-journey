## Lab Overview

This lab focuses on using the **Python Debugger (pdb)** to identify and fix bugs in a Python program.

I applied debugging techniques to different versions of the Caesar cipher program created in a previous lab. By stepping through the code, inspecting variables, and analyzing program flow, I was able to locate and understand errors more effectively.

The lab demonstrates how debugging tools help improve code reliability and simplify troubleshooting in Python programs.

### Steps:

1. I tested the first buggy version of the Caesar cipher program and encountered a traceback during execution. The error occurred because the cipher key was being treated as a string when the program attempted to add it to an integer inside the encryptMessage function.
   Using the debugger and the traceback details, I identified that the issue was caused by a type mismatch in the line calculating newPosition. The fix was to convert cipherKey to an integer before using it in the calculation.
   This step demonstrated how debugging helps identify the exact source of an error and apply a targeted correction.

   <img width="500" height="314" alt="Screenshot 2026-04-15 at 15 16 16" src="https://github.com/user-attachments/assets/19b02ce2-a039-49bd-a9af-03628d6a8568" />

2. I created a new Python file and tested the second buggy version of the Caesar cipher program. Unlike the first version, this one completed without a traceback, but the output showed that the message was only partially encrypted.
   By stepping through the program and trying different inputs, I observed that uppercase letters were encrypted correctly, while lowercase letters were not. This pointed to an issue in how the message was being prepared before the encryption loop.
   The bug was caused by assigning **uppercaseMessage = message** instead of converting the input to uppercase. Updating it to **uppercaseMessage = message.upper()** fixed the issue and ensured the full message was encrypted and decrypted correctly.   

   <img width="500" height="396" alt="Screenshot 2026-04-15 at 15 24 35" src="https://github.com/user-attachments/assets/c7939bd4-3e82-46d9-afd0-c4f2009d1b87" />

3. I created a third version of the buggy Caesar cipher program and tested it with sample input. The program ran without errors and encrypted the message correctly, but the decrypted output was still incorrect.
   By reviewing the decryption logic, I identified that the decryptMessage function calculated a negative key in decryptKey, but then mistakenly passed the original cipherKey into encryptMessage instead of the negative value.
   The fix was to replace:
   **return encryptMessage(message, cipherKey, alphabet)**
   with:
   **return encryptMessage(message, decryptKey, alphabet)**
   After applying this correction, the program decrypted the message properly. This step showed how debugging can uncover logical errors even when the program appears to run successfully.

   <img width="500" height="481" alt="Screenshot 2026-04-15 at 15 30 07" src="https://github.com/user-attachments/assets/c75be379-2971-4e30-b805-e920ddcff787" />

4. I created the fourth buggy version of the Caesar cipher program and tested it with sample input. The program ran without errors, and the message was encrypted correctly, but the decrypted output was identical to the encrypted text.
   By reviewing the final print statement, I identified that the program was displaying myEncryptedMessage instead of myDecryptedMessage.
   The fix was to replace:
   **print(f'Decrypted Message: {myEncryptedMessage}')**
   with:
   **print(f'Decrypted Message: {myDecryptedMessage}')**
   After correcting the print statement, the program displayed the proper decrypted message. This final step demonstrated how even small output-related mistakes can affect the correctness of a program’s results.

   <img width="500" height="416" alt="Screenshot 2026-04-15 at 15 35 48" src="https://github.com/user-attachments/assets/1e39441f-8753-4f6e-a74c-954be9150cab" />

   
