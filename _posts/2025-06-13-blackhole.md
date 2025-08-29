---
title: But what IS a black hole?
subtitle: Submission to SoME 2025
layout: post
author: Ganga Singh Manchanda
category: physics
---

In the public domain, black holes are generally understood as local astrophysical phenomena. This short article aims to move past this treatment and impress on an enthusiastic (non-expert) reader a global understanding of black holes. By exploring relativity via causal structure rather than tensor calculus, our discussion covers advanced topics whilst remaining accessible.

---

<div style="text-align: center; font-size: 3em; font-weight: bold;">
  \[ B=M/M\cap[J^-(\mathcal{I}^+)] \]
</div>

BEHOLD! A black hole. What you see above is a formal (global) definition which effectively says:

<div align="center">
<blockquote>A black hole is a causally disconnected region of spacetime</blockquote>
</div>

Across six chapters we will build up to an understanding of this equation such that by the end of this article, you (the reader) can sit in peace satisfied in your knowledge of what a black hole really is:

1. Spacetime
2. Geodesics
3. Causality
4. Horizons
5. A Dark Star
6. The Singularity

---

### Spacetime

Intuitively, humans adopt a Newtonian picture of the universe. Everything that exists does so within the confines of up-down, side-to-side, and back-and-forth; the three dimensions of space that you can move freely within. Yet there is another direction in which you travel, one that you have no control over - time. If the set of a show exists in three dimensions, the show must go on via a fourth. Quite simply, this is formalised as absolute space (a fixed 3D grid) evolving through absolute time (a fixed 1D line):
<img src="{{ '/assets/threeplusone.png' | relative_url }}"
     alt="Spacetime"
     style="width:600px !important; height:auto;">
This picture is wrong. In 1905, Einstein (building on the work of Lorentz, Minkowski, Poincare, etc) ruined everything by coming up with an even better idea - that the flows of space and time are not absolute and are not separate.  We instead picture a malleable and deformable spacetime (4D grid) where every point corresponds to both a place and time, an event. Obviously as beings that exist in 3 spatial dimensions, drawing a 4D grid is quite impossible but we can get an idea by simply imagining all the points together. All of the the universe exists within the confines of this spacetime. The set of points that make up the 4D grid is called the manifold $M$. Cant imagine it? Thats okay neither can we. Humans perceive the universe as 3+1 dimensions rather than 4 so to draw it can be quite a struggle. 

### Geodesics

The manifold $M$ formalises the “arena” that things in the universe exist within, but what things are there? Simply put there are two types of things: matter and light, differentiated by mass alone. Matter, burdened by mass, is bound to its local surroundings allowing matter to choose its own speed. Light, unburdened by mass, has no such luxury and must always travel at $c=3\times10^8\,\text{ms}^{-1}$ (in a vacuum) and no faster. In a way, having mass simply gives the ability to slow down by holding onto the nearby Higgs field - like a bird dragging its feet in water.

Let us consider a particle which exists at some time and space denoted by the event $p$. If the particle is stationary, its position in space cannot move yet its position in time cannot stop moving. The result is that the trajectory of the particle through spacetime, its worldline, goes directly upwards. If the particle was a photon, it must travel at $c$ such that the wordline drawn is a $45\degree$ line. Take some time to think about why this is so.
<img src="{{ '/assets/spacetime.png' | relative_url }}"
     alt="Spacetime"
     style="width:250px !important; height:auto;">
Massive particles of varying speeds have wordlines that lie in between these two extremes - these are called timelike trajectories. The trajectory of the photon is called a null trajectory. Outside of that is spacelike. Spacetime can curve. A free particles worldlines is always a geodesic (shortest path). If the spacetime is curved, then the geodesic that a THING takes is apparently curved, which is why things fall. Earth creates a WELL which things fall into. This is the source of gravity in everyday life - perhaps a familiar picture.

### Causality

A very important question: what events can influence one another? Light represents the limits of what is possible in this realm as it can transmits signals between points in space at the fastest speed possible and this transmission may causes things to happen. We describe this as a causal connection. Imagine wiggling a magnet, the EM force transmits that force to CAUSE another magnet to wiggle outside. Suppose you shine a flashlight into empty space. What ensues is a future lightcone, describing all the events that can be reached by that flashlights signal. Inversely a past lightcone shows all the events that could have influenced a point

