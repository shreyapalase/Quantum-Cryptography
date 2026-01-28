# Day6 Notes - BB84 Quantum Key Distribution (QKD) Protocol, Intercept–Resend Attack, QBER, and Security Concepts

---

## 1. Introduction to BB84 Protocol

The BB84 protocol, proposed in 1984 by Charles Bennett and Gilles Brassard, is the first and most fundamental **Quantum Key Distribution (QKD)** protocol. Its goal is to allow two legitimate parties, traditionally called **Alice** (sender) and **Bob** (receiver), to establish a **shared secret key** over an insecure quantum channel in the presence of a potential eavesdropper known as **Eve**. The security of BB84 does not rely on computational assumptions but instead on the **laws of quantum mechanics**, particularly the principles of **quantum superposition**, **measurement disturbance**, and the **no-cloning theorem**.

In BB84, Alice encodes classical bits into **quantum states (qubits)** using two different bases. Bob measures the received qubits using randomly chosen bases. After the quantum transmission phase, Alice and Bob communicate over a public classical channel to compare bases (not measurement results), discard mismatched measurements, and obtain a **raw key**. Any eavesdropping attempt necessarily introduces detectable errors, which allows Alice and Bob to assess the security of the channel.

---

## 2. Quantum States and Encoding in BB84

BB84 uses **two mutually unbiased bases**:

1. **Rectilinear (Z) Basis**
   - $$|0\rangle$$
   - $$|1\rangle$$

2. **Diagonal (X) Basis**
   - $$|+\rangle = \frac{|0\rangle + |1\rangle}{\sqrt{2}}$$
   - $$|-\rangle = \frac{|0\rangle - |1\rangle}{\sqrt{2}}$$

Alice randomly selects a bit value (0 or 1) and a basis (Z or X) and prepares the corresponding quantum state. 
Bob independently and randomly chooses a basis for measurement. If Bob measures in the same basis used by Alice, he obtains the correct bit with probability 1. If the bases differ, the measurement outcome is completely random due to the orthogonality properties of quantum states.

---

## 3. Intercept–Resend Attack

The **Intercept–Resend attack** is the simplest and most illustrative eavesdropping strategy in BB84. In this attack, Eve intercepts each qubit sent by Alice, measures it using a randomly chosen basis (Z or X), and then resends a new qubit to Bob based on her measurement result.

The key weakness of Eve’s strategy lies in the fact that she **does not know which basis Alice used**. If Eve measures in the wrong basis, she collapses the quantum state into a random outcome. When she resends this disturbed state to Bob, even if Bob chooses the correct basis, the original information may already be lost. This unavoidable disturbance is a direct consequence of the **quantum measurement postulate**, which states that measuring a quantum system generally alters its state unless the system is already in an eigenstate of the measurement operator.

---

## 4. Mathematical Analysis of Intercept–Resend Attack

Let us analyze the error introduced by Eve quantitatively.

- Probability that Eve chooses the **correct basis**:
  
$$
P_{\text{Eve correct}} = \frac{1}{2}
$$

- Probability that Eve chooses the **wrong basis**:
  
$$
P_{\text{Eve wrong}} = \frac{1}{2}
$$

If Eve measures in the wrong basis, she sends a qubit that has a **50% probability of being incorrect** when Bob measures it in the correct basis.

Thus, the overall probability of an error introduced by Eve is:

$$
\text{QBER} = \frac{1}{2} \times \frac{1}{2} = \frac{1}{4} = 25\%
$$

This means that an intercept–resend attack introduces a **25% Quantum Bit Error Rate**, which is significantly higher than normal channel noise.

---

## 5. Quantum Bit Error Rate (QBER)

The **Quantum Bit Error Rate (QBER)** is defined as the fraction of bits where Alice’s and Bob’s measurement results disagree:

$$
\text{QBER} = \frac{\text{Number of incorrect bits}}{\text{Total number of compared bits}}
$$

After the raw key is generated, Alice and Bob publicly compare a randomly chosen subset of bits. If the observed QBER exceeds a predefined threshold, they conclude that an eavesdropper is present and **abort the protocol**. In ideal BB84, a QBER close to 0% is expected. A QBER near 25% is a strong indication of an intercept–resend attack.

---

## 6. How QBER Reveals Eve

The fundamental reason QBER reveals Eve is that **quantum information cannot be measured without disturbance**. Eve’s measurement introduces randomness that propagates forward to Bob’s measurements. Even though Eve may correctly guess the basis some of the time, her incorrect guesses create statistically detectable inconsistencies.

Unlike classical eavesdropping, where copying information can be done invisibly, quantum eavesdropping leaves a **measurable footprint**. By comparing a subset of their bits, Alice and Bob can estimate the error rate of the channel. If this error exceeds what can be explained by normal noise, Eve’s presence is confirmed with high confidence.

---

## 7. Security Threat Concept in BB84

The **security threat model** in BB84 assumes that Eve has unlimited computational power and full access to the quantum and classical channels, except that she cannot violate the laws of quantum mechanics. The protocol’s security is based on three key quantum principles:

1. **No-Cloning Theorem**  
   Eve cannot make perfect copies of unknown quantum states.

2. **Measurement Disturbance**  
   Any measurement by Eve alters the quantum state.

3. **Random Basis Selection**  
   Eve cannot predict Alice’s or Bob’s choices.

Even more sophisticated attacks than intercept–resend (such as collective and coherent attacks) are also detectable and can be mitigated through **error correction** and **privacy amplification**. As long as the QBER remains below a critical threshold (approximately 11% for BB84), a secure key can still be extracted.

---

## 8. Conclusion

The BB84 protocol demonstrates how quantum mechanics enables fundamentally secure communication. The intercept–resend attack clearly illustrates why eavesdropping is detectable: Eve’s lack of basis information forces her to introduce errors. The Quantum Bit Error Rate acts as a powerful diagnostic tool that transforms quantum disturbances into classical evidence of an attack. Through this mechanism, BB84 achieves security not by secrecy of the protocol, but by the unavoidable physical consequences of quantum measurement.

---

## 9. Key Takeaways

- Intercept–resend attack causes **25% QBER**
- QBER is the primary indicator of eavesdropping
- Security relies on quantum laws, not computation
- BB84 remains secure even against powerful adversaries

---

**Written b ** : Shreya Palase

**Date** : 28-January-2026

Thank you and Keep Learning!
