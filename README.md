# 🔐 Quantum Cryptography — Theory to Practice

![Quantum](https://img.shields.io/badge/Quantum-Cryptography-blueviolet)
![Python](https://img.shields.io/badge/Language-Python-blue)
![Status](https://img.shields.io/badge/Status-Active-success)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

A comprehensive **theory + simulation–based implementation repository** exploring **Quantum Cryptography**, from fundamental quantum mechanics concepts to advanced secure key distribution protocols and attack modeling.

This project bridges **quantum information theory** and **practical cryptographic engineering**, with clean simulations, security analysis, and visualization dashboards.

---

## 📌 Table of Contents

- [Overview](#overview)
- [Core Concepts Covered](#core-concepts-covered)
- [Protocols & Simulations](#protocols--simulations)
- [Security & Attack Models](#security--attack-models)
- [Advanced Cryptographic Mechanisms](#advanced-cryptographic-mechanisms)
- [Security Metrics Dashboard](#security-metrics-dashboard)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)

---

## 🧠 Overview

Quantum Cryptography leverages the laws of **quantum mechanics** to achieve **information-theoretic security**, unattainable by classical cryptographic systems.

This repository focuses on:
- **Simulation-based proof of security**
- **Attack detection using quantum principles**
- **Clean-channel vs noisy-channel analysis**
- **Multi-party and adaptive cryptographic models**

All implementations are designed to be **educational, modular, and extensible**.

---

## 📚 Core Concepts Covered

### 1️.Qubit and Measurement
- Computational and Hadamard bases
- Measurement collapse behavior
- Basis mismatch effects

### 2️.Superposition and Shannon Entropy
- Quantum uncertainty modeling
- Entropy comparison: classical vs quantum
- Information leakage analysis

### 3.Quantum State as a Cryptographic Symbol
- Mapping qubit states to cryptographic alphabets
- State preparation and decoding

### 4.No-Cloning Theorem (Simulation Proof)
- Practical demonstration of impossibility
- Attack failure analysis using cloning attempts

---

## 🔁 Protocols & Simulations

### 5️5.BB84 Protocol (Clean Channel)
- End-to-end key generation
- Basis reconciliation
- Key sifting and final key extraction

### 6️6.BB84 with Intercept-Resend Attack
- Eve’s intervention modeling
- Error rate increase detection
- Key discard thresholds

### 7️7.BB84 Under Noise
- Channel noise modeling
- Quantum Bit Error Rate (QBER) analysis
- Secure key rate degradation

---

## 🔗 Entanglement-Based Cryptography

### 8️8.Entanglement for Cryptography
- EPR pair generation
- Correlated measurement outcomes

### 9️9.E91-Style Entangled Key Distribution
- Entanglement-based QKD
- Device independence assumptions

###  10.Bell Inequality & Eavesdropper Detection
- CHSH inequality computation
- Eve detection via Bell violation
- Classical vs quantum correlation comparison

---

## 🛡️ Advanced Cryptographic Mechanisms

### 1️11. Quantum Authentication Encoding
- Quantum message authentication
- Detection of tampering attempts

### 1️12. Multi-Party Quantum Key Agreement
- Collaborative key generation
- Fairness and consensus properties

### 1️13. Adaptive Basis Selection
- Dynamic basis optimization
- Attack-aware basis adaptation

---

## 🕵️ Security & Attack Models

### 1️14. Side-Channel Simulation
- Detector efficiency mismatch
- Timing and measurement leakage
- Practical implementation weaknesses

---

## 📊 Security Metrics Dashboard

### 15.Security Matrices Dashboard
- QBER visualization
- Mutual information (Alice–Bob / Alice–Eve)
- Bell violation metrics
- Key rate vs noise graphs

> 📈 Designed for **research insight and teaching demonstrations**

---

## 🧰 Tech Stack

- **Python**
- NumPy 
- Matplotlib 
- Jupyter Notebook
- Custom Quantum State Simulator (no black-box SDKs)
- Qiskit 2.2.3

---

## 🗂️ Project Structure

```text
quantum-cryptography/
│
├── Day01_Qubit_and_Measurement/
│   ├── qubit_measurement.ipynb
│   ├── README.md
│   └── day01_notes
│   
│       
│
├── Day02_Superposition_and_Entropy/
│   ├── superposition_entropy.ipynb
│   ├── README.md
│   └── day02_notes.md
│      
│      
│
├── Day03_Quantum_State_as_Crypto_Symbol/
│   ├── quantum_symbol.ipynb
│   ├── README.md
│   └── day03_notes.md
│       
│
├── Day04_No_Cloning_Theorem/
│   ├── no_cloning_simulation.ipynb
│   ├── README.md
│   └── day04_notes.md
│      
│
├── Day05_BB84_Clean_Channel/
│   ├── bb84_clean.ipynb
│   ├── README.md
│   └── day05_notes.md
│
│
├── Day06_BB84_Intercept_Resend_Attack/
│   ├── bb84_attack.ipynb
│   ├── README.md
│   └── day06_notes.md
│       
│
├── Day07_BB84_Under_Noise/
│   ├── bb84_noise.ipynb
│   ├── README.md
│   └── day07_notes.md
│      
│
├── Day08_Entanglement_for_Cryptography/
│   ├── entanglement_crypto.ipynb
│   ├── README.md
│   └── day08_notes.md
│      
│
├── Day09_E91_Entangled_QKD/
│   ├── e91_protocol.ipynb
│   ├── README.md
│   └── day09_notes.md
│      
│
├── Day10_Bell_Inequality_Eavesdropper_Detection/
│   ├── bell_inequality.ipynb
│   ├── README.md
│   └── day10_notes.md
│      
│
├── Day11_Quantum_Authentication/
│   ├── quantum_authentication.ipynb
│   ├── README.md
│   └── day11_notes.md
│       
│
├── Day12_Multi_Party_QKA/
│   ├── multi_party_qka.ipynb
│   ├── README.md
│   └── day12_notes.md
│       
│
├── Day13_Adaptive_Basis_Selection/
│   ├── adaptive_basis.ipynb
│   ├── README.md
│   └── day13_notes.md
│      
│
├── Day14_Side_Channel_Simulation/
│   ├── side_channel_attack.ipynb
│   ├── README.md
│   └── day14_notes.md
│      
│
├── Day15_Security_Metrics_Dashboard/
│   ├── security_dashboard.ipynb
│   ├── README.md
│   └── day15_notes.md
│      
│
├── requirements.txt
└── README.md


```

---

##  Author & Contact

**Author** : Shreya Palase(codeQubit)

**Field** : Quantum Cryptography |Quantum Information Security

**Affiliation**: Independent Research / Study

🔗 **GitHub** : https://github.com/shreyapalase

---

## 🔐 Usage & Security Notice

⚠️ Important Security Statement

This repository is created strictly for educational, academic, and research purposes.

❌ Unauthorized use, reproduction, or modification is prohibited

❌ Do NOT deploy these implementations in real-world security systems

❌ Do NOT use without explicit permission from the author

The simulations do not guarantee production-grade security and are not audited for real cryptographic deployment.

Any misuse of the concepts, code, or simulations is solely the responsibility of the user.

📩 For collaboration, reuse, or publication-related requests, contact the author directly.

---

## ⭐ Support & Acknowledgment

If you find this work valuable:

⭐ Star the repository

👤 Follow for future quantum security projects

📢 Share with students and researchers in quantum cryptography


“Quantum mechanics doesn’t just encrypt data — it exposes the act of spying itself.”

