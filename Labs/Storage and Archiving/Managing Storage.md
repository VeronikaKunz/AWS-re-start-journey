## Lab Overview

In this lab, I used the AWS Command Line Interface (AWS CLI) to manage data on Amazon EBS volumes. The main focus was on creating and maintaining snapshots, as well as automating their management using scripts.

Working within a pre-configured AWS environment, I also explored how to synchronize data between an EBS volume and an Amazon S3 bucket, and how to use S3 versioning to recover deleted files.

### Steps:

1. In this step, I prepared the environment for data synchronization between an EBS volume and Amazon S3. I created a new S3 bucket with a unique name to store the data that would be synced.
   Additionally, I attached an IAM role to the Processor EC2 instance, granting it the necessary permissions to interact with AWS services such as S3 and EBS. This ensured that the instance could securely access and transfer data without requiring manual credential configuration.

2. Then, I used the AWS CLI to manage EBS snapshots for an EC2 instance. I first connected to the Command Host instance using EC2 Instance Connect, which served as the central point for executing all commands.
   I identified the EBS volume attached to the Processor instance, safely stopped the instance, and created an initial snapshot to ensure data consistency. After verifying the snapshot completion, I restarted the instance.
   To automate the process, I configured a cron job to create snapshots at regular intervals, allowing continuous backups. I then reviewed the generated snapshots and used a Python script to retain only the most recent ones, ensuring efficient storage management by removing older snapshots.

   <img width="500" height="63" alt="Screenshot 2026-03-19 at 21 53 44" src="https://github.com/user-attachments/assets/5d35ecba-0973-4045-9530-6a1fba1e401a" />

3. In this task, I synchronized local files with an Amazon S3 bucket using the AWS CLI. I first enabled versioning on the bucket to ensure that previous versions of files could be preserved and recovered if needed.
   I then uploaded and synchronized files between the local directory and the S3 bucket, verifying that the data was correctly stored. To demonstrate file management, I deleted a file locally and used the sync command with the --delete option to reflect the change in the bucket.
   I restored the deleted file by retrieving its previous version from S3 and re-synchronizing the data, highlighting how versioning supports data recovery and protects against accidental deletions.

   <img width="500" height="354" alt="Screenshot 2026-03-19 at 22 13 40" src="https://github.com/user-attachments/assets/1b031718-a286-43f6-95e9-cb2b2eee0cea" />
