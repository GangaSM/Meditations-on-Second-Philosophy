---
title: But what IS a black hole?
subtitle: Submission to SoME 2025
layout: post
author: Ganga Singh Manchanda
category: physics
---

In the public domain, black holes are generally understood as local astrophysical phenomena. This short article aims to move beyond this treatment and impress upon an enthusiastic (non-expert) reader a global understanding of black holes. By exploring relativity via causal structure rather than tensor calculus, our discussion covers advanced topics whilst remaining accessible.

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
This picture is wrong. In 1905, Einstein (building on the work of Lorentz, Minkowski, Poincaré, etc) ruined everything by coming up with an even better idea - that the flows of space and time are not absolute and are not separate.  We instead picture a malleable and deformable “spacetime” (4D grid) where every point corresponds to both a place and time, an event. The set of points that make up this grid is called the manifold $M$ and all of the universe exists within its confines. Can’t picture it? That’s okay, neither can we. Humans perceive the universe as $3+1$D (Newtonian picture) so visualising 4D geometry can be difficult. Eliminating two spatial dimensions allows us to convey information using spacetime diagrams:
<img src="{{ '/assets/grid.png' | relative_url }}"
     alt="grid"
     style="width:250px !important; height:auto;">
A concise statement of relativity by Wheeler says

> Spacetime tells matter how to move; matter tells spacetime how to curve

As a consequence of this, an empty universe is a flat universe - one with zero curvature in the manifold. In the presence of a mass, “wells” are induced in the spacetime:
<img src="{{ '/assets/well.png' | relative_url }}"
     alt="well"
     style="width:800px !important; height:auto;">

### Geodesics

The manifold $M$ formalises the “arena” that things in the universe exist within, but what things are there? Simply put there are two types of things: matter and light. Matter, burdened by mass, is slow, while light, free of that burden, travels at $c=3\times10^8\,\text{ms}^{-1}$ (in a vacuum) and no faster. Like a bird dragging its feet in water, massless particles grab onto the surrounding Higgs field to acquire mass and in doing so slow down.

Consider a massive particle which exists at some event $p$. If the particle is stationary, its position in space cannot move yet its position in time cannot stop moving. The result is that the trajectory of the particle through spacetime, its worldline, is directly upwards. As the speed of this particle increases towards $c$, so would the angle of its trajectory towards $45^\circ$ - these trajectories are classified as timelike. If that particle was instead massless (a photon of light), it would travel at $c$ and its worldline would be drawn at $45^\circ$ - a so-called null trajectory:
<img src="{{ '/assets/worldlines.png' | relative_url }}"
     alt="worldlines"
     style="width:250px !important; height:auto;">
So long as a particle is free from the influence of external forces, these worldlines are minimal - that is they follow the shortest path through spacetime, a geodesic. In flat spacetime, the shortest path is a straight line. In curved spacetimes, a “straight line” is curved such that geodesic motion deviates from an external observer’s idea of straight, though it is minimal. This is why things fall. The Earth creates a well beneath our feet as seen in the above figure. Matter, following its geodesic, falls into that well and we interpret that falling as a gravitational attraction towards the ground.

### Causality

What events can influence one another? By wiggling a magnet I can cause a magnet somewhere else to wiggle via electromagnetic interaction (in the form of light). We call this a causal connection. To cause something requires a signal to be transmitted from source to receiver such that the fastest way to signal is with light (along a null trajectory). To see how this is relevant, shine a flashlight into empty space ($p$) and follow the light. What ensues is a cone, mapping out all the events that light could reach as it propagates outwards in space and time:
<img src="{{ '/assets/cones.png' | relative_url }}"
     alt="cones"
     style="width:250px !important; height:auto;">
