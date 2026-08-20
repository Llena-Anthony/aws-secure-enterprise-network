# Enterprise Network Requirement

## 1. Project Scenario

This project simulates the network infastructure of a small technology companyu using both an on-premise network and Amazon Web Services (AWS).

## 2. Organization

The organization consists of:

- Administration
- Finance
- Engineering
- IT
- Guest users

## 3. Network requirements

The network must:

- Separate departments using logical network segmentations.
- Provide dedciated network segments for management, employees, serveres, and guests.
- Allow communication only between authorized network segments.
- Restrict unnecessary access to sensitive network and systems.
- Use a structured IP addressing and subnetting scheme.
- Provide DHCP services for clients devices where appropriate.
- Provide DNS functionality
- Provide internet connectivity where required.
- Maintain separate IP address spaces for the on-premise and AWS environment

## 4. On-Premise Network Requirements

The simulated on-premises environment must provide:

- VLAN-based network segmentation
- Inter-VLAN routing.
- Separate VLAN for different organizational functions.
- DHCP for client devices.
- DNS services.
- Access Control Lists (ACLs) for traffic restrictions.
- A dedicated management network.
- A dedicated server network.
- An isolated guest network.
- Appropriate switching and routing infrastructure.

## 5. AWS Network Requirements

The AWS environment must provide: 

- A custom Amazon VPC.
- Public and private subnets.
- An Internet Gateway for public resources.
- Separate route tables for public and private networks.
- Security groups that permit only required traffic.
- A public EC2 instance for controlled internet-facing services.
- A private EC2 instance without direct public internet exposure.
- Controlled communication between public and private workloads.

## 6. Security Requirements

The environment must:

- Follow the principle of least privilege.
- Minimize unnecessary public exposure.
- Restrict administrative access.
- Isolate guests users from internal resources.
- Protect sensitve network segments. 
- Use IAM roles and policies for AWS access control.
- Maintain logs of relevant AWS activity.
- Monitor cloud resources for security-related events.
- Support investigation and remediation of controlled security misconfiguration.

## 7. Security Monitoring Requirements

The AWS environment will use security and monitoring capabiliities including:

- AWS CloudTrail for API and account activity auditing.
- Amazon CloudWatch for monitoring and logging.
- Amazon GuardDuty for threat detection.

Security events and configuration issues identified during the project will be documented and investigated.

## 8. Project Constraints

- The environment is designed for educational and portfolio purposes.
- The security testing will only be performed against resources owned and controlled by the project author.
- AWS resoures should be selected and terminated when appropriate to minimize unnecessary costs.
- The Packet Tracer environment represents the simulated on-premises infrastructure.
- The cononection between the Packet Tracer environment and AWS may initially be represebted conceptually rather than as a production site-to-site connection.

## 9. Success Criteria

The project will be considered when:

- Department networks are corretly segmented.
- Authorized network communication succeeds.
- Unauthorized network communication is blocked.
- Public AWS resources are reachable only through explicitly permitted traffic.
- Private AWS resources are not directly exposed to the public internet.
- AWS access follows defined IAM permissions
- Logging and monitoring provide visibility into relevant AWS activity.
- Controlled secutiy misconfigurations can be identified, documented, remediated, and verified.
- The final architecture and implementation are documented in the project repository.