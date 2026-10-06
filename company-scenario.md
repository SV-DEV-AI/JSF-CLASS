# Company Scenario: Bank ATM Network Simulation

## Business Overview
A national bank operates across three major cities: **Patna**, **Delhi**, and **Mumbai**. 
The core banking applications and the centralized ATM Database Server are hosted in the **Delhi** data center. 
Customers accessing ATMs in Patna and Mumbai require highly reliable, low-latency connectivity to the Delhi ATM server to perform transactions.

## Problem Statement
ATMs handle critical financial transactions. A single point of network failure (e.g., a leased line going down) could isolate an entire city's ATM network, leading to service disruption, financial loss, and customer dissatisfaction. A linear topology (Patna-Delhi-Mumbai) is unacceptable as a failure would cut off an entire branch.

## Objectives
1. **High Availability:** Implement a fault-tolerant triangular network topology connecting all three cities.
2. **Dynamic Routing:** Utilize OSPF (Open Shortest Path First) to dynamically manage routing tables and instantly adapt to link state changes.
3. **Failover Capability:** Ensure that if the direct link between any two cities (e.g., Patna to Delhi) fails, the network automatically reroutes traffic through the third city (Mumbai) without manual intervention.
4. **Verification:** Rigorously test and document the failover and recovery process using ICMP and traceroute utilities.
