# Project Report: Deploying an Apache Web Server on AWS with Custom VPC Configuration  
## Executive Summary
This report details the implementation of an Apache Web Server deployment on AWS within a custom Virtual Private Cloud (VPC). The project was meticulously documented using GitHub to ensure transparency and version control. The tasks involved configuring a secure and scalable cloud infrastructure, launching an EC2 instance, and setting up a web server. Each step demonstrated proficiency in cloud resource management, networking, and software deployment.  

## Introduction  
The primary objective of this project was to design and deploy a scalable web application environment on AWS. It involved:  
1. Setting up version control using GitHub for documentation and collaboration.  
2. Configuring a custom VPC with subnets, an Internet Gateway, and security policies.  
3. Launching an EC2 instance and installing Apache Web Server.  
This report outlines the implementation process, key configurations, and final outcomes.  

## Project Objectives  
1. Utilize GitHub for collaborative documentation and version control.  
2. Create a custom VPC to manage networking and resource allocation.  
3. Deploy and configure an EC2 instance with Apache Web Server.
   
## Implementation Details  
## 1.0 Setting Up GitHub for Documentation and Version Control
### 1.1 GitHub Account Creation  
-Registered a GitHub account using a professional username (‘ayoolakehinde92@gmail.com and onabusola’).
-![Github sign up page](https://github.com/user-attachments/assets/3591864b-b89c-4fdd-a9ac-0349e4caafe9)
### 1.2 Git Installation and Configuration 
- Installed Git locally from [GitHub Desktop](https://github.com/apps/desktop/).   
### 1.3 Repository Creation and Cloning  
- Created a new public repository named ‘AWS-Web-Application’.  
- Initialized the repository with a ‘onabusola/README.md’ file.  
- and commit to save changes on the repository
- and keep adding my file
![github readme md](https://github.com/user-attachments/assets/b41d534a-6d3f-4c13-a911-1e814a0370b0)
## 2.0 Configuring a Custom VPC
### 2.1 VPC Creation 
-I used the created VPC named ‘Lita_project-vpc’ with CIDR block ‘10.0.0.0/16’.
![vpc creation](https://github.com/user-attachments/assets/2d2604f2-e40c-4a0e-a54f-874237cb7d54)
![vpc creation2](https://github.com/user-attachments/assets/5c1be980-4b4f-4819-a2fe-c4a201ddfb12)
![vpc creation3](https://github.com/user-attachments/assets/728db19d-ff01-44c1-94e4-2c8e6a0c3caa)  
### 2.2 Subnets Configuration 
- two subnets  was created:  
- Public Subnet: CIDR block ‘10.0.1.0/24’.  Using subnet-0ecd659b88e6ad1d3 (Lita_project-subnet-public1-eu-west-1 
- Private Subnet: CIDR block ‘10.0.2.0/24’.  
### 2.3 Internet Gateway and Route Table
- Created and attached an Internet Gateway to ‘Lita_project’.  
- Configured the route table for the public subnet to allow internet access (‘0.0.0.0/0’).  
### 2.4 Network Access Control Lists (NACLs)  
-Configured NACLs to allow HTTP (port 80) and SSH (port 22) traffic for the public subnet.  
### 2.5 Security Groups
-I created a Security Group to:  
- allow HTTP traffic (port 80) from all IP addresses.  
 -allow SSH traffic (port 22) to all IP address.  
### 2.6 security group
i Created a name for my security group and allowed SSH and HTTP traffic
![security group inbound rule](https://github.com/user-attachments/assets/6dd2272c-c4a7-4dbf-b7c0-8aa75da1cf33)
![Security group](https://github.com/user-attachments/assets/afc21fa3-feac-43d3-9da8-0d1daa7c3ac1)
![Security group creation](https://github.com/user-attachments/assets/c87b3220-c6c8-47e5-8de4-ddae18989501)
Security group created successfully
![security group created](https://github.com/user-attachments/assets/e4651457-1adf-4fa9-8e45-62fb46fcdbf4)
## 3.0 Launching an EC2 Instance and Deploying Apache
### 3.1 EC2 Instance Launch 
Launched an EC2 instance named ‘kehindeayoola_lita’ with the following configurations:  
- AMI: Amazon Linux 2.
![amazon linus 2 under instance selected](https://github.com/user-attachments/assets/6711b932-522b-46d3-a561-fdfbddac970a)
- Instance Type:t2. micro.  
- Key Pair: I Created and downloaded security key as ‘kehindeayoolaona_litakp’.
![key pair  instance](https://github.com/user-attachments/assets/85ab36b7-e602-4d62-b479-179038e7cb4b) 
 Networking:
- Associated the instance with ‘kehindeayoola_lita’ and the Lita project public subnet.  
- Enabled auto-assign Public IP.  
- Attached the previously created Security Group.
![Ec2 creation](https://github.com/user-attachments/assets/0f7a10e0-7d32-4c55-b8bf-eef9e77ebb71)   
The diagrams showing the process involved in launching EC2 instance ;
![Amazon linus 2 under instance](https://github.com/user-attachments/assets/ebaaf521-98d1-4a5c-adec-838625b3785c)
![amazon linus 2 under instance selected](https://github.com/user-attachments/assets/7c94f8ee-1bea-4273-b6f2-872e5ef7b237)
![key pair  instance](https://github.com/user-attachments/assets/9d516a6d-a911-427b-b454-4688b9a52b6d)
![subnet](https://github.com/user-attachments/assets/6af18b9a-28a1-4992-baf3-c46926f0e19b)
![instance launch](https://github.com/user-attachments/assets/507e627d-3e4c-4846-ac60-c3c8ffd8fc88)
![instance launched](https://github.com/user-attachments/assets/22d03389-428e-4200-a87a-fc1c8e77a032)
![instance successfully launched](https://github.com/user-attachments/assets/0629f6c4-c9ba-4c0d-9901-e9774e0c87bd) 
![Ec2 creation](https://github.com/user-attachments/assets/8b860061-78a5-4c2e-bd92-d212ddc99b16)
![security group inbound rule](https://github.com/user-attachments/assets/b1a52c3e-d74d-47f9-a972-bd57f893e3b3)
![instance creation](https://github.com/user-attachments/assets/624dce89-e6f0-4116-874b-355d1bd5928b)
### 3.2 Apache Web Server Installation  
i accessed the instance via SSH client and installed and enabled Apache using; 
  Sudo yum update -y  
  Sudo yum install httpd -y  
  Sudo systemctl start httpd
  Sudo systemctl enable httpd 
I accessed the instance via SSH client
![connect to instance](https://github.com/user-attachments/assets/e56d3794-995d-4054-9f39-34e8a400118b)
I Installed and enabled Apache  
![apache installed](https://github.com/user-attachments/assets/b85231a0-f3ff-4e8d-a323-1772898b91ad)    
### 3.3 Verification 
-	Verified the Apache installation by entering the public IP  3.249.142.168 of the instance in a web browser.  
![apache installed](https://github.com/user-attachments/assets/ec33403b-0144-4ea1-adab-15a3ad7aaefb)
I verified that Apache has been installed
## 4.0 Documenting and Pushing Final Results to GitHub 
### 4.1 Documentation Updates
- Updated ‘README.md’ with:  
- Detailed project description.  
- Screenshots of key configurations and outputs.   
 - Committed and pushed final updates to GitHub
![github readme md](https://github.com/user-attachments/assets/3d6d241c-ac81-46c9-8d87-40ea5b438c79)
## 5.0 Challenges and Lessons Learned  
### Challenges:  
  - Configuring the network for secure yet functional access.  
  - Ensuring all dependencies were installed correctly for Apache.  

### Lessons Learned:
  - Gained practical experience with GitHub for version control and documentation.  
  - Acquired foundational skills in AWS networking, resource allocation, and instance management.  

## 6.0 Conclusion
The project was successfully completed, demonstrating proficiency in configuring cloud infrastructure, deploying web services, and maintaining detailed project documentation. The deployed Apache Web Server is fully functional and accessible. The documentation is available on GitHub for review and further improvement.  



