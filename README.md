# ansible-aws-vpc
# AWS VPC Automation using Ansible

## Project Overview

This project demonstrates Infrastructure Automation on AWS using Ansible.  
The AWS networking environment is created using Ansible playbooks following Infrastructure as Code (IaC) principles.

The automation provisions a production-style AWS setup including a custom VPC, public and private subnets, routing components, and EC2 instances accessed through a Bastion Host.

---

## Architecture

Internet  
│  
Internet Gateway  
│  
Public Subnets  
│  
Bastion Host  
│  
NAT Gateway  
│  
Private Subnets  
│  
Private EC2 Instances  

---

## Technologies Used

AWS EC2  
AWS VPC  
Ansible  
AWS CLI  
Python Boto3  
Git and GitHub  
Ubuntu Linux  

---


---

## Environment Setup

1. Launch an Ubuntu EC2 instance to act as the Ansible control node.
2. Install Ansible and AWS CLI.
3. Attach IAM Role with required permissions.
4. Install Python boto and boto3 libraries.
5. Clone the GitHub repository on the Ansible server.

---

## VPC Deployment

Run the following command to create networking infrastructure:
## ansible-playbook vpc_setup.yml

Resources created:

- Custom VPC
- Public Subnets
- Private Subnets
- Internet Gateway
- Route Tables
- NAT Gateways

---

## Bastion Host Deployment

Run the following command:
ansible-playbook bastion-host.yml

Resources created:

- Bastion Host in Public Subnet
- EC2 instance in Private Subnet 1
- EC2 instance in Private Subnet 3

---

## Bastion Access Model

The Bastion Host allows secure SSH access to instances located inside private subnets.  
Private instances are not directly exposed to the internet and outbound internet connectivity is provided through NAT Gateway.

---

## Learning Outcomes

- Infrastructure as Code implementation using Ansible
- AWS VPC and subnet architecture design
- Multi Availability Zone deployment
- Secure access using Bastion Host
- AWS automation using playbooks
- Dependency-based infrastructure provisioning

---

## Cleanup Procedure

To avoid AWS charges, delete all created resources after testing.

1. Terminate all EC2 instances
2. Delete NAT Gateways
3. Release Elastic IP addresses
4. Delete Route Tables
5. Detach and delete Internet Gateway
6. Delete Subnets
7. Delete VPC

---

## Author

AWS Infrastructure Automation Project using Ansible
