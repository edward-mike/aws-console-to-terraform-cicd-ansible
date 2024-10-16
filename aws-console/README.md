<!-- Project Readme with sections to other resources -->
# System Architecture Overview

This project demonstrates the deployment of a multi-tiered architecture on AWS, with a focus on leveraging AWS services for scalability, availability, and resource management. The application uses a pre-built Node.js and React.js project for learning purposes, allowing the primary emphasis to be on the AWS infrastructure and resources.

##### 1. Whole Architecture

![Architecture diagram 1](/architecture-diagrams/3-tier-architecture-project-1.png)

##### 2. Closer Look at; Subnets, NAT Gateway, Internet Gateway and route tables

![Architecture diagram 2](/architecture-diagrams/3-tier-architecture-igw-nat-subnets-rt.png)

## Architecture Breakdown

### 1. Public-Facing Load Balancer
- **Component:** Application Load Balancer (ALB)
- **Role:** The ALB serves as the main entry point for client traffic. It routes incoming requests to the web tier EC2 instances, ensuring seamless external access.

### 2. Web Tier
- **Components:** EC2 Instances running Nginx
- **Technology:** React.js for the frontend
- **Role:** 
   - The Nginx web servers in the web tier serve the React.js website to clients.
   - They also handle API calls, redirecting these to the internal load balancer for further processing by the application tier.

### 3. Internal Load Balancer
- **Component:** Internal Application Load Balancer
- **Role:** 
   - Receives API requests from the web tier.
   - Forwards traffic to the application tier for data processing.

### 4. Application Tier
- **Technology:** Node.js
- **Role:** 
   - The application tier processes API calls and performs data manipulation.
   - It interacts with the Aurora MySQL database to handle any necessary data operations.

### 5. Database Layer
- **Component:** Aurora MySQL (Multi-AZ)
- **Role:** The database is configured in a multi-AZ setup, ensuring data redundancy and high availability. It stores and retrieves the application data as required.

## Focus on AWS Resources

The primary focus of this project is on AWS infrastructure, with an emphasis on learning how to use key AWS services such as:
- **Load Balancers (ALB):** For traffic routing and load distribution.
- **EC2 Instances:** To host both web and application tiers.
- **Aurora MySQL (Multi-AZ):** For a scalable, highly available database solution.
- **Auto Scaling Groups (ASG):** For dynamic scaling based on traffic.
- **Health Checks:** To ensure the availability of resources.

The Node.js and React.js components are pre-built and used solely for demonstration purposes, allowing learners to focus on understanding and deploying AWS resources effectively.

## Scalability and Availability Features

### Load Balancing
- Both the public-facing and internal load balancers ensure traffic is distributed evenly across multiple instances, improving performance and reliability.

### Health Checks
- Health checks are implemented to monitor the status of instances at every tier. Traffic is automatically routed to healthy instances, maintaining system stability.

### Auto Scaling Groups
- Auto Scaling Groups (ASGs) are configured for the web and application tiers to dynamically adjust the number of instances based on traffic, ensuring efficient resource use and system availability during traffic spikes.

---

This architecture provides a robust, scalable solution to handle web traffic, process API requests, and manage data across multiple availability zones, ensuring seamless user experiences while focusing on AWS services and their capabilities.

I am working on this project as part of my preparation for the **AWS Solutions Architect Associate** exam, aiming to deepen my understanding of AWS services and infrastructure design.
