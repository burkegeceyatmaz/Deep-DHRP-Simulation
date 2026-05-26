# Deep-DHRP-Simulation

# Deep-DHRP: Dynamic Hybrid VANET Routing Protocol

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/burke/HybridCNN/blob/main/Hybridcnn.ipynb)

## Overview
This repository contains the simulation code, physical layer configurations, and mobility traces for the **Deep Hybrid Routing Protocol (Deep-DHRP)**. Deep-DHRP is designed to resolve the performance trade-off between reactive and proactive routing in Vehicular Ad-hoc Networks (VANETs) by replacing static thresholds with a Dual-Stream Hybrid Convolutional Neural Network (H-CNN).

By fusing kinematic state vectors with a 40x40 spatial occupancy grid, the AI agent dynamically toggles between AODV and OLSR while modulating transmission power via an adaptive cross-layer mechanism. The protocol successfully guarantees a Packet Delivery Ratio (PDR) exceeding 90% across all tested urban densities (up to 500 nodes).

## Repository Contents
* `Hybridcnn.ipynb` - The core Google Colab execution script containing the Dual-Stream H-CNN architecture and simulation logic.
* `mobility.tcl` - Real-world urban SUMO mobility traces, deterministic traffic patterns, and spatial coordinates from Cyprus.
* `train.csv` - The balanced dataset containing 165,896 topological samples generated for training the neural network.

## Protocol Mechanics & Hysteresis Logic
Unlike conventional scalar-based protocols, Deep-DHRP utilizes non-linear decision boundaries driven by spatial topology. The core fallback hysteresis logic dictates:
* **High Density:** The protocol transitions to proactive **OLSR** when the local neighbor count exceeds an upper bound of 80 nodes, triggering Eco-Mode (21.5 dBm) to mitigate broadcast storms.
* **Low Density:** The protocol reverts to reactive **AODV** when density diminishes below 60 nodes to conserve bandwidth, utilizing Boost-Mode (28.0 dBm) to bridge sparse communication voids.

## Hardware and Physics Parameters (5G NR-V2X)
* **MAC / PHY Standard:** IEEE 802.11bd / C-V2X
* **Base Data Rate:** 3 Mbps (BPSK 1/2)
* **Receiver Sensitivity:** -98.0 dBm
* **SINR Decoding Threshold:** 1.0 dB
* **CNN Edge Footprint:** 12.92 MB

## Usage Instructions
Reviewers and researchers can run the simulation natively in the browser without local dependencies by clicking the "Open in Colab" badge above. 

To run the framework locally:
1. Clone this repository to your local machine.
2. Ensure you have Python 3.8+, PyTorch, Pandas, and Scikit-Learn installed.
3. Run the notebook using Jupyter or execute the converted Python script in an environment integrated with NS-3 (v3.36.1) and SUMO.

## Research Team
**Burke Geceyatmaz, Kamil Yurtkan, and Fatma Tansu Hocanın** *Cyprus International University*

---
*Note: The performance metrics presented in this repository are derived from a 1:1 deterministic replay of real-world SUMO mobility traces, reflecting absolute physical layer outcomes for the captured urban scenario.*
