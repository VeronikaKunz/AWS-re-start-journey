## Lab Overview

In this lab, I worked with AWS Lambda to build and configure a serverless reporting solution. The objective was to automate the generation of a sales analysis report by extracting data from a database, processing it through Lambda functions, and delivering the results by email.
The solution combined several AWS services, including Lambda, Amazon SNS, AWS Systems Manager Parameter Store, and Amazon CloudWatch. I focused on deploying and configuring the serverless components, managing permissions, creating the required Lambda layer for external dependencies, and testing the workflow. This lab also demonstrated how scheduled events and CloudWatch logs can be used to automate and troubleshoot serverless applications.

### Steps:

1. In this task, I created a Lambda layer to package and reuse an external library required for database connectivity. This approach avoids duplicating dependencies across functions and ensures a cleaner and more maintainable serverless architecture.

   <img width="500" height="183" alt="Screenshot 2026-03-26 at 21 05 09" src="https://github.com/user-attachments/assets/43c0f49e-1197-4980-9ccc-afb78337788b" />

I then created a Lambda function responsible for extracting data from the database and attached the previously created layer so the function could use the required library. 

After importing the provided function code and configuring the handler, I reviewed the logic to understand how it retrieves and processes data.

   <img width="500" height="189" alt="Screenshot 2026-03-26 at 21 05 16" src="https://github.com/user-attachments/assets/5f3b9efc-5955-4b06-b5a9-e4b75b070e10" />

Finally, I configured the network settings by connecting the function to the appropriate VPC, subnet, and security group. This was necessary to allow secure communication between the Lambda function and the database running on the EC2 instance, ensuring the function could successfully access and query the data.

   <img width="500" height="361" alt="Screenshot 2026-03-26 at 21 08 34" src="https://github.com/user-attachments/assets/9fceda05-f646-466f-aeec-87d469c5f2f3" />

    
2. In this task, I tested the data extractor Lambda function using database credentials stored in Parameter Store to ensure secure access. The initial execution failed due to a timeout, which I identified as a connectivity issue with the database.
     
  <img width="500" height="166" alt="Screenshot 2026-03-26 at 21 19 46" src="https://github.com/user-attachments/assets/2fe33153-8739-4552-8743-c9c281436416" />

   After updating the security group to allow access on the required port, the function executed successfully. 

  <img width="500" height="160" alt="Screenshot 2026-03-26 at 21 24 26" src="https://github.com/user-attachments/assets/13c942e2-4f01-4819-a0b1-e0062f8d0bf4" />

  I then generated sample data through the café application and verified that the function correctly retrieved and returned the data from the database.

  <img width="500" height="224" alt="Screenshot 2026-03-26 at 21 32 42" src="https://github.com/user-attachments/assets/4c092a8c-b897-4b4f-be9f-18a261b5f1f7" />


3. In this task, I created an SNS topic to handle notifications for the sales analysis report and configured it to deliver messages to subscribed users. I also copied the topic ARN for later use in integrating it with Lambda functions.
   I then subscribed an email address to the topic and confirmed the subscription, enabling the system to send report notifications via email.

  <img width="500" height="172" alt="Screenshot 2026-03-26 at 21 13 13" src="https://github.com/user-attachments/assets/77a575a3-b27e-4845-b296-896b93616714" />

4. I created the main Lambda function responsible for generating the sales analysis report using the AWS CLI. The function was configured with the appropriate IAM role and environment variables so it could retrieve database details, invoke the data extractor function, and publish the results to an SNS topic.

  <img width="500" height="340" alt="Screenshot 2026-03-26 at 22 07 40" src="https://github.com/user-attachments/assets/661cacea-1a5b-4a17-bcd6-439e33e3c843" />

   After testing the function and confirming that the report was successfully sent via email, I added a scheduled trigger using CloudWatch Events. This enabled automatic report generation on a defined schedule, demonstrating a fully automated serverless workflow.

  <img width="500" height="297" alt="Screenshot 2026-03-26 at 22 13 47" src="https://github.com/user-attachments/assets/0085c1ca-39f6-403d-b77d-b610229b9f29" />
