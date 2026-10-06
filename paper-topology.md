# Paper Topology / Initial Design

The paper topology establishes the visual blueprint of our network before we move to Packet Tracer.

## ASCII Diagram

```text
                                 [ATM Server]
                                10.10.2.10/24
                                      |
                                  (SW2 Delhi)
                                      |
                                  [R2 Delhi]
                                 OSPF 2.2.2.2
                                 /          \
            10.0.12.0/30        /            \       10.0.23.0/30
            (Primary Route)    /              \     (Redundant Route)
                              /                \
                             /                  \
                            /                    \
                     [R1 Patna]----------------[R3 Mumbai]
                    OSPF 1.1.1.1               OSPF 3.3.3.3
                         |                      |
                    (SW1 Patna)            (SW3 Mumbai)
                         |                      |
                  [ATM PC Patna]          [ATM PC Mumbai]
                  10.10.1.10/24           10.10.3.10/24
                                                
                           |---- 10.0.13.0/30 ----|
                              (Redundant Route)
```

## Interface Mappings (Packet Tracer Planning)
*Note: Interfaces (e.g., Gig0/0 or Se0/0/0) will be finalized once specific router hardware (like the 2911 or 4331 series) is selected in Packet Tracer.*

- **R1 (Patna)**
  - LAN: Gig0/0 (or similar) -> 10.10.1.1
  - WAN to R2: Se0/0/0 (or similar) -> 10.0.12.1
  - WAN to R3: Se0/0/1 (or similar) -> 10.0.13.1

- **R2 (Delhi)**
  - LAN: Gig0/0 (or similar) -> 10.10.2.1
  - WAN to R1: Se0/0/0 (or similar) -> 10.0.12.2
  - WAN to R3: Se0/0/1 (or similar) -> 10.0.23.1

- **R3 (Mumbai)**
  - LAN: Gig0/0 (or similar) -> 10.10.3.1
  - WAN to R2: Se0/0/1 (or similar) -> 10.0.23.2
  - WAN to R1: Se0/0/0 (or similar) -> 10.0.13.2

## Redundancy Explanation
The triangle shape guarantees that if the `10.0.12.0/30` link between R1 and R2 is physically disconnected, R1 can still reach the ATM Server by routing traffic through R3 (over `10.0.13.0/30` and `10.0.23.0/30`).
