# Test Plan & Test Matrix

| Test ID | Source | Destination | Purpose | Method | Expected Result | Actual Result | Evidence | Pass/Fail | Notes |
|---|---|---|---|---|---|---|---|---|---|
| T01 | Patna PC | Patna Gateway | Local LAN connectivity | ping 10.10.1.1 | PASS | NOT TESTED | PENDING | PENDING | - |
| T02 | Delhi PC | Delhi Gateway | Local LAN connectivity | ping 10.10.2.1 | PASS | NOT TESTED | PENDING | PENDING | - |
| T03 | Mumbai PC | Mumbai Gateway | Local LAN connectivity | ping 10.10.3.1 | PASS | NOT TESTED | PENDING | PENDING | - |
| T04 | Patna PC | ATM Server | End-to-end connectivity | ping 10.10.2.10 | PASS | NOT TESTED | PENDING | PENDING | - |
| T05 | Delhi PC | ATM Server | End-to-end connectivity | ping 10.10.2.10 | PASS | NOT TESTED | PENDING | PENDING | - |
| T06 | Mumbai PC | ATM Server | End-to-end connectivity | ping 10.10.2.10 | PASS | NOT TESTED | PENDING | PENDING | - |
| T07 | R1 (Patna) | OSPF Neighbors | Verify adjacencies | show ip ospf neighbor | Neighbors 2.2.2.2 & 3.3.3.3 FULL | NOT TESTED | PENDING | PENDING | - |
| T08 | R2 (Delhi) | OSPF Neighbors | Verify adjacencies | show ip ospf neighbor | Neighbors 1.1.1.1 & 3.3.3.3 FULL | NOT TESTED | PENDING | PENDING | - |
| T09 | R3 (Mumbai) | OSPF Neighbors | Verify adjacencies | show ip ospf neighbor | Neighbors 1.1.1.1 & 2.2.2.2 FULL | NOT TESTED | PENDING | PENDING | - |
| T10 | R1 (Patna) | Routing Table | Verify OSPF routes learned | show ip route | OSPF routes to 10.10.2.0, 10.10.3.0, 10.0.23.0 | NOT TESTED | PENDING | PENDING | - |
| T11 | Patna PC | ATM Server | Determine initial path | tracert 10.10.2.10 | R1 -> R2 -> Server (expected) | NOT TESTED | PENDING | PENDING | - |
| T12 | R1 (Patna) | Link Failure | Simulate WAN failure | Manually disconnect R1-R2 link | Link goes down | NOT TESTED | PENDING | PENDING | - |
| T13 | R1 (Patna) | OSPF State | Verify failed adjacency removed | show ip ospf neighbor | Neighbor 2.2.2.2 is gone | NOT TESTED | PENDING | PENDING | - |
| T14 | R1 (Patna) | Routing Table | Verify alternate route injected | show ip route | Route to 10.10.2.0 is now via 10.0.13.2 (R3) | NOT TESTED | PENDING | PENDING | - |
| T15 | Patna PC | ATM Server | Verify connectivity during failure | ping 10.10.2.10 | PASS (Traffic rerouted) | NOT TESTED | PENDING | PENDING | - |
| T16 | Patna PC | ATM Server | Determine alternate path | tracert 10.10.2.10 | R1 -> R3 -> R2 -> Server | NOT TESTED | PENDING | PENDING | - |
| T17 | R1 (Patna) | Link Restoration | Restore primary link | Reconnect R1-R2 link | Adjacency to 2.2.2.2 forms | NOT TESTED | PENDING | PENDING | - |
| T18 | Patna PC | ATM Server | Final connectivity check | ping 10.10.2.10 | PASS | NOT TESTED | PENDING | PENDING | - |
