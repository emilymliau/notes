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
- accelerated computing: used for GPU-optimized workflows, such as floating point number calculations, graphics processing, or data pattern matching
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
- Savings Plan: 72% discount for critical/predictable workloads, where users must commit to a consistent usage level over a certain time period of 1-3 years
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
  
**TOPICS TO REVIEW**
- Types of Amazon EC2 Instances
- Amazon EC2 Pricing Options
- Elastic Load Balancing (ELB)
- Cloud Messaging Services
  
## Module 3: Exploring Compute Services

AWS Compute Options
- unmanaged service: user has control over patching, scaling, and OS management; AWS manages underlying infrastructure
- managed service: AWS manages operational responsibilities; user focuses on building application rather than building infrastructure
- fully managed service: no need for user to provision or manage any servers, as AWS manages all the infrastructure

AWS Lambda
- AWS Lambda: serverless compute service used to build event-driven applications
- 3 major components of AWS Lambda: function, triggers, runtimes

Containers and Orchestration
- container: package an application's code and dependencies into a single, portable unit for workflows that require security, reliability, and scalability
- containers allow for faster start times and improved resource effiency
- containers are faster and more resource efficient than VMs since they share host's OS

Orchestration Services
- Amazon Elastic Container Service (ECS): user defines application's container images and resources, such as EC2 instance types and load balancers; used for small-to-medium sized businesses
- Amazon Elastic Kubernetes Service (EKS): run Kubernetes clusters on AWS; used when enterprises need full control over infrastructure
- Amazon Elastic Container Registry (ECR): fully managed container registry that stores, manages, and deploys container images, including application and its dependencies
- Amazon EC2: user manages virtual machines that run containers; users have full control, but need to manage underlying infrastructure
- Amazon Fargate: serverless architecture that offers efficiency and convenience
- AWS Elastic Beanstalk: user provides application code and configurations, and AWS builds the environment based on provided information
- AWS Batch: run heavy batch computing workloads with infrastructure management, such as data processing or running simulations
- Amazon LightSail: simplifies hosting for running web applications and websites
- AWS Outposts: links AWS cloud services with on-prem data center for hybrid environments

**TOPICS TO REVIEW**
- AWS Service Models
  
## Module 4: Going Global

Choosing AWS Regions
- compliance: regulatory compliance and data protection laws differ across regions
- proximity: regions closer to customers reduce data travel time and latency
- feature availability: consider specific AWS features and services available in each region
- pricing: different operational costs across regions
  
AWS Global Infrastructure
- agility: ability to quickly adapt to changing requirements or market conditions
- elasticity: ability of a system to automatically scale resources in response to changes in demand
- edge location: locations outside of AZs that cache content to frequently accessed content to users with lower latency
  
Infrastructure and Automation
- AWS CloudFormation: service to model and set up AWS resources so users can focus on managing applications rather than resources
- supports infrastructure as code (IaC) to enable consistent, repeatable deployments across different environments
  
## Module 5: Networking

Networking Components
- Amazon Virtual Private Cloud (VPC): provision an isolated section of AWS Cloud where user can launch AWS resources in a virtual network they define themselves; allows users to control network resources and security
- with VPC, users can organize their resources, share public resources, and isolate private resources
- benefits of Amazon VPC: increase security, save time, control environment
- subnet: range of IP addresses in user's VPC; allows user to organize resources into smaller sections and can be public or private
- private subnet: contain resources that should not be exposed to internet
- public subnet: resources with information that customers have privileges to view
- public subnet requires internet gateway, private subnet requires virtual private gateway
- virtual private network: VPN encrypts internet traffic to protect it from others who try to intercept or monitor it
  
Types of Gateways
- internet gateway: VPC component that allows communication between VPC and internet
- virtual private gateway: encrypted VPN connection to access private, internal AWS resources; allows protected internet traffic to enter into VPC
- AWS Transit Gateway: connect Amazon VPCs and on-prem networks through central hub
- Network Address Translation (NAT) Gateway: instances in private subnet can connect to services outside VPC, but external services cannot create connections with private instances
- Amazon API Gateway: AWS service for creating, publishing, monitoring, and securing APIs at any scale
  
