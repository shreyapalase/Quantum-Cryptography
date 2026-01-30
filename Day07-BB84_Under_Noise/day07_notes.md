# Day7 Notes - BB84 Protocol Under Noise 

## Introduction

The BB84 protocol is the first and most fundamental **Quantum Key Distribution (QKD)** protocol, proposed by Bennett and Brassard in 1984. Its security relies on the principles of **quantum mechanics**, particularly the **no-cloning theorem** and **measurement disturbance**. In an ideal theoretical setting, BB84 assumes a noiseless quantum channel and perfect devices. However, in real-world implementations, **quantum noise** is unavoidable and significantly affects the performance and security of the protocol. Noise introduces errors in the transmitted qubits, which may resemble the effects of an eavesdropping attack. Therefore, understanding BB84 under noisy conditions is essential to distinguish between **natural channel imperfections** and **malicious attacks**, and to design practical and secure QKD systems.

---

## Quantum Noise Sources in BB84 Protocol

Quantum noise refers to random and uncontrollable disturbances that affect the quantum states during preparation, transmission, or measurement. In BB84, Alice encodes classical bits into quantum states using two conjugate bases (rectilinear and diagonal), and Bob measures these states after transmission through a quantum channel. During this process, noise can alter the quantum states, causing Bob’s measurement outcomes to differ from Alice’s original bits even when no eavesdropper is present.

One major source of quantum noise is **channel noise**, which arises due to interaction between the transmitted photons and the environment. In optical fiber-based QKD systems, effects such as **photon absorption, scattering, and birefringence** can cause polarization changes or photon loss. In free-space QKD, atmospheric turbulence and background radiation introduce similar disturbances. These environmental interactions can be modeled as quantum decoherence, where the purity of the quantum state degrades over time.

Mathematically, noise in a quantum channel is often modeled using a **quantum depolarizing channel**. If Alice sends a qubit state \( \rho \), the noisy channel transforms it as:

$$
\rho' = (1 - p)\rho + \frac{p}{3}(\sigma_x \rho \sigma_x + \sigma_y \rho \sigma_y + \sigma_z \rho \sigma_z)
$$

Here, \( p \) represents the probability of noise, and \( \sigma_x, \sigma_y, \sigma_z \) are the Pauli operators. This equation shows that with probability \( p \), the qubit undergoes a random error, leading to incorrect measurement outcomes at Bob’s side.

Another important noise source is **detector noise**, which includes dark counts and imperfect detection efficiency. Dark counts occur when a detector clicks even in the absence of a photon, introducing random bits into the key. Similarly, **state preparation errors** at Alice’s side can cause deviations from the intended quantum states. All these noise sources collectively increase the **Quantum Bit Error Rate (QBER)** in the BB84 protocol.

---

## Difference Between Noise and Attack in BB84

A critical challenge in BB84 under noisy conditions is distinguishing between **quantum noise** and an **eavesdropping attack**. Noise is a natural, unintentional phenomenon caused by imperfect hardware and environmental interactions, whereas an attack is a deliberate attempt by an eavesdropper (Eve) to gain information about the secret key.

In the BB84 protocol, an eavesdropper typically performs an **intercept-resend attack**, where Eve measures the qubits sent by Alice and resends new qubits to Bob. Since Eve does not know which basis Alice used, her measurements disturb the quantum states, introducing detectable errors. This disturbance increases the QBER in a way that is statistically distinguishable from an ideal noiseless channel.

For example, in an intercept-resend attack, Eve randomly chooses a measurement basis. With probability \( \frac{1}{2} \), she chooses the wrong basis, which leads to an incorrect state being resent to Bob. This results in a theoretical QBER of:

$$
\text{QBER}_{\text{attack}} = 25\%
$$

In contrast, noise-induced errors usually lead to a **lower and more stable QBER**, depending on channel quality. The total observed QBER in a practical system can be expressed as:

$$
\text{QBER}_{\text{total}} = \text{QBER}_{\text{noise}} + \text{QBER}_{\text{attack}}
$$

The key idea is that while both noise and attacks increase QBER, **attacks introduce additional correlations** between Eve’s information and Bob’s measurement results. BB84 uses **error rate estimation and privacy amplification** to ensure security as long as the observed QBER remains below a certain threshold (typically around 11% for standard BB84 with one-way classical communication). If the QBER exceeds this threshold, the protocol is aborted, as it becomes impossible to guarantee secrecy.

---

## Practical QKD Simulation Under Noise

Practical QKD simulations play a crucial role in understanding the performance of BB84 under realistic noisy conditions. These simulations model the entire QKD process, including state preparation, quantum channel noise, measurement, classical post-processing, and key generation. By introducing controlled noise parameters, researchers can evaluate the robustness and efficiency of the BB84 protocol.

In a typical simulation, Alice generates a random bit string and a random basis string. Each bit is encoded into a quantum state and transmitted through a noisy channel. The noise is introduced using probabilistic error models such as bit-flip, phase-flip, or depolarizing noise. Bob measures the incoming qubits using randomly chosen bases, and then Alice and Bob perform **basis reconciliation** over a public classical channel.

The effect of noise is quantified using the **Quantum Bit Error Rate**, defined as:

$$
\text{QBER} = \frac{\text{Number of incorrect bits}}{\text{Total number of compared bits}}
$$

Once QBER is estimated, **error correction** algorithms such as Cascade or LDPC codes are applied to reconcile discrepancies between Alice’s and Bob’s keys. However, error correction leaks some information to Eve, which must be removed using **privacy amplification**. The final secure key rate \( R \) can be approximated as:

$$
R = 1 - 2H(\text{QBER})
$$

where \( H(x) \) is the binary Shannon entropy given by:

$$
H(x) = -x\log_2 x - (1 - x)\log_2(1 - x)
$$

This equation highlights how increasing noise directly reduces the achievable secure key rate. Practical simulations help determine acceptable noise levels, optimal system parameters, and realistic security margins for real-world QKD implementations.

---

## Conclusion

The study of BB84 under noise is essential for bridging the gap between theoretical quantum cryptography and practical secure communication systems. Quantum noise originates from environmental interactions and imperfect devices, while attacks are intentional actions by an eavesdropper. Although both lead to increased error rates, BB84 employs statistical analysis and post-processing techniques to ensure security as long as the noise remains below a critical threshold. Practical QKD simulations provide valuable insights into system performance, allowing researchers to evaluate security, optimize designs, and move closer to large-scale deployment of quantum-secure communication networks.

---

**Written By** : Shreya Palase

**Date** : 30-Jan-2026

Thank You and Keep Learning!
