# AWS VPC Peering | EWB Cloud Lab Project

A hands-on AWS networking project demonstrating private communication between two Amazon Virtual Private Clouds (VPCs) using VPC Peering, route tables, security groups, and EC2 connectivity testing.

## Project Overview

This project implements VPC Peering between two VPCs in the AWS `eu-north-1` (Europe – Stockholm) region. The goal is to enable private communication between App-A and App-B using their private IP addresses, without assigning public IPv4 addresses to the application instances.

## Project Objectives

- Create and configure two separate VPCs.
- Configure public and private subnets according to the project design.
- Deploy a Bastion Host and two application EC2 instances.
- Create and activate a VPC Peering connection.
- Configure routes in the relevant route tables.
- Configure security group rules for SSH and ICMP traffic.
- Test connectivity before and after peering, including controlled failure and recovery.
- Document the architecture, implementation, verification, and cleanup evidence.

## AWS Services and Components

- Amazon VPC
- Amazon EC2
- VPC Peering
- Subnets and route tables
- Internet Gateway
- Security Groups
- SSH, ICMP, and Linux ping utilities

## Network Configuration

| Component | Configuration |
|---|---|
| AWS Region | `eu-north-1` |
| VPC-A | `ewb-vpc-a` — `10.10.0.0/16` |
| VPC-B | `ewb-vpc-b` — `10.20.0.0/16` |
| Public Subnet A | `10.10.1.0/24` |
| Private Subnet A | `10.10.2.0/24` |
| Private Subnet B | `10.20.1.0/24` |
| Bastion Host | `10.10.1.10` private IP |
| App-A | `10.10.2.10` private IP |
| App-B | `10.20.1.10` private IP |
| VPC Peering | `pcx-0f932f23edeec4c44` |

**Note:** The project design does not include a public subnet or Internet Gateway in VPC-B. App-A and App-B are private application instances.

## Architecture

The architecture connects VPC-A and VPC-B through an active VPC Peering connection. The route tables provide routes to the remote VPC CIDR ranges. The Bastion Host provides the SSH jump-host path to App-A and App-B, subject to the configured security group rules.

![AWS VPC Peering Architecture](architecture/EWB_VPC_Peering_Architecture.png)

## Implementation Steps

1. Created VPC-A and VPC-B in `eu-north-1`.
2. Configured the public subnet and private subnet in VPC-A, and the private subnet in VPC-B.
3. Launched the Bastion Host, App-A, and App-B EC2 instances.
4. Created and accepted the VPC Peering connection.
5. Added the required peering routes to the relevant route tables.
6. Configured SSH and ICMP inbound security group rules.
7. Tested connectivity between App-A and App-B.
8. Removed the ICMP Echo Request rule for a controlled failure test, then restored the rule and tested recovery.
9. Checked instance addressing and documented resource cleanup.

## Verification and Testing

The project testing workflow covers these scenarios:

| Test | Expected/recorded purpose |
|---|---|
| Baseline without peering routes | Demonstrate the initial connectivity failure |
| Forward ping: App-A → App-B | Verify connectivity across the peering connection |
| Reverse ping: App-B → App-A | Verify return-direction connectivity |
| Controlled failure | Verify ping failure after removing the relevant ICMP rule |
| Recovery | Verify connectivity after restoring the ICMP rule |

Use the screenshots in this repository and the detailed project report as the evidence for the actual command output and results.

## Project Documentation

- [Architecture Diagram](architecture/EWB_VPC_Peering_Architecture.png)
- [Final Project Report](docs/HimanshuRaj_EWB_VPC_Peering_Final_Report.pdf)
- [View All Screenshots](screenshots/)
  
The file paths above should match the actual names and locations in the repository. If a filename differs, update its link to match the uploaded file.

## Cleanup

The project evidence includes cleanup of the EC2 instances, security groups, route tables, VPC Peering connection, Internet Gateway, subnets, and VPCs.

Confirm the cleanup state against the final AWS Console evidence. Do not recreate resources solely for documentation.

## Key Learnings

- AWS VPC and subnet design
- VPC Peering and CIDR-based routing
- Route table configuration
- Security group rules for SSH and ICMP
- Bastion Host and SSH jump-host access
- Private EC2 connectivity testing
- Controlled failure, recovery, and troubleshooting
- Cloud project documentation and resource cleanup

## Author

**Himanshu Raj**

GitHub: [HimanshuRaj02](https://github.com/HimanshuRaj02)

---

*Completed as a practical AWS cloud networking project.*
