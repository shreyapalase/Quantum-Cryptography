# Day1  Notes -Qubit ,Measurement and Quantum Randomness

Quantum cryptography is a field of cryptography that applies the principles of **quantum mechanics** to achieve secure communication. Unlike classical cryptography, which relies on computational assumptions, quantum cryptography derives its security from **fundamental physical laws**, making it secure even against adversaries with unlimited computational power.

---

## What Is a Qubit?

A **qubit (quantum bit)** is the fundamental unit of quantum information.

A classical bit can exist only in one of two states:
- 0
- 1

A qubit, however, can exist in a **superposition** of both states simultaneously.

Mathematically, a qubit is represented as:

$$
|\psi\rangle = \alpha |0\rangle + \beta |1\rangle
$$

where:
- $\alpha$ and $\beta$ are complex probability amplitudes  
- $|\alpha|^2 + |\beta|^2 = 1$  
- $|\alpha|^2$ is the probability of measuring 0  
- $|\beta|^2$ is the probability of measuring 1  

This property allows quantum systems to encode information in ways that classical systems cannot.

---

## Measurement and Wavefunction Collapse

Measurement in quantum mechanics is an **active and irreversible process**.

Before measurement:
- The qubit exists in a superposition of states

After measurement:
- The qubit collapses into one definite classical state

For a qubit in the state:

$$
|\psi\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle
$$

The outcomes are:
- 0 with probability 50%
- 1 with probability 50%

Once measured, the superposition is destroyed. This phenomenon, known as **wavefunction collapse**, is essential in quantum cryptography because any measurement attempt can be detected.

---

## Quantum Randomness vs Pseudo-Randomness

### Pseudo-Randomness

Classical random number generators are typically:
- Algorithm-based
- Deterministic
- Dependent on an initial seed

If the seed or algorithm is known, future outputs can be predicted, which poses a serious risk in cryptographic systems.

---

### Quantum Randomness

Quantum randomness arises from **intrinsic quantum uncertainty**.

When a quantum state in superposition is measured:
- The outcome is fundamentally unpredictable
- No hidden variable determines the result

Quantum randomness is:
- Truly random
- Non-deterministic
- Impossible to reproduce or predict

This makes it superior to pseudo-randomness for cryptographic purposes.

---

## Cryptographic Relevance of Randomness

Randomness is a critical component of secure cryptographic systems and is used in:
- Key generation
- One-time pads
- Nonces
- Session keys

Weak or predictable randomness can lead to:
- Key compromise
- Replay attacks
- Complete system failure

Quantum cryptography ensures randomness that is **physically guaranteed**, not algorithmically simulated.

---

## Single-Qubit Circuit with Hadamard Gate

Consider a single qubit initialized in the state:

$$
|0\rangle
$$

Applying a **Hadamard (H) gate** produces an equal superposition:

$$
H|0\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)
$$

Measuring this qubit in the **Z-basis** results in:
- 0 with probability 0.5
- 1 with probability 0.5

Each measurement outcome is intrinsically random.

---

## Effect of Multiple Shots

A **shot** refers to one execution of the quantum circuit followed by measurement.

### 100 Shots
- Small sample size
- Large statistical fluctuations
- Results may noticeably deviate from ideal probabilities

### 1000 Shots
- Improved statistical stability
- Distribution approaches theoretical values

### 10000 Shots
- Strong convergence toward a 50%–50% distribution
- Confirms the probabilistic nature of quantum mechanics

This demonstrates that individual quantum events are random, while large samples obey precise statistical laws.

---

## Relation to Quantum Cryptography

This simple circuit captures the essence of **quantum key generation**:

- Each measurement produces one random bit
- Randomness is guaranteed by quantum mechanics
- Quantum states cannot be cloned
- Any eavesdropping attempt causes detectable disturbances

Quantum key distribution protocols such as **BB84** rely on these exact principles to securely distribute cryptographic keys.

---

## Summary

- Qubits enable superposition and intrinsic randomness
- Measurement causes irreversible wavefunction collapse
- Quantum randomness is superior to pseudo-randomness
- Cryptographic security depends critically on randomness
- Repeated measurements show statistical convergence
- These principles form the foundation of quantum cryptography


---

**Written By** : Shreya Palase

**Date** : 19 -Jan-2026

Thank you and Keep learning!
