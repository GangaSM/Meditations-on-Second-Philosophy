---
title: The Physic(al) Process - A tale of trial and error in a quantum world
subtitle: Submission to Sikhs in Academia 2026
layout: post
author: Ganga Singh Manchanda
category: philosophy of physics
---

We provide a brief introduction to the scientific method as applied to physics, emphasising the role of mathematical formalism in the construction and refinement of physical theories. Following this we discuss how physics on a small scale requires a new theory---quantum theory---presented through the lens of generalised probability. Though the application of quantum theory has been widely successful over the last century, certain pathologies cannot be ignored. We present three of these in order of increasing severity: the problems of limitation, interpretation, and existence.

---

I'm a theoretical physicist*, but what does that mean? Does it mean the work I do isn't real? Does it mean I make up extra dimensions when things don't work out? Does it mean I'm annoyingly pedantic about everything just like Sheldon? Today I want to dispel some misunderstandings about what physicists do. In the first half I'll discuss what physics is and how ideas about the physical world develop. I'll then present a particularly compelling way of thinking about quantum theory. In the second half I'll give some short words on the various problems that plague physics:

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

To start then, let's guess some rule based on our intuition and write it down on a piece of paper. My intuition tells me that a fast, heavy punch hurts more than a slow, light punch. I might then write down:
$$\text{force}=\text{mass}\times\text{velocity}$$
and then we check the physical consequences implied by this rule. Congratulations, you are now a theoretical physicist! Next we have to check that the universe actually obeys this rule, so we go out into the world and test whether what we've written down actually matches what happens. This is the job of the experimental physicist. If there is a discrepancy between prediction and experiment then the rules we wrote down were wrong and we go back to the drawing board. In this case we were wrong, but not entirely. According to this rule, the follow through on a punch has no impact on how much it hurts. If you've ever been punched, you know that just isn't true. Returning to the problem, let's instead write:
$$\text{force}=\text{mass}\times\text{acceleration}$$
and have an experimentalist verify again. Acceleration accounts for this follow through unlike velocity. This time we find that the rule holds, **but only under certain conditions**. And it's this phrase that contains everything important about how physics actually works. No rule is final.

In fact, when we move to scenarios where mass continually changes---like a rocket burning its fuel as it propels itself---this equation no longer holds. To resolve this we go back to the drawing board again, keeping the elements that agree with observation and discarding the elements that don't. This back and forth is the process by which physics happens and it leads us to a set of rules that encompasses more and more physical phenomena accurately. In the end we hope to have one set of rules which describes everything. 

I also hope this clarifies that the word theory doesn't mean unproven, it just refers to the development of the mathematical half of the physical process. As a side note, certain types of observation are more powerful than others. Symmetries in particular are exceptional at constraining theory and are 'fault tolerant' but we won't have time to discuss this further.

## A Quantum World

The process works very well. Over the last century, as experimentalists have created more and more powerful tools we've been able to make observations closer and closer to the level of atoms and molecules and on this small scale, physics isn't as simple as $\text{force}=\text{mass}\times\text{acceleration}$. To extend classical physics to this previously unknown realm, we can apply the physical process to develop a new theory, quantum theory. Observational evidence suggests that we live in a quantum world and so we'll discuss this quantum world under the disclaimer that these are simplified ideas because the real thing would require some complicated mathematics and much more than 15 minutes.

Imagine a ball. I place it at some starting position and give it a kick. As the ball flies through the air, it has a definite position, $x$, and momentum, $p$, at every point it passes. As a result I can trace out its path mathematically and predict the final position it will reach. If I repeat this, I can reasonably expect the same result.

Now imagine an electron, a fundamental particle. I can place it at some starting position and give it a 'kick', but I won't see what I see with the ball. In fact, I won't see much at all because observation and measurement works very differently in the quantum world. 

In quantum theory, it's all about possibility. An electron could be here, or it could be there, and until I take a peek and find out, its in both. An electron could have this momentum, or it could have that momentum, and again until I take a peek it has both. This isn't simply a statement of uncertainty, the particle really is in both positions until we measure and it really does have both momenta until we measure (subject to interpretation). The idea of a localised particle has no meaning before we peek because our observation forces it to pick an option.

