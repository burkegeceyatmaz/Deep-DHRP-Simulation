# Deep-DHRP: Dynamic Hybrid VANET Routing Protocol

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/burke/HybridCNN/blob/main/Hybridcnn.ipynb)

## Description
This repository contains the simulation framework, physical layer configurations, and mobility traces for the **Deep Hybrid Routing Protocol (Deep-DHRP)**. Deep-DHRP resolves the fundamental performance trade-off between reactive (AODV) and proactive (OLSR) routing in Vehicular Ad-hoc Networks (VANETs). By replacing static thresholds with a spatial-aware deep learning agent, the protocol dynamically modulates transmission power and routing paradigms to guarantee a Packet Delivery Ratio (PDR) exceeding 90% in dense urban topologies.

## Dataset Information
The simulation and model training rely on two primary data sources:
* **`mobility.tcl` (Urban Mobility Traces):** 100% real-world, deterministic traffic patterns and spatial coordinates derived from Kyrenia, Cyprus, generated via SUMO.
* **`train.csv` (Training Dataset):** A rigorously balanced dataset containing 165,896 topological samples and kinematic events used to train the Hybrid CNN without majority-class bias.

## Code Information
* `Hybridcnn.ipynb` - The primary Google Colab execution script. Contains the Dual-Stream H-CNN architecture, training loop, and the continuous physics simulation engine.
* `main.py` - The local Python execution equivalent for offline environments.

## Usage Instructions
The easiest way to review or run the simulation is natively in the browser by clicking the "Open in Colab" badge at the top of this file. 

To run the framework locally:
1. Clone this repository:
   ```bash
   git clone [https://github.com/burke/HybridCNN.git](https://github.com/burke/HybridCNN.git)
