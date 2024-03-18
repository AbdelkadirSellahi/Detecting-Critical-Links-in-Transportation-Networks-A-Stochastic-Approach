# Critical Links Detection in Stochastic Networks: Application to Transportation Networks

## Introduction
Natural disasters, including floods and earthquakes, pose significant challenges to emergency management systems, often leading to chaotic situations where quick and effective response is crucial to minimize the impact on human lives. One critical aspect of emergency management is the efficient evacuation of injured individuals from disaster sites to medical facilities for urgent treatment. To address this challenge, this project aims to simulate the evacuation process in disaster situations, leveraging concepts from Markov Decision Processes (MDPs) to model ambulance routing while considering real-time updates such as road congestion and disruptions.

In particular, the project focuses on identifying critical links in stochastic transportation networks to enhance network resilience and mitigate the impact of disruptions. By employing probabilistic analysis techniques, the algorithm identifies the most crucial links in the transportation network that, if disrupted, would have the most significant impact on network performance. This approach enables efficient resource allocation and risk management, ultimately contributing to more effective emergency response and reduced human casualties during disasters.

## Solution Overview

The solution employs a probabilistic analysis approach to identify critical links in transportation networks. 

By simulating different scenarios and evaluating the impact of disruptions, the algorithm identifies the most critical links that, if disrupted, would have the most significant impact on network performance, optimizing ambulance routing in real-time. 

This approach allows for a more responsive and efficient disaster response strategy, potentially saving lives by reducing the time to treatment.

## Features

- **Dynamic Traffic Simulation:** Models traffic congestion dynamically, affecting evacuation route choices.
- **Hospital Capacity Management:** Simulates hospital capacities, rerouting ambulances as hospitals reach capacity.
- **Critical Path Analysis:** Identifies and analyzes the impact of critical roads on the evacuation process, including simulations of road disruptions.
- **Stochastic Modeling:** Uses Markovian Decision Processes to simulate the uncertainty in travel times due to varying traffic conditions.

## Configuration Table

The simulation can be customized according to various parameters detailed in the table below. These settings allow users to tailor the simulation to different scenarios, network conditions, and objectives.

| Parameter | Description | Default Value | Notes |
|-----------|-------------|---------------|-------|
| `Graph Data File` | Path to the `.gml` file containing the network graph. | `Siouxfallcri.gml` | Ensure the file format is supported. |
| `Disaster Sites` | Node IDs representing the locations of disasters. | `[n1]` | Can be a list of multiple nodes. |
| `Hospital Nodes` | Node IDs designated as hospitals. | `['n7', 'n9', 'n22']` | Adjust based on the network graph. |
| `Congestion Levels` | Specifies how road congestion is modeled. | Dynamic | Can be static or dynamic. |
| `Hospital Capacities` | Maximum capacity for each hospital node. | 100 | Can vary between hospitals. |
| `Simulation Rounds` | Number of simulations to run for evaluating network resilience. | 1 | Increase for more thorough analysis. |
| `Critical Road Threshold` | Determines how critical roads are identified. | Top 10% | Based on frequency in shortest paths. |
| `Real-time Data Integration` | Whether to use real-time traffic data. | False | Set to true if real-time data is available. |


## Input

- **Transportation network data** (e.g., `Siouxfallcri.gml`)
  A representation of the city's road network in a `.gml` file, detailing nodes (intersections/hospitals) and edges (road segments) along with attributes such as length and maximum speed.
  - **Disaster Site:** Detailing nodes (intersections) , representing the location(s) of the disaster.
- **Parameters** such as `hospitals`, number of `casualties`, and `hospital capacity`

## Output

Upon running the simulation, the following outputs are generated ( in `data.txt` ):

- **Identified critical links**: The simulation identifies critical links in the stochastic transportation network, highlighting segments whose disruption would have a significant impact on overall network performance.

- **Simulation results**: The simulation provides comprehensive results before and after deleting the critical link. This includes:
  - Total traversal time: The total time taken for the evacuation process from disaster sites to medical facilities.
  - Critical edge information: Details about the critical edge identified, including the nodes connected and their significance in the transportation network.

**The simulation is performed twice**: once before deleting the critical link and once after. This allows for a comparison of evacuation efficiency and network resilience in both scenarios, providing insights into the effectiveness of the proposed approach in enhancing emergency response strategies.


## Algorithm

The core algorithm of this simulation follows a two-step process: 

  - backward traversal for shortest path identification.
  - scenario simulation for evaluating disruption impacts.

Here's a breakdown of each step:

### Backward Traversal for Shortest Paths

1. **Initialization:** The algorithm begins with the entire network graph loaded, including nodes (intersections and hospitals) and edges (road segments). Each hospital node is considered a starting point for backward traversal.

2. **Path Calculation:** For each hospital node, the algorithm computes the shortest path to all other nodes in the network. This computation accounts for dynamic conditions such as current traffic congestion and road availability. The process involves:
    - Estimating travel times for each road segment based on current congestion levels.
    - Utilizing a priority queue to select the next node for exploration based on the least cumulative travel time.
    - Updating path and travel time estimates as better routes are discovered through the backward traversal from hospitals to other nodes.

3. **Result Storage:** The shortest paths and their corresponding expected travel times are stored. This information forms the basis for routing decisions in the simulation.

### Scenario Simulation for Evaluating Disruption Impacts

1. **Disruption Identification:** The algorithm identifies critical roads within the network by analyzing their frequency of appearance in shortest paths. The most critical roads are those whose disruption would significantly impact the evacuation efficiency.

2. **Impact Simulation:** For each identified critical road, the algorithm simulates a scenario where that road is unavailable (e.g., due to damage or blockage). This involves:
    - Removing the road from the network graph.
    - Recalculating the shortest paths from hospitals to all other nodes under this new condition.
    - Comparing the recalculated paths and travel times to the original scenario to assess the impact.

3. **Performance Evaluation:** The simulation evaluates network performance under disruptions by measuring changes in overall travel times and the number of nodes that become less accessible or inaccessible. This step helps in understanding the resilience of the evacuation routes and identifying potential bottlenecks.

### Optimization Techniques

- **Dynamic Congestion Updates:** The algorithm can incorporate real-time data to update road congestion levels, enabling dynamic adjustment of evacuation routes.
- **Parallel Processing:** To enhance performance, shortest path calculations for different hospital nodes can be executed in parallel.

This algorithmic approach allows for a detailed analysis of evacuation strategies in disaster scenarios, providing valuable insights into optimal routing and network resilience.


## Getting Started

To get started with the project, ensure you have the necessary dependencies installed and provide the required input data. You can then run the simulation to identify critical links in the transportation network.

## Usage
1. Install the required dependencies.
2. Provide the transportation network data (e.g., Siouxfallcri.gml).
3. Configure the simulation parameters (number of casualties, hospital capacity, etc.).
4. Run the simulation to identify critical links and assess network resilience.

## Contributing
Contributions to the project are welcome. You can contribute by adding new features, optimizing algorithms, or improving documentation.

## Authors
- [**ABDELKADIR Sellahi**](https://github.com/AbdelkadirSellahi)
