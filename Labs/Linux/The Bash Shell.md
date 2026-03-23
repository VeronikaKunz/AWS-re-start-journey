## Lab Overview

In this lab, I worked with the Bash shell to improve efficiency and customize the command-line environment. The main focus was on creating aliases to simplify repetitive tasks and managing the PATH variable to make custom commands easily accessible.

### Steps:
  
   1. I created a custom Bash alias to simplify the process of backing up files and directories. The alias was configured to use the tar command with compression, allowing quick creation of archive files.
      After defining the alias, I tested it by backing up a folder into a compressed archive, verifying that all contents were included. Finally, I confirmed that the backup file was successfully created in the directory.

      <img width="235" height="32" alt="Screenshot 2026-03-23 at 16 56 52" src="https://github.com/user-attachments/assets/edff5da5-c433-41c3-8097-aabfd89d3551" />

   2. I explored how the PATH environment variable works and how it affects command execution. I first ran a script from different locations to understand why it could not be executed directly without specifying its path.
      After reviewing the PATH variable, I identified that the script’s directory was not included. I then updated the PATH to include this directory, allowing the script to be executed from any location without specifying its full path.
      This demonstrated how managing the PATH variable improves efficiency and simplifies working with executable files.

      <img width="500" height="86" alt="Screenshot 2026-03-23 at 17 00 33" src="https://github.com/user-attachments/assets/247e20c1-ddc8-409d-b09a-622a27ff2b66" />
