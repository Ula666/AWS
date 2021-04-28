
### What is cloud computing
- The cloud computing are services that are accessed over the internet. Cloud servers are located inside data centers around the world and allow for on-demand availability of computer system resources, especially data storage and computing power, without direct active management by the user.  
### 3 benefits
- Cost saving is one of the biggest Cloud Computing benefits. It helps you to save money as it does not need any physical hardware investments.
- Security
- Loss Prevention
### best use cases/who is using it in the industry .
- AWS, Microsoft Azure, Google Cloud Platform
- Website Hosting – This is one of the most common business-oriented uses of cloud computing. While companies can host their web presences on physical servers or single cloud servers, the true scale and ability to grow comes when these business start enabling transactions or other web-based services within their hosted environments.

### What is AWS
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
- It works as a firewall for this instance (for ex. app). Enables to specify the port range
- works on the instance level
- they are attached to your VPC and subnet
- they have inbound and outbound traffic rules deffined 
- security groups are stateful if you allowed inbound rule that will automatically be allowed outbound

### What is subnet?
- subnet can have multiple EC2 instances
- is a logical subdivision of an IP network.: 1,16 The practice of dividing a network into two or more networks is called subnetting. Computers that belong to the same subnet are addressed with an identical most-significant bit-group in their IP. Perfect for security
- make network more efficient 
- A range og IP addresses in your VPC


### VPC
- Virtual private Cloud gives the ability to define and control a virtual network that is logically isolated from all other public cloud tenants, creating a private, secure place on the public cloud. Enables you to launch AWS resources into a virtual network that you've.
- it allows to have different EC2 on the same network and interact with each other, we can also create multiple subnets with our VPC
- it benefits us with scalability of infranstructure of AWS

### Route table
- used to determine where external network traffic is directed 
- is a set of rules called routes

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
- Failback: The ability to switch back from a redundant component 

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

### NACL (Network Access Control List)
- stateless, becuase you have to have rules to allow request to come in and to allow the response to go back out
- Extra level of security. Is an additional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets.
- work at the network/subnet level

### Ephemeral ports
- short-lived ports
- automatically allocated ports based on the demand
- allow outbound responses to cliet on the internet
- port range 1024 -65535
- can also be called Dynamic Ports


### Internet gateway
- is the point which allow us to connect to Internet/Let's your subnet connect to Internet
- gateway that you attach to your VPC to enable communication between resourcses in your VPC and the internet

