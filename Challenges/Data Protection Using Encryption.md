## Lab Overview

This lab explores how encryption is used to protect data. I connected to an EC2 instance, set up the AWS Encryption CLI, and created an encryption key using AWS KMS.

I then created text files, encrypted them using the key, and confirmed that the content became unreadable. Finally, I decrypted the files to restore the original data.

The lab shows how encryption and decryption work in practice and how AWS tools help keep data secure.

### Steps:

1. I created a symmetric encryption key in AWS KMS to use for encrypting and decrypting data.
   In the KMS console, I created a new key with the alias **MyKMSKey** and added a description. I assigned the **voclabs** role as both the key administrator and user, ensuring it has full permissions to manage and use the key.
   After creating the key, I copied its ARN for later use. This key will be used in the next steps to securely encrypt and decrypt files.

   <img width="500" height="278" alt="Screenshot 2026-04-16 at 16 12 32" src="https://github.com/user-attachments/assets/0dfede34-34fd-4bc3-9d21-b6c91e105dfb" />

2. I connected to the EC2 File Server using Session Manager and configured AWS credentials so the instance could access the KMS key.
   I updated the credentials file with the values from Vocareum and verified the configuration. Then, I installed the AWS Encryption CLI and updated the system path to enable encryption and decryption commands.
   This setup allowed the instance to securely interact with AWS KMS for the next steps.

3. I created sample text files and added sensitive content to one of them. Then, I used the AWS Encryption CLI with my KMS key to encrypt the file and store the encrypted version in a separate folder.
   After confirming the file was encrypted and unreadable, I ran the decrypt command using the same key. This restored the original file, and I verified that the content matched the initial plaintext.
   This task showed how data can be securely encrypted and later decrypted using the same key.
