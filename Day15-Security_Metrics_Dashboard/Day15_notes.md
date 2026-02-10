#  Day15 Notes - Security Metrics Dashboard for Quantum Key Distribution (QKD)

## 1. Introduction

A **Security Metrics Dashboard** in Quantum Key Distribution (QKD) is a comprehensive analytical framework designed to continuously observe, measure, and interpret the critical parameters that define the security and performance of a QKD system. Unlike classical cryptographic systems, whose security depends on computational hardness assumptions, QKD derives its security directly from the laws of quantum mechanics. This makes real-time monitoring of physical and informational parameters essential. The dashboard acts as a centralized decision-making layer that combines raw physical measurements with post-processing results to determine whether the generated cryptographic key is secure enough for use. It bridges the gap between abstract quantum theory and practical secure communication by transforming quantum measurements into actionable security judgments.

---

## 2. Quantum Bit Error Rate (QBER)

Quantum Bit Error Rate (QBER) is one of the most fundamental and sensitive security metrics in a QKD system. It represents the proportion of bits for which the sender (Alice) and the receiver (Bob) obtain different values after the quantum transmission and basis reconciliation steps. Mathematically, it is defined as:

$$
QBER = \frac{N_{error}}{N_{total}}
$$

QBER arises due to multiple factors such as channel noise, imperfect optical components, detector dark counts, and environmental disturbances. However, its most critical role is as an indicator of eavesdropping. According to quantum mechanics, any attempt by an eavesdropper (Eve) to measure or clone quantum states will inevitably disturb them, thereby increasing the error rate. Each QKD protocol has a maximum tolerable QBER threshold (for example, approximately 11% for BB84), beyond which secure key extraction becomes impossible. Thus, QBER functions as a real-time alarm system: if it exceeds the allowed threshold, the system automatically aborts the key generation process to maintain unconditional security.

---

## 3. Entropy

Entropy measures the degree of randomness present in the generated key and is directly related to its unpredictability. In QKD, high entropy is essential because any predictability in the key can be exploited by an adversary. Shannon entropy is commonly used to quantify this randomness and is given by:

$$
H(X) = -\sum_{i} p_i \log_2 p_i
$$

In an ideal QKD system, the probabilities of obtaining bit values 0 and 1 are equal, resulting in maximum entropy of 1 bit per symbol. Deviations from this ideal scenario indicate bias, which may arise from hardware imperfections, asymmetric losses, or information leakage to an eavesdropper. Entropy analysis allows the system to estimate how much usable randomness remains after accounting for errors and potential attacks. This estimation is crucial for determining the strength of the final key and for deciding how aggressively privacy amplification must be applied to eliminate any partial information that Eve might possess.

---

## 4. Key Rate

The key rate quantifies the efficiency and practicality of a QKD system by measuring how many secure key bits can be generated per second after all post-processing steps. It reflects not only the quality of the quantum channel but also the effectiveness of classical procedures such as error correction and privacy amplification. The final secure key rate is typically expressed as:

$$
R_{secure} = R_{raw} \left[1 - f_{EC}H(QBER) - H_{Eve}\right]
$$

Here, the raw key rate represents the initial bit generation speed before processing, while the subsequent terms account for information lost during error correction and the estimated knowledge of Eve. A high QBER or low entropy directly reduces the key rate because more bits must be discarded to preserve security. Therefore, the key rate serves as a holistic performance indicator that balances security requirements with operational feasibility. A positive secure key rate signifies that secure communication is achievable, whereas a zero or negative rate implies that the channel conditions are too poor or too compromised for safe use.

---

## 5. Mutual Information

Mutual information measures the amount of information shared between two parties and plays a critical role in assessing QKD security. The mutual information between Alice and Bob, denoted as $I(A:B)$, reflects how well correlated their keys are and is given by:

$$
I(A:B) = 1 - H(QBER)
$$

Conversely, the mutual information between Alice and Eve, $I(A:E)$, represents the maximum information an eavesdropper could have obtained about the key. Security in QKD fundamentally depends on maintaining the inequality:

$$
I(A:B) > I(A:E)
$$

This condition ensures that Bob has more information about the key than Eve, allowing Alice and Bob to distill a secure key through classical post-processing. If Eve’s information becomes comparable to or exceeds Bob’s, the protocol can no longer guarantee security. Mutual information thus provides a theoretical foundation for deciding whether secure key distillation is possible under observed channel conditions.

---

## 6. Privacy Amplification

Privacy amplification is a critical post-processing step that transforms a partially secure key into a fully secure one by reducing Eve’s information to a negligible level. Based on the estimated information leakage derived from QBER and entropy analysis, Alice and Bob apply hash functions to compress the key. The resulting key length is given by:

$$
L_{final} = L_{input} - I_{Eve}
$$

Although privacy amplification reduces the key length, it dramatically increases security by ensuring that any information potentially known to Eve becomes statistically insignificant. This step guarantees that the final key is suitable for cryptographic use, even if Eve had limited access to the raw key material.

---

## 7. Summary of Security Metrics

A security metrics dashboard does not rely on a single parameter but evaluates multiple metrics simultaneously. QBER detects disturbances and potential attacks, entropy measures randomness, key rate assesses practical usability, mutual information evaluates information dominance, and privacy amplification ensures final secrecy. The combined interpretation of these metrics enables robust, real-time security decisions that no individual parameter could provide on its own.

---

## 8. Judging QKD Security Using the Dashboard

The security of a QKD session is judged by applying strict acceptance criteria across all monitored metrics. The system verifies that QBER remains below protocol-defined thresholds, entropy is sufficiently high, mutual information favors legitimate users, and the final secure key rate is positive:

$$
R_{secure} > 0 \Rightarrow \text{Key is secure and usable}
$$

If any of these conditions fail, the dashboard triggers an automatic abort. This conservative decision-making approach ensures unconditional security, even in the presence of sophisticated attacks or adverse channel conditions.

---

## 9. Transition to the Project Phase

Once the security dashboard confirms that all metrics lie within acceptable bounds, the QKD system transitions from analysis to application. The validated secure key is exported to encryption modules such as AES or One-Time Pad systems. Simultaneously, dashboard data is logged for performance evaluation, auditing, and certification purposes. This transition marks the practical realization of QKD, where theoretical security guarantees are transformed into operational secure communication.

---

## 10. Additional Related Metrics

Detection efficiency measures the fraction of transmitted photons that are successfully detected and directly impacts both key rate and security. Channel loss quantifies signal attenuation over distance and influences vulnerability to certain attacks. Timing jitter reflects detector timing uncertainty and contributes to increased error rates. Finite key effects account for statistical fluctuations in real-world systems, where keys are not infinitely long, and are incorporated into security bounds through failure probabilities.

---

## 11. Conclusion

A Security Metrics Dashboard is the cornerstone of any practical QKD implementation. By continuously analyzing physical disturbances, informational leakage, and system performance, it ensures that only keys with provable quantum security are released for cryptographic use. Through the integrated evaluation of QBER, entropy, key rate, and related metrics, the dashboard transforms QKD from a theoretical concept into a reliable and deployable security technology.

---

**Written By** : Shreya Palase

**Date** : 09-Feb-2026

Thank you and keep learning!
