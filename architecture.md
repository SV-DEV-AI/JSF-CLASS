# Architecture

## Logical Architecture
The architecture is based on a robust, fault-tolerant triangle topology interconnecting three regional routing hubs using point-to-point `/30` WAN links.

- **Hub 1: Patna (R1)**
- **Hub 2: Delhi (R2) [Data Center]**
- **Hub 3: Mumbai (R3)**

### Core Components
1. **Routing Layer:** Three Cisco Routers (e.g., 2911 or 4331) running OSPFv2 in Area 0.
2. **Access Layer:** Three Cisco Switches (e.g., 2960) providing connectivity to end devices in each location.
3. **End Devices:** Representative ATM PCs in each branch and the centralized ATM Server in Delhi.

## Redundant Routing Design
By connecting all three routers together (R1-R2, R2-R3, R1-R3), we establish multiple paths to the ATM server in Delhi.
- **Primary Path (Patna to Server):** Patna PC -> SW1 -> R1 -> R2 -> SW2 -> ATM Server.
- **Secondary Path (Patna to Server):** Patna PC -> SW1 -> R1 -> R3 -> R2 -> SW2 -> ATM Server.

OSPF will calculate the lowest cost path for normal traffic. Upon a link failure (e.g., the Serial link between R1 and R2 goes down), OSPF will detect the dead interval or link state change, recalculate the Shortest Path First (SPF) tree, and immediately inject the alternate path (via R3) into the routing table.

## IP Addressing Strategy
- **LANs:** Standard `/24` subnets (10.10.x.0/24) for local device scalability.
- **WANs:** Strict `/30` point-to-point subnets (10.0.x.0/30) to conserve IP space and restrict broadcast domains.
- **OSPF Router IDs:** Loopback-style arbitrary IPv4 addresses (1.1.1.1, 2.2.2.2) for stable OSPF process identification.
