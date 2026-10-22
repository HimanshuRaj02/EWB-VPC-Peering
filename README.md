# AWS VPC Peering | EWB Cloud Lab Project

A hands-on AWS networking project demonstrating VPC Peering between two Amazon Virtual Private Clouds (VPCs) to enable private communication between resources in separate VPC networks.

## Project Overview

This project focuses on configuring VPC Peering, updating route tables, and validating private connectivity between resources deployed in two VPCs.

## Objectives

- Create and configure two separate VPCs.
- Configure VPC Peering between the VPCs.
- Update route tables to enable communication between private network ranges.
- Configure security rules required for connectivity.
- Test and document network connectivity.
- Document the architecture, configuration, and verification process.

## AWS Services Used

- Amazon VPC
- Amazon EC2
- VPC Peering
- Route Tables
- Security Groups

## Architecture

The architecture consists of two VPCs connected through a VPC Peering connection. Route tables direct traffic between the respective VPC CIDR ranges, while security rules control permitted communication.

<!-- Add the verified architecture diagram here. -->

## Implementation Steps

1. Configure the first VPC and its network resources.
2. Configure the second VPC and its network resources.
3. Create and accept the VPC Peering connection.
4. Update the route tables on both sides.
5. Verify the required security group rules.
6. Test connectivity between the EC2 instances.
7. Capture evidence and document the results.

## Verification and Testing

Connectivity was tested between the resources in the two VPCs. Refer to the project report and screenshots for the configuration details and recorded test results.

> Add only the test results confirmed by your actual screenshots and project evidence.

## Project Documentation

The detailed project report, architecture diagram, and implementation screenshots will be maintained in this repository.

## Cleanup

AWS resources should be checked in the AWS Console after testing to confirm their current status and avoid unexpected charges.

## Key Learnings

- AWS VPC networking fundamentals
- VPC Peering configuration
- Route table configuration and traffic routing
- Security group rules
- EC2 connectivity testing
- AWS networking documentation and troubleshooting

## Author

**Himanshu Raj**

GitHub: [HimanshuRaj02](https://github.com/HimanshuRaj02)

---

*Project completed as a practical AWS cloud networking exercise.*
