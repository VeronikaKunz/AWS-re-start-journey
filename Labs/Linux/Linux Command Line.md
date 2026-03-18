## Lab Overview

In this lab, I worked with the command line environment to better understand my current system and active session. The main goal was to practice running basic Linux commands and exploring how to retrieve system information.

I accessed the AWS Management Console through the lab environment and used a pre-configured instance to execute commands. The lab focused on viewing system details and using bash history to search for and re-run previously executed commands.

### Steps:

1. Opened a terminal window and navigated to the directory containing the labsuser.pem key file using the cd command.

2. Modified the file permissions with chmod 400 to restrict access and ensure the key is secure and readable only by the user.

3. Retrieved the EC2 instance’s public IP address from the AWS Management Console.

4. Initiated an SSH connection to the Amazon Linux EC2 instance using the key pair and the ssh command.

5. Confirmed the connection by typing yes when prompted to verify the server’s authenticity on the first login.

6. Successfully connected to the instance using key-based authentication, without the need for a password.
<img width="500" height="300" alt="Screenshot 2026-03-18 at 19 20 37" src="https://github.com/user-attachments/assets/fc595723-ff7e-441e-9005-454d155f5749" />


7. Used basic Linux commands such as **whoami**, **hostname -s**, and **uptime -p** to gather information about the current user, system identity, and runtime status.
 <img width="355" height="84" alt="Screenshot 2026-03-18 at 19 34 05" src="https://github.com/user-attachments/assets/ebfba54f-a626-406e-ab4f-b2a862ec7f43" />


8. Executed the **who -H -a** command to view detailed information about logged-in users and active sessions.
<img width="500" height="99" alt="Screenshot 2026-03-18 at 19 36 24" src="https://github.com/user-attachments/assets/f3df7c62-941a-44f3-b3cc-488581c3363b" />


9. Checked date and time in different time zones using environment variables (e.g., **TZ=America/New_York date**) to understand system time configuration.
<img width="388" height="55" alt="Screenshot 2026-03-18 at 19 39 30" src="https://github.com/user-attachments/assets/0de774c9-583f-40db-9dbb-5af8b557e797" />


10. Explored calendar formats using commands like **cal -j**, **cal -s**, and **cal -m** to view standard and Julian date representations.
<img width="263" height="240" alt="Screenshot 2026-03-18 at 19 39 39" src="https://github.com/user-attachments/assets/9241b0aa-c511-4a2e-b963-cbe617568189" />


11. Retrieved user and group identification details using the **id** command for the current user.
<img width="500" height="45" alt="Screenshot 2026-03-18 at 19 41 01" src="https://github.com/user-attachments/assets/772d417e-09c9-4774-81a6-d561d1b49b42" />


12. Viewed command history with the **history** command to review previously executed commands.
<img width="262" height="138" alt="Screenshot 2026-03-18 at 19 42 02" src="https://github.com/user-attachments/assets/c421fd92-7d42-455c-a453-c2e4d664e60f" />


13. Used reverse search (CTRL + R) to quickly locate and reuse past commands, improving efficiency.


14. Re-ran previous commands using shortcuts such as !! to streamline workflow and reduce repetition.
