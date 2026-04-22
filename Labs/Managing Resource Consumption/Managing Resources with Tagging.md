## Lab Overview:

I worked with AWS resource tagging to organize and manage EC2 instances using metadata-based attributes. I inspected existing tags with the AWS CLI, used tags to identify groups of instances, and applied scripts to start and stop multiple instances simultaneously based on those tags.

I also explored how tagging can support governance and automation by identifying resources that do not meet tagging requirements and considering how they could be terminated programmatically. This lab helped me understand how tags are used for resource management, automation, and policy enforcement in AWS.

### Steps:

1. I used the AWS CLI and JMESPath queries to identify EC2 instances associated with the ERPSystem project and progressively refined the output to display only the most relevant information, such as instance IDs, Availability Zones, and tag values. By combining multiple tag filters, I narrowed the results to only development instances within the project.
   This exercise helped me understand how tags can be used not just for organization, but also for targeted resource discovery and automation. I also gained hands-on experience using JMESPath queries to extract and format useful data from complex AWS CLI output.

   <img width="500" height="344" alt="Screenshot 2026-04-22 at 11 22 44" src="https://github.com/user-attachments/assets/5beef8b1-7ba7-4a61-8a74-c0b166131995" />

2. I reviewed a Bash script that automatically updated the Version tag for all ERPSystem instances in the development environment. Instead of editing each instance manually, I ran the script to locate the matching instances by tag and overwrite their Version value in one batch operation.
   This showed me how tagging can be managed efficiently at scale through automation. I also saw how AWS CLI output can be converted into plain text and passed directly into other commands, which is useful for scripting bulk changes across resources.

3. I used the provided PHP script to manage EC2 instances based on tags, which made it possible to stop and restart the development servers for the ERPSystem project as a group. Rather than handling each instance manually, I ran the script with tag filters so it targeted only the resources that matched the specified project and environment.
   This demonstrated how tags can drive operational automation across multiple AWS resources. I also saw how the AWS SDK for PHP can search across regions, identify matching instances, and perform bulk actions like stopping and starting systems in a more efficient way.

   <img width="500" height="269" alt="Screenshot 2026-04-22 at 11 27 12" src="https://github.com/user-attachments/assets/29e8b971-a1aa-4c02-9aad-1b8461b8a764" />

4. I explored a “tag-or-terminate” policy by identifying EC2 instances in a private subnet that did not comply with the required Environment tagging standard. After intentionally removing tags from selected instances to simulate non-compliance, I reviewed and ran a script that detected those instances and terminated them automatically.
   This challenge showed how tagging can support security governance, not just organization. I also learned how compliance checks can be automated by comparing tagged resources against all instances in a subnet and taking corrective action programmatically.

   <img width="500" height="179" alt="Screenshot 2026-04-22 at 11 37 05" src="https://github.com/user-attachments/assets/028dc6a1-9e67-42a0-ba0e-d809f2b52242" />


