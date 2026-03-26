## Challenge overview


In this challenge, I worked with Amazon S3 to practice basic storage operations and access management. I created a new S3 bucket, ensuring that the name was unique and compliant with AWS naming requirements, which is necessary because S3 bucket names are globally unique.

I then uploaded an object into the bucket to simulate storing a file in the cloud. 

<img width="500" height="361" alt="Screenshot 2026-03-26 at 17 05 38" src="https://github.com/user-attachments/assets/540f5773-0e9f-45ba-814a-2f3c9766dc03" />


When I attempted to access the object through a web browser, access was denied, which demonstrated that S3 objects are private by default to ensure data security.

To make the object accessible, I updated its permissions to allow public read access at the object level, without exposing the entire bucket. 

<img width="500" height="475" alt="Screenshot 2026-03-26 at 17 16 19" src="https://github.com/user-attachments/assets/2516ab9f-90ba-42e6-ab25-2c9d0e0b87ab" />


This approach ensures controlled access while maintaining overall security. After applying these changes, I was able to successfully open the object in the browser, confirming that the configuration worked as expected.

Finally, I used the AWS CLI to list the contents of the bucket, which allowed me to verify that the object was correctly uploaded and available. 

<img width="500" height="72" alt="Screenshot 2026-03-26 at 17 17 27" src="https://github.com/user-attachments/assets/bb6d9d1b-e8aa-4431-8958-bd7a2e0e372d" />


**This challenge demonstrated how to manage object storage, control access, and validate resources in Amazon S3.**
