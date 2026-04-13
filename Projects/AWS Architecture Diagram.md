# 3D E-Commerce Platform — AWS Architecture

## Overview

This project presents the design of a **scalable, secure, and high-performance AWS architecture** for a 3D e-commerce platform.
The goal was to build a system capable of handling **large 3D assets, global user traffic, and real-time interactions**, while maintaining strong reliability and cost efficiency.

The solution follows modern cloud best practices and demonstrates how to combine multiple AWS services into a **cohesive, production-ready system**. 


## Architecture Approach

The platform is designed around a layered architecture that separates responsibilities across edge services, networking, compute, and data.

User requests are first handled at the edge using Amazon Route 53 and CloudFront, ensuring low latency and fast global content delivery. Security is enforced early through AWS WAF and Shield, protecting the system from malicious traffic before it reaches the backend.

Within the AWS environment, a custom VPC is used to isolate resources. Public subnets expose only the necessary entry points, while application servers and databases are placed in private subnets to reduce risk and improve security.

The core application runs on EC2 instances managed by an Auto Scaling Group across multiple Availability Zones. This allows the platform to automatically adapt to traffic changes while maintaining high availability. For asynchronous and background processes, AWS Lambda is used to decouple non-critical tasks from the main request flow.


## Data & Storage Strategy

A combination of database technologies is used to balance performance and consistency.

DynamoDB is responsible for high-speed operations such as product catalog access, shopping carts, and session data. For transactional workloads like orders and payments, Amazon Aurora (RDS) ensures data integrity through ACID-compliant operations.

All static content, including 3D assets and frontend files, is stored in Amazon S3 and delivered via CloudFront. This significantly reduces load on the application servers and improves overall performance.


## Request Flow

From a user perspective, the interaction is seamless. A request is routed through Route 53 to CloudFront, where content is either served directly from cache or forwarded securely to the backend. After passing security checks, API requests enter the VPC, are distributed by the load balancer, and processed by EC2 instances.

The application interacts with the appropriate data stores and may trigger asynchronous workflows through Lambda, ensuring that time-consuming operations do not impact the user experience. 


## Key Design Principles

The architecture is built around a few core principles:

* High availability through multi-AZ deployment and failover mechanisms
* Scalability via Auto Scaling and serverless components
* Performance optimization using CDN caching and efficient routing
* Strong security with layered protection and network isolation
* Cost efficiency through on-demand resource usage and monitoring


## Key Takeaway

This project highlights a simple but powerful idea:

> Choosing the right service for each task and integrating them effectively is the foundation of a strong cloud architecture.


## Architecture Diagram

<img width="535" height="655" alt="Screenshot 2026-04-13 at 21 10 35" src="https://github.com/user-attachments/assets/ff994728-455a-4cb0-ac9e-d1000f861ff7" />


## Technologies Used

AWS EC2, Lambda, S3, CloudFront, DynamoDB, Aurora (RDS), Route 53, WAF, Shield, CloudWatch