With the ball, I could talk about the its position and its momentum, and how the two are related. I can say that when the ball is first kicked, it has the greatest momentum, and that when its finally stopped it has the least momentum. In this way, the positions and momenta of the ball are correlated. I can't do the same thing with the electron. The universe places a limit on how much I can simultaneously know about position and momentum through Heisenberg's uncertainty principle:
$$\Delta x\Delta p\ge\frac{\hbar}{2}$$
This equation describes a tradeoff in information between position and momentum. The more I know about position the less I know about momentum. The more I know about momentum the less I know about position. 

The best comparison I can make is to think about an ice cube moving around in the dark. I can't see, so all I can do is grab at it to know its position. It's really slippery though, so as I grab it, it shoots out of my hand. The more tightly I grasp it, the more quickly it shoots out of my hand and so the more accurately I can measure its position, the less certain I am of its momentum in the next moment.

On a large scale, the distinction becomes negligible. $\hbar$ is an absurdly small number which matters on the scale of an electron but not at the scale of the ball so that for all intents and purposes, we can know about a ball's position and momentum simultaneously. 

I'd like to emphasise that understanding all of this is important and not just academic curiosity. Quantum theory governs the flow of electrons in transistors, and without its development, modern phones and computers wouldn't exist. Quantum theory determines how light travels through fibre-optic cables and through the atmosphere, enabling connection to the internet. Quantum theory underpins the entire modern world and we take it for granted. 

## Generalised Probability

Now comes the interesting part. I'm going to argue that all this feels weird to us because the universe is based on a more general theory of probability than what humans intuitively understand.

Consider the very human example of height and shoe size. All humans have some height and some shoe size (assuming they have feet). Even before I check all 8 billion of them, they exist. I might imagine some spreadsheet somewhere with 8 billion entries that look like $(\text{height},\text{shoe size})$ acting as an underlying description of reality.

In terms of the ball, all possible positions and momenta exist in a spreadsheet called the state space. If there are two positions, left and right, and two momenta, forwards and backwards, then all information about the ball is encoded in the pair $(x,p)$. The complete set of options the ball can exist in, the state space, is then:
<div style="text-align: center; font-size: 1em;">
	\[ \Omega=\{(L,F),(L,B),(R,F),(R,B)\} \]
<\div>
Any one of these four options represents a complete specification of reality and even if we don't know the exact state of the ball, we know it's one of these four options. 

In a state space description of reality, knowledge of one variable can narrow down knowledge of the other. Imagine that $(R,B)$ was no longer an option and the state space was reduced to:
$$\Omega=\{(L,F),(L,B),(R,F)\}$$
Here when $x=L$, $p(L,F)=p(L,B)=\frac{1}{2}$, and when $x=R$, $p(R,F)=1$. In this case, if I know that $x=R$, then I immediately know that $p=F$ because the two results are correlated through the joint distribution $p(x,p)$.

The electron doesn't admit a joint distribution like the ball does. Instead everything we know about a given electron is encoded in a state $\psi$ which replaces the $(x,p)$ picture we have for the information of the ball. At any given time, I can interpret $\psi$ through the lens of position, as some probability of seeing a position $p_\psi(x)=|\psi(x)|^2$, or through the lens of momentum, as $p_\tilde{\psi}(p)=|\tilde{\psi}(p)|^2$, but never as $p_{\psi\backslash\tilde{\psi}}(x,p)$ at the same time. Quantum theory removes the spreadsheet underneath and instead follows the rule:
$$\psi + \text{measurement of }x\text{ OR }p\longrightarrow\text{probabilities of }x\text{ OR }p$$
If I choose to measure position, quantum theory tells me the probabilities for position outcomes. If I choose momentum, it tells me the probabilities for momentum outcomes. But the theory cannot describe probabilities for position and momentum outcomes at the same time. This is more general than the description of the ball, because in the quantum theory I can never have a situation where knowing the position $x=R$, immediately tells me the momentum $p=F$. The Heisenberg uncertainty principle forbids correlations as restrictive as this one, and so it forbids an underlying spreadsheet from describing an electron. 

If I have many electrons, these quantum effects average out over the collective resulting in the emergence of a ball that behaves like a ball rather than a ball that behaves like an electron.
