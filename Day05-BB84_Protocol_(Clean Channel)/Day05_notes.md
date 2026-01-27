# Day5 Notes - BB84 Quantum Key Distribution Protocol (Clean Channel)

## 1. Introduction to Quantum Key Distribution (QKD)
Quantum Key Distribution enables two distant parties to establish a shared secret key using quantum mechanical principles. Unlike classical cryptography, 
its security does not rely on computational hardness. BB84 is the first and most widely studied QKD protocol.

---

## 2. Overview of BB84 Protocol
The BB84 protocol was proposed by Bennett and Brassard in 1984. It uses single-photon polarization states to encode classical bits. 
Security is guaranteed by quantum properties such as measurement disturbance and superposition.

---

## 3. Communication Model
BB84 uses two channels:
- A **quantum channel** for transmitting qubits.
- A **classical public channel** for protocol coordination.

The quantum channel must preserve quantum states, while the classical channel need only be authenticated.

---

## 4. Quantum Bases Used in BB84
BB84 employs two mutually unbiased bases: computational (Z) and diagonal (X). Measuring a state in the wrong basis yields a random result.  
The basis states are defined as  

$$
\text{Z-basis: } \{|0\rangle, |1\rangle\}
$$

$$
\text{X-basis: } \{|+\rangle, |-\rangle\}
$$

---

## 5. Mathematical Representation of Diagonal States
Diagonal basis states are superpositions of computational basis states. This superposition causes measurement uncertainty under basis mismatch.

$$
|+\rangle = \frac{|0\rangle + |1\rangle}{\sqrt{2}}
$$

$$
|-\rangle = \frac{|0\rangle - |1\rangle}{\sqrt{2}}
$$

---

## 6. Random Bit and Basis Selection by Alice
Alice generates two random sequences: one for classical bits and one for bases. Each bit is encoded into a qubit according to the chosen basis. 
Randomness is essential to prevent predictability.

---

## 7. Quantum State Transmission
Alice sends the prepared qubits sequentially through a clean quantum channel. 
Since the channel is ideal, no noise or photon loss occurs. The quantum states reach Bob unchanged.

---

## 8. Measurement Strategy of Bob
Bob randomly chooses a basis (Z or X) for measuring each incoming qubit. 
If his chosen basis matches Alice’s, the correct bit value is obtained with certainty. Otherwise, the outcome is random.

---

## 9. Role of Basis Mismatch
When Alice and Bob use different bases, Bob’s measurement result has equal probabilities of being 0 or 1.  

$$
P(0) = P(1) = \frac{1}{2}
$$  

These outcomes provide no reliable information and are excluded from the final key.

---

## 10. Basis Reconciliation Using Classical Channel
After transmission, Alice and Bob publicly compare their basis choices. Bit values are never disclosed.
Only measurements with matching bases are kept for further processing.

---

## 11. Safety of Classical Communication
Classical communication reveals no secret information. Even if intercepted, it cannot be used to reconstruct the key.  
Security relies on the fact that quantum measurement outcomes remain private.

---

## 12. Sifted Key Generation
The bits corresponding to matching bases form the sifted key. In a clean channel, all sifted bits are identical for Alice and Bob.  
The expected length of the sifted key is  

$$
\frac{N}{2}
$$  

where  $N$ is the number of transmitted qubits.

---

## 13. Quantum Bit Error Rate (QBER)
QBER measures the fraction of incorrect bits in the sifted key. For a clean channel with no noise or interference,  

$$
\text{QBER} = 0
$$  

This confirms perfect correlation between Alice and Bob.

---

## 14. Error Correction Requirement
Since the QBER is zero in a clean channel, error correction procedures are unnecessary. All sifted bits are already identical and error-free.

---

## 15. Privacy Amplification
Privacy amplification is used to reduce Eve’s information in real-world scenarios. In an ideal clean channel without eavesdropping, this step is not required.

---

## 16. No-Cloning Theorem and Security
The no-cloning theorem prohibits copying an unknown quantum state.  

$$
|\psi\rangle \nrightarrow |\psi\rangle|\psi\rangle
$$  

This prevents any undetectable interception of quantum data.

---

## 17. Key Rate in Ideal Conditions
The asymptotic key generation rate for BB84 in a clean channel is  

$$
R = \frac{1}{2}
$$  

Half of the transmitted qubits contribute directly to the final key.

---

## 18. Final Secret Key
After sifting, the remaining bits form the final shared secret key. This key can be used in symmetric encryption algorithms such as the one-time pad or AES.

---

## 19. Advantages of BB84 Protocol
- Provably secure using quantum mechanics
- Simple and experimentally realizable
- Detects any unauthorized observation

---

## 20. Limitations in Practical Systems
Real-world implementations face noise, photon loss, and detector inefficiencies. These require additional steps like error correction and privacy amplification.

---

## 21. Importance of BB84 in Quantum Cryptography
BB84 laid the foundation for all modern QKD protocols. It provides a practical demonstration of unconditional security and 
remains a reference model in quantum communication research.

---

**Written By** : Shreya Palase

**Date** : 27-January-2026

Thank you and keep Learning!
