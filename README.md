
## What is cloud computing
- The cloud computing are services that are accessed over the internet. Cloud servers are located inside data centers around the world and allow for on-demand availability of computer system resources, especially data storage and computing power, without direct active management by the user.  
### 3 benefits
- Cost saving is one of the biggest Cloud Computing benefits. It helps you to save money as it does not need any physical hardware investments.
- Security
- Loss Prevention
### best use cases/who is using it in the industry .
- AWS, Microsoft Azure, Google Cloud Platform
- Website Hosting – This is one of the most common business-oriented uses of cloud computing. While companies can host their web presences on physical servers or single cloud servers, the true scale and ability to grow comes when these business start enabling transactions or other web-based services within their hosted environments.

## What is AWS
- Amazon Web Services (AWS) is a cloud service provider. AWS offers a wide range of cloud services, from basic hosting and deployment to analytics, blockchain, machine learning, and more. 
### 3 advantages of AWS/who is using AWS in the industry (Netflix, Twitch, LinkedIn, Facebook)
- Flexible : AWS enables you to select the operating system, programming language, web application platform, database, and other services you need. With AWS, you receive a virtual environment that lets you load the software and services your application requires. 
- Cost-Effective : You pay only for the compute power, storage, and other resources you use, with no long-term contracts or up-front commitments.
- Secure : AWS utilizes an end-to-end approach to secure and harden our infrastructure, including physical, operational, and software measures.

### Types of cloud computing
- over the cloud - public cloud (aws)
- on premises- private cloud (Vagrant, virtual box)
- hybrid cloud (50/50, example: banks, on-premises datacenter  with a public cloud, allowing data and applications to be shared between them.)
- ![image](https://user-images.githubusercontent.com/47173937/115534871-22563f00-a290-11eb-825e-1aca97a2215c.png)


- SaaS - software as a service
- Infrastructure as a service ( IaaS )
- AI as a service ( AIaaS )

- scale out - (add new server) Scaling out a microservices application can be as simple as spinning up a new container running a webserver app and adding it to the load balancer pool. When scaling out the idea is that it is possible to add identical services to a system to increase performance. 
- scale up - (make server bigger) the goal is to increase the resources supporting your application to reach or maintain adequate performance. In a hardware-centric world, this might mean adding a larger hard drive to a computer for increased storage capacity. 

- ![image](https://user-images.githubusercontent.com/47173937/115534485-bd024e00-a28f-11eb-9cf2-a17a88f45ade.png)

- example name for aws:
- Eng84_ula_app / - Eng84_ula_db
- security group works on instance level
- example: Eng84_ula_app_sg

### ec2
- Amazon Elastic Compute Cloud (EC2) is a part of Amazon's cloud-computing platform, Amazon Web Services (AWS), that allows users to rent virtual computers on which to run their own computer applications.  
- Benefits: One of the main benefits of AWS EC2 is its elastic load balancing. This automatically distributes incoming application traffic across several instances, while also identifying unhealthy instances and rerouting traffic to the healthy versions until restored. 

### Security Group
- It works as a firewall for this instance (for ex. app)

### What is subnet?
- can have multiple instances
- is a logical subdivision of an IP network.: 1,16 The practice of dividing a network into two or more networks is called subnetting. Computers that belong to the same subnet are addressed with an identical most-significant bit-group in their IP. Perfect for security

### VPC
- Virtual private Cloud - A VPC gives an enterprise the ability to define and control a virtual network that is logically isolated from all other public cloud tenants, creating a private, secure place on the public cloud.


### Awailablity zones:
- https://aws.amazon.com/about-aws/global-infrastructure/regions_az/
- Region is a physical location around the world where we cluster data centers. We call each group of logical data centers an Availability Zone.
- An Availability Zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity in an AWS Region. 
- AWS Local Zones place compute, storage, database, and other select AWS services closer to end-users.

### High availablity 
- each AWS Region has multiple AZs.  customers who care about the availability and performance of their applications want to deploy these applications across multiple AZs in the same region for fault tolerance and low latency. AZs are connected to each other with fast, private fiber-optic networking, enabling you to easily architect applications that automatically fail-over between AZs without interruption.

### Monolithic Architecture
- Monolith means composed all in one piece. The Monolithic application describes a single-tiered software application in which different components combined into a single program from a single platform.

### 2 tier architecture
- It is Client Server Architecture.
- There is direct communication between entities.
- It is divided into two parts viz. client application (known as client tier) and database (known as data tier).
- Adv: easy to maintain, modification is easy
- Disadv: very cost effective

### 3 tier architecture
- It is used in web based applications.
- It has three layers viz. client layer, business layer and data layer.
- Adv: improves data integrity, It offers higher level of security as client does not have access to the database directly.
