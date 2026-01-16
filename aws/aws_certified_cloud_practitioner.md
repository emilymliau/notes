# AWS Certified Cloud Practitioner

**[AWS Cloud Practitioner Essentials](https://skillbuilder.aws/learn/94T2BEN85A/aws-cloud-practitioner-essentials/8D79F3AVR7)**

## Module 1: Introduction to the Cloud

Terminology
- cloud computing: delivering IT resources on-demand through internet connection and paying for resources (compute power, storage) as you use them remotely
- region: physical locations located around the world that contain groups of 3+ data centers (availability zones) where all components of an application live
- availability zone (AZ): independent data center with its own resources that is connected by networks; resources should be distributed across multiple AZs
  
3 types of cloud deployment: cloud, on-premises, and hybrid
- cloud-based deployment: resources, application design and deployment are all hosted/performed in cloud environments
- on-premises deployment: dedicated set of resources and low latency
- hybrid deployment: cloud-based and on-premises resources are used together; applicable for legacy applications that must be kept on-premises for maintenance and regulatory purposes 
  
6 main benefits of AWS Cloud:
- the cost of resources (compute power, storage) depends on usage, rather than fixed price
- AWS can be used by many organizations, small and large, at lower cost
- customers can adjust resource usage based on needs, rather than making estimates or guesses
- business can quickly deploy applications/services and adapt faster
- no need to spend money or time to run/maintain data centers
- no need to set up internal infrastructure to expand globally, can deploy services in minutes with AWS
  
2 components of AWS global infrastructure:
- high availability: ensuring applications are accessible with minimal downtime; if one component fails, another can take over so the service continues running
- fault tolerance: designing a system that continues to operate even if multiple components fail
  
AWS shared responsibility model:
- customer and AWS responsible for ensuring workloads are secure
- AWS manages security of cloud, including physical, network, and hypervisor layers  
&nbsp;&nbsp;&nbsp;  - software for compute, storage, database, networking  
&nbsp;&nbsp;&nbsp;  - hardware, AWS global infrastructure
- customer manages security in the cloud, including OS, applications, and data  
&nbsp;&nbsp;&nbsp;  - customer data, client-side data encryption
- AWS or customer responsibility: server-side encryption, network traffic protection, platform + application management, OS, network, and firewall configuration

## Module 2: Compute in the Cloud; Amazon Elastic Compute Cloud (EC2)

Terminology
- compute: processing power needed to run applications, manage data, and perform calculations
- compute in the cloud: creating virtual machines with cloud provider to run applications/jobs on the internet
  
Amazon EC2
- EC2: isolated virtual machine that shares resources provided by physical host machine (multi-tenancy)
- hypervisor: responsible for resource sharing and isolation
- 3 main steps to use EC2 instance: launch, connect, and use
- to launch instance, must specify type of instance and OS
- customer responsible for managing OS, networking, and applications on EC2 instances
- AWS manages physical hardware
- deploy EC2 instances across multiple AZs to leverage high availability, allowing instances in different AZs to handle traffic when one fails
  
On-Prem Resource Management
- spend money upfront to purchase hardware
- install and configure servers in physical data center
  
Cloud Resource Management
- only pay for resources when instance is running, scale/pause resource usage based on business needs
- provision and launch Amazon EC2 instance within minutes
  
Types of Amazon EC2 Instances
- EC2 instance types: general purpose, compute optimized, memory optimized, accelerated computing, storage optimized
- general purpose: balance of compute, memory, and networking resources for diverse workloads
- compute optimized: used for compute-intensive tasks (gaming, HPC, ML)
- memory optimized: used for memory-intensive tasks (large-scale data processing)
- accelerated computing: used for performing functions such as floating point number calculations, graphics processing, or data pattern matching
- storage optimized: used for high-performance workloads for data stored locally (large databases, data warehousing, I/O-intensive applications)
  
Accessing APIs
- can access APIs through AWS management console, AWS CLI, or AWS SDK
- AWS management console: provides visual web interface for managing and configuring AWS services
- AWS CLI: manage AWS services from the command line on Windows, macOS, and Linux for automation and scripting
- AWS SDK: provides language-specific APIs for integrating AWS services into applications across multiple programming languages
  
Creating an EC2 Instance
- required configurations: AMI, instance type, storage
1. select Amazon Machine Image (AMI) to configure OS and software
2. select instance type
3. select key pair (public, private)
4. select network settings
5. select storage option
  
Amazon Machine Images (AMI)
- AMI: pre-built VM that contains resources to start instance, including OS, storage, architecture, permissions, and additional software; can launch multiple EC2 instances from one AMI
- repeatability: maintain consistent development/testing environments for each new EC2 instance
  
How to Use AMIs
- build custom AMI
- use pre-configured AMIs developed by AWS for common OS and software
- purchase AMIs from AWS Marketplace for specific use cases
  
Amazon EC2 Pricing Options
- On-Demand: pay-as-you-use, no upfront payments and can use without making long-term commitments
- Savings Plan: 72% discount for critical/predictable workloads, where users must commit to a consistent usage level over a certain time period
- Reserved Instances: 75% discount, intended for steady-state workloads or those with predictable level of usage
- Spot Instances: request unused EC2 capacity at up to 90% discount, but the capacity can be reclaimed by AWS at any point
- Dedicated Hosts: reserve entire physical server where customers control resource allocation, intended for workloads with strict security requirements or compliance with regulatory standards
- Dedicated Instances: isolated workloads but relies on shared infrastructure
- Capacity Reservations: critical workloads with strict capacity requirements, where compute capacity reserved in specific AZ
  
Scaling Amazon EC2
- elasticity: automatically scale resources based on real-time business need
- scalability: a system's ability to handle increased load by adding resources  
&nbsp;&nbsp;&nbsp;  - scale up (vertical scaling): add more resources to existing machines; intended for variable workloads  
&nbsp;&nbsp;&nbsp;  - scale out (horizontal scaling): add more machines; intended for predictable workloads or resource-intensive tasks  
- EC2 Auto Scaling: adjusts number of instances by adding or removing them based on demand and Amazon CloudWatch metrics  
&nbsp;&nbsp;&nbsp;  - dynamic scaling: adapts in real-time to levels of demand  
&nbsp;&nbsp;&nbsp;  - predictive scaling: establishes appropriate number of instances based on anticipated demand  
  
Key Settings for EC2 Auto Scaling Group
- minimum capacity: least number of EC2 instances required for application to run
- desired capacity: ideal number of EC2 instances required to handle current workload
- maximum capacity: upper limit on number of EC2 instances that can be launched to prevent over-scaling
  
Elastic Load Balancing (ELB)
- load balancing: distribute application loads/traffic across available resources to prevent over- or under-utilization and optimize computing performance
- distributes traffic across EC2 instances and enables automatic scaling based on traffic
  
ELB Routing Methods
- Round Robin: distributes traffic evenly across available servers in cyclic manner
- Least Connections: routes traffic to server with fewest active connections
- IP Hash: uses client's IP address to route traffic to one server
- Least Response Time: directs traffic to server with fastest response time
  
Cloud Messaging Services
- Amazon EventBridge: serverless service that routes events to relevent services, allowing for event-driven systems
- Amazon SQS: messages are stored in queue for users and services, preventing data loss when service in unavailable
- Amazon SNS: publishers send messages to subscribers through SNS topics
- tightly coupled architecture: components are tightly connected and dependent on each other
- loosely coupled architecture: components can operate independently

## Module 3: Exploring Compute Services


## Module 4: Going Global


## Module 5: Networking


## Module 6: Storage


## Module 7: Databases


## Module 8: AI, ML, and Data Analytics


## Module 9: Security


## Module 10: Monitoring, Compliance, and Governance in the AWS Cloud


## Module 11: Pricing and Support


## Module 12: Migrating to the AWS Cloud


## Module 13: Well-Architected Solutions


