# AWS VPC — Infrastructure as Code (Terraform)

## Overview
Provisioned a VPC on AWS using Terraform, including public and private subnets, 
an internet gateway, and route tables. Built as part of an AWS Solutions Architect portfolio.

## Architecture
- VPC: 10.0.0.0/16
- Public Subnet: 10.0.1.0/24 — internet-facing, auto-assigns public IPs
- Private Subnet: 10.0.2.0/24 — internal only, no direct internet access
- Internet Gateway: attached to VPC, routes public traffic out
- Route Table: directs 0.0.0.0/0 traffic from public subnet through the IGW

## Prerequisites
- Terraform >= 1.5.0
- AWS CLI configured with valid credentials
- IAM user with VPC permissions

## Usage
```bash
terraform init
terraform plan
terraform apply
terraform destroy   # clean up all resources when done
```

## What I Learned
- How Terraform state tracks real infrastructure
- CIDR block planning — splitting a /16 VPC into /24 subnets
- The difference between public and private subnet routing
- Why the Internet Gateway + Route Table association is what makes a subnet truly public
- Tagging strategy for environment and cost tracking

## Project Status
Complete.
