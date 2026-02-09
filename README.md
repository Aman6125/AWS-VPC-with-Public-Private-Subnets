AWS VPC with Public & Private Subnets (Production-Style)
📌 Project Overview

This project demonstrates a real-world AWS networking architecture using a custom VPC with public and private subnets.
The goal is to securely host private EC2 instances while allowing controlled internet access and private access to Amazon S3.

This setup follows production best practices commonly used in DevOps and Cloud environments.

🏗 Architecture Design

The architecture includes:

One custom VPC

One public subnet

One private subnet

Internet Gateway (IGW)

NAT Gateway

Bastion Host (Public EC2)

Private EC2 instance

S3 Gateway VPC Endpoint

IAM Role for secure access

Private resources are never directly exposed to the internet.

🔁 Traffic Flow Explanation

Internet → Public EC2 via Internet Gateway

Private EC2 → Internet via NAT Gateway (outbound only)

Private EC2 → Amazon S3 via VPC Gateway Endpoint (no internet used)

This ensures security, lower cost, and better performance.

🔐 Security Implementation

Private EC2 has no public IP

SSH access to private EC2 is only via Bastion Host

IAM Role is used instead of access keys

S3 access stays inside AWS network using VPC Endpoint

🧪 Verification & Testing

The following checks were performed:

Public EC2

Public IP assigned ✅

Internet access verified using ping and curl ✅

Private EC2

No public IP assigned ✅

Internet access works via NAT Gateway ✅

S3 access works via IAM Role and VPC Endpoint ✅

🛠 AWS Services Used

Amazon VPC

Amazon EC2

Internet Gateway

NAT Gateway

Amazon S3

VPC Gateway Endpoint

IAM

🎯 Learning Outcomes

Strong understanding of AWS VPC networking

Difference between public and private subnets

NAT Gateway vs Internet Gateway

Bastion Host pattern

Secure S3 access using VPC Endpoint

IAM Role-based authentication