This is the future lightcone of event $p$, and working backwards we can describe a past lightcone of all the events which could have sent a signal to $p$, thereby influencing it. Events within these cones can influence/be influenced by the event $p$. Outside the cone there can be no causal relation without faster-than-light signalling such that these events must be causally disconnected. The set of events that make up the future/past lightcone is called the causal future/past of $p$, $J^+(p)/J^-(p)$. We expect that the light emitted from $p$ travels onwards and outwards forever, reaching an arbitrarily distant observer. The point at the end of the road where all light eventually escapes to is called future null infinity, $\mathcal{I}^+$(technically not in the manifold; look up conformal compactification for more detail).

### Horizons

$J^-(\mathcal{I}^+)$ is the causal past of future null infinity - the set of all events that can send a signal outwards forever. Critically, does $M\cap J^-(\mathcal{I}^+)=M$ always hold? In simpler terms, for any spacetime, can every event in the universe send a signal to infinity? No, and the implications are extraordinary. In certain spacetimes, there must exist a set of events from which no signal can escape to infinity - events which are causally disconnected. These spacetimes contain a black hole. If a magnet is inside a black hole, then no matter what I do to it, it can never cause anything to happen to a magnet outside the black hole. If $M\cap J^-(\mathcal{I}^+)$ is the set of events that can send a signal to infinity, then cutting them out of the manifold (complement with respect to $M$) leaves only the causally disconnected events - the black hole, $B=M/[M\cap J^-(\mathcal{I}^+)]$:
<img src="{{ '/assets/venn.png' | relative_url }}"
     alt="worldlines"
     style="width:800px !important; height:auto;">
A universe containing a black hole is split in two, partitioned by $\mathcal{H}^+=\text{Boundary}(M\cap J^-(\mathcal{I}^+))$. This is the future event horizon and it acts as a point of no return. Once crossed, not even light can escape, justifying the name black hole. A subtle but important point is that while the horizon carries great significance globally, a local observer crossing it may not even notice. The definition given restricts causal relations only, with no requirement that the spacetime interior and exterior to the black hole be different.

### A Dark Star

Over 200 years ago, Laplace speculated about a “dark star” - a star so dense that its gravitational attraction would stop its light from ever leaving. It was tough to take such an idea seriously given the prevailing theories of gravity and light at the time, but in the midst of WWI, shortly after Einstein’s gravitational revolution, Schwarzschild discovered a similar object.

The Schwarzschild solution to the Einstein field equations describes a spherically symmetric, non-rotating mass at the centre of a universe, which creates a well so deep that null trajectories become trapped beyond the horizon. For an observer beyond the horizon all paths point towards the centre as the geometry of spacetime warps to funnel every possible future towards the same fate. Reaching the centre of the black hole becomes as unavoidable as Monday. This dark star captures the essential character of a black hole. Though we can talk about the formation of a black hole from the gravitational collapse of a star and discuss its density and lensing and other such properties, these are not fundamental. Causal structure is fundamental and the Schwarzschild solution satisfies the requirements on causal structure laid out in this article to be called a black hole. 

### The Singularity

At the centre of the Schwarzschild black hole lies a defect where spacetime ceases to exist. A point where curvature isn’t just large, but infinite and relativity fails spectacularly. The singularity. Clearly we should just cut the singularity out of the manifold and the problem is sorted, right? If only. Singularities indicate geodesic incompleteness of a manifold - they are points where a geodesic can simply end. Once a trajectory reaches the singularity there is no next step, no more spacetime to evolve into. Mathematically excising the singularity won’t change this fact. 

Penrose and Hawking proved that singularities are inevitable under gravitational collapse, but it is crucial to emphasise that the global definition of a black hole requires no singularity. A black hole is characterised by causal disconnectedness, irrespective of the features of the interior. Besides, singularities are inconsistent with a quantum theory of gravity and aren’t expected to exist in reality, unlike black holes, which we have a lovely photo of. Still, the singularity serves a purpose - it reminds us that black holes push our theories to breaking point, hinting that a deeper description of reality awaits beyond them. Black holes are not simply astrophysical objects, their presence in a universe fundamentally changes it.
