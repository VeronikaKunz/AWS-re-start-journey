## Lab Overview

In this lab, I worked with Amazon Elastic Block Store (EBS) to understand how to manage storage for an EC2 instance. The main focus was on creating and attaching storage volumes, configuring them for use, and managing backups.

I created an EBS volume, attached and mounted it to an EC2 instance, and explored how to create snapshots for data backup and recovery. Additionally, I learned how to restore storage by creating a new volume from an existing snapshot.

### Steps:

1. First, I created a new Amazon EBS volume using the EC2 Management Console. I ensured that the volume was configured with the correct type and size, and most importantly, placed it in the same Availability Zone as the existing EC2 instance so it could be attached later.
   I also applied a tag to the volume for easier identification and management. After creation, I verified that the volume status changed to Available, confirming that it was ready for use.

    <img width="500" height="172" alt="Screenshot 2026-03-19 at 20 55 18" src="https://github.com/user-attachments/assets/67201daf-17ca-4d22-ba4c-3b7e650ee57c" />


2. Then, I attached the newly created EBS volume to the existing EC2 instance. I selected the appropriate instance and specified a device name to ensure the volume could be correctly identified by the operating system.
   After attaching the volume, I verified that its status changed to In-use, confirming that it was successfully connected to the EC2 instance and ready for further configuration.

    <img width="294" height="104" alt="Screenshot 2026-03-19 at 20 58 05" src="https://github.com/user-attachments/assets/1e316211-a1d4-44f8-9a5a-3c44e840b155" />


3. In this step, I configured the newly attached EBS volume on the EC2 instance. I first verified the existing storage and confirmed that the new volume was not yet mounted.
   I then created a file system on the volume and set up a mount point to make it accessible within the operating system. After mounting the volume, I updated the system configuration to ensure it would automatically mount after a reboot.
   Finally, I verified the successful setup by checking the available storage and tested the volume by creating and reading a sample file.

   <img width="500" height="328" alt="Screenshot 2026-03-19 at 21 03 22" src="https://github.com/user-attachments/assets/6d3c03b7-8011-4386-9cbd-d9fc7b3907d9" />


4. Now, I created a snapshot of the EBS volume to back up its data. I initiated the snapshot through the EC2 Management Console and added a tag for easier identification. I then monitored the snapshot process until its status changed from Pending to Completed, confirming that the backup was successfully created.
   To demonstrate the purpose of the snapshot, I deleted a previously created file from the volume and verified its removal. This step highlighted how snapshots can be used for data recovery if needed.

   <img width="500" height="44" alt="Screenshot 2026-03-19 at 21 10 35" src="https://github.com/user-attachments/assets/4bd117d8-6b5b-4878-9afb-bf5a426cd00f" />


5.  In this task, I restored data from an EBS snapshot by creating a new volume based on the snapshot. I ensured the volume was created in the correct Availability Zone so it could be attached to the EC2 instance.
    After attaching the restored volume to the instance, I mounted it to a new directory within the operating system to make it accessible. Finally, I verified that the previously deleted file was successfully recovered, demonstrating how snapshots can be used for data restoration.

    <img width="500" height="81" alt="Screenshot 2026-03-19 at 21 17 36" src="https://github.com/user-attachments/assets/27f31a8e-657b-4c2c-bb75-737033b8fa8f" />

    
