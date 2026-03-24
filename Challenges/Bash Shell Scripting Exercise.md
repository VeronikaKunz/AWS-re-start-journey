## Challenge Overview

In this challenge, I created a Bash script to automate the generation of empty files with sequential names. The script was designed to identify the highest existing file number and create the next batch of 25 files without hard-coding values.

### Steps

   1. Created a Bash script to create 25 empty files using the **touch** command. Configured the script to generate filenames using a fixed name prefix followed by sequential numbers.

      <img width="500" height="128" alt="Screenshot 2026-03-24 at 22 55 24" src="https://github.com/user-attachments/assets/1e4cedd0-df94-4811-a0ab-7e19a0547bce" />

   2. Added logic to detect the highest existing file number in the directory so the script could continue numbering automatically.

      **last_file=$(ls veronika*.txt | sort -V | tail -1)**
      
      Where:
      
      **sort -V → correct numeric order**
      
      **tail -1 → highest file**

   4. I could design the script so that each time I run it, it creates the next batch of 25 files with increasing numbers starting with the last or maximum number that already exists.

      **last_num=$(ls veronika*.txt | wc -l); start=$((last_num)); for i in {1..25}; do touch "veronika$((start + i)).txt"; done**

      <img width="500" height="213" alt="Screenshot 2026-03-24 at 23 19 22" src="https://github.com/user-attachments/assets/adf4ffc5-bac4-4289-af18-6c6f9d4beb69" />
