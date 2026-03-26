## Lab Overview

In this lab, I worked with Amazon S3 to create and configure a storage solution for sharing images with an external user. I set up an S3 bucket and ensured that the appropriate permissions were in place so that the external user could upload, modify, and delete files securely.
I also configured event notifications to automatically trigger alerts when changes occur in the bucket. This demonstrated how S3 can be integrated with other AWS services to enable real-time monitoring and improve visibility over data updates.

### Steps:

   1. I created an Amazon S3 bucket using the AWS CLI to store and share image files, ensuring the bucket name was globally unique and followed naming conventions. This provided a centralized location for storing media assets.
      I then uploaded a set of images into the bucket using a sync command, which efficiently transferred multiple files at once. Finally, I verified that the upload was successful by listing the contents of the bucket, confirming that all files were stored correctly and ready for use.

      <img width="500" height="216" alt="Screenshot 2026-03-26 at 15 22 25" src="https://github.com/user-attachments/assets/f2fce6fc-7b59-4ab2-8747-7dcd36b3a936" />

   2. I reviewed the IAM group and user permissions to understand how access to the S3 bucket is controlled. The mediaco group was configured with specific policies that allow users to view the bucket and perform actions such as uploading, retrieving, and deleting objects within a defined folder, ensuring controlled and secure access.
      I then verified that the **mediacouser** inherits these permissions through group membership and tested them by performing allowed actions such as viewing, uploading, and deleting files. At the same time, I confirmed that restricted actions, such as modifying bucket permissions, were blocked. This demonstrated how IAM policies enforce security and ensure that users only have access to the actions they are intended to perform.

   3. I configured event notifications for the S3 bucket to enable automatic alerts whenever changes occur in the bucket contents. To achieve this, I created an SNS topic and set up the necessary permissions to allow Amazon S3 to publish messages to it.
      I then subscribed an email endpoint to receive notifications and configured the S3 bucket to trigger events for object creation and deletion within a specific folder. This demonstrated how S3 can be integrated with SNS to provide real-time notifications, improving monitoring and visibility of changes in the storage system.

      <img width="500" height="178" alt="Screenshot 2026-03-26 at 15 45 42" src="https://github.com/user-attachments/assets/5da3bce1-a7a9-490f-90a5-f6507cbe744b" />

   4. I tested the S3 event notification configuration by performing common actions on the bucket using the AWS CLI with mediacouser credentials. Uploading and deleting objects triggered email notifications, confirming that the integration between Amazon S3 and SNS was working correctly.
      I also verified that retrieving objects did not generate notifications, as expected based on the configuration. Finally, I tested an unauthorized action by attempting to modify object permissions, which was correctly denied. This confirmed that both the notification setup and access controls were functioning as intended.
