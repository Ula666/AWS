
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

### How to make your app High availablity 
- Add multiple regions and providers in case of failure it redirect the trafic 
- Highly available systems are reliable in the sense that they continue operating even when critical components fail. They are also resilient, meaning that they are able to simply handle failure without service disruption or data loss, and seamlessly recover from such failure.

### Elements for a complete High availability system
- Redundancy: Ensuring that critical system components have another identical component with the same data can take over in case of failure.
- Monitoring: Identifying problems in production systems that may disrupt or degrade service.
- Failover: The ability to switch from an active system component to a redundant component in case of failure, imminent failure, degraded performance, or functionality.
- Failback: The ability to switch back from a redundant component t

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


### NACL 
- Extra level of security

### AMI
-  Provides information to launch instance needs to work after security


 ![image](https://user-images.githubusercontent.com/47173937/115889962-5b3b1300-a44c-11eb-8b32-54b8ad967f68.png)

### Stateful filtering 
- tracks the origin of a request and can automatically allow the reply to the request to be returned to the originating computer. For example, a stateful filter that allows inbound traffic to tcp port 80 on a webserver will allow the return traffic, usually on a high numbered port (e.g. destination tcp port 63,912) to pass through the stateful filter between the client and the webserver. The filtering device maintains a state table that tracks the origin and destination port numbers and IP addresses. Only one rule is required on the filtering device: allow traffic inbound to the web server on tcp port 80).
- Security groups are stateful. This means that if they allow a request to come in they will always lets the response back out. Even if the outbound rules don't allow it. The outbound rules only apply to request made FROM your machine.

- NACLs are stateless. You have to have rules to allow the request to come in and to allow the response to go back out.



## AWS Task (Two tier architecture deployment):
 1. Create VPC:
 - In AWS > VPC > Create VPC
 - VPC Settings: name- ex.:eng84_ula_vpc, ipv4- ex.:(`66.66.0.0/16` - first two numbers supposed to be unique, and then two next are 0s)
 2. Create Internet Gateway:
 - In VPC > Internet Gateways > Create Internet Gateway 
 - Internet Gateway Settings: name- ex.: eng84_ula_internet_gateway
 - After that we have to find out gateway from the list, right-click and choose "Attach to VPC"
3. Create subnet:
- VPC > Subnets > Create Subnet
- In Create subnet page we have to specify the name of a subnet ex.: `eng84_ula_public_subnet`, and the IPv4 CIDR block, which has to be slightly different from VPC IPv4 CIDRs, ex.: `66.66.1.0/24` 
The first 2 numbers of this subnet must be the same as VPC's, the third number must be unique, it can't be the same as another subnet you have created. The fourth number must be 0. We have to also use /24.
- Next we have to repeat this step to create private subnet with different IPv4 CIDR block ex.: `66.66.10.0/24`
4. Routing tables:
- In VPC > Route Tables 
- From the list of route tables find the ona that is attached to Your VPC. (Click on one and check the VPC name in the Summary)
- Rename your route table, ex.: `eng84_ula_public_rt`
- Next we want to add internet access for this subnet, next to Summary you will find Routes
- Routes > Edit routes
- Add new route `0.0.0.0/0` with Target as your Internet gateway `igw...` and Save
- Go back to the route table page and select yur route table again and select Subnet Associations > Edit Subnet Associations
- Select your Public subnet and Save
- After that we have to create a new route table for the database with no internet access
- VPC > Route Table > Create route table
- attach the new rote table to your VPC (key: Name, Value: `eng84_ula_routeTable_db`) > Save
- From the list of route tables, select your new route table > choose Subnet Associations > Edit Subnet Associations
- Select your private subnet and Save
5. Now we will create new EC2 instances:
- Go to EC2 > Instances > Instances > Launch Instances
- From the list of AMI choose `Ubuntu Server 16.04 LTS (HMV), SSD Volume Type`
- On the next page choose `t2 micro` and click Next
- On the Configure Instance Details page, select Network and choose your VPC's name
- In the Subnet section choose your Public subnet
- In the Auto-assign Public IP section choose Enable and click Next
- Add Storage page should be left on default 
- On Add Tags page create a tag with sensible name ex.: `eng84_ula_app` and click Next
- On Configure Security Group page set a Security Group Name ex.: `eng84_ula_public_sg` and you can add description
- We want two types:
- Firstly The SSH must be set to TCP, port: 22, Source: My IP, description ex.: admin access
- HTTP - TCP - 80 - Custom - 0.0.0.0/0, ::0, Description ex.: http access
- On the final page click Launch and select `Choose an existing key pair` and select `DevOpsStudent` > Launch Instances
 - Now we have to create another Instance for database:
 - Create new Instance just like we did for the app instance( pages: Step 1 and Step 2 are the same), then on the Step 3 page make sure to set Subnet to your Private subnet
- Pages for Step 4 and 5 exactly the same as for app, only change the tag name to ex.: `eng84_ula_db`
- On the Step 6 page: Security Group Name: ex.: `eng84_ula_private_sg`, SSH the same, but the other one has to be Type: All traffic - Protocol:All - Por:0-65535 - Source:Custom with IP:(your public subnet IPv4) ex.:`66.66.1.0/24` - Description: Access from the public subnet
- Next steps are exactly the same as for the app

6. Test the connection:






