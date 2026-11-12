---
type: idea
title: A normal-tube multiplicity bound for Gaussian low-count halfspace sets
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - gaussian-geometry
  - rank-level-sets
  - background-gate
---

New geometric lemma proposed by root, currently under independent check; not yet an approved result or FDR proof. Let unit normals n_j and offsets b_j≤B define A_k={x:#{j:n_j·x>b_j}≤k}. On a regular boundary facet belonging to hyperplanej and oriented into an additional violation, shoot rays y=x+t n_j,t>0. Set d_i(y)=n_i·y−b_i. For any indexi with d_i(y)>d_j(y)=t>0, at the projected pointx=y−t n_j one has n_i·x−b_i=d_i−t(n_i·n_j)>0. Since x has at mostk other strict violations, j must be among the topk+1 positive signed distances at y. Thus these outward facet tubes should have multiplicity≤k+1 a.e. (coincident/duplicate hyperplanes require explicit merging or a precise weighted-count convention). Each tube integral equals its Gaussian facet area times ∫_0^∞e^{−b_jt−t²/2}dt≥Q(B)/φ(B). Integrating multiplicity over the entire Gaussian space, without claiming rays stay outside A_k, yields proposed Gaussian boundary area ≤(k+1)φ(B)/Q(B), independent of dimension and number ofhalfspaces. For Gaussian alternatives T_j=θ_j+v_j·Z withθ_j>0, common thresholdz givesoffsets z−θ_j≤z. This may control low-alternative-count/rare-BH-rank regions. It does not itself sum the full BH false-discovery integrals or establish the sharp constant. First check all ray orientations, degeneracies and tube Jacobians; do not assume convexity for k>0.
