# Requirements

## 1. Primary Technical Objective
Build a fault-tolerant three-city bank network for Experiment 6 using a triangular router topology.

## 2. Specific Network Requirements
- **Locations**: Patna, Delhi, Mumbai.
- **Topology**: Triangle (R1-R2, R2-R3, R1-R3) to guarantee redundant paths.
- **Dynamic Routing**: OSPF Area 0.
- **Failover**: Traffic must automatically switch to an alternate route if the primary link (e.g., Patna-Delhi) fails.

## 3. Required End Devices
- Representative ATM terminals (PCs) at each location.
- ATM/Application Server located in Delhi.

## 4. Verification Requirements
- Ping and traceroute testing for normal connectivity.
- Deliberate link failure (cable disconnect) to observe OSPF reconvergence.
- Post-failure ping and traceroute testing to verify alternate route.
- Link restoration testing.

## 5. Documentation Requirements
- Complete 20-25 page report following exact teacher sequence.
- 30 Viva questions.
- 7-minute Teacher Demonstration script.
- Actual screenshots and observed results (no fabricated output).
