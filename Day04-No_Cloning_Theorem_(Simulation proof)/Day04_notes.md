# Day4 Notes - **No-Cloning Theorem (Quantum Computing)**

---

## **1. Introduction and Foundation**

Quantum mechanics fundamentally differs from classical physics in how information is represented and manipulated.  
In classical systems, information can be copied perfectly without disturbing the original. However, quantum information is encoded in **quantum states**, which may exist in **superpositions** and are governed by linear operators.  
The **No-Cloning Theorem** formalizes the impossibility of creating an identical copy of an **unknown arbitrary quantum state**.

This theorem is not a technological limitation but a **fundamental law of nature** derived directly from the postulates of quantum mechanics.

---

## **2. Statement of the No-Cloning Theorem**

**Statement:**  
> It is impossible to construct a universal quantum machine that can perfectly copy (clone) an arbitrary unknown quantum state.

More formally, there exists **no unitary operator** that can clone all possible quantum states.  
This means that **non-orthogonal states cannot be copied**, although orthogonal states can be duplicated if known.

The theorem preserves the intrinsic randomness and privacy of quantum information.

---

## **3. Mathematical Description of a Quantum State**

A general quantum state (qubit) is represented as:

$$
|\psi\rangle = \alpha |0\rangle + \beta |1\rangle
$$

where:

- $$\alpha, \beta \in \mathbb{C}$$  
- $$|\alpha|^2 + |\beta|^2 = 1$$

An unknown quantum state means the coefficients $$\alpha$$ and $$\beta$$ are not known to the observer.

---

## **4. Assumption of a Cloning Operation**

Assume there exists a **quantum cloning machine** represented by a unitary operator $$U$$ such that:

$$
U \left(|\psi\rangle \otimes |0\rangle \right) = |\psi\rangle \otimes |\psi\rangle
$$

Here:

- $$|\psi\rangle$$ is the state to be cloned  
- $$|0\rangle$$ is a fixed blank state  
- $$U$$ acts universally for all states

This assumption will be shown to be invalid.

---

## **5. Simulation Proof of the No-Cloning Theorem**

Consider two arbitrary quantum states:

$$
|\psi\rangle \quad \text{and} \quad |\phi\rangle
$$

If cloning were possible, then:

$$
U(|\psi\rangle |0\rangle) = |\psi\rangle |\psi\rangle
$$

$$
U(|\phi\rangle |0\rangle) = |\phi\rangle |\phi\rangle
$$

Now take the inner product of these two results:

$$
\langle \psi | \phi \rangle = \langle \psi | \phi \rangle^2
$$

This implies:

$$
\langle \psi | \phi \rangle (1 - \langle \psi | \phi \rangle) = 0
$$

So:

$$
\langle \psi | \phi \rangle = 0 \quad \text{or} \quad 1
$$

### **Conclusion of Proof**

- States must be **orthogonal** or **identical** to be cloned  
- Arbitrary quantum states are generally **non-orthogonal**

➡️ Hence, **universal cloning is impossible**.

---

## **6. Why Copying Quantum States Breaks Cryptography**

Quantum cryptography relies on the fact that **quantum states cannot be copied without disturbance**.  
If cloning were possible, an attacker could duplicate transmitted quantum bits and measure them later without detection.

This would eliminate the fundamental security advantage of quantum communication over classical methods.  
The no-cloning theorem ensures that **quantum encryption is information-theoretically secure**, not just computationally secure.

---

## **7. Security Implications for Eavesdropping**

In protocols like **BB84**, an eavesdropper (Eve) may try to intercept and copy quantum states.

Due to no-cloning:

- Eve cannot copy the qubit  
- Measuring the qubit **disturbs its state**  
- Disturbance introduces detectable errors  

Thus, any eavesdropping attempt leaves a measurable trace, alerting the legitimate users.

---

## **8. Measurement Disturbance and Information Leakage**

Quantum measurement collapses the wavefunction:

$$
|\psi\rangle \rightarrow |0\rangle \quad \text{or} \quad |1\rangle
$$

Eve must measure to gain information, but measurement irreversibly alters the state.  
This property, combined with no-cloning, ensures **zero-knowledge leakage without detection**.

---

## **9. Relation to Linearity of Quantum Mechanics**

Quantum evolution is linear:

$$
U(\alpha |\psi\rangle + \beta |\phi\rangle) = \alpha U|\psi\rangle + \beta U|\phi\rangle
$$

Cloning would require a **nonlinear operation**, which violates quantum postulates.  
Thus, the no-cloning theorem arises naturally from **linearity and unitarity**.

---

## **10. Approximate and Probabilistic Cloning (Advanced Concept)**

Although perfect cloning is impossible, **approximate cloning** is allowed.

For example, **Bužek–Hillery quantum cloning machine** produces imperfect copies with fidelity:

$$
F = \frac{5}{6}
$$

Such cloning still introduces errors and cannot break cryptographic security.

---

## **11. No-Cloning vs No-Deleting Theorem**

The **No-Deleting Theorem** states that quantum information cannot be destroyed completely.  
Together, these theorems imply **quantum information is conserved**, unlike classical data.

This strengthens the conceptual foundation of quantum information theory.

---

## **12. Impact on Quantum Computing**

- Prevents copying of intermediate quantum states  
- Enforces use of **entanglement and teleportation**  
- Influences quantum error correction design  

Quantum algorithms must work without duplicating data, unlike classical algorithms.

---

## **13. Role in Quantum Teleportation**

Quantum teleportation does **not violate no-cloning** because:

- Original state is destroyed during measurement  
- Only one copy exists at any time  

This confirms consistency of teleportation with quantum laws.

---

## **14. Summary of Key Points**

- Perfect cloning of unknown quantum states is impossible  
- Proof arises from linearity and inner product preservation  
- Ensures security of quantum cryptography  
- Prevents undetectable eavesdropping  
- Influences quantum computing and communication  
- Only approximate cloning is allowed  

---

**Written By:** Shreya Palase

**Date** - 26-january-2026

Thank you and keep learning!
