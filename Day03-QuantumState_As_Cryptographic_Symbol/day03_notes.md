#  Day3 Notes - Quantum State as a Cryptographic Symbol  

---

## 1. Introduction: Quantum States in Cryptography

Classical cryptography represents information using classical bits, which can take definite values 0 or 1. These symbols can be copied, read, and measured without altering the underlying information. As a result, classical cryptographic security depends largely on computational hardness assumptions.

Quantum cryptography replaces classical symbols with **quantum states**. A quantum state encodes information in physical properties such as polarization or phase of a photon. Due to the laws of quantum mechanics, these states cannot be observed or copied without causing detectable changes, making them ideal cryptographic symbols.

The security of quantum cryptography is therefore **physical**, not computational.

---

## 2. Mathematical Representation of Quantum States

### 2.1 Pure Quantum States

A pure quantum state describes a system with maximum possible information about its physical configuration. Mathematically, it is represented as a vector in a complex Hilbert space:

$$
|\psi\rangle \in \mathcal{H}
$$

For a two-level quantum system (qubit), the state can be written as:

$$
|\psi\rangle = \alpha |0\rangle + \beta |1\rangle
$$

Here, $|0\rangle$ and $|1\rangle$ are orthonormal basis states, and the complex amplitudes $\alpha$ and $\beta$ represent probability amplitudes. The normalization condition:

$$
|\alpha|^2 + |\beta|^2 = 1
$$

ensures that the total probability of all measurement outcomes is one.

---

### 2.2 Density Matrix Representation

In realistic cryptographic scenarios, quantum systems are often subject to noise, loss, or partial knowledge. Such systems are better described using **density matrices** rather than pure states.

A density matrix is defined as:

$$
\rho = \sum_i p_i |\psi_i\rangle \langle \psi_i|
$$

where $p_i$ represents the probability that the system is in state $|\psi_i\rangle$. Density matrices allow us to model mixed states, decoherence, and the presence of an eavesdropper.

Important properties of a density matrix are:

$$
\rho^\dagger = \rho,\quad \text{Tr}(\rho) = 1,\quad \rho \ge 0
$$

---

## 3. Orthogonal vs Non-Orthogonal Quantum States

### 3.1 Orthogonal Quantum States

Two quantum states are orthogonal if their inner product is zero:

$$
\langle \psi | \phi \rangle = 0
$$

Orthogonal states correspond to perfectly distinguishable physical states. A measurement exists that can identify these states with certainty and without error. This behavior closely resembles classical symbols.

For example:

$$
\langle 0 | 1 \rangle = 0
$$

Because of perfect distinguishability, orthogonal states do **not** provide intrinsic cryptographic security.

---

### 3.2 Non-Orthogonal Quantum States

Non-orthogonal states have a non-zero inner product:

$$
\langle \psi | \phi \rangle \neq 0
$$

A common example is:

$$
|+\rangle = \frac{|0\rangle + |1\rangle}{\sqrt{2}}, \quad
\langle 0 | + \rangle = \frac{1}{\sqrt{2}}
$$

Non-orthogonal states cannot be perfectly distinguished by any measurement. Any attempt to identify them introduces uncertainty and errors. This indistinguishability is a purely quantum phenomenon and forms the basis of quantum cryptographic security.

---

## 4. Why Non-Orthogonality Gives Security

### 4.1 Fundamental Measurement Limits

Quantum mechanics places strict limits on how well non-orthogonal states can be distinguished. For two non-orthogonal states $|\psi_0\rangle$ and $|\psi_1\rangle$, the minimum error probability satisfies:

$$
P_{\text{error}} \ge \frac{1}{2} \left(1 - \sqrt{1 - |\langle \psi_0 | \psi_1 \rangle|^2}\right)
$$

This inequality shows that an eavesdropper cannot identify the state without making errors. These unavoidable errors propagate into the communication channel and can be detected by legitimate users.

---

### 4.2 No-Cloning Theorem

The no-cloning theorem states that it is impossible to create an identical copy of an unknown quantum state. Formally, there exists no unitary operator $U$ such that:

