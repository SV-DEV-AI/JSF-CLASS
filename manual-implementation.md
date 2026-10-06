# Manual Implementation Tracker

**HUMAN OPERATOR / STUDENT INSTRUCTIONS:** 
Please complete these steps exactly as written in Cisco Packet Tracer. 
Mark the `Status` as `DONE` and provide screenshots to me (your AI Agent) when requested so we can move to the next phase.

## Phase 3: Hardware Placement & Connections

| Step | Device/Component | Action | Exact Procedure | Expected Result | Evidence Required | Status |
|---|---|---|---|---|---|---|
| 3.1 | Routers | Place R1, R2, R3 | Drag three **2911 Routers** into the workspace. Name them R1, R2, R3. | Routers placed | None yet | PENDING |
| 3.2 | Router Modules | Add Serial Modules | Turn OFF each router. Drag **HWIC-2T** module into the right slot. Turn ON each router. | Routers have Serial0/0/0 and Serial0/0/1 | None yet | PENDING |
| 3.3 | Switches | Place SW1, SW2, SW3 | Drag three **2960 Switches** into the workspace. Name them SW1, SW2, SW3. | Switches placed | None yet | PENDING |
| 3.4 | End Devices | Place PCs and Server | Drag 1 PC to Patna (ATM-Patna), 1 PC to Delhi (ATM-Delhi), 1 PC to Mumbai (ATM-Mumbai), 1 Server to Delhi (ATM-Server). | End devices placed | None yet | PENDING |
| 3.5 | LAN Cabling | Connect Routers to Switches | Use **Copper Straight-Through** cable. Connect R1 (Gig0/0) to SW1 (Gig0/1). Repeat for R2 (Gig0/0)->SW2, R3 (Gig0/0)->SW3. | Green link lights eventually | None yet | PENDING |
| 3.6 | PC Cabling | Connect PCs to Switches | Connect ATM-Patna (FastEthernet0) to SW1. ATM-Delhi to SW2. ATM-Mumbai to SW3. ATM-Server to SW2. | Green link lights | None yet | PENDING |
| 3.7 | WAN Cabling | Connect R1-R2 | Use **Serial DCE** cable. Connect R1 (Se0/0/0) to R2 (Se0/0/0). (Ensure R1 gets the DCE clock side). | Red links (until no shut) | None yet | PENDING |
| 3.8 | WAN Cabling | Connect R2-R3 | Use **Serial DCE** cable. Connect R2 (Se0/0/1) to R3 (Se0/0/1). (Ensure R2 gets the clock side). | Red links (until no shut) | None yet | PENDING |
| 3.9 | WAN Cabling | Connect R1-R3 | Use **Serial DCE** cable. Connect R3 (Se0/0/0) to R1 (Se0/0/1). (Ensure R3 gets the clock side). | Red links (until no shut) | Screenshot: Complete Topology | PENDING |

## Phase 4: IP Assignment & Configurations

| Step | Device | Action | Exact Procedure | Expected Result | Evidence Required | Status |
|---|---|---|---|---|---|---|
| 4.1 | PC | Configure ATM-Patna | Desktop -> IP Configuration. IP: 10.10.1.10, Mask: 255.255.255.0, Gateway: 10.10.1.1 | IP set | None yet | PENDING |
| 4.2 | PC | Configure ATM-Delhi | Desktop -> IP Configuration. IP: 10.10.2.20, Mask: 255.255.255.0, Gateway: 10.10.2.1 | IP set | None yet | PENDING |
| 4.3 | PC | Configure ATM-Mumbai | Desktop -> IP Configuration. IP: 10.10.3.10, Mask: 255.255.255.0, Gateway: 10.10.3.1 | IP set | None yet | PENDING |
| 4.4 | Server | Configure ATM-Server | Desktop -> IP Configuration. IP: 10.10.2.10, Mask: 255.255.255.0, Gateway: 10.10.2.1 | IP set | None yet | PENDING |
| 4.5 | Router | Configure R1 | Open R1 CLI. Paste contents of `configurations/R1.txt` | No syntax errors, links go green | None yet | PENDING |
| 4.6 | Router | Configure R2 | Open R2 CLI. Paste contents of `configurations/R2.txt` | No syntax errors, links go green | None yet | PENDING |
| 4.7 | Router | Configure R3 | Open R3 CLI. Paste contents of `configurations/R3.txt` | No syntax errors, links go green | Screenshot: R1 `show ip interface brief` | PENDING |

---
**STOP HERE.** Please complete Phases 3 and 4 in Packet Tracer, and provide the two required screenshots (Complete Topology, and `show ip interface brief` on R1). Also, confirm all configurations are applied successfully. 
Once you provide these, I will mark tests T01-T03 as ready to proceed and we will do the verification testing!
