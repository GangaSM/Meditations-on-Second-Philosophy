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
  \[ B=M/[M\cap J^-(\mathcal{I}^+)] \]
</div>

BEHOLD! A black hole. What you see above is a formal (global) definition which effectively says:

<div align="center">
<blockquote>A black hole is a causally disconnected region of spacetime</blockquote>
</div>

Across the following chapters we will build up to an understanding of this equation such that by the end of this article, you (the reader) can sit in peace satisfied in your knowledge of what a black hole really is:

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
     alt="threeplusone"
     style="width:800px !important; height:auto;">
This picture is wrong. In 1905, Einstein (building on the work of Lorentz, Minkowski, Poincare, etc) ruined everything by coming up with an even better idea - that the flows of space and time are not absolute and are not separate.  We instead picture a malleable and deformable “spacetime” (4D grid) where every point corresponds to both a place and time, an event. The set of points that make up this grid is called the manifold $M$ and all of the universe exists within its confines. Can’t picture it? Thats okay, neither can we as humans perceive the universe as $3+1$D (as with the Newtonian picture). Eliminating two spatial dimensions allows us to draw informative spacetime diagrams:
<img src="{{ '/assets/grid.png' | relative_url }}"
     alt="grid"
     style="width:250px !important; height:auto;">
A concise statement of relativity by Wheeler says that
> Spacetime tells matter how to move; matter tells spacetime how to curve
The presence of mass in a universe induces “wells” as shown earlier that curve the spacetime. To demonstrate this kind of warping, we commonly see pictures where the surface of the manifold is distorted from flat:
<img src="{{ '/assets/well.png' | relative_url }}"
     alt="well"
     style="width:800px !important; height:auto;">

### Geodesics

The manifold $M$ formalises the “arena” that things in the universe exist within, but what things are there? Simply put there are two types of things: matter and light. Matter, burdened by mass, is free chooses its own speed, while massless light has no such luxury and must always travel at $c=3\times10^8\,\text{ms}^{-1}$ (in a vacuum) and no faster. In a sense, mass is just the ability of a particle to slow down by holding onto the local Higgs field - like a bird dragging its feet in water.

Consider a particle which exists at some time and space denoted by the event $p$. If the particle is stationary, its position in space cannot move yet its position in time cannot stop moving. The result is that the trajectory of the particle through spacetime, its worldline, is directly upwards. If the particle was a photon, it must travel at $c$ such that the wordline is drawn at $45^\circ$. Take some time to think about why this is so. Light travels on a so-called null trajectory while massive particles of varying speeds follow timelike trajectories, in between the two extremes:
<img src="{{ '/assets/worldlines.png' | relative_url }}"
     alt="worldlines"
     style="width:250px !important; height:auto;">
So long as a particle is free from the influence of external forces, these worldlines are minimal - that is they follow the shortest path through spacetime, a geodesic. If the spacetime is curved, then the geodesic (shortest path) follows that curve and motion deviates from a straight line in our perspective. This is why things fall. The Earth below our feet creates a well which matter follows its natural geodesic into.

### Causality

What events can influence one another? Imagine wiggling a magnet such that the electromagnetic force (a form of light) transmits that force to cause another magnet to wiggle somewhere else. We describe this as a causal connection. Light represents the fastest possible signalling possible between two events such that the extreme limits of signalling follow null trajectories. 

Shine a flashlight into empty space ($p$) and follow the light. What ensues is a cone, mapping out all the events that light could reach as it propagates outwards in space and time:
<img src="{{ '/assets/cones.png' | relative_url }}"
     alt="cones"
     style="width:250px !important; height:auto;">
This is the future lightcone of event $p$, and working backwards we can describe a past lightcone of all the events which could have send a signal to $p$, thereby influencing it. Events within these cones can influence/be influenced by the event $p$. Outside the cone there can be no causal relation without faster-than-light signalling. The set of events that make up the future/past lightcone is called the causal future/past of $p$, $J^+(p)/J^-(p)$. We expect that the light emitted from $p$ travels onwards and outwards forever, reaching an arbitrarily distant observer. The point at the end of the road where all light escapes to in the end is called future null infinity $\mathcal{I}^+$,(technically not in the manifold; look up conformal compactification for more detail).

### Horizons

The set of events $J^-(\mathcal{I}^+)$ is the causal past of future null infinity - all events that can send a signal to infinity. Critically, we ask does $M\cap J^-(\mathcal{I}^+)=M$ always hold? In simpler terms, for any spacetime can every event in the universe send a signal to infinity? No, and the implications are extraordinary. In certain spacetimes, there must exist a set of events from which no signal can escape to infinity - events which are causally disconnected. These spacetimes contain a black hole. If a magnet is inside a black hole then no matter what I do to it, it can never cause anything to happen to a magnet outside the black hole. If $J^-(\mathcal{I}^+)$ is the set of points that can send a signal to infinity, then the black hole is the complement of this set with respect to the entire manifold $B=M/M\cap[J^-(\mathcal{I}^+)]$ (we cut out all the points that can reach infinity from the manifold):
<img src="{{ '/assets/venn.png' | relative_url }}"
     alt="worldlines"
     style="width:800px !important; height:auto;">
The universe is partitioned by $\mathcal{H}^+=\text{Boundary}(J^-(\mathcal{I}^+))$. This is the future event horizon. A subtle point is that this horizon is a global feature but an observer crossing it feels nothing special locally. 

### A Dark Star

Over 200 years ago Laplace, armed only with Newtonian gravity, speculated about a “dark star” - a star whose gravity was so great that its attraction would stop its light from ever leaving. Shortly after Einsteins publication of his general theory of relativity, Schwarzschild imagined a similar object in this more advanced formalism of gravity, where the curvature is so strong and creates a well so deep that even the null trajectories of light cannot escape.

Laplace and Schwarzschilds dark star describe the most commonly understood form of a black hole, but the true definition of a black hole extends far beyond them as demonstrated. Our definition is generic.

### The Singularity

In the aforementioned Schwarzschild solution, one of the key features is that at the centre of the black hole, the curvature isn’t just deep but infinitely deep. The curvature diverges and spacetime ceases to exists there. This point is called a singularity. 

In fact singularities are worse than simply points where curvature diverges, they are defects in spacetime. They are points where a geodesic simply stops (defining geodesic incompleteness of the entire manifold). 

Penrose and Hawking proved that under very general conditions, singularities are inevitable in gravitational collapse, but it is crucial to emphasize, the global definition requires no singularity. The black hole is defined by causal relations, not by what happens in the interior and besides, Quantum Gravity has singularity resolution for gravitational collapse (supposedly).

If we trust the mathematics, the singularity leads to another universe through the Einstein-Rosen bridge. We can have black holes without horizons (see violations of cosmic censorship) and even without singularities. Our conclusions are clear. Black holes are not simply astrophysical objects, their presence in a universe fundamentally changes it.
