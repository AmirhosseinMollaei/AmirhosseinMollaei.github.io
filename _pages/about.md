---
permalink: /
title: "About"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

{% include base_path %}

I am a PhD student in [Mechanical Engineering](https://engineering.lehigh.edu/mem) at
[Lehigh University](https://www.lehigh.edu/), in the
[Autonomous and Intelligent Robotics Lab (AIRLab)](https://robotics.lehigh.edu/), advised by
[Prof. Nader Motee](https://engineering.lehigh.edu/faculty/nader-motee). I started in 2023 and
passed my doctoral general examination in March 2026. Before Lehigh I did my B.Sc. at Sharif
University of Technology.

I work on robots that have to stay safe while they are still building the map they depend on. What
keeps me on this problem is that it is really one problem rather than two. The viewpoint a robot
most wants is usually the one it can least afford to approach. A lot of systems settle that with a
weight someone tuned by hand. I would rather write the conflict down and solve it.

So my work puts the safety certificate and the perception objective into a single optimization
problem over a 3D Gaussian-splat map, solved fast enough to sit inside the control loop. Safety
stays a hard constraint. Perception is what yields when there is no safe way to see more.

Three questions take up most of my time: how to make view selection cheap enough to run online, how
to make a safety guarantee hold against the uncertainty the map actually carries instead of a
thresholded occupancy grid, and how to extend both to teams of robots that cannot share their maps.

I care about getting this onto hardware. My methods run in Isaac Sim and on real platforms,
including Ackermann-steered mobile robots and a Kinova Gen3 manipulator.

<div style="border:1px solid rgba(128,128,128,.4); border-left:5px solid #c9521f; padding:1.1em 1.3em; margin:2em 0; border-radius:3px;" markdown="1">
**Open to a Summer 2027 research internship.** I am looking for a position in robot perception,
planning, and control. If your team works on these problems, I would be glad to hear from you:
[ammb23@lehigh.edu](mailto:ammb23@lehigh.edu).
</div>

## Demo

{% include demo-video.html src="hero.mp4" caption="Safe active perception running online in Isaac Sim: a 3D Gaussian-splat map, a risk-aware barrier, and next-best-view selection in the loop." %}

## Research interests

- **Safe active perception** — joint perception and control under a map that is still uncertain
- **Next-best-view planning** — information-theoretic view selection, expected information gain,
  Fisher information, oracle-efficient selection
- **3D Gaussian Splatting** — explicit differentiable radiance fields for real-time robotics
- **Active scene learning** — online map construction driven by what the robot still needs to see
- **Distributed and multi-robot optimization** — consensus ADMM, coupled next-best-view problems,
  privacy-preserving coordination

## Recent publications

{% assign recent = site.publications | sort: "date" | reverse %}
{% for paper in recent limit: 5 %}
- [{{ paper.title }}]({{ base_path }}{{ paper.url }}) &middot; *{{ paper.venue }}*
{% endfor %}

See the [full publication list]({{ base_path }}/publications/), or
[my Google Scholar profile](https://scholar.google.com/citations?user=Epox5eQAAAAJ&hl=en).
Each paper's demo video is on the [Research]({{ base_path }}/portfolio/) page.

## News

<!-- To add a news item, copy the line format below and put it at the TOP of this list. -->
<!-- - **[Mon YYYY]** What happened. -->

- **[Oct 2026]** Poster accepted at the Northeast Robotics Colloquium, Princeton University:
  *Perception Control Barrier Function Approach to Next-Best View-Action Planning in 3D Gaussian Maps*.
- **[Oct 2026]** Posted *TRACE* to arXiv. *Splat-CBF* and *TRACE* are both under review at ICRA 2027.
- **[Sep 2026]** *AGILE-GS* and *LiTe-GS* are under review at WACV 2027. Both preprints are on arXiv.
- **[Sep 2026]** Presented *SemSafe-3DGS* at the SeMaNa workshop, IROS 2026.
- **[Jul 2026]** Presented at ECC 2026 in Reykjavik.
- **[Jun 2026]** Presented at ICRA 2026 in Vienna.
- **[Jun 2026]** Posted *Multi-Agent Next-Best-View Optimization for Risk-Averse Planning* to arXiv.
- **[May 2026]** Our CDC 2026 paper was accepted as an invited session paper.
- **[Mar 2026]** Passed the PhD general examination at Lehigh.

## Education

- **Ph.D.**, Mechanical Engineering, Lehigh University, 2023&ndash;present.
  Doctoral general examination passed, March 2026.
- **M.S.**, Mechanical Engineering, Lehigh University, 2025
- **B.Sc.**, Sharif University of Technology, 2023

## Teaching

Teaching assistant at Lehigh University for **Convex Optimization** and **Control Systems**.

## Technical skills

- **Programming:** Python, C++, MATLAB
- **Robotics and simulation:** ROS/ROS2, Isaac Sim, Isaac Lab, Habitat-Sim, MuJoCo
- **Methods and tools:** PyTorch, 3D Gaussian Splatting, control barrier functions,
  convex optimization, Git, Linux
- **Platforms:** Kinova Gen3, Ackermann-steered mobile robots, RGB-D cameras
