## Lab Overview

In this lab, I worked with the AWS Command Line Interface (AWS CLI) on an Amazon EC2 instance to explore Amazon S3 and IAM services. The focus was on creating and managing cloud resources and understanding how to deploy a static website using Amazon S3.

### Tasks:

1. In this task, I connected to an Amazon Linux EC2 instance using AWS Systems Manager Session Manager. I accessed the lab details to retrieve the Instance Session URL and used it to open a browser-based terminal session. This allowed me to securely connect to the instance as the **ssm-user** without requiring SSH keys or additional configuration.
2. Then, I configured the AWS CLI on the Amazon Linux EC2 instance. Since the AWS CLI was already pre-installed, I used the aws configure command to set up access credentials. I entered the provided **access key**, **secret key**, **default regio**n, and **output format** to enable secure interaction with AWS services directly from the terminal.
   <img width="500" height="163" alt="Screenshot 2026-03-19 at 14 30 58" src="https://github.com/user-attachments/assets/cdc65db2-c487-4e52-8381-33c9847e3031" />

3. Now, I created an Amazon S3 bucket using the AWS CLI. I used the **aws s3api create-bucket** command, specifying a unique bucket name and the required region configuration. Since the default region differs from the lab requirement, I included additional parameters to ensure the bucket was created in the correct region. After execution, I verified the successful creation of the bucket through the returned **JSON**response.
   <img width="500" height="93" alt="Screenshot 2026-03-19 at 14 33 35" src="https://github.com/user-attachments/assets/7159fddc-c05e-4662-9d11-1862fe0ca44f" />

4. In the next step, I created a new IAM user using the AWS CLI and configured login access for the AWS Management Console. I then signed in as the new user to verify access and observed initial permission restrictions.
   To enable full interaction with Amazon S3, I identified the appropriate AWS managed policy and attached it to the user. After updating permissions, I verified that the user had the required access to work with S3 resources.
   
   <img width="500" height="516" alt="Screenshot 2026-03-19 at 14 41 24" src="https://github.com/user-attachments/assets/bb2c659b-82ef-4103-95d1-cc0bd995d2b8" />

6. In this task, I updated the permissions of the S3 bucket to allow public access. I modified the block public access settings by disabling the restriction, enabling the bucket to be accessible from the internet.
   Additionally, I adjusted the object ownership configuration by enabling ACLs, allowing more granular control over access permissions. These changes were necessary to prepare the bucket for hosting a publicly accessible static website.

   <img width="500" height="191" alt="Screenshot 2026-03-19 at 14 47 41" src="https://github.com/user-attachments/assets/cc487b2c-0962-417e-96df-632ff19b4dc1" />

8. After that, I prepared the website files for deployment by extracting the provided archive on the EC2 instance. I navigated to the appropriate directory, unpacked the compressed file, and accessed the extracted folder.
   I then verified that the extraction was successful by checking for the required files and directories, including the main **index.html** file and supporting assets such as CSS and images.

    <img width="356" height="56" alt="Screenshot 2026-03-19 at 14 49 55" src="https://github.com/user-attachments/assets/214de2b8-7c49-44fa-b9db-706daf8775a7" />

10. In this task, I configured the S3 bucket for static website hosting and uploaded the website files using the AWS CLI. I defined the index document to ensure the correct file is served when the website is accessed.
    I then uploaded all website files to the bucket with public read permissions, enabling them to be accessible over the internet. After the upload, I verified the contents of the bucket and confirmed that static website hosting was enabled.

    <img width="500" height="87" alt="Screenshot 2026-03-19 at 14 57 09" src="https://github.com/user-attachments/assets/f3d69fc2-4ad3-46f0-b565-e0e8cff7bbc0" />

12. Finally, I accessed the bucket’s website endpoint URL to validate that the website was successfully deployed and publicly available.

    <img width="500" height="573" alt="Screenshot 2026-03-19 at 14 59 05" src="https://github.com/user-attachments/assets/c87e18fb-a879-4997-b8b7-1d5cdfc147a4" />

14. In this task, I created a reusable deployment script to simplify and automate updates to the S3-hosted website. I reviewed previously executed commands and used them to build a bash script that uploads website files to the S3 bucket.
    I created and edited the script using the VI editor, added the necessary commands, and made the file executable. To test the process, I modified the website’s HTML file and executed the script to update the content in Amazon S3.

    <img width="500" height="393" alt="Screenshot 2026-03-19 at 15 03 36" src="https://github.com/user-attachments/assets/2891bc64-c653-4c63-b140-a5559656f00a" />


16. After running the script, I refreshed the website in the browser to confirm that the changes were successfully applied. Additionally, I explored a more efficient approach using the aws s3 sync command, which updates only modified files instead of uploading all content each time.


