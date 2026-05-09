---
title: The Physic(al) Process
subtitle: _A tale of trial and error in a quantum world_
subsubtitle: Submission to Sikhs in Academia 2026
layout: post
author: Ganga Singh Manchanda
category: philosophy of physics
---

We provide a brief introduction to the scientific method as applied to physics, emphasising the role of mathematical formalism in the construction and refinement of physical theories. Following this we discuss how physics on a small scale requires a new theory---quantum theory---presented through the lens of generalised probability. Though the application of quantum theory has been widely successful over the last century, certain pathologies cannot be ignored. We present three of these in order of increasing severity: the problems of limitation, interpretation, and existence.

---
I'm a theoretical physicist*, but what does that mean? Does it mean the work I do isn't real? Does it mean I make up extra dimensions when things don't work out? Does it mean I'm annoyingly pedantic about everything just like Sheldon? Today I want to dispel some misunderstandings about what physicists do by telling a story. In the first half I'll discuss what physics is and how ideas about the physical world develop. I'll then present a particularly compelling way of thinking about quantum theory. In the second half I'll give some short words on the various problems that plague physics:

1. Foundations
	1. Trial and Error
	2. A Quantum World
	3. Generalised Probability
2. Problems
	1. Limitation
	2. Interpretation
	3. Existence

---

# Foundations

## Trial and Error

The ambition of every physicist is to understand how the universe works. More specifically we want to describe a set of rules which everything in the universe (and the universe itself) obeys. These rules are written down in the language of mathematics. Ideally the universe is distilled into as few rules as possible, but the world is complicated and if the equations come out messy, we cannot bend nature to our will for the sake of compactness.

To start then, lets guess some rule based on our intuition and write it down on a piece of paper. My intuition tells me that a fast, heavy punch hurts more than a slow, light punch. I might then write down:
$$ force=mass\times velocity $$
and then we check the physical consequences implied by this rule. This is the job of the theoretical physicist. Next we have to check that the universe actually obeys this rule, so we go out into the world and test whether what we've written down actually matches what happens. This is the job of the experimental physicist. If there is a discrepancy between prediction and experiment then the rules we wrote down were wrong and we go back to the drawing board. In this case we were wrong, but not entirely. According to this rule, the follow through on a punch makes no difference to how much it hurts. If you've ever been punched, you know that just isn't true. Returning to the problem, let's instead write:
$$ force=mass\times acceleration $$
and have an experimentalist verify again. Acceleration accounts for this follow through unlike velocity. This time we find that the rule holds, **but only under certain conditions**. And it's this phrase that contains everything important about how physics actually works. No rule is final.

In fact, when we move to scenarios where mass continually changes---like a rocket burning its fuel as it propels itself---this equation no longer holds. To resolve this we go back to the drawing board again, keeping the elements that agree with observation and discarding the elements that don't. This back and forth is the process by which physics happens and it leads us to a set of rules than encompasses more and more physical phenomena accurately.

I also hope this clarifies that the word theory doesn't mean unproven. It just means... The aim is to have one set of rules describe everything. We don't have that yet but we’re working towards it. Modern physicists rely a lot on symmetries to do this. They are fundamental. Symmetries are better because they are “fault tolerant” with observations (in a way). Summary of the physical process, powerful but honest about its own limitations.

## A Quantum World

The process works very well. Over the last century, as experimentalists have created more and more powerful tools we've been able to make observations closer and closer to the level of atoms and molecules. On this small scale, physics isn't as simple as $force = mass \times acceleration$. To extend classical physics to this new realm, a new theory was developed---quantum theory--- and no experiment has since contradicted it. The observational evidence leads us to believe that the world is quantum. We'll discuss this quantum world under the disclaimer that I'm presenting general ideas rather than the real thing which would require some complicated mathematics and much more than 15 minutes.

Consider a ball. I place it at a position $x_{\text{initial}}$ and give it a kick. In the classical theory, as the ball flies through the air, it has a definite position and momentum at every point it passes. As a result I can trace its path mathematically and predict the final position $x_{\text{final}}$ it reaches. If I repeat this with the same ball and kick, I can reasonably expect the same result. All the information about the ball is encoded in the points $(x,p)$ that define its position and momentum at any given time. We can reduce this to the state $\rho(x,p)$.

