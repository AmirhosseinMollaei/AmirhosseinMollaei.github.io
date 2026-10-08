---
title: "TRACE: Privacy-Preserving Next-Best-View Selection"
collection: portfolio
order: 3
date: 2026-09-30
video: trace.mp4
excerpt: "Under review, ICRA 2027. Share the light, not the map. Robots contribute to each other's information gain by exchanging two ray aggregates rather than their splats, reaching 97.9% of the centralized information gain."
---

{% include demo-video.html src="trace.mp4" caption="Privacy-preserving next-best-view selection over distributed 3D Gaussian-splat maps." %}

Each robot in a team builds its own 3D Gaussian Splatting map and keeps it private. A robot wants
the view with the largest expected information gain about the splats along its own path. The problem
is that this gain depends on the other robots' maps. Their splats occlude its own and shine from
behind them, so the gain is really defined against the pooled map, and no robot holds that map.

The paper turns on one observation: the coupling passes through only two ray quantities, the
transmittance in front of a splat and the radiance behind it. Both are sums over the hits of the
ray, so both decompose across robots. Each robot sums them over depth bins in its own map along the
rays of a candidate view, and sends those sums with their pose derivatives. The robot planning the
view assembles them into its own expected information gain and the gradient on SO(3). Those
transmittance and radiance aggregates give the method its name.

No robot shares its splats, and the message size does not grow with the map. The reconstruction is
proved exact unless a depth bin behind a splat mixes hits from two robots, with a bounded error when
it does. Over 100 next-best-view decisions in Habitat-Sim, TRACE picks a heading within 15 degrees
of the centralized choice in 83.3% of cases, and its views reach 97.9% of the centralized
information gain.

**Under review** at IEEE ICRA 2027.

- [Paper on arXiv](https://arxiv.org/abs/2610.00822)
