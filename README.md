# NoCSim
## Felicia Liu, Ying Meng

## URL
(Add URL Here)

## Summary
This project implements a Network-on-Chip (NoC) simulator for parallel architectures. The performance and scalability of different NoC topologies, including bus, crossbar, ring, and mesh, are studied under different workloads.

## Background
In modern computer architecture, routers are growing in importance due to the multi-core and heterogeneous nature of modern processors, making more and more applications memory-bound. Efficient router architecture that caters to different use cases must be built to facilitate cross-core communication and data coherence. Routers can be evaluated in terms of multiple aspects such as latency, bandwidth, contention management, scalability, and cost. Simulating different router topologies can provide us insights into which one to use under various constraints to achieve better overall performance.

The simplest interconnect topology is a bus. It is highly cost-effective since all nodes share one bus wire. It usually uses a snooping protocol to maintain coherence across nodes. However, it performs poorly at high contention due to limited bandwidth.

To resolve high contention, a crossbar interconnect is introduced. With every node directly connecting with all the other nodes through switches, crossbar has O(1) latency and high bandwidth. However, it has a much higher cost of O(N^2) and is difficult to arbitrate at scale.

Other topologies that balance cost and effective bandwidth include ring and mesh. Ring interconnect connects a node with its two neighbors and forms a circular path. This results in O(N) cost and O(N) latency. Mesh connects all nodes in a square topology, with N number of nodes per row and column, which leads to O(N) cost and O(N) latency.

## Challenge
In order to correctly simulate how different router topologies behave in hardware, we need to come up with quantitative specifications for evaluating latency, bandwidth, contention management, scalability, and cost. We need to simulate the routers in edge cases such as high senders/receivers contention and have the router run real-world workloads to simulate how they behave under common conditions. Interfacing our simulated router topologies with real-world workloads may require parsing existing traces and comparing performance with existing designs.

## Resources/Platform Choice
We will construct our simulation based on Gem5, an open-source computer architecture simulator. In this framework, C++ is used to build core simulation infrastructure and Python is used for configuration and scripting.

## Goals and Deliverables
We plan to generate performance graphs from our simulation results that can verify the expected characteristics of the basic topologies mentioned above. We also plan to identify the most suitable topology for each workload tested.

If we have more time, we hope to simulate with more granularity and generate performance graphs for different types of flow control, and potentially come up with a custom topology and analyze its behavior.

The key focus of this project is understanding the impacts of topology on router latency, throughput, and scalability, as well as optimizing router and link parameters to balance performance with other constraints. The results will help identify the best topology for specific workload demands and achieve resource-efficient design choices.

## Schedule
- **11.11 - 11.17:** Investigate Gem5 infrastructure and build a basic simulation structure
- **11.18 - 11.24:** Build all topologies, write test cases, and run performance testing
- **11.25 - 12.1:** Interface with workload and optimize configuration, write milestone report
- **12.2 - 12.8:** Implement any feedback, finalize simulation configuration
- **12.9 - 12.13:** Graph simulation results, prepare for demo
