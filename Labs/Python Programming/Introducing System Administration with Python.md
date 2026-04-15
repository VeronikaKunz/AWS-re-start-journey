## Lab Overview

This lab explores how Python can interact with the operating system by executing Bash commands.

I used the **os.system()** function and the **subprocess.run()** module to run terminal commands directly from a Python script. This demonstrated how Python can automate system-level tasks and integrate with the command line environment.

The lab highlights the practical use of Python for scripting, automation, and managing system operations.

### Steps:

1. I imported the os module and used the **os.system()** function to execute a Bash command directly from Python.
   By passing the **"ls"** command as a string, I was able to display the contents of the current directory in the console. This demonstrated how Python can interact with the operating system to run terminal commands.

   <img width="500" height="362" alt="Screenshot 2026-04-15 at 14 13 57" src="https://github.com/user-attachments/assets/8d4a71aa-7d60-4d95-8211-3f43c40584be" />

2. I imported the subprocess module and used the **subprocess.run()** function to execute the ls Bash command from within Python.
   By passing the command as a list **(["ls"])**, I was able to run it and display the directory contents in the console. This approach is more powerful and flexible than **os.system()**, as it allows better control over inputs, outputs, and error handling when working with system commands.

   <img width="500" height="483" alt="Screenshot 2026-04-15 at 14 17 25" src="https://github.com/user-attachments/assets/ba7d0b09-7b73-4018-bf9c-00d1f4e1eaf0" />

3. I updated the script to pass multiple arguments to the **subprocess.run()** function by using a list.
   By adding the **"-l"** option to the **ls command (["ls", "-l"])**, I was able to display the directory contents in a detailed, long-listing format. This demonstrated how additional command-line arguments can be included when executing system commands from Python.

   <img width="500" height="595" alt="Screenshot 2026-04-15 at 14 19 36" src="https://github.com/user-attachments/assets/e9faaa98-e60d-4d8c-a056-ea88583dc73a" />

4. I modified the **subprocess.run()** function to include a third argument specifying a file name.
   By running the command **["ls", "-l", "README.md"]**, I was able to display detailed information for a specific file instead of the entire directory. This demonstrated how to target individual files when executing system commands from Python.

   <img width="500" height="381" alt="Screenshot 2026-04-15 at 14 21 21" src="https://github.com/user-attachments/assets/434765ee-53f5-4795-9422-494441f5ab16" />

5. I used the **subprocess.run()** function to execute the **uname -a** command and retrieve system information.
   By storing the command and its argument in variables, I printed a descriptive message and then executed the command to display details about the system, such as the operating system, kernel version, and architecture.
   This step demonstrated how Python can be used to gather and display system-level information through Bash commands.

   <img width="500" height="395" alt="Screenshot 2026-04-15 at 14 23 14" src="https://github.com/user-attachments/assets/40398c08-ec91-4c2a-aa67-503ea407f18f" />

6. I used the **subprocess.run()** function to execute the **ps -x** command and retrieve information about active processes on the system.
   By defining the command and its argument in variables, I printed a descriptive message and then ran the command to display currently running processes, including their IDs and statuses.
   This demonstrated how Python can be used to monitor system activity by executing standard Bash commands.

   <img width="500" height="589" alt="Screenshot 2026-04-15 at 14 25 04" src="https://github.com/user-attachments/assets/26765985-7fb1-4fca-a1d0-3f74c2a76e37" />
