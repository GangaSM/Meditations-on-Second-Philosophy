---
title: "Bell Inequalities and Random Numbers: A Guide to DIQRNGs"
layout: post
author: Ganga Singh Manchanda
category: physics
---



In this article we're going to think about randomness. Everyone has some sort of belief in randomness, most common those beliefs is that it exists. For the most part however our lives and experiences and ideas aren't random, they are shaped by previous actions and events and interactions. If I asked you to shout out a random number right now, even that isn't truly random because we all carry these inherent biases around with us as if it was baggage. Specific numbers have special associations (a birthday for example) and some numbers are just pleasing to think about (7 I'm looking at you) and this all makes a human a terrible random number generator. Ask a computer then, surely a sufficiently powerful computer can produce a random number. And it can, but given enough information that 'random' number can be predicted because classical computers rely on a seed which is usually based on something `random' from the real world. Another solution is necessary then. A number of applications such as secure communication and probabilistic modelling require randomness, and if the randomness is predictable then these applications fail. Quantum Mechanics will provide us that solution in the form of a **Device-Independent Quantum Random Number Generator (DIQRNG)**

> 'God does not play dice with the universe' - Albert Einstein

> 'He sure does' - Ganga Singh Manchanda

---

Random numbers are a necessary resource for Cryptography, scientific Experiments + simulations, Statistical Sampling, Gambling and Lotteries.

*   **Pseudo-Random Number Generators (PRNGs):** These are deterministic algorithms that start from a seed value and produce sequences that *appear* random. However, given the seed and the algorithm, the entire sequence is predictable. They are useful for simulations but completely insecure for cryptography if the seed is compromised or the state is revealed. They don't generate true randomness, but rather *expand* a small amount of initial randomness (the seed).
*   **Hardware Random Number Generators (HRNGs):** These exploit unpredictable physical processes (like thermal noise in resistors, atmospheric noise, radioactive decay, timing jitter, etc.). The *source* of randomness here is physical entropy.
    *   **The Problem:** The randomness from HRNGs depends entirely on the assumption that the physical process is truly unpredictable and that the *device implementing it is working exactly as intended*. How do you verify this? How do you know there isn't a subtle bias, a malfunction, or even a hidden backdoor that allows someone to predict or control the output?

Quantum mechanics provides a natural source of true randomness. Measurements of quantum systems on incompatible observables yield fundamentally unpredictable outcomes. Examples include measuring the polarization of a single photon, the decay of an unstable atom, or the path taken by a particle in a superposition.

*   **Device-Dependent QRNGs:** Most existing QRNGs are device-dependent. They rely on measuring a specific quantum system (e.g., sending a photon into a beam splitter and measuring which path it takes) and *trusting* that the device (the source, the beam splitter, the detectors) is working correctly and is built according to specifications that guarantee quantum randomness.
    *   **The Problem:** Like HRNGs, the security of these QRNGs is conditional on trusting the device. If the device is manufactured by a malicious party, or if it degrades over time, the "random" output could be subtly biased or even predictable, completely undermining security applications like cryptography. How can a user verify the device's integrity without fully reverse-engineering and characterizing it?

This is where device independence comes in. A DIQRNG doesn't require you to trust the *internal workings* or *specifications* of the quantum device. Its randomness is certified and quantified purely by observing its *output behavior* in a specific, carefully designed test.

The core idea is to use quantum correlations that are so strong that they cannot be explained by any theory based on *local realism*. These are the correlations that violate **Bell inequalities**.

*   **The Central Principle:** If a device can produce correlations that violate a Bell inequality, then its outcomes *must* contain genuine, unpredictable randomness. This is because any hypothetical "hidden variables" that could predetermine the outcomes in a local way are mathematically proven to be incompatible with observing a Bell violation. If the outcomes aren't predetermined by local hidden variables, they must be fundamentally random when the measurement choices are made.
*   **The Guarantee:** The level of Bell violation observed provides a *lower bound* on the amount of true, unpredictable randomness present in the raw outputs, *regardless* of how the device is built or if it's trying to "cheat."

This is a incredibly powerful guarantee, offering a level of trust unprecedented in other forms of randomness generation.

## 2. Foundational Concepts for DIQRNGs

To understand DIQRNGs in excruciating detail, we need to revisit some fundamental concepts:

### 2.1 True Randomness vs. Weak Randomness

*   **True Randomness (Strong Randomness):** A sequence where each bit is independent and uniformly distributed (each bit is 0 or 1 with probability 1/2, independent of all other bits). This is the ideal for applications like cryptography.
*   **Weak Randomness:** A sequence that is unpredictable to some degree, but might be biased or correlated. For example, bits that are 1 with probability 0.6, or where consecutive bits have some dependency.
*   **Min-Entropy:** A rigorous mathematical measure of the *worst-case* unpredictability of a random source. For a random variable \[X\], the min-entropy is \[H_{\min}(X) = -\log_2(\max_x P(X=x))\], where \[\max_x P(X=x)\] is the highest probability of any specific outcome \[x\].
    *   A source with \[k\] bits of perfect randomness has $H_{\min} = k$.
    *   A source with \[n\] bits where the most likely \[n\]-bit string has probability \[2^{-m}\] has \[H_{\min} = m\]. We say it contains $m$ bits of *guaranteed* randomness. $m \le n$. A DIQRNG uses the Bell violation to lower-bound $m$ for the raw outcomes.

### 2.2 Entanglement

*   DIQRNGs are based on violating Bell inequalities, which requires quantum entanglement.
*   An entangled state of two particles A and B (held by Alice and Bob, respectively) is a state that cannot be written as a simple product of states of A and B ($|\Psi\rangle \ne |\psi_A\rangle \otimes |\psi_B\rangle$).
*   Measurements performed on entangled particles exhibit correlations that are stronger than classically possible. A standard example is the singlet state for two spin-1/2 particles: $\frac{1}{\sqrt{2}}(|\uparrow\downarrow\rangle - |\downarrow\uparrow\rangle)$. If Alice measures spin-up in the Z direction, Bob is guaranteed to measure spin-down in the Z direction, and vice-versa. The outcomes are perfectly anti-correlated, but the individual outcomes for Alice (or Bob) *before* measurement are completely random (50/50 chance of up/down).

### 2.3 Bell Inequalities (specifically CHSH)

This is the mathematical core of the DI certificate.

*   **Local Realism:** The conjunction of two ideas:
    *   *Realism:* Physical properties have definite values independent of measurement (often attributed to pre-existing "hidden variables" $\lambda$).
    *   *Locality:* What happens in one region of space doesn't instantaneously influence what happens in a distant region.
*   **Bell's Theorem:** No physical theory based on local realism can reproduce *all* the predictions of quantum mechanics. Specifically, quantum mechanics predicts correlations that violate Bell inequalities.
*   **The CHSH Inequality:** A widely used form of Bell inequality, named after Clauser, Horne, Shimony, and Holt. It involves two parties, Alice and Bob, each choosing between two possible measurement settings and getting one of two possible outcomes.
    *   Alice's settings: $x \in \{0, 1\}$ (or $\{a, a'\}$). Outcomes: $A \in \{-1, +1\}$.
    *   Bob's settings: $y \in \{0, 1\}$ (or $\{b, b'\}$). Outcomes: $B \in \{-1, +1\}$.
    *   They receive entangled particles from a source. They choose settings *randomly and independently* and measure simultaneously in distant labs.
    *   They calculate the correlation function for each pair of settings: $E(x,y) = \langle A_x B_y \rangle$, the average product of their outcomes when Alice used setting $x$ and Bob used setting $y$.
    *   The CHSH parameter is defined as: $S = E(0,0) + E(0,1) + E(1,0) - E(1,1)$. (Note the minus sign on the last term; equivalent forms exist with different sign patterns or combinations).
    *   **The CHSH Inequality (Local Realism Bound):** Under the assumption of local realism, it can be proven that the value of $S$ must satisfy:
        $|S| \le 2$.
        *   *Brief Intuition for why $|S| \le 2$ under local realism:* For any given run defined by hidden variables $\lambda$, Alice's outcomes $A_0(\lambda), A_1(\lambda)$ are fixed to $\pm 1$, and Bob's outcomes $B_0(\lambda), B_1(\lambda)$ are fixed to $\pm 1$. The crucial point is that $A_x(\lambda)$ only depends on $x$ and $\lambda$, not $y$, and $B_y(\lambda)$ only depends on $y$ and $\lambda$, not $x$. Consider the quantity $A_0 B_0 + A_0 B_1 + A_1 B_0 - A_1 B_1 = A_0(B_0 + B_1) + A_1(B_0 - B_1)$. Since $A_0, A_1, B_0, B_1$ are all $\pm 1$, $B_0+B_1$ can only be $-2, 0, 2$, and $B_0-B_1$ can only be $-2, 0, 2$. Specifically, if $B_0=B_1$, $B_0-B_1=0$ and $B_0+B_1=\pm 2$. If $B_0 \ne B_1$, $B_0+B_1=0$ and $B_0-B_1=\pm 2$. In either case, exactly one of $(B_0+B_1)$ or $(B_0-B_1)$ is zero, and the other is $\pm 2$. So, for any $\lambda$, the quantity $A_0(B_0 + B_1) + A_1(B_0 - B_1)$ is either $A_0(\pm 2)$ or $A_1(\pm 2)$, which is always $\pm 2$. The expectation value $E(S)$ is an average over $\lambda$, and the average of a value that is always $\pm 2$ must be between $-2$ and $2$. Thus, $|S| \le 2$ for any local realistic theory.
    *   **Quantum Bound (Tsirelson's Bound):** For specific entangled states (like the singlet state) and optimal measurement settings, quantum mechanics predicts a maximum value for $S$:
        $|S| \le 2\sqrt{2} \approx 2.828$.
        *   This value is greater than 2 and has been verified experimentally.

*   **Bell Violation as a Resource:** The fact that experiments observe $|S| > 2$ means that the correlations are *non-local* and/or *non-real*. This non-local-realism is the fundamental resource for device-independent applications, including randomness generation.

## 3. The DIQRNG Protocol: From Bell Violation to Random Bits

A DIQRNG combines a Bell test experiment with classical post-processing. Here's a detailed breakdown of the process, performed over many experimental trials:

### 3.1 The Experimental Setup (The Untrusted Device)

The core of the DIQRNG is a device (which you, the user, do *not* trust) composed of three main parts:

1.  **Source:** Designed to produce and distribute entangled pairs of particles (e.g., photons, ions, electrons) to two distant locations, Alice's lab and Bob's lab.
2.  **Alice's Measurement Apparatus:** Located in Alice's lab, receives one particle from the source. It has inputs for selecting one of two measurement settings ($x \in \{0, 1\}$) and outputs for the measurement outcome ($A \in \{-1, +1\}$).
3.  **Bob's Measurement Apparatus:** Located in Bob's lab, receives the other particle from the source. It has inputs for selecting one of two measurement settings ($y \in \{0, 1\}$) and outputs for the measurement outcome ($B \in \{-1, +1\}$).

Crucially, Alice's and Bob's labs are separated by a significant distance to ensure the measurements can be performed in a **space-like separated** manner – that is, within a time window where no signal traveling at the speed of light or slower can pass information between setting choices and measurement outcomes. This closes the **locality loophole**.

Additionally, the measurement settings ($x$ and $y$) must be chosen randomly and independently in each trial. The source of this randomness for setting choices is a critical point, related to the **freedom-of-choice loophole**. Often, this is assumed to come from a small amount of *trusted* initial randomness, or from a physical process deemed sufficiently uncorrelated with the source and measurement devices.

### 3.2 The Data Acquisition Phase (Performing the Bell Test)

This phase is repeated for a large number of trials $N$ (e.g., millions or billions):

1.  **Trial Start:** The source attempts to produce and distribute an entangled pair.
2.  **Random Setting Choice:** Alice's apparatus receives a random bit $x$ (0 or 1) for its setting. Bob's apparatus receives a random bit $y$ (0 or 1) for its setting. These choices must be independent.
3.  **Simultaneous Measurement:** Alice's apparatus performs a measurement according to setting $x$ and obtains outcome $A$. Bob's apparatus performs a measurement according to setting $y$ and obtains outcome $B$. These measurements must happen quickly and concurrently enough to be space-like separated given the distance between them.
4.  **Data Recording:** Alice records $(x, A)$ and Bob records $(y, B)$ for that trial.
5.  **Successful Trial Check:** A successful trial occurs when both Alice and Bob obtain a valid outcome (closing the **detection loophole** requires the probability of both getting an outcome to be sufficiently high, above a certain threshold depending on the inequality). If a trial is unsuccessful (e.g., a particle was lost), it's discarded *without introducing bias*.

After $N$ trials, Alice has a list of $(x_i, A_i)$ pairs, and Bob has a list of $(y_i, B_i)$ pairs, where $i$ indexes the successful trials. They then bring their data together (classically) for the certification phase.

### 3.3 The Randomness Certification Phase (Calculating the Bell Violation)

This is where the device-independent guarantee is established.

1.  **Estimate Correlations:** Using the collected data, calculate the empirical correlation functions $\tilde{E}(x,y)$ for each pair of settings. For example, $\tilde{E}(0,0)$ is the average of $A_i \times B_i$ over all trials where Alice used setting 0 and Bob used setting 0.
    $\tilde{E}(x,y) = \frac{1}{N_{x,y}} \sum_{i \text{ s.t. } x_i=x, y_i=y} A_i B_i$, where $N_{x,y}$ is the number of trials with settings $(x,y)$.
2.  **Calculate the CHSH Parameter:** Compute the experimental CHSH value $\tilde{S} = \tilde{E}(0,0) + \tilde{E}(0,1) + \tilde{E}(1,0) - \tilde{E}(1,1)$.
3.  **Check for Bell Violation:** Compare the absolute value $|\tilde{S}|$ to the local realism bound of 2. Due to statistical fluctuations in a finite number of trials, a true quantum device will yield $|\tilde{S}|$ slightly below the theoretical maximum $2\sqrt{2}$, but ideally above 2 with high statistical significance.
4.  **Bound the Min-Entropy:** This is the crucial theoretical step. There are mathematical proofs that rigorously connect the observed value of $|\tilde{S}|$ to a lower bound on the **min-entropy** of the raw outcomes $(A_i, B_i)$, conditioned on the settings $(x_i, y_i)$. The exact formula depends on the specific Bell inequality and the security assumptions, but generally:
    $H_{\min}(\text{Outcomes } | \text{ Settings}) \ge f(|\tilde{S}|)$
    where $f$ is a function that increases with $|\tilde{S}|$ and $f(2) = 0$. If $|S| > 2$, then $f(|S|) > 0$, meaning there is a guaranteed amount of random bits per trial. A higher violation means a higher guaranteed min-entropy per trial.
    *   *Conceptual Link:* The proof relies on the fact that if the outcomes were determined by hidden variables $\lambda$, the correlations would satisfy $|S| \le 2$. If you observe $|S| > 2$, then the outcomes *could not* have been fully determined by local hidden variables *at the time the measurement settings were chosen*. This "undetermined" nature translates directly into unpredictability and thus, randomness. The degree of violation quantifies how much the outcomes deviate from *any* local-realistic explanation