Now consider an electron. I can place it at a position $x_{\text{initial}}$ and give it a 'kick', but I won't see what I see with the ball. In fact, I won't see much at all because observation/measurement works very differently in the quantum world. 

In quantum theory, its all about possibility. An electron could be here, or it could be there. Until I take a peek and find out, its in both. An electron could have this momentum, or it could have that momentum, and again until I take a peek it has both. I emphasise that this isn't simply a statement of uncertainty, the particle really is in both positions until we measure and it really does have both momenta until we measure. Before we peek, the idea of a localised particle has no meaning. Its just distributed probability until our observation forces its hand. 

Similarly to the ball, I can talk about the particles position or I can talk about the particles momentum. Unlike the ball, I can never talk about these two at the same time because observation is relative to some basis. 

Everything we know about a given electron is encoded in a state $\psi$. This replaces the $(x,p)$ picture we have for the information of the ball. At any given time, I can interpret $\psi$ through the lens of position, as some probability of seeing a position $p(x)=|\psi(x)|^2$, or through the lens of momentum, as $p(p)=|\tilde{\psi(p)}|^2$, but never as $\Psi(x,p)$ at the same time. The universe places a limit on how much I can simultaneously know about an electron through Heisenberg's uncertainty principle:
$$\Delta x\Delta p\ge\frac{\hbar}{2}$$
The tells us about the tradeoff in information between position and momentum. The more I know about position the less I know about momentum. The more I know about momentum the less I know about position. Its like trying to grasp at one of those slime balls. To know its position really well I have to grab really tightly. By trying to grab really tightly it shoots out of my hand. The harder I try to grab the more quickly it shoots out and the less certain I am of its momentum.

On a large scale, the distinctions between the electron and the ball become negligible. If I have lots of electrons each with this 'fuzzy' quantum behaviour, for the collective it all averages out and I end up with the emergence of a ball that behaves like a ball rather than a ball that behaves like an electron.

Understanding all this is important. Quantum theory governs the flow of electrons in transistors, and without its development, modern phones and computers would not exist. Quantum theory governs...

## Generalised Probability

Now comes the interesting part. I'm going to present a slightly technical argument that all these weird phenomena are simply the consequences of a generalised theory of probability. The rules of probability that humans understand emerge from a more foundational idea of probability that the universe at the level of the electron follows.

In normal probability theory, we deal with an underlying sample space $\Omega$. All the different probabilistic options exist within the space. In the case of a coin toss, I can get heads or tails so the sample space looks like $\Omega=(\text{Heads},\text{Tails})$. We can consider a simplified version of the ball (discrete) so that there are two options for its position and two options for its momentum. The sample space looks like $\Omega=()$. We can draw options from this joint distribution. 

Quantum theory allows for more options than this. There are some sets of observables for which there does exist a joint distribution. Those are commuting. Position and momentum are not one of these so we cannot describe their correlations through a joint distribution space. 

For an electron, we can prepare a state $\psi$ and measure position to obtain $p_\psi(x)$, or measure momentum to obtain $p_\psi(p)$. Both distributions are well-defined. But there is, in general, no joint distribution $p(x,p)$ that reproduces both. The assumption of a single underlying sample space fails.

It is important to understand what this means. Classical probability is not just “probabilities assigned to outcomes”; it is probabilities constrained to arise from a global joint distribution. This constraint severely limits the correlations that are possible.

Quantum theory removes this constraint.

A state $\psi$ no longer defines a distribution over hidden configurations. Instead, it defines a rule:

$\text{(state)} + \text{(choice of observable)} \;\longrightarrow\; \text{probability distribution over outcomes}$.

Joint distributions exist only for compatible observables—those that can be measured together. For incompatible observables, no joint description is required or even possible.

This is not a restriction; it is a generalisation. By abandoning the requirement of a global joint distribution, quantum theory allows statistical behaviour that classical probability forbids.

Concretely, there exist sets of correlations between observables that cannot be realised by any joint distribution on a sample space, but which are realised in quantum experiments. The classical framework excludes these by construction. The quantum framework includes them.

Classical probability is therefore recovered as a special case: when all observables are compatible, a joint distribution exists and the usual picture is restored. Quantum theory extends this to situations where such a joint description cannot be formed.

The difference between the ball and the electron is not simply that one is deterministic and the other probabilistic. It is that they obey different kinds of probability theory. Classical systems admit a single global description. Quantum systems do not, and it is precisely this that makes the theory more general.
