---
type: idea
title: Verified normal-tube bound for Gaussian low-count regions
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - gaussian-perimeter
  - proved-local-tool
  - rank-level-sets
---

The geometric candidate in idea_90d6b04eaf56 has now been independently reconstructed and root-checked with a complete elementary proof, no novelty claim. Let unit normals n_j, offsets b_j≤B, and A_k={x:#{j:n_j·x>b_j}≤k}. Its reduced-boundary Gaussian perimeter satisfies Pγ(A_k)≤(k+1)φ(B)/Q(B), for all finite dimensions/counts and arbitrary degeneracy among Gaussian projections. Proof: orient each physical regular boundary patch toward the disallowed side, selecting an original constraint. Its outward normal tube has Gaussian mass equal to patcharea times∫_0∞e^{-b_jt−t²/2}dt≥patcharea Q(B)/φ(B). At a pointy inL distinct tubes, choose minimum positive source distance t_j. Each other sourcei gives an original strict violation atx_j=y−t_jn_j because t_i−t_j(n_i·n_j)>0; henceL−1≤k. Integrate multiplicity over the WHOLE space (rays may reenter the nonconvex set). Identical constraints are grouped; opposing coincident hyperplanes are oriented using original weight increase. Weighted extension with original w_j≥w_min: Pγ({Σw_j1{violation}≤s})≤(floor(s/w_min)+1)φ(B)/Q(B). Complete proof, all degeneracies, fixed-order density/band corollaries, and exact finite-N BH primary-block implications: research-local/gaussian_k_exception_background_tubes_20261104_v1.md. For alternatives θ_j>0 at common thresholdz, offsetsz−θ_j≤z. This supplies genuine dimension-free geometry but does NOT sum varying BH ranks or prove the target constant. The variable-rank and offset budgets remain missing. Only a draft observation; not a native-approved asset.
