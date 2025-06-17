---
title: "Quantum Mechanics and Random Numbers: A Guide to DIQRNGs"
layout: post
author: Ganga Singh Manchanda
category: physics
---



## 1. Introduction

In this article we're going to think about randomness. Everyone has some sort of belief in randomness, most common those beliefs is that it exists. For the most part however our lives and experiences and ideas aren't random, they are shaped by previous actions and events and interactions. If I asked you to shout out a random number right now, even that isn't truly random because we all carry these inherent biases around with us as if it was baggage. Specific numbers have special associations (a birthday for example) and some numbers are just pleasing to think about (7 I'm looking at you) and this all makes a human a terrible random number generator. Ask a computer then, surely a sufficiently powerful computer can produce a random number. And it can, but given enough information that 'random' number can be predicted because classical computers rely on a seed which is usually based on something `random' from the real world. Another solution is necessary then. A number of applications such as secure communication and probabilistic modelling require randomness, and if the randomness is predictable then these applications fail. Quantum Mechanics will provide us that solution in the form of a **Device-Independent Quantum Random Number Generator (DIQRNG)**

> 'God does not play dice with the universe' - Albert Einstein

> 'He sure does' - Ganga Singh Manchanda

---

## 2. Bell Nonlocality and Randomness

### 2.1. Local Hidden Variables and Bell Inequalities

Assume Alice and Bob share a bipartite system and perform local measurements. A local hidden variable (LHV) model assumes the joint distribution of outcomes can be written as:
\[ P(a, b | x, y) = \int d\lambda \, \rho(\lambda) P(a|x,\lambda) P(b|y,\lambda) \]
where:
- $$ \lambda $$: hidden variable shared between the parties
- $$ x, y $$: measurement settings
- $$ a, b $$: outcomes
- $$ \rho(\lambda) $$: probability distribution over hidden variables

A **Bell inequality** is a constraint that must be satisfied by any such LHV model. The **CHSH inequality** is the most well-known:

$$ S = |E(00) + E(01) + E(10) - E(11)| \leq 2 $$

Here, the correlation function \( E(xy) \) is defined as:

$$ E(xy) = \sum_{a,b} (-1)^{a \oplus b} P(a, b | x, y) $$

Quantum mechanics allows:

$$ S_{\text{max}} = 2\sqrt{2} \approx 2.828 $$

This quantum violation of the CHSH bound indicates **nonlocality** and, importantly, **intrinsic randomness**.

---

### 2.2. Randomness from Bell Violation

If the outcome of a measurement can’t be explained by any deterministic model (due to Bell violation), then it must contain randomness. In DIQRNG, we exploit this by:

- Generating measurement outcomes via entangled quantum states.
- Violating a Bell inequality in a statistically significant way.
- Using the amount of violation to quantify the amount of extractable randomness.

---

## 3. Mathematical Formalism

### 3.1. Modeling the Experiment

Assume a repeated experiment over \( n \) rounds.

At each round:
- Alice chooses input $$ x_i \in \{0,1\} $$, Bob chooses $$ y_i \in \{0,1\} $$.
- They receive outputs $$ a_i, b_i \in \{0,1\} $$.
- The observed frequencies define the empirical conditional probabilities:

$$ \hat{P}_n(a,b|x,y) = \frac{1}{n_{x,y}} \sum_{i=1}^n \delta_{x_i,x} \delta_{y_i,y} \delta_{a_i,a} \delta_{b_i,b} $$

A Bell inequality (e.g., CHSH) is evaluated on this empirical distribution.

### 3.2. Min-Entropy and Guessing Probability

The **min-entropy** of Alice’s outcome given adversary’s side information $$ E $$ is:

$$ H_{\min}(A|E) = -\log_2 P_{\text{guess}}(A|E) $$

Where $$ P_{\text{guess}} $$ is the maximum probability that an adversary with access to $$ E $$ can correctly guess Alice’s output. From a CHSH violation $$ S $$, one can lower-bound the min-entropy using known results (Pironio et al. 2010):

$$ H_{\min}(A|E) \geq 1 - \log_2\left(1 + \sqrt{2 - \frac{S^2}{4}}\right) $$

This gives the number of **certified bits of randomness per round**.

---

### 3.3. Entropy Accumulation Theorem (EAT)

For a sequence of quantum measurements, the **Entropy Accumulation Theorem** (EAT) provides a way to bound the total min-entropy over \( n \) rounds.

Let each round be modeled by a **quantum instrument** \( \mathcal{M}_i \), and suppose the outcome statistics satisfy an EAT channel structure. Then:

$$ H_{\min}^{\epsilon}(A^n | E) \geq n \cdot h_{\text{min}}(S) - \Delta(n, \epsilon) $$

where:
- $$ h_{\text{min}}(S) $$: per-round min-entropy rate as a function of the Bell violation
- $$ \Delta(n, \epsilon) $$: finite-size correction term, logarithmic in \( 1/\epsilon \)

This allows randomness certification in **finite-size experiments**.

---

## 4. Protocol Outline

A full DIQRNG protocol proceeds as follows:

### Step 1: Entanglement Source

Generate pairs of entangled particles in state \( |\psi\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle) \) using, for example, SPDC.

### Step 2: Random Input Selection

Use independent weak random sources (or prior randomness) to choose measurement settings \( x_i \), \( y_i \). These should be space-like separated to maintain the no-signaling assumption.

### Step 3: Measurement and Outcome Collection

Perform measurements and record inputs and outputs:
- $$ X^n = (x_1, \dots, x_n) $$
- $$ Y^n = (y_1, \dots, y_n) $$
- $$ A^n = (a_1, \dots, a_n) $$
- $$ B^n = (b_1, \dots, b_n) $$

### Step 4: CHSH Evaluation and Entropy Estimation

Estimate empirical CHSH value $$ \hat{S}_n $$. Use this to bound the min-entropy $$ H_{\min}(A^n|E) $$ via EAT.

### Step 5: Randomness Extraction

Apply a **quantum-proof randomness extractor**, such as Trevisan’s extractor, to produce a nearly uniform output string \( R \) with:

$$ R = \text{Ext}(A^n, \text{seed}) $$

This seed can be reused if the extractor is strong.

---

## 5. Randomness Extraction

### 5.1. Extractors and Adversaries

Given $$ A^n $$ with high min-entropy conditioned on quantum side information \( E \), we apply an extractor:

$$ \text{Ext}: \{0,1\}^n \times \{0,1\}^d \to \{0,1\}^m $$

such that $$ \| \rho_{R,E} - \tau_m \otimes \rho_E \|_{\text{tr}} \leq \epsilon $$, i.e., the extracted output is $$ \epsilon $$-close to uniform and independent of the adversary's state.

### 5.2. Toeplitz Hashing and Trevisan Extractors

- **Toeplitz hashing**: Efficient, uses fast matrix multiplication, and requires minimal seed.
- **Trevisan’s extractor**: Provably secure against quantum side information, but more computationally intensive.

---

## 6. Security Assumptions

### 6.1. Assumptions in DIQRNG

1. **Quantum Mechanics**: The systems behave according to quantum theory.
2. **No-Signaling**: Measurements are performed in space-like separated regions.
3. **Measurement Independence**: Inputs $$ x $$, $$ y $$ are independent of hidden variables $$ \lambda $$.
4. **Trusted Extractor**: The randomness extractor must be correctly implemented and independent of the devices.
5. **Finite Statistics Accounted For**: All error probabilities are bounded within acceptable $$ \epsilon $$-security margins.

---

### 6.2. Composability

Modern DIQRNG protocols are designed to be **composable**, i.e., the security guarantees hold even when used as part of a larger cryptographic protocol.

Security is quantified via the **trace distance**:

$$ \| \rho_{R,E} - \tau_m \otimes \rho_E \|_{\text{tr}} \leq \epsilon $$

where $$ R $$ is the output string and $$ \tau_m $$ is the uniform distribution over $$ m $$ bits.

---

## 7. Practical Implementations and Challenges

### 7.1. Experimental Considerations

- **Detector efficiency**: Must exceed the threshold (~75% for CHSH).
- **Timing synchronization**: Measurement events must be precisely coordinated.
- **Input randomness**: Even the weak randomness used to choose measurement settings must be unpredictable.

### 7.2. Recent Experimental Milestones

- **Hensen et al. (2015)**: First loophole-free Bell test using entangled NV centers.
- **Liu et al. (2018)**: Real-time DIQRNG implementation generating 6.5 kb of randomness in ~96 hours.
- **Big Bell Test (2018)**: Human-generated random numbers used to close the freedom-of-choice loophole.

---

## 8. Conclusion

Device-independent quantum random number generation represents the **gold standard** of randomness certification. By harnessing quantum nonlocality and removing trust assumptions on hardware, DIQRNG protocols provide robust, cryptographically secure random numbers even in adversarial settings.

While current implementations are limited by efficiency and generation rate, continued progress in quantum hardware, integrated optics, and fast extractors is expected to make DIQRNGs increasingly practical and foundational for future quantum technologies.

---

## References

1. Pironio, S. et al., *Random numbers certified by Bell’s theorem*, Nature 464, 1021 (2010).
2. Arnon-Friedman, R. et al., *Practical device-independent quantum cryptography via entropy accumulation*, Nat. Commun. 9, 459 (2018).
3. Colbeck, R., Renner, R., *Free randomness can be amplified*, Nat. Phys. 8, 450 (2012).
4. Hensen, B. et al., *Loophole-free Bell inequality violation using electron spins separated by 1.3 kilometres*, Nature 526, 682 (2015).
5. Liu, Y. et al., *Device-Independent Quantum Random Number Generation*, Nature 562, 548 (2018).

