---
title: But what IS a black hole?
layout: post
author: Ganga Singh Manchanda
category: physics
---

Submission to SoME 2025

In the public domain, black holes are generally understood as local astrophysical phenomena. This article aims to move past this treatment and impress on an enthusiastic (non-expert) reader a global understanding of black holes. Our discussion is high-level yet accessible as we introduce topics in General Relativity via causal structure rather than via tensor calculus.

---

<div style="text-align: center; font-size: 3em; font-weight: bold;">
  \[ B=M/M\cap[J^-(\mathcal{I}^+)] \]
</div>

BEHOLD! This is a black hole (from a global perspective). What you see is a very formal statement which effectively says

> A black hole is a causally disconnected region of spacetime

Across six chapters we will break this equation down such that by the end of the article a reader could sit in peace, knowing what a black hole truly is

1. Spacetime
2. Geodesics
3. Causality
4. Horizons
5. A Dark Star
6. The Singularity

---

### Spacetime

Intuitively, humans adopt a Newtonian picture of the universe. Everything that exists does so within the confines of up-down, side-to-side, and back-and-forth - three dimensions of space that you (the reader) can move freely within. If the set of a show exists in these three dimensions, then the show must go on because THINGS also exists in a fourth dimension - time - and unlike the other three you have no control over its flow.

This picture is wrong. In 1905, Einstein (along with Lorentz, Minkowski, Poincare etc) ruined everything by coming up with an even better idea - that space and time are not separate. Where before, we imagined absolute space (a fixed 3D grid) evolving through absolute time (a fixed 1D line), we now imagine a malleable spacetime (4D grid):

IMAGES

which can bend and distort and where every point corresponds to both a place and time, an event. All of the the universe exists within the confines of this 4D grid. The set of points that make up that grid is called the manifold \( M \)$.

### Geodesics

The manifold \( M \) allows us to formalise the `arena' that THINGS in the universe exist within, but what are these THINGS?

Simply put there are two types of THINGS: matter and light, differentiated by mass alone. Matter is bound by mass, allowing it to sit still. Light, unburdened by mass, must always be on the move travelling up to a maximum of \( c=3\times10^8\,\text{ms}^{-1} \) and no faster.

Let us first consider a stationary particle which exists at some point in space. Though the particle is stationary in space, it must still move through time such that its trajectory draws out a worldline through the manifold. This worldline is straight. 

![Spacetime]({{ '/assets/spacetime.png' | relative_url | height=48px }})

A free particles worldines is always a geodesic (shortest path)

We have ordinary matter which travels through spacetime on physical trajectories characterised by a speed limit. The speed of light, c. While matter travels under the speed limit (timelike geodesics), light travels at this speed limit (null trajectories). 

If the spacetime is curved, then the geodesic that a THING takes is apparently curved, which is why things fall. Earth creates a WELL which things fall into. This is the source of gravity in everyday life - perhaps a familiar picture

### Causality

Light represents the limits of what is possible in the universe. Light can transmits signals between places and this transmission is what causes things to happen. We beg the question, what events influence one another?

Suppose you shine a flashlight into empty space. Where does the light go?

We describe this as a causal connection. Imagine wiggling a magnet, the EM force transmits that force to CAUSE another magnet to wiggle outside. We cut the universe in two parts. In one part, things can influence each other and in the other half they cant. This causal connection only goes one way and that is the black hole. We end up with LIGHTCONES. past light cone can influence a point. point can influence future light cone (for any point \[ p \in M \])

IMAGE

This motivates the formal definitions:

\[ J^+(p) \] is the causal future of p and \[ J^-(p) \] is the causal past of p. Basically all the points that exist within those two cones. These sets let us talk globally about cause and effect in spacetime

In Newton’s universe: it just travels outward forever. In relativity, we make this idea precise by introducing **conformal infinity**. Future null infinity \[ \mathcal{I}^+ \] is the idealized “place” where light rays that escape forever end up (see a penrose diagram). Past null infinity \[ \mathcal{I}^- \] is where incoming light originates. In flat spacetime, every null geodesic starting inside eventually reaches \[ \mathcal{I}^+ \]. No event is hidden.

### Horizons

Consider the set of points defined by \[J^-(\mathcal{I}^+)\]. These are all the events which constitute the causal past of future null infinity. Anywhere in spacetime that can send a signal to infinity is encompassed in this set. We ask does \[ J^-(\mathcal{I}^+)=M \] ALWAYS hold? The answer is no. In certain spacetimes there must exist a set of points which cannot send a signal to infinity.

We consider the limit points of the set \[ \mathcal{H}^+=\text{Boundary}(J^-(\mathcal{I}^+)) \]. This is the (future) event horizon, which divides the universe into two regions. Outside, signals can eventually escape to infinity, while inside signals are trapped forever It is a point of no return. This is the essence of a black hole. If there is a region of spacetime from which no signal, not even light, can escape to infinity, then that region is causally sealed off. In particular, if  \[ J^-(\mathcal{I}^+) \] is the set of points that can send a signal to infinity, then the black hole is the complement of this set with respect to the entire manifold \[ B=M/M\cap[J^-(\mathcal{I}^+)] \]. Using a Venn diagram:

IMAGE

Notice something subtle: the horizon is a **global feature**. An observer crossing it feels nothing special locally. Only by considering the entire causal structure — who can reach infinity, and who cannot — does the horizon become apparent. If a magnet is inside a black hole then no matter what I do to it, it can never cause anything to happen to a magnet outside the black hole

There exist many different types of black hole in General relativity, but all obey this condition.

### A Dark Star

Over 200 years ago, Pierre-Simon Laplace speculated about a “dark star.” At the time Newtons theory of Gravity prevailed, but a corpuscular theory of light predicted a bending of light in a gravitational field. Laplace then imagine a star so great that its gravitational field would stop its light from ever leaving, a dark star. In Einsteins theory of Gravity, 

> Mass (energy) tells spacetime how to curve, spacetime tells mass (energy) how to move - Wheeler

and so shortly after his publication, Schwarzschild came up with a solution that contained a similar ‘dark star’ where the curvature is so deep that light becomes stuck in a deep well and cannot escape. The matter content and arrangement defines the universe

Laplace and Schwarzschilds dark star, talk about curvature and astrophysical examples of black holes but that they dont need to be in that form and that they exactly satisfy the definition laid out here. The dark star is one way of having a black hole in a universe, but its not the only way and our definition moves past this. We can have black holes without horizons and even without singularities. Light gets pulled back due to curvature

### The Singularity

In the aforementioned Schwarzschild solution, one of the key features is that at the centre of the black hole, the curvature isnt just deep but infinitely deep. The curvature diverges and spacetime ceases to exists there. This point is usually called a singularity. 

In fact singularities are worse than simply points where curvature diverges, they are defects in spacetime. They are points where a geodesic simply stop, indicating a geodesic incompletness of the entire manifold. 

Most black hole spacetimes contain singularities — regions where spacetime ends abruptly. From what weve discussed it seems that a black holes doesn't necessarily clothe a singularity, and that would be correct. A black hole doesn't require a singularity. But in most solutions we look at there is a singularity. Penrose and Hawking proved that under very general conditions (like positive energy density), singularities are inevitable in gravitational collapse. Dont worry, quantum gravity has singularity resolution (supposedly)

> A universe with a black hole is fundamentally different to a universe without one.

But it is crucial to emphasize: the **global definition of a black hole does not rely on singularities**. The black hole is defined by causal disconnection from \[\mathcal{I}^+\], not by what happens in the interior.