$$
U |\psi\rangle |0\rangle = |\psi\rangle |\psi\rangle
$$

for all possible $|\psi\rangle$. This means an eavesdropper cannot copy a quantum state and defer measurement. Any interception attempt must involve direct measurement, which inevitably causes disturbance.

---

## 5. Information Gain vs Information Disturbance

### 5.1 Conceptual Understanding

In quantum mechanics, information extraction is not free. Whenever a measurement is performed to gain information about a quantum state, the state itself is altered. This leads to a trade-off between information gain and disturbance.

Let:

- $I_E$ denote the information gained by an eavesdropper
- $D$ denote the disturbance introduced into the system

Then qualitatively:

$$
I_E \uparrow \Rightarrow D \uparrow
$$

---

### 5.2 Quantitative Measures

Disturbance can be quantified using **state fidelity**, which measures how much a state changes after interaction:

$$
F(\rho, \rho') = \left( \text{Tr} \sqrt{\sqrt{\rho} \rho' \sqrt{\rho}} \right)^2
$$

Information gain is bounded by the **Holevo bound**, given by:

$$
\chi = S(\rho) - \sum_i p_i S(\rho_i)
$$

where the von Neumann entropy is defined as:

$$
S(\rho) = -\text{Tr}(\rho \log \rho)
$$

---

### 5.3 Cryptographic Consequences

As an eavesdropper attempts to gain more information, the disturbance increases. This disturbance manifests as an increased error rate in the shared key. Legitimate users can detect this by comparing a subset of their measurement results.

---

## 6. Confusion Matrix: Theory and Importance

### 6.1 Concept of Confusion Matrix

A confusion matrix is a structured way to represent how often transmitted quantum states are correctly or incorrectly identified after measurement. It provides a clear statistical picture of system performance.

In quantum cryptography, confusion matrices help analyze errors due to noise, imperfect detectors, or eavesdropping.

---

### 6.2 Mathematical Representation

For binary quantum states, a confusion matrix can be written as:

$$
C =
\begin{bmatrix}
P(0|0) & P(1|0) \\
P(0|1) & P(1|1)
\end{bmatrix}
$$

Each element represents the conditional probability of measuring a particular outcome given the transmitted state.

---

### 6.3 Importance in Security Analysis

Confusion matrices allow estimation of the **Quantum Bit Error Rate (QBER)**. A high QBER indicates potential eavesdropping or excessive noise. Security protocols define maximum tolerable QBER thresholds beyond which secure key generation is impossible.

---

### 6.4 Practical Implementation

In practice, confusion matrices are implemented using experimental measurement data. They are widely used in:

- Quantum key distribution experiments
- Optical communication systems
- Machine-learning-based quantum attack detection

---

## 7. Additional Relevant Concepts

### 7.1 Quantum State Discrimination

Quantum state discrimination studies how well quantum states can be distinguished under optimal measurements. For minimum-error discrimination:

$$
P_e = \frac{1}{2} \left(1 - \sqrt{1 - |\langle \psi_0 | \psi_1 \rangle|^2} \right)
$$

This theory directly quantifies the limits of eavesdropping strategies.

---

### 7.2 POVM Measurements

Positive Operator-Valued Measures (POVMs) generalize projective measurements and are defined as:

$$
\sum_i E_i = I, \quad E_i \ge 0
$$

POVMs allow more flexible measurement strategies and often maximize information gain, but they still cannot bypass the information–disturbance trade-off.

---

### 7.3 Security as a Physical Principle

Unlike classical cryptography, quantum cryptography derives its security from the mathematical structure of Hilbert spaces and the postulates of quantum mechanics. Security proofs are therefore independent of algorithmic or computational assumptions.

---

## 8. Conclusion

Quantum states function as cryptographic symbols because they obey physical laws that restrict information access. Non-orthogonality, measurement disturbance, and the impossibility of cloning ensure that any eavesdropping attempt leaves detectable traces. Tools such as confusion matrices and entropy measures allow precise security analysis, making quantum cryptography fundamentally secure.

---

**Written By :** Shreya Palase

**Date :** 22-Janaury-2026

Thank you and Keep Leraning!