AWS Client VPN
- networking service to connect to remote workers and on-premises networks to the cloud
- provides authentication and remote access
- fully managed, elastic service that scales up or down based on user demand
- provides secure access to AWS resources and on-prem networks through an OpenVPN-based client
- uses the AWS global network to work with global Regions
  
AWS Site-to-Site VPN
- creates a secure connection between data center to AWS Cloud resources
- provides high availability, secure and private sessions, and accelerates applications
- can be used for application migration and secure communication between remote locations
  
AWS PrivateLink
- provides high availability and security for user to privately connect VPC to services and resources without internet gateway, NAT device, public IP address, Direct Connect connection, or AWS Site-to-Site VPN connection
- user controls API endpoints, sites, services, and resources through their VPC
- secures traffic and connection with simplified management rules
- connects clients in user's VPC to resources, other VPCs, and endpoints
  
AWS Direct Connect
- establish dedicated private connection between network and VPC in AWS Cloud
- reduce network costs and increases amount of bandwidth
- used for latency-sensitive applications, large-scale data migration/transfer, and hybrid cloud architectures
- latency-sensitive applications: bypass internet and provide consistent, low-latency network experience for video streaming and real-time applications needing high performance
- large-scale data migration/transfer: ensure smooth and reliable data transfers at large-scale for real-time analysis
- hybrid cloud architectures: use Direct Connect to link AWS and on-prem networks to build applications across multiple environments without compromising performance

Subnets
- subnet: section of VPC to group resources based on security and operational needs, can be public or private
- public subnet: contains resources that need to be accessible by the public
- private subnet: contains resources that should only be accessible through private network
- user defines rules in VPC to allow resources in different subnets to communicate with each other
  
Network Traffic
- packet: unit of data sent over the internet or a network; enters VPC through internet gateway
- network ACL: virtual firewall that controls inbound and outbound traffic at the subnet level
- each AWS account includes default network ACL, and user can add additional rules
- subnet level, stateless packet filtering, allow and deny type rules, return traffic must be implicitly allowed for inbound and outbound, user has broad control of traffic in and out of subnets
- stateless packet filtering: network ACLs do not retain information on inbound and outbound packets
- user is responsible for securing subnets and resources in VPC with network ACLs and security groups
  
Security Groups
- denies all inbound traffic and allows all outbound traffic
- user can create one or multiple security groups for multiple Amazon EC2 instances within the same VPC
- stateful packet filtering: security groups retain information about previous decisions made for incoming packets
- instance level, stateful packet filtering, allow type rules, return traffic is automatically allowed if inbound traffic is allowed, user has fine-grained control of traffic for individal EC2 instances

Building an Amazon VPC
- create VPC, subnets, internet gateway, and route traffic
- edge networking: bringing information storage and computing abilities closer to the devices that produce that information and the users who consume it
Global Networking
- edge networking: bringing information storage and computing abilities closer to devices that produce that information and the users who consume it
- allows organizations to access data and content with lower latency

Amazon Route 53
- DNS that provides reliable and cost-effective way to route end users to internet applications
- manage DNS records for domain names
- connects user requests to infrastructure running inside and outside of AWS

Amazon CloudFront
- CloudFront: content delivery network that delivers your content with faster loading times, cost savings, and reliability
- stores copies of content at locations closer to users to enable low latency

AWS Global Accelerator
- uses AWS global network to improve application availability, performance, and security

## Module 6: Storage


## Module 7: Databases


## Module 8: AI, ML, and Data Analytics


## Module 9: Security


## Module 10: Monitoring, Compliance, and Governance in the AWS Cloud


## Module 11: Pricing and Support


## Module 12: Migrating to the AWS Cloud


## Module 13: Well-Architected Solutions


