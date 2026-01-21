# Day2 Notes - Superposition And Shannon Entrophy

---

## 1. Superposition Principle

The **principle of superposition** is one of the most fundamental ideas in quantum mechanics and distinguishes quantum systems from classical systems. In classical physics, a system exists in one definite state at a time. For example, a classical bit can be either `0` or `1`. In contrast, a **quantum system** can exist in a *linear combination* of multiple possible states simultaneously. This means that before measurement, a quantum state does not have a single definite value but rather a set of probabilities associated with different outcomes.

Mathematically, the state of a quantum system is represented by a vector in a complex Hilbert space. If a quantum system can be in two basis states, denoted as `|0⟩` and `|1⟩`, then according to the superposition principle, the most general state `|ψ⟩` can be written as:

$$
|\psi\rangle = \alpha |0\rangle + \beta |1\rangle
$$

Here, `α` and `β` are **complex probability amplitudes**. These amplitudes contain both magnitude and phase information, which plays a crucial role in quantum interference phenomena. The actual probabilities of obtaining `|0⟩` or `|1⟩` upon measurement are given by the squared magnitudes of these amplitudes:

$$
P(0) = |\alpha|^2, \quad P(1) = |\beta|^2
$$

To ensure total probability equals one, the amplitudes must satisfy the normalization condition:

$$
|\alpha|^2 + |\beta|^2 = 1
$$

The superposition principle allows quantum systems to perform computations on multiple states simultaneously, which is the conceptual foundation of **quantum parallelism**. However, once a measurement is performed, the superposition collapses into one of the basis states, a phenomenon known as **wave function collapse**. This dual nature of continuous evolution (via Schrödinger’s equation) and discontinuous measurement is a defining feature of quantum mechanics.

---

## 2. Shannon Entropy

**Shannon entropy** is a measure of uncertainty or information content in a random variable. Introduced by Claude Shannon in 1948, it forms the foundation of classical information theory. Entropy quantifies how unpredictable a system is: the more uncertain the outcome, the higher the entropy.

For a discrete random variable `X` with possible outcomes `{x₁, x₂, ..., xₙ}` and corresponding probabilities `{p₁, p₂, ..., pₙ}`, the Shannon entropy `H(X)` is defined as:

$$
H(X) = - \sum_{i=1}^{n} p_i \log_2 p_i
$$

The logarithm base 2 is used so that entropy is measured in **bits**. If one outcome has probability 1 (complete certainty), then the entropy is zero:

$$
H(X) = 0
$$

This indicates that no new information is gained when the outcome is already known. On the other hand, entropy is maximized when all outcomes are equally likely. For example, for a fair coin:

$$
p(0) = p(1) = \frac{1}{2}
$$

$$
H(X) = -\left( \frac{1}{2}\log_2\frac{1}{2} + \frac{1}{2}\log_2\frac{1}{2} \right) = 1 \text{ bit}
$$

Thus, Shannon entropy captures the **average information gained per measurement** and plays a central role in data compression, communication theory, and cryptography.

---

## 3. Entropy as a Key Strength Metric

In cryptography, entropy is directly related to **key strength**. A cryptographic key with low entropy is more predictable and therefore vulnerable to brute-force or statistical attacks. High entropy implies a high level of randomness, making it computationally infeasible for an attacker to guess the key.

If a key is generated from a probability distribution that is not uniform, an attacker can exploit the bias to reduce the effective search space. The entropy of the key distribution provides a quantitative measure of how secure the key is. For a uniformly random key of length `n` bits, the entropy is:

$$
H = n \text{ bits}
$$

This means there are `2^n` equally likely keys. However, if the distribution is biased, the entropy will be lower than `n`, reducing security. Therefore, entropy serves as a **key strength metric**, indicating how resistant a cryptographic system is to attacks based on guessing or information leakage.

---

## 4. Why Maximum Entropy is Desired in Quantum Cryptography

In **quantum cryptography**, particularly in **Quantum Key Distribution (QKD)** protocols such as BB84, maximum entropy is highly desirable because it ensures **maximum unpredictability** of the generated key. Quantum mechanics provides inherent randomness through the measurement of quantum states, which cannot be replicated or predicted by classical means.

A quantum system prepared in a superposition state and measured in a randomly chosen basis produces outcomes that are fundamentally random. If an eavesdropper (Eve) attempts to intercept and measure the quantum states, the act of measurement will inevitably disturb the system due to the **no-cloning theorem** and the measurement postulate. This disturbance introduces detectable errors, alerting legitimate parties to the presence of an attacker.

Maximum entropy in quantum cryptography ensures that:

- The key has no statistical bias
- Eve has minimal information about the key
- Any eavesdropping attempt increases observable error rates

In information-theoretic terms, the goal is to maximize the entropy of the key conditioned on Eve’s knowledge:

$$
H(K | E) \approx H(K)
$$

This means that even with all available information, the attacker gains essentially no knowledge about the key. As a result, maximum entropy is not just desirable but **essential** for achieving unconditional security in quantum cryptographic systems.

---

## Summary

- **Superposition** allows quantum systems to exist in multiple states simultaneously.
- **Shannon entropy** measures uncertainty and information content.
- **Entropy** acts as a quantitative metric for cryptographic key strength.
- **Maximum entropy** in quantum cryptography guarantees unpredictability and resistance to eavesdropping.

These concepts together form the theoretical backbone of modern quantum information science.
# Quantum Information Theory – Deep Conceptual Notes

