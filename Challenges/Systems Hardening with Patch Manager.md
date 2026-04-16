## Lab Overview

In this lab, I worked with AWS Systems Manager Patch Manager to keep EC2 instances up to date and compliant with security requirements.

I used the default patch baseline to scan and patch Linux instances, and created a custom patch baseline for Windows instances. By assigning patch groups, I was able to apply the correct baseline to different systems and manage updates more effectively.

Finally, I verified patch compliance to ensure that all instances met the required update standards.

### Steps:

1. I used AWS Systems Manager Patch Manager to update the Linux EC2 instances using the default Amazon Linux 2 baseline.
   After checking the instances in Fleet Manager, I started a patch operation with scan and install enabled, allowing reboot if needed. I targeted the instances using the tag **Patch Group = LinuxProd**.
   Then I monitored the process and confirmed that all Linux instances were successfully patched.

   <img width="500" height="352" alt="Screenshot 2026-04-16 at 14 40 51" src="https://github.com/user-attachments/assets/78638c83-7cec-4b14-a81c-47d4227ad61d" />

2. I created a custom patch baseline in AWS Systems Manager for Windows instances to focus specifically on security updates.
   In Patch Manager, I defined a new baseline (**WindowsServerSecurityUpdates**) and configured it for Windows Server 2019. I added rules to include only security updates with Critical and Important severity levels, setting automatic approval after 3 days.
   After creating the baseline, I linked it to the WindowsProd patch group so it can be applied to the correct instances. This setup gives more control over which updates are installed on Windows systems.

   <img width="500" height="316" alt="Screenshot 2026-04-16 at 14 53 27" src="https://github.com/user-attachments/assets/1655ca28-fc4f-4708-8bb3-870d36b4a96c" />

3. I tagged the Windows EC2 instances with **Patch Group = WindowsProd** so they could be targeted by Patch Manager.
   After that, I went to Systems Manager and used **Patch Manager → Patch now** to run a patch operation. I configured it to scan and install updates, reboot if needed, and target instances using the WindowsProd tag.
   I monitored the execution through the provided Execution ID and checked the Run Command output to confirm that the patching process was applied correctly to the Windows instances.

   <img width="500" height="366" alt="Screenshot 2026-04-16 at 15 09 15" src="https://github.com/user-attachments/assets/ef8d583b-f7a4-4dfa-a7be-e2c058f61ace" />

4. I checked Patch Manager and confirmed that all six instances were compliant.
   In the Compliance reporting tab, I verified each instance and reviewed key details like patch status and last operation date. I also checked a Windows instance to see which patches were installed.

   
