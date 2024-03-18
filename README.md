# Critical Links Detection in Stochastic Networks: Application to Transportation Networks

## Introduction
Natural disasters, including floods and earthquakes, pose significant challenges to emergency management systems, often leading to chaotic situations where quick and effective response is crucial to minimize the impact on human lives. One critical aspect of emergency management is the efficient evacuation of injured individuals from disaster sites to medical facilities for urgent treatment. To address this challenge, this project aims to simulate the evacuation process in disaster situations, leveraging concepts from Markov Decision Processes (MDPs) to model ambulance routing while considering real-time updates such as road congestion and disruptions.

In particular, the project focuses on identifying critical links in stochastic transportation networks to enhance network resilience and mitigate the impact of disruptions. By employing probabilistic analysis techniques, the algorithm identifies the most crucial links in the transportation network that, if disrupted, would have the most significant impact on network performance. This approach enables efficient resource allocation and risk management, ultimately contributing to more effective emergency response and reduced human casualties during disasters.


## Problem Statement
Transportation networks are vulnerable to various disruptions, which can lead to significant delays and economic losses. Identifying critical links in these networks is essential for efficient resource allocation and risk management.

## Solution Overview
The solution employs a probabilistic analysis approach to identify critical links in transportation networks. By simulating different scenarios and evaluating the impact of disruptions, the algorithm identifies the most critical links that, if disrupted, would have the most significant impact on network performance.

## Features
- Detection of critical links in transportation networks
- Probabilistic analysis to assess network resilience
- Efficient resource allocation and risk management

## Input
- Transportation network data (e.g., Siouxfallcri.gml)
- Parameters such as hospitals, number of casualties, and hospital capacity


## Output
Upon running the simulation, the following outputs are generated:

- **Identified critical links**: The simulation identifies critical links in the stochastic transportation network, highlighting segments whose disruption would have a significant impact on overall network performance.

- **Simulation results**: The simulation provides comprehensive results before and after deleting the critical link. This includes:
  - Total traversal time: The total time taken for the evacuation process from disaster sites to medical facilities.
  - Critical edge information: Details about the critical edge identified, including the nodes connected and their significance in the transportation network.

**The simulation is performed twice**: once before deleting the critical link and once after. This allows for a comparison of evacuation efficiency and network resilience in both scenarios, providing insights into the effectiveness of the proposed approach in enhancing emergency response strategies.


## Algorithm
The algorithm employs backward traversal to identify the shortest paths from hospitals to other nodes in the network. 
It then simulates different scenarios to evaluate the impact of disruptions on network performance.

## Getting Started
To get started with the project, ensure you have the necessary dependencies installed and provide the required input data. You can then run the simulation to identify critical links in the transportation network.

## Usage
1. Install the required dependencies.
2. Provide the transportation network data (e.g., Siouxfallcri.gml).
3. Configure the simulation parameters (number of casualties, hospital capacity, etc.).
4. Run the simulation to identify critical links and assess network resilience.

## Contributing
Contributions to the project are welcome. You can contribute by adding new features, optimizing algorithms, or improving documentation. Please follow the contribution guidelines when submitting pull requests.

