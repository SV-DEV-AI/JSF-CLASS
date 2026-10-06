# OSPF Design Parameters

## General Configuration
- **Protocol:** OSPFv2 (Open Shortest Path First)
- **Process ID:** 1 (Local to router)
- **Area:** 0 (Single-Area OSPF configuration)

## Router IDs
- **R1 (Patna):** 1.1.1.1
- **R2 (Delhi):** 2.2.2.2
- **R3 (Mumbai):** 3.3.3.3

*Router IDs are manually assigned to ensure process stability and easy identification in routing tables (e.g., when viewing `show ip ospf neighbor`).*

## Networks Advertised

### R1 (Patna)
- `10.10.1.0 0.0.0.255 area 0` (Patna LAN)
- `10.0.12.0 0.0.0.3 area 0` (WAN to Delhi)
- `10.0.13.0 0.0.0.3 area 0` (WAN to Mumbai)

### R2 (Delhi)
- `10.10.2.0 0.0.0.255 area 0` (Delhi LAN)
- `10.0.12.0 0.0.0.3 area 0` (WAN to Patna)
- `10.0.23.0 0.0.0.3 area 0` (WAN to Mumbai)

### R3 (Mumbai)
- `10.10.3.0 0.0.0.255 area 0` (Mumbai LAN)
- `10.0.23.0 0.0.0.3 area 0` (WAN to Delhi)
- `10.0.13.0 0.0.0.3 area 0` (WAN to Patna)

## Security and Efficiency
- **Passive Interfaces:** We will configure the LAN interfaces (`Gig0/0`) as `passive-interface` on all routers. This prevents OSPF from sending hello packets onto the LAN segments (improving security and saving bandwidth) while still advertising the LAN subnets to other OSPF routers.