---

## 1. Superposition Principle

The **principle of superposition** is one of the most fundamental ideas in quantum mechanics and distinguishes quantum systems from classical systems. In classical physics, a system exists in one definite state at a time. For example, a classical bit can be either `0` or `1`. In contrast, a **quantum system** can exist in a *linear combination* of multiple possible states simultaneously. This means that before measurement, a quantum state does not have a single definite value but rather a set of probabilities associated with different outcomes.

Mathematically, the state of a quantum system is represented by a vector in a complex Hilbert space. If a quantum system can be in two basis states, denoted as `|0⟩` and `|1⟩`, then according to the superposition principle, the most general state `|ψ⟩` can be written as:

$$
|\psi\rangle = \alpha |0\rangle + \beta |1\rangle
$$

Here, `α` and `β` are **complex probability amplitudes**. These amplitudes contain both magnitude and phase information, which plays a crucial role in quantum interference phenomena. The actual probabilities of obtaining `|0⟩` or `|1⟩` upon measurement are given by the squared magnitudes of these amplitudes:

$$
P(0) = |\alpha|^2, \quad P(1) = |\beta|^2
$$

To ensure total probability equals one, the amplitudes must satisfy the normalization condition:

$$
|\alpha|^2 + |\beta|^2 = 1
$$

The superposition principle allows quantum systems to perform computations on multiple states simultaneously, which is the conceptual foundation of **quantum parallelism**. However, once a measurement is performed, the superposition collapses into one of the basis states, a phenomenon known as **wave function collapse**. This dual nature of continuous evolution (via Schrödinger’s equation) and discontinuous measurement is a defining feature of quantum mechanics.

---

## 2. Shannon Entropy

**Shannon entropy** is a measure of uncertainty or information content in a random variable. Introduced by Claude Shannon in 1948, it forms the foundation of classical information theory. Entropy quantifies how unpredictable a system is: the more uncertain the outcome, the higher the entropy.

For a discrete random variable `X` with possible outcomes `{x₁, x₂, ..., xₙ}` and corresponding probabilities `{p₁, p₂, ..., pₙ}`, the Shannon entropy `H(X)` is defined as:

$$
H(X) = - \sum_{i=1}^{n} p_i \log_2 p_i
$$

The logarithm base 2 is used so that entropy is measured in **bits**. If one outcome has probability 1 (complete certainty), then the entropy is zero:

$$
H(X) = 0
$$

This indicates that no new information is gained when the outcome is already known. On the other hand, entropy is maximized when all outcomes are equally likely. For example, for a fair coin:

$$
p(0) = p(1) = \frac{1}{2}
$$

$$
H(X) = -\left( \frac{1}{2}\log_2\frac{1}{2} + \frac{1}{2}\log_2\frac{1}{2} \right) = 1 \text{ bit}
$$

Thus, Shannon entropy captures the **average information gained per measurement** and plays a central role in data compression, communication theory, and cryptography.

---

## 3. Entropy as a Key Strength Metric

In cryptography, entropy is directly related to **key strength**. A cryptographic key with low entropy is more predictable and therefore vulnerable to brute-force or statistical attacks. High entropy implies a high level of randomness, making it computationally infeasible for an attacker to guess the key.

If a key is generated from a probability distribution that is not uniform, an attacker can exploit the bias to reduce the effective search space. The entropy of the key distribution provides a quantitative measure of how secure the key is. For a uniformly random key of length `n` bits, the entropy is:

$$
H = n \text{ bits}
$$

This means there are `2^n` equally likely keys. However, if the distribution is biased, the entropy will be lower than `n`, reducing security. Therefore, entropy serves as a **key strength metric**, indicating how resistant a cryptographic system is to attacks based on guessing or information leakage.

---

## 4. Why Maximum Entropy is Desired in Quantum Cryptography

In **quantum cryptography**, particularly in **Quantum Key Distribution (QKD)** protocols such as BB84, maximum entropy is highly desirable because it ensures **maximum unpredictability** of the generated key. Quantum mechanics provides inherent randomness through the measurement of quantum states, which cannot be replicated or predicted by classical means.

A quantum system prepared in a superposition state and measured in a randomly chosen basis produces outcomes that are fundamentally random. If an eavesdropper (Eve) attempts to intercept and measure the quantum states, the act of measurement will inevitably disturb the system due to the **no-cloning theorem** and the measurement postulate. This disturbance introduces detectable errors, alerting legitimate parties to the presence of an attacker.

Maximum entropy in quantum cryptography ensures that:

- The key has no statistical bias
- Eve has minimal information about the key
- Any eavesdropping attempt increases observable error rates

In information-theoretic terms, the goal is to maximize the entropy of the key conditioned on Eve’s knowledge:

$$
H(K | E) \approx H(K)
$$

This means that even with all available information, the attacker gains essentially no knowledge about the key. As a result, maximum entropy is not just desirable but **essential** for achieving unconditional security in quantum cryptographic systems.

---

## Summary

- **Superposition** allows quantum systems to exist in multiple states simultaneously.
- **Shannon entropy** measures uncertainty and information content.
- **Entropy** acts as a quantitative metric for cryptographic key strength.
- **Maximum entropy** in quantum cryptography guarantees unpredictability and resistance to eavesdropping.


---

**Written By :** Shreya Palase

**Date** : 21-Jan-2026

Thank you And Keep Learning!
