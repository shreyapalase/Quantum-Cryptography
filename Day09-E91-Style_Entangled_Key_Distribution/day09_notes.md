# Day9 Notes - E91-Style Entangled Key Distribution

## 1. Introduction to E91 Protocol

The E91 protocol is an entanglement-based Quantum Key Distribution (QKD) scheme proposed by Artur Ekert in 1991. Unlike earlier prepare-and-measure protocols, E91 relies entirely on the quantum phenomenon of entanglement to distribute cryptographic keys securely. The protocol uses pairs of entangled particles shared between two distant users, traditionally called Alice and Bob. The security of E91 is fundamentally guaranteed by the violation of Bell’s inequalities, making it one of the earliest protocols to directly link quantum non-locality with cryptographic security.

---

## 2. Difference Between BB84 and E91 Protocols

The BB84 and E91 protocols differ fundamentally in their operational principles and security assumptions. BB84 is a prepare-and-measure protocol in which Alice prepares quantum states and sends them to Bob, while E91 is an entanglement-based protocol where both parties receive particles from a shared entangled source.

In BB84, security is based on the uncertainty principle and the no-cloning theorem. Alice sends qubits prepared in randomly chosen bases, and Bob measures them randomly. Eavesdropping introduces detectable errors due to measurement disturbance. In contrast, E91 does not require Alice to prepare quantum states; instead, both Alice and Bob perform measurements on entangled particles. Security in E91 is derived from Bell inequality violations, which confirm the presence of genuine quantum correlations.

Another important difference is trust. BB84 assumes that Alice’s state preparation device is trusted, whereas E91 can operate in a **device-independent** manner. Even if the source of entangled particles is untrusted or controlled by an adversary, the violation of Bell inequalities ensures security in E91. This makes E91 more robust in scenarios where hardware security cannot be fully guaranteed.

---

## 3. Role of Entanglement in E91

Entanglement is the core resource that enables security in the E91 protocol. In E91, a source generates pairs of maximally entangled particles and distributes one particle to Alice and the other to Bob. A typical entangled state used is a Bell state:

$$
|\Psi^-\rangle = \frac{1}{\sqrt{2}} (|01\rangle - |10\rangle)
$$

In this state, neither particle has an individual definite value, but their measurement outcomes are perfectly correlated (or anti-correlated) depending on the measurement basis. When Alice measures her particle, Bob’s particle state is instantaneously determined, regardless of the distance between them.

These correlations cannot be explained by classical physics and are stronger than any classical correlation. Because entanglement is destroyed or weakened by measurement, any attempt by an eavesdropper to intercept the particles will reduce the observed correlations. This reduction can be detected by statistical analysis of measurement results, ensuring that only genuinely entangled particles are used for key generation.

---

## 4. Bell Inequality and Security in E91

The security of the E91 protocol is verified through the violation of Bell inequalities, specifically the CHSH (Clauser–Horne–Shimony–Holt) inequality. Alice and Bob randomly choose different measurement settings and compute correlation values based on their outcomes.

The CHSH parameter is defined as:

$$
S = E(a, b) + E(a, b') + E(a', b) - E(a', b')
$$

Where:
- \( E(a, b) \) represents the correlation between Alice’s and Bob’s measurements
- \( a, a' \) are Alice’s measurement settings
- \( b, b' \) are Bob’s measurement settings

For any classical or local hidden-variable theory, the inequality holds:

$$
|S| \leq 2
$$

Quantum mechanics allows entangled states to violate this bound, achieving:

$$
|S| \leq 2\sqrt{2}
$$

A violation of this inequality confirms the presence of quantum entanglement and guarantees that no classical eavesdropper can reproduce the observed correlations. If the measured value of \( S \) drops below the quantum threshold, Alice and Bob discard the key.

---

## 5. Device-Independent Security in E91

One of the most significant advantages of the E91 protocol is its support for **device-independent security**. Device-independent QKD means that the security of the protocol does not rely on trusting the internal functioning of the quantum devices used by Alice and Bob.

In E91, security is inferred directly from observable statistics, namely Bell inequality violations. Even if the measurement devices or the entanglement source are imperfect or partially controlled by an adversary, as long as the observed correlations violate Bell inequalities, the generated key remains secure.

This property protects against side-channel attacks and implementation flaws, which are major vulnerabilities in classical and semi-quantum cryptographic systems. Device-independent security represents a major theoretical advancement and is one of the strongest security guarantees achievable in cryptography.

---

## 6. Eavesdropping Detection and Error Analysis

In the E91 protocol, any eavesdropping attempt inevitably alters the entangled state. An eavesdropper attempting to measure or clone the particles breaks entanglement due to the no-cloning theorem:

$$
|\psi\rangle \neq |\psi\rangle |\psi\rangle
$$

This disturbance increases the quantum bit error rate (QBER) and reduces Bell inequality violations. Alice and Bob publicly compare a subset of their measurement outcomes to estimate the error rate. If the error rate exceeds a predefined threshold, the key is discarded.

This mechanism ensures that secrecy is not assumed but verified experimentally during each key exchange session.

---

## 7. Comparison with Classical Key Distribution

Unlike classical key distribution methods, which rely on computational assumptions, E91 provides **information-theoretic security**. Classical systems can be broken if an adversary gains enough computational power, such as through quantum computing. In contrast, E91’s security is rooted in physical laws that cannot be bypassed without violating quantum mechanics.

Additionally, classical systems allow undetectable copying of information, while quantum entanglement prevents this through fundamental measurement disturbance and non-local correlations.

---

## 8. Additional Advantage: Source Independence

An important additional feature of the E91 protocol is **source independence**. The entangled particle source does not need to be trusted and can even be placed between Alice and Bob or controlled by an adversary. As long as Bell inequality violations are observed, the source must be producing genuine entangled states.

This makes E91 particularly suitable for network-based quantum communication and satellite-based QKD systems, where trust assumptions about intermediate nodes are difficult to enforce.

---

## 9. Conclusion

The E91-style entangled key distribution protocol represents a foundational advancement in quantum cryptography. By directly leveraging quantum entanglement and Bell inequality violations, E91 achieves unparalleled security guarantees, including device-independent and information-theoretic security. Its resistance to both classical and quantum attacks makes it a critical protocol for future secure communication infrastructures.

---

## 10. Key Points Summary

- E91 is an entanglement-based QKD protocol proposed in 1991.
- It differs from BB84 by relying on Bell inequality violations rather than state preparation.
- Entanglement ensures strong, non-classical correlations.
- Device-independent security protects against faulty or malicious hardware.
- Security is guaranteed by physical laws, not computational assumptions.

---

**Written By** : Shreya Palase

**Date** : 01-feb-2026

Thank you and Keep Learning!

---