IMAGE

These lightcones can be formalised by two sets: $J^+(p)$ is the causal future of p and $J^-(p)$ is the causal past of p. These sets let us talk globally about cause and effect in spacetime

We expect that the light emitted from $p$ travels onwards forever. We make this idea precise with future null infinity $\mathcal{I}^+$, the idealized “place” where light rays that escape forever end up (see a Penrose diagram for more). Past null infinity $\mathcal{I}^-$ is where incoming light originates.

### Horizons

Consider the set of points defined by $J^-(\mathcal{I}^+)$. These are all the events which constitute the causal past of future null infinity - anywhere in spacetime that can send a signal to infinity is encompassed in this set. We ask does $J^-(\mathcal{I}^+)=M$ ALWAYS hold? The answer is no. In certain spacetimes there must exist a set of points which cannot send a signal to infinity. In flat spacetime, every null geodesic starting inside eventually reaches $\mathcal{I}^+$. No event is hidden.

We consider the limit points of the set $\mathcal{H}^+=\text{Boundary}(J^-(\mathcal{I}^+))$. This is the (future) event horizon, which divides the universe into two regions. Outside, signals can eventually escape to infinity, while inside signals are trapped forever It is a point of no return. This is the essence of a black hole. If there is a region of spacetime from which no signal, not even light, can escape to infinity, then that region is causally sealed off. In particular, if  $J^-(\mathcal{I}^+)$ is the set of points that can send a signal to infinity, then the black hole is the complement of this set with respect to the entire manifold $B=M/M\cap[J^-(\mathcal{I}^+)]$. Using a Venn diagram:

IMAGE

Notice something subtle: the horizon is a **global feature**. An observer crossing it feels nothing special locally. Only by considering the entire causal structure — who can reach infinity, and who cannot — does the horizon become apparent. If a magnet is inside a black hole then no matter what I do to it, it can never cause anything to happen to a magnet outside the black hole. There exist many different types of black hole in General relativity, but all obey this condition.

### A Dark Star

Over 200 years ago, Pierre-Simon Laplace speculated about a “dark star.” At the time Newtons theory of Gravity prevailed, but a corpuscular theory of light predicted a bending of light in a gravitational field. Laplace then imagine a star so great that its gravitational field would stop its light from ever leaving, a dark star. In Einsteins theory of Gravity, 

> Mass (energy) tells spacetime how to curve, spacetime tells mass (energy) how to move
> - John Archibald Wheeler

and so shortly after his publication, Schwarzschild came up with a solution that contained a similar ‘dark star’ where the curvature is so deep that light becomes stuck in a deep well and cannot escape. The matter content and arrangement defines the universe

Laplace and Schwarzschilds dark star, talk about curvature and astrophysical examples of black holes but that they dont need to be in that form and that they exactly satisfy the definition laid out here. The dark star is one way of having a black hole in a universe, but its not the only way and our definition moves past this. We can have black holes without horizons and even without singularities. Light gets pulled back due to curvature

### The Singularity

In the aforementioned Schwarzschild solution, one of the key features is that at the centre of the black hole, the curvature isnt just deep but infinitely deep. The curvature diverges and spacetime ceases to exists there. This point is usually called a singularity. 

In fact singularities are worse than simply points where curvature diverges, they are defects in spacetime. They are points where a geodesic simply stop, indicating a geodesic incompletness of the entire manifold. 

Most black hole spacetimes contain singularities — regions where spacetime ends abruptly. From what weve discussed it seems that a black holes doesn't necessarily clothe a singularity, and that would be correct. A black hole doesn't require a singularity. But in most solutions we look at there is a singularity. Penrose and Hawking proved that under very general conditions (like positive energy density), singularities are inevitable in gravitational collapse. Dont worry, quantum gravity has singularity resolution (supposedly). A universe with a black hole is fundamentally different to a universe without one.

But it is crucial to emphasize: the **global definition of a black hole does not rely on singularities**. The black hole is defined by causal disconnection from $\mathcal{I}^+$, not by what happens in the interior.
