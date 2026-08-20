# IP Addressing Plan

## 1. Overview

This document defines the IP addressing strategy for the Secure AWS Enterprise Network Projects.

The Network uses separate private address spaces for the simulated on-premise enterprise network and the AWS cloud environment.

| Environment | Address Space | Purpose |
| --- |--- |--- |
| On-Premises | `192.168.0.0/16` | Enterprise LAN and VLANs |
| AWS | `10.20.0.0/16` | Cloud infrastructure |

The address spaces do not overlap, allowing the environment to support routed connectivity in a future hybrid network implementation.

--- 

## 2. On-Premise Addressing

The on-premises environment is divided into VLANs based on organizational funtion and security requirements.

| VLAN ID | Name | Subnet | Default Gateway | Purpose |
|---:|---|---|---|---|
| 10 | Management | `192.168.10.0/24` | `192.168.10.1` | Network infrastructure management |
| 20 | Administration | `192.168.20.0/24` | `192.168.20.1` | Administrative users |
| 30 | Engineering | `192.168.30.0/24` | `192.168.30.1` | Engineering users |
| 40 | Finance | `192.168.40.0/24` | `192.168.40.1` | Finance users |
| 50 | Servers | `192.168.50.0/24` | `192.168.50.1` | Internal servers and services |
| 60 | Guest | `192.168.60.0/24` | `192.168.60.1` | Isolated guest devices |

---

## 3. AWS Addressing

The AWS environment uses the private `10.20.0.0/16` address space.

| Network | CIDR | Purpose |
|---|---|---|
| AWS VPC | `10.20.0.0/16` | Main AWS network |
| Public Subnet | `10.20.1.0/24` | Internet-facing resources |
| Private Subnet | `10.20.10.0/24` | Internal cloud resources |

### Public Subnet

The public subnet uses:

`10.20.1.0/24`

Resources placed in this subnet may use a route to an Internet Gateway when public connectivity is required.

### Private Subnet

The private subnet uses:

`10.20.10.0/24`

Resources placed in this subnet will not have direct inbound connectivity from the public internet.

---

## 4. Address Separation

The on-premises and AWS environments intentionally use different, non-overlapping private IP ranges.

```text
On-Premises
192.168.0.0/16

AWS
10.20.0.0/16
```

This separation simplifies routing and allows the architecture to support future hybrid connectivity without overlapping address-space conflicts.

---

## 5. Security Considerations

Network addressing is aligned with the project's segmentation strategy.

Separate subnets and VLANs provide boundaries between:

- Management systems
- Administrative users
- Engineering users
- Finance users
- Internal servers
- Guest devices
- Public AWS resources
- Private AWS resources

Network segmentation alone does not enforce security. Access between these networks will be controlled using technologies such as:

- Access Control Lists (ACLs) in the simulated enterprise network
- AWS Security Groups
- AWS Network ACLs where appropriate
- Routing policies
- Identity and access controls

---

## 6. Future Expansion

The addressing plan reserves sufficient address space for future network segments.

Possible future additions include:

- Additional AWS Availability Zones
- Additional private subnets
- Database subnets
- Dedicated security or monitoring networks
- Additional enterprise VLANs
- Hybrid network connectivity