## Lab Overview

In this lab, I worked with an Amazon Linux EC2 instance in the AWS Vocareum environment. The main goal was to learn how to connect to a remote server using SSH and explore Linux documentation tools.

I accessed the AWS Management Console, where a pre-configured EC2 Command Host was provided. The lab focused on establishing an SSH connection and understanding how to use the man command, including its search functionality and structure.

### Tasks Performed: 

1. Opened a terminal window and navigated to the directory containing the labsuser.pem key file using the cd command.

2. Modified the file permissions with chmod 400 to restrict access and ensure the key is secure and readable only by the user.

3. Retrieved the EC2 instance’s public IP address from the AWS Management Console.

4. Initiated an SSH connection to the Amazon Linux EC2 instance using the key pair and the ssh command.

5. Confirmed the connection by typing yes when prompted to verify the server’s authenticity on the first login.

6. Successfully connected to the instance using key-based authentication, without the need for a password.
<img width="500" height="300" alt="Screenshot 2026-03-18 at 18 45 11" src="https://github.com/user-attachments/assets/cff81443-4c71-47e8-ab10-813c348294bb" />

7. Opened the Linux manual pages by executing the **man man** command in the terminal to access documentation for the man utility itself.
<img width="500" height="300" alt="Screenshot 2026-03-18 at 18 47 40" src="https://github.com/user-attachments/assets/450d4438-ed2d-4332-8332-af2f83871e2a" />

8. Navigated through the man pages using keyboard controls (arrow keys) to scroll and review the content.

9. Identified and examined key sections of the man pages, such as **NAME**, **SYNOPSIS**, **DESCRIPTION**, **OPTIONS**, and **EXAMPLES**.

10. Analyzed the **DESCRIPTION** section to understand how commands are explained, including the use of section numbers for categorization.

11. Observed the overall structure and organization of the man pages to better understand how Linux documentation is presented.

12. Used the search and navigation features within the man pages to locate specific information efficiently.

13. Exited the man pages by pressing **q** to return to the terminal.
