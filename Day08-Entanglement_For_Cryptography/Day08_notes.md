# Day8 Notes - Quantum Entanglement for Cryptography

## 1. Introduction

Quantum cryptography is a field of cryptography that uses principles of quantum mechanics to achieve secure communication. One of the most powerful and unique phenomena enabling quantum cryptography is **quantum entanglement**. Entanglement introduces correlations between quantum systems that are fundamentally different from classical correlations, allowing cryptographic protocols with security guaranteed by the laws of physics rather than computational assumptions. This makes entanglement-based cryptography resistant to future threats such as quantum computers.

---

## 2. What is Quantum Entanglement?

Quantum entanglement is a physical phenomenon in which two or more quantum particles become linked in such a way that the quantum state of each particle cannot be described independently, even when the particles are separated by large distances. Once entangled, a measurement performed on one particle instantaneously determines the outcome of a corresponding measurement on the other particle, regardless of the distance between them. This behavior cannot be explained using classical physics and reflects the non-local nature of quantum mechanics.

Mathematically, consider a pair of qubits in an entangled Bell state:

$$
|\Phi^+\rangle = \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle)
$$

In this state, neither qubit has a definite value on its own. However, when one qubit is measured, the other qubit’s state is instantly determined. If the first qubit is measured as `0`, the second will also be `0`. If the first is `1`, the second will be `1`. The system must be treated as a single quantum entity rather than two independent particles.

A key feature of entanglement is that it **violates classical locality**, which is experimentally verified using Bell’s inequalities. These violations confirm that entangled correlations are stronger than any classical correlation and cannot be reproduced by shared classical randomness.

---

## 3. Why Entanglement Enables Sharing Secrets

Entanglement enables secret sharing because it creates **perfectly correlated random outcomes** between legitimate parties while preventing any third party from accessing the same information without detection. When two users (commonly called Alice and Bob) share entangled particles, measurements on those particles produce correlated results that can be used to generate identical cryptographic keys.

The crucial advantage is that quantum measurement disturbs the system. If an eavesdropper (Eve) tries to intercept or measure one of the entangled particles, the entangled state collapses or becomes altered. This disturbance introduces detectable errors in the correlations observed by Alice and Bob, immediately revealing the presence of an attacker.

For example, if Alice and Bob measure entangled qubits in the same basis, their results will match with high probability:

$$
P(a = b) = 1
$$

However, if an eavesdropper intervenes, the probability of mismatched results increases:

$$
P(a \neq b) > 0
$$

This property allows Alice and Bob to verify the integrity of their shared data before using it as a secret key. If the observed error rate exceeds a predefined threshold, the key is discarded, ensuring security.

---

## 4. Role of Entanglement in Quantum Key Distribution (QKD)

Entanglement plays a central role in **entanglement-based Quantum Key Distribution (QKD)** protocols such as the Ekert protocol (E91). In this protocol, a source generates pairs of entangled photons and sends one photon to Alice and the other to Bob. Both parties randomly choose measurement bases and record their outcomes.

The security of the protocol relies on testing Bell’s inequality. If the measurement correlations violate Bell’s inequality, Alice and Bob can be confident that their shared key is secure and that no eavesdropper has tampered with the system.

A commonly used Bell inequality is the CHSH inequality:

$$
S = E(a, b) + E(a, b') + E(a', b) - E(a', b')
$$

Where:
- \( E(a, b) \) represents the correlation between measurements
- Classical systems satisfy \( |S| \leq 2 \)
- Quantum entanglement allows \( |S| \leq 2\sqrt{2} \)

A violation of this inequality confirms the presence of entanglement and guarantees that the shared key is fundamentally secure.

---

## 5. Cryptographic Advantage of Entanglement

The main cryptographic advantage of entanglement is **information-theoretic security**, meaning security does not depend on the computational power of an attacker. Classical cryptographic systems rely on mathematical problems that are assumed to be hard to solve, such as factoring large numbers. In contrast, entanglement-based cryptography remains secure even against attackers with unlimited computational resources.

Another advantage is **eavesdropper detection**. Any attempt to observe or intercept an entangled particle alters its quantum state. This makes passive eavesdropping impossible without leaving detectable traces. Unlike classical communication, where copying data is trivial, quantum information cannot be cloned due to the no-cloning theorem:

$$
|\psi\rangle \neq |\psi\rangle |\psi\rangle
$$

This theorem ensures that quantum states cannot be duplicated perfectly, preventing attackers from secretly copying cryptographic keys.

Entanglement also enables **device-independent cryptography**, where security can be guaranteed even if the physical devices used are partially untrusted. By observing Bell inequality violations, users can confirm security without knowing the internal workings of their devices.

---

## 6. Comparison with Classical Cryptography

In classical cryptography, secrecy depends on assumptions such as limited computational power or the difficulty of mathematical problems. If these assumptions fail, the entire system becomes vulnerable. Entanglement-based cryptography, however, is protected by physical laws that cannot be bypassed without violating quantum mechanics.

Classical key distribution requires secure channels or trusted intermediaries, whereas entanglement allows keys to be established securely over public channels. Any interception attempt is automatically revealed through error analysis and correlation testing.

---

## 7. Conclusion

Quantum entanglement provides a revolutionary foundation for cryptography by enabling secure key sharing, guaranteed eavesdropper detection, and information-theoretic security. Its non-classical correlations allow cryptographic protocols that are fundamentally more secure than classical methods. As quantum technologies advance, entanglement-based cryptography is expected to play a crucial role in protecting sensitive information against both classical and quantum threats.

---

## 8. Key Takeaways

- Quantum entanglement links particles in a way that defies classical physics.
- It enables secure secret sharing through perfectly correlated measurements.
- Any eavesdropping attempt introduces detectable disturbances.
- Entanglement-based cryptography offers security guaranteed by physical laws.
- It is resistant to future quantum computing attacks.


---

**Written By** : Shreya Palase

**Date** : 31-Jan-2026

Thank you and keep Learning!

---
