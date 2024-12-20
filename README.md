# RS-FEDRAD: Robust and Scalable Federated Ransomware Detection Using TTP-Enhanced Dataset

## Introduction
RS-FEDRAD presents a robust, federated, and privacy-conscious ransomware detection system that integrates a comprehensive feature set, including API calls, DLL interactions, Mutex data, and associated TTPs. It achieves state-of-the-art performance with:

- **99.90% accuracy**
- **99.50% average federated accuracy**
- **Resilience to black-box and white-box attacks**

RS-FEDRAD is designed to be scalable, decentralized, and resilient, making it a pioneering approach to ransomware detection in the context of federated learning.

## Table of Contents
- [Introduction](#introduction)
- [Key Contributions](#key-contributions)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Experimental Results](#experimental-results)
- [System Requirements](#system-requirements)

---

## Key Contributions

1. **TTP-Enhanced Dataset**: A novel dataset that maps ransomware features (API calls, DLL interactions) to TTPs, enhancing detection capabilities.
2. **Hybrid CNN-LSTM Model**: Combines Convolutional Neural Networks (CNNs) for spatial pattern analysis and Long Short-Term Memory (LSTM) for temporal pattern learning.
3. **Scalable Federated Learning**: Supports dynamic client participation, enabling privacy-preserving, decentralized training.
4. **Adversarial Resilience**: Demonstrates robustness against FGSM and BIM attacks with minimal accuracy degradation (~0.20%).

---

## Project Structure

The repository contains the following key directories:

- **`src/`**: Contains scripts for data preprocessing, model training, and federated learning setup.
- **`scripts/`**: Contains scripts for running clients, adversarial training, and centralized experiments.
- **`results/`**: Stores logs, metrics, and visualizations of experimental results.
- **`data/`**: Placeholder for the TTP-enhanced dataset used in experiments.

---

## Setup Instructions

### 1. Data Preprocessing

Navigate to the `src` folder and run the following script to preprocess the dataset:

Run the following in your terminal to preprocess the data:
`python src/data_preprocessing.py`

This script performs:
- Standardization, shuffling, and splitting of the dataset.
- Creation of 10 client-specific datasets for federated training.
- The number of clients can be adjusted for scalability.

### 2. Federated Training

#### Step 1: Initialize the Flower Server

Run the server script:

`python src/start_server.py`

- By default, the server is configured for 10 clients. You can modify the number of clients and training rounds in `start_server.py`.

#### Step 2: Start Clients

In parallel, run the following command for each client:

`python scripts/run_federated-client.py`

- Training begins once at least 2 clients have connected, and it continues as more clients join.

#### Step 3: Results

Training metrics (accuracy, precision, recall, F1-score) and client-specific history are saved in the `results/experiment_results` directory.

---

### Adversarial Training

To train with adversarial examples, follow the same federated training setup but use the adversarial client scripts:

- **BIM Attacks**:
  `python scripts/adversarial-bim_run_client.py`

- **FGSM Attacks**:
  `python scripts/adversarial-fgsm_run_client.py`

### Centralized Training

For centralized training, run the `centralized-run.py` script, which combines all client datasets into a single repository for central training:

`python scripts/centralized-run.py`

---

## Experimental Results

RS-FEDRAD achieves the following state-of-the-art results:

- **Overall Accuracy**: 99.90%
- **Average Federated Accuracy**: 99.50%
- **Adversarial Resilience**: Accuracy degradation is minimal (~0.20%) under FGSM and BIM attacks.

Results visualizations are stored in the `results/experiment_plots` directory, while metrics and training history are saved in `results/experiment_results`.

---

## System Requirements

- **Python**: 3.9+
- **Dependencies**:
  - `flwr==1.2.0`
  - `tensorflow==2.10.0`
  - `numpy==1.23.5`
  - `pandas==1.5.3`
  - `scikit-learn==1.2.2`


`pip install -r requirements.txt`

---

