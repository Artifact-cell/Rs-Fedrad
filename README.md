# RS-FEDRAD: Robust and Scalable Federated Ransomware Detection Using TTP-Enhanced Dataset  

![Python](https://img.shields.io/badge/python-3.9-blue) ![License](https://img.shields.io/badge/license-MIT-green)

## Abstract
Ransomware continues to evolve as a significant cybersecurity threat, employing advanced evasion techniques such as polymorphism and obfuscation to bypass detection mechanisms. Conventional detection approaches fail against such modern ransomware due to reliance on limited feature sets and centralized architectures, leading to privacy and scalability issues.  

**RS-FEDRAD** addresses these challenges by integrating **Federated Learning (FL)** with deep dynamic analysis, leveraging a novel **TTP-enhanced dataset**. This decentralized, privacy-preserving solution provides robust detection with state-of-the-art performance metrics, including **99.90% accuracy** and resilience to adversarial attacks.

---

## Table of Contents
1. [Abstract](#abstract)
2. [Key Contributions](#key-contributions)
3. [Project Structure](#project-structure)
4. [Setup Instructions](#setup-instructions)
5. [Experimental Results](#experimental-results)
6. [System Requirements](#system-requirements)

---

## Key Contributions
- **TTP-Enhanced Dataset**: Enriched with ransomware behavior insights (API calls, DLL interactions, Mutex operations).
- **Hybrid CNN-LSTM Model**: Combines spatial and temporal pattern analysis for superior performance.
- **Scalable Federated Learning**: Enables dynamic client participation for privacy-preserving decentralized training.
- **Adversarial Resilience**: Maintains performance under FGSM and BIM attacks with minimal accuracy degradation (~0.20%).

---

## Project Structure
The repository contains the following key directories:
- `src`: Scripts for data preprocessing, model training, and federated learning setup.
- `scripts`: Scripts for running clients, adversarial training, and centralized experiments.
- `results`: Logs, metrics, and visualizations of experimental results.
- `data`: Placeholder for the TTP-enhanced dataset used in experiments.

---

## Setup Instructions

### Prerequisites
1. Clone the repository:
   ```bash
   git clone https://github.com/Artifact-cell/Rs-Fedrad.git
   cd Rs-Fedrad
