AWS 3-Tier Web Application Infrastructure
Overview
This project demonstrates the deployment of a scalable and cost-optimized 3-tier web architecture on AWS, manually built using the AWS Management Console. The solution provides high availability, security, and optimal resource usage for dynamic web applications.​

Architecture Components
VPC: Custom Virtual Private Cloud for isolation

Subnets: 2 Public (Web tier) and 4 Private (App & DB tiers) subnets across multiple Availability Zones

Load Balancer: Application Load Balancer (ALB) for distributing traffic to web/application servers

Auto Scaling Groups: Automatically scale EC2 instances up/down in web and application tiers based on demand

Database: Amazon RDS instance deployed in private subnets (multi-AZ for resilience)

Session Manager: Secure shell access to EC2 instances without NAT gateway or bastion host

Security Groups: Tier-specific security groups regulating traffic between layers

Features
Highly Available: Resources span two availability zones for fault tolerance

Cost Optimized: NAT gateways removed; Session Manager enables secure instance access

Automated Scaling: Resource groups (web & app tiers) adjust to traffic load

Secure Networking: Database isolated within private subnet; no public access

Manual Deployment: All resources created, configured, and managed through AWS Console

Prerequisites
AWS account with administrator permissions

Basic AWS Console experience

Steps to Deploy
VPC & Subnets

Create a custom VPC and 6 subnets (2 public for web, 4 private for app and DB tiers)

Assign subnets to different availability zones for high availability

Internet Gateway

Attach an Internet Gateway to VPC

Configure route tables for public subnets to allow web traffic

Security Groups

Define tier-specific security groups with strict inbound/outbound rules

Load Balancer & Auto Scaling Groups

Create an Application Load Balancer (ALB) for public-facing access

Set up Auto Scaling Groups for both web and app tiers

Database Deployment

Launch Amazon RDS in private subnets

Configure DB security group for access from application tier only

Session Manager Configuration

Enable AWS Systems Manager for EC2 instances

Access private instances without NAT gateway or bastion host

Cost Optimization

Remove NAT gateways

Use Session Manager for maintenance and troubleshooting

Cleanup

Manually delete all resources when decommissioning the environment

Customization
Network CIDR blocks, subnet sizes, instance types, and DB configurations can be tailored during setup.

Additional AWS services (e.g., monitoring, S3 storage) can be added.

Skills & Tools Demonstrated
AWS Cloud Networking (VPC, Subnets, Security Groups)

EC2, Load Balancer, Auto Scaling, RDS setup

Cost Optimization strategies

Secure access and role-based permissions

Manual cloud resource management

Author
Atharv [or your preferred name]

Contributing
Suggestions, improvements, or questions are welcome. Please raise an issue or submit a pull request.