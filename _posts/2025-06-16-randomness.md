---
title: Achieving quantum randomness
layout: post
author: Ganga Singh Manchanda
category: physics
---



Introduction: What Is Randomness?
Randomness usually means unpredictability—coin tosses, rolling dice, thermal noise. But there's a crucial distinction: in classical physics, randomness is epistemic—it comes from ignorance. If we knew all the initial conditions, we could predict everything. The universe is, in principle, deterministic.

Quantum physics challenges this. According to quantum theory, some events truly lack a predetermined outcome. This ontological randomness is not due to lack of knowledge—it is part of reality itself. And the strongest evidence for this comes from a seemingly abstract piece of mathematics: the Bell inequalities.

Bell’s Theorem: Testing the Boundaries of Reality
Let’s briefly look at the logic behind Bell's theorem.

Suppose you have two particles, A and B, prepared in an entangled state and sent to two distant locations. You measure them using different settings, say 
x
x for Alice and 
y
y for Bob, and record outcomes
a
a and 
b
b, each being 
±
1
±1.

Bell showed that any local hidden variable theory must obey certain inequalities. One of the most famous is the CHSH inequality (Clauser-Horne-Shimony-Holt):

∣
E
(
a
x
b
y
)
+
E
(
a
x
b
y
′
)
+
E
(
a
x
′
b
y
)
−
E
(
a
x
′
b
y
′
)
∣
≤
2
∣E(a 
x
​	
 b 
y
​	
 )+E(a 
x
​	
 b 
y 
′
 
​	
 )+E(a 
x 
′
 
​	
 b 
y
​	
 )−E(a 
x 
′
 
​	
 b 
y 
′
 
​	
 )∣≤2
Here:

E
(
a
x
b
y
)
E(a 
x
​	
 b 
y
​	
 ) is the expected value of the product of outcomes for settings 
x
x and 
y
y
The inequality holds for all local deterministic models
Quantum mechanics, however, predicts that for certain entangled states and measurement settings, the above expression can reach:

∣
E
QM
∣
=
2
2
∣E 
QM
​	
 ∣=2 
2
​	
 
This is known as the Tsirelson bound. Experiments confirm this violation, ruling out all local hidden variable theories.

Randomness in the Violation
So where does randomness enter?

In any classical deterministic theory, outcomes 
a
a and 
b
b are functions of:

The local setting (e.g., 
a
=
f
(
x
,
λ
)
a=f(x,λ))
A shared hidden variable 
λ
λ, which determines outcomes in advance
If Bell inequalities are violated, no such function exists—the outcomes cannot be fully determined by 
λ
λ. In particular, for some measurement settings, the outcome must be fundamentally unpredictable.

Mathematically, this means that even if you fix all the information available prior to the measurement (including any hidden variables), the probability distribution over outcomes must remain nontrivial. That is:

0
<
P
(
a
=
±
1
∣
x
,
λ
)
<
1
0<P(a=±1∣x,λ)<1
This unpredictability is not due to experimental noise or lack of control—it is a certified, irreducible randomness mandated by the structure of quantum theory itself.

Device-Independent Randomness Generation
This insight has been turned into practical technology.

In device-independent random number generation, two devices are tested for Bell inequality violation. If the violation exceeds a certain threshold, you can provably extract random bits from the output. Even if the devices are untrusted or adversarial, they cannot fake the violation without actually generating randomness.

The theory guarantees that a certain min-entropy can be extracted. For instance, if the CHSH value 
S
S is measured to be 
2.5
2.5, then you can bound the conditional probabilities:

H
∞
(
a
∣
x
,
λ
)
≥
1
−
log
⁡
2
(
1
+
2
−
S
2
4
)
H 
∞
​	
 (a∣x,λ)≥1−log 
2
​	
 (1+ 
2− 
4
S 
2
 
​	
 
​	
 )
This gives you a lower bound on how unpredictable each bit is.

Experimental Realizations
Experiments have successfully implemented randomness certification using Bell violations:

In 2015, loophole-free Bell tests were performed by groups at Delft, NIST, and Vienna. These used high-efficiency detectors and fast switching to close major experimental gaps.
In 2018, a group used a cosmic Bell test, where settings were determined by photons from quasars billions of years old, ensuring the freedom-of-choice assumption was not compromised.
In 2020, researchers achieved real-time randomness generation at rates of up to megabits per second, certified directly by CHSH violations.
These experiments turned quantum philosophy into quantum engineering.

Philosophical Consequences
Quantum randomness invites reflection on deep questions:

Is the universe fundamentally indeterministic? Bell’s theorem suggests so, unless one accepts radical alternatives like superdeterminism, where even your experimental choices are preordained.
Can we have free will in a quantum world? Some argue that quantum randomness reintroduces an element of freedom into nature, though that remains controversial.
Does randomness emerge from ignorance or from the structure of reality itself? Bell's theorem leans toward the latter.
Conclusion
Bell's theorem did more than challenge local realism—it gave us a way to test the unpredictability of the universe. In doing so, it revealed that randomness isn't a bug in physics—it's a fundamental feature.

And perhaps even more remarkable, this foundational insight has given rise to secure communication technologies, randomness beacons, and a deeper understanding of nature's limits.

In the quantum world, we don’t just guess—we certify unpredictability.

Further Reading
Bell, J.S. (1964). On the Einstein Podolsky Rosen Paradox
Pironio et al. (2010). Random numbers certified by Bell’s theorem, Nature
Acín & Masanes (2016). Certified randomness in quantum physics, Nature
