## Challenge Overview

In this challenge, I built a serverless solution using AWS Lambda, Amazon S3, and Amazon SNS to automatically count the number of words in a text file. When a file is uploaded to an S3 bucket, the Lambda function is triggered, processes the file, and sends the result via email.

This lab demonstrated how AWS services can be integrated to create an automated, event-driven workflow.

### Tasks & Steps

**Task 1: Create SNS Topic**
 - Created an SNS topic and added an email subscription.
 - Confirmed the subscription.

   <img width="500" height="196" alt="Screenshot 2026-04-07 at 21 10 38" src="https://github.com/user-attachments/assets/04126a7a-9588-4c0b-ac52-e0b0f7b80cef" />


Purpose: Enable email notifications for the word count result.

**Task 2: Create S3 Bucket**
 - Created an S3 bucket in the same region.

   <img width="500" height="314" alt="Screenshot 2026-04-07 at 21 10 17" src="https://github.com/user-attachments/assets/1c80e9bb-3d36-4f28-b077-c01ccafe83d3" />


Purpose: Store uploaded files and trigger the Lambda function.

**Task 3: Create Lambda Function**
 - Created a Python-based Lambda function with LambdaAccessRole.
 - Implemented logic to read the file, count words, and send the result to SNS.
 - Deployed the function.

   <img width="500" height="466" alt="Screenshot 2026-04-07 at 21 11 25" src="https://github.com/user-attachments/assets/04334915-d24e-455f-b799-4e38cd6cb21c" />


Purpose: Process the file and generate the required output.

**Task 4: Configure Trigger**
 - Connected the S3 bucket to the Lambda function.
 - Configured it to trigger on file upload events.

   <img width="500" height="339" alt="Screenshot 2026-04-07 at 21 13 31" src="https://github.com/user-attachments/assets/f948ed02-1df5-4fd2-9eac-d84f54faf56e" />


Purpose: Automate execution when a file is uploaded.

**Task 5: Test the Solution**
 - Uploaded sample .txt file.
 - Verified that the correct word count was sent via email.

Purpose: Ensure the workflow functions correctly end-to-end.

### Result

The solution successfully automated word counting and email notifications, demonstrating the use of serverless and event-driven architecture in AWS.

<img width="500" height="245" alt="Screenshot 2026-04-07 at 21 02 11" src="https://github.com/user-attachments/assets/c560311f-84e3-4814-8772-b99071ac54bd" />

