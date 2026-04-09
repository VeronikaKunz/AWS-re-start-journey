## Lab Overview

In this lab, I focused on monitoring applications and infrastructure using AWS monitoring services. I worked with Amazon CloudWatch and AWS Config to collect system metrics, analyze logs, and track infrastructure compliance.

I used AWS Systems Manager Run Command to install the CloudWatch agent on EC2 instances, enabling the collection of both system metrics and application logs. I then monitored this data using CloudWatch Metrics and CloudWatch Logs. Additionally, I configured real-time notifications using CloudWatch Events and used AWS Config to evaluate and track infrastructure compliance.

### Steps:

1. I used AWS Systems Manager Run Command to install the CloudWatch agent on the EC2 web server instance. After confirming a successful installation, I created a configuration file in Parameter Store to define which logs and system metrics should be collected. The configuration included web server access and error logs, as well as CPU, memory, and disk metrics.
   I then executed another Run Command to start and configure the CloudWatch agent using the stored parameter. Once completed, the agent began collecting and sending log data to CloudWatch Logs and system metrics to CloudWatch Metrics.

   <img width="500" height="343" alt="Screenshot 2026-04-09 at 15 08 53" src="https://github.com/user-attachments/assets/97e8e281-1966-4a7d-84f1-c2c53d57f177" />

2. I accessed the web server using its public IP address and generated log data by requesting a non-existing page, which produced a 404 error. This action created entries in the web server access logs.
   I then navigated to Amazon CloudWatch and opened the Log groups section, where I located the HttpAccessLog and HttpErrorLog groups created by the CloudWatch agent. By opening the corresponding log stream, I was able to view the incoming log data, including the request I generated and its associated 404 status code.

   <img width="500" height="492" alt="Screenshot 2026-04-09 at 15 20 23" src="https://github.com/user-attachments/assets/538ac29f-8075-48fa-8f81-bd64347ea2b3" />

3. I created a metric filter in CloudWatch Logs to detect 404 errors in the web server access logs. Using the HttpAccessLog log group, I defined a filter pattern to identify log entries with a status code of 404 and tested it against the existing log data to confirm it returned matching results.
   I then configured the metric by assigning a filter name, namespace, and metric name, ensuring that each occurrence of a 404 error would be recorded as a metric in CloudWatch. This allows the log data to be transformed into measurable metrics that can later be used for monitoring and alerting.

   <img width="500" height="352" alt="Screenshot 2026-04-09 at 15 25 27" src="https://github.com/user-attachments/assets/f06805c5-80e0-42a3-9272-4d1c80f088a7" />

4. I created a CloudWatch alarm based on the previously defined 404 error metric to detect abnormal activity in the web server logs. The alarm was configured to trigger when the number of 404 errors reached a defined threshold within a one-minute period.
   I set up an SNS topic to receive email notifications and confirmed the subscription. To test the alarm, I generated multiple invalid requests on the web server, which produced additional 404 errors. After a short time, the alarm transitioned to the Alarm state, and a notification email was received, confirming that the monitoring and alerting setup was working correctly.

   <img width="500" height="593" alt="Screenshot 2026-04-09 at 15 35 06" src="https://github.com/user-attachments/assets/ffa7eba5-6dfe-4bd0-b3c9-5bdba8ac5cfd" />

5. I explored the performance metrics of the EC2 web server using both the EC2 Monitoring tab and Amazon CloudWatch. I reviewed standard metrics such as CPU utilization, disk activity, and network usage directly from the EC2 console.
   I then navigated to CloudWatch Metrics to analyze additional data collected by the CloudWatch agent, including disk usage and memory utilization from inside the instance. By browsing different metric categories, I was able to observe how CloudWatch combines system-level and service-level metrics to provide a comprehensive view of instance performance.

   <img width="500" height="515" alt="Screenshot 2026-04-09 at 15 45 45" src="https://github.com/user-attachments/assets/ad7e5318-71f7-4487-840b-fabf566d476b" />

6. I created a CloudWatch Events rule to monitor EC2 instance state changes, specifically when an instance is stopped or terminated. The rule was configured to trigger on these events and send notifications through an existing SNS topic.
   To test the setup, I stopped the web server instance, which generated an event captured by CloudWatch. Shortly after, I received an email notification containing the details of the instance state change, confirming that real-time monitoring and alerting were working correctly.

   <img width="500" height="265" alt="Screenshot 2026-04-09 at 16 17 32" src="https://github.com/user-attachments/assets/d2e6c2b4-aed4-401b-9258-c1da0744f6ef" />

7. I enabled AWS Config to monitor and evaluate the configuration of AWS resources in the environment. After completing the initial setup, I created managed rules to check compliance with tagging standards and resource usage.
   I configured the required-tags rule to ensure that all resources include a project tag and added the ec2-volume-inuse-check rule to identify EBS volumes that are not attached to EC2 instances. After the evaluation completed, I reviewed the results and observed both compliant and non-compliant resources, confirming that AWS Config was successfully tracking configuration compliance.

   <img width="500" height="241" alt="Screenshot 2026-04-09 at 16 29 10" src="https://github.com/user-attachments/assets/04ddc64a-039c-4d0a-b1cd-80db756426a2" />