### AMI
-  Provides information to launch instance needs to work after security
![image](https://user-images.githubusercontent.com/47173937/116391351-f5b5a080-a816-11eb-9d89-0c4ed7d4daf0.png)



 ![image](https://user-images.githubusercontent.com/47173937/115889962-5b3b1300-a44c-11eb-8b32-54b8ad967f68.png)

### Stateful filtering 
- tracks the origin of a request and can automatically allow the reply to the request to be returned to the originating computer.
- Security groups are stateful. This means that if they allow a request to come in they will always lets the response back out. Even if the outbound rules don't allow it. The outbound rules only apply to request made FROM your machine.
- NACLs are stateless. You have to have rules to allow the request to come in and to allow the response to go back out.



# AWS Task (Two tier architecture deployment):
 **1. Create VPC:**
 - In AWS > VPC > Create VPC
 - VPC Settings: name- ex.:eng84_ula_vpc, ipv4- ex.:(`66.66.0.0/16` - first two numbers supposed to be unique, and then two next are 0s)   
 
 **2. Create Internet Gateway:**
 - In VPC > Internet Gateways > Create Internet Gateway 
 - Internet Gateway Settings: name- ex.: eng84_ula_internet_gateway
 - After that we have to find out gateway from the list, right-click and choose "Attach to VPC"  
 
 **3. Create subnet:**
- VPC > Subnets > Create Subnet
- In Create subnet page we have to specify the name of a subnet ex.: `eng84_ula_public_subnet`, and the IPv4 CIDR block, which has to be slightly different from VPC IPv4 CIDRs, ex.: `66.66.1.0/24` 
The first 2 numbers of this subnet must be the same as VPC's, the third number must be unique, it can't be the same as another subnet you have created. The fourth number must be 0. We have to also use /24.
- Next we have to repeat this step to create private subnet with different IPv4 CIDR block ex.: `66.66.10.0/24`  

 **4. Routing tables:**
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

 ## **5. Now we will create new EC2 instances:**
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
- Go back to the instances list > choose you instance > connect > copy example into git bash
- ### in the app instance: 
- `sudo apt-get update -y`
- `sudo apt-get upgrade -y`
- `sudo apt-get install nginx -y`
-`sudo systemctl status nginx` to check nginx status
- copy code from OS to AWS EC2 app with scp command
- you have to first go into folder with OS (ex.:eng84_dev_env) and use commands below: 
- `scp -i ~/.ssh/your_pem_file -r app/ ubuntu@ip:~/app/` - to copy OS from the other folder
- `scp -i ~/.ssh/pem_file -r ubuntu@ip~/` to copy one file
- `scp -i ~/.ssh/pem_file -r environment/ ubuntu@ip:~/ `
### to fix permision issue for provision file use dos2unix commands:
- `wget "http://ftp.de.debian.org/debian/pool/main/d/dos2unix/dos2unix_6.0.4-1_amd64.deb"`
- `sudo dpkg -i dos2unix_6.0.4-1_amd64.deb`
- `dos2unix provision.sh`
### check if the app is running correctly:
- `cd app`, `npm start` you should see "Your app is listening on port 3000
- if it's not you have to add another seucrity to your app,(custome TCP - 3000 - allow all)
- in web browser: `http://54.155.241.206:3000/` , `http://54.155.241.206/fibonacci/5`

- ### Now we have to create another Instance for database:
- Create new Instance just like we did for the app instance( pages: Step 1 and Step 2 are the same), then on the Step 3 page make sure to set Subnet to your Private subnet
- Pages for Step 4 and 5 exactly the same as for app, only change the tag name to ex.: `eng84_ula_db`
- On the Step 6 page: Security Group Name: ex.: `eng84_ula_private_sg`, SSH the same, but the other one has to be Type: All traffic - Protocol:All - Port:0-65535 - Source:Custom with IP:(your public subnet IPv4) ex.:`66.66.1.0/24` - Description: Access from the public subnet
- ### in the db instance:
- `wget -qO - https://www.mongodb.org/static/pgp/server-3.2.asc | sudo apt-key add -`
- `echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list`
- `sudo apt-get update`
- `sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20`

- `sudo mkdir -p /data/db`
- `sudo chown -R mongodb:mongodb /var/lib/mongodb`
- `sudo sed -i 's/127.0.0.1/0.0.0.0/g' /etc/mongod.conf`
- `sudo systemctl enable mongod`
- `sudo service mongod start`
- add in aws db instnace security group> custom tcp > port:27017

- ### in the app instance: 
- `sudo echo "export DB_HOST=mongodb://privateIPofDB:27017/posts" >> ~/.bashrc` 
- `source ~/.bashrc `
- `cat ~/.bashrc     ` to check 

- `cd app`, `cd seeds`, `node seed.js`
- go back to app and `npm start` to check the `ip/posts` page in web browser search bar
- Next steps are exactly the same as for the app  
- 

 **6. Test the connection:**
 - Now we have to connect to the app
 - Select your App instance > click Connect at the top
 - Copy the Example command which starts with ssh -i
 - Now open a Git Bash Shell and navigate to `~/.ssh` folder using `cd .ssh` command
 - Paste the command you just copied
 - Type Yes when asked a question
 - Now you should be connected to your App(Ubuntu16.04)
 - Inside the Ubuntu APP machine: (`sudo apt-get update -y` and `sudo apt-get upgrade -y`, `sudo apt-get install nginx` to install Nginx, `sudo systemctl status nginx` to check if it was installed)  
 
 - Now let's connect to you database instance, we will have to use proxy ssh
 - From the list of instances choose your App instance and go to Networking 
 - Copy the Public IPv4 address and save it somewhere
 - Next choose you database instance and copy the Private IPv4 address and save it somewhere 
 - Now using those two values(IPs) you can connect to your database
 - `ssh -i ~/.ssh/DevOpsStudent.pem -o ProxyCommand="ssh -i ~/.ssh/DevOpsStudent.pem -W %h:%p ubuntu@app_public_ip" ubuntu@private_ip_of_db` 
 - You should now be connected 
 
 **7. Upate the Database Instance**
 - Firstly we have to give the database access to the internet
 - EC2 > Security Groups > Your Private Security Group Name
 - Inbound Rules > Edit Inbound Rules
 - In the Edit section add new rule
 - Type:HTTP - Source:Custom- IP:0.0.0.0/0 > Save
 - Go to the VPC > Route Tables > Select your Public route table
 - Subnet Addociations > Edit Subnet Associations
 - In the edit section select BOTH subnets and Save
 - Now you should be able to connect to you database instance same as you did with app instance
 - `ssh -i "your_pem_file.pem" ubuntu@db_public_ip`
 - set up all things you need for your db, then change back those settings restart the db instance  

**8. Add NACL:**
- **NACL inbound rules**
- 100 allows inbound HTTP 80 traffic from any IPv4 address
- 110 allows inbound SSH 22 traffic from your netwok over the internet
- 120 allows inbound return traffic from hosts on the internet that are responding to requests origininating in the subnet - TCP 1024 - 65535

- **NACL outbound rules**
- 100 allow on port 80 
- 110 we need the CIDR block(10.0.2.0) and allow 27017 for outbound access to our mongo DB server and private subnet
- 120 allow short lived ports 1024 - 65535

 - private NACL:
 - inbound
 - port 27017 from public subnet
 - ssh from my/your ip



### What is s3:
- simple storage service provided by AWS, at anytime from around the world  it's used to store and retrieve any amount of data, it's store evrything in form of buckets
- we can also host our static website on S3






- we need running EC2 to shh into the instance and AWS access and secret
- Create a bucket from AWSCLI
- upload data
- download data
- delete data
- permissions of the bucket


- in oreder to have AWSCLI we need to install the required dependecies: 
- python
- pip
- configure the AWSCLI with AWS keys to authenticate the access from our machine to s3
- `sudo apt-get install python` to install Python
- `sudo apt-get install awscli` to install AWSCLI
- `aws configure` to configure the s3
- we had to add access key ID and secret access key, then the region and input format(json)
- `aws s3 ls` to check whats available in s3
- `aws s3 mb s3://eng84ulas3 --region eu-west-1` to create the bucket
- `aws s3 cp README.md s3://eng84ulas3 ` to copy readme file to s3
- to add perimssions: go to bucket > choose your bucket > file > permission > edit permissions > allow all and save
- `rm README.md ` to delete a file
- `aws s3 sync s3://eng84ulas3 README.md` to download a file from a bucket
- `aws s3 rm s3://eng84ulas3/README.md` to remove a file
- `aws s3 rb s3://eng84ulas3` to remove a bucket
- `aws s3 rb s3://eng84ulas3 --force` to delete the bucket and everything inside 


