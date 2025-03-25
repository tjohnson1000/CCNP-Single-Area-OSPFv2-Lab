# Cisco Single-Area OSPFv2 Lab

## Overview
This project is a practical lab focused on configuring and verifying **Single-Area OSPFv2** on Cisco routers. The lab walks through foundational routing configuration using **R1, R2, and R3**, emphasizing OSPF concepts, optimization, and verifying DR/BDR roles and neighbor adjacencies.

## Lab Topology
- **Routers:** R1, R2, R3
- **Switch:** DS-1 (for VLAN access)
- **Loopback Interfaces** simulate internal subnets

## Objectives
1. Configure basic router and switch settings
2. Enable Single-Area OSPFv2 with various configuration styles:
   - Interface-specific (R1)
   - Explicit IP addresses (R2)
   - Wildcard masks (R3)
3. Advertise and verify a default route
4. Optimize OSPF behavior with:
   - Passive interfaces
   - Adjusted hello/dead timers
   - Reference bandwidth tuning
5. Configure and validate DR/BDR roles

## Key Configuration Highlights
- R1 advertises a default route (`default-information originate`) via a loopback interface.
- Passive interfaces are used to prevent unnecessary OSPF updates.
- DR/BDR priority is managed to ensure specific role assignments:
  - R1 → DR (priority 255)
  - R2 → BDR (default priority)
  - R3 → DROTHER (priority 0)

## Verification Commands
```bash
show ip protocols | section ospf
show ip route ospf
show ip ospf interface brief
show ip ospf neighbor
show ip ospf interface g0/0 | include Timer
```

## Repository Structure
```
├── configs/
│   ├── R1_Config.txt
│   ├── R2_Config.txt
│   ├── R3_Config.txt
├── README.md
├── screenshots/
└── topology.png
```

## Conclusion
This lab reinforces CCNP-level knowledge in **OSPFv2 routing**, from base setup to optimization and neighbor state verification. It’s ideal for networking professionals preparing for real-world deployments or Cisco certifications.

---
**Author:** Travis Johnson  
**Company:** 10Digit Solutions LLC  
**GitHub Repository:** [Add link when available]
