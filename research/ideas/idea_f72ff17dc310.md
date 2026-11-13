---
type: idea
title: Per-null reduction proves the angular-cluster entropy bound with explicit A_1
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_angular_cluster_entropy_bound
tags: []
---

Found in refute search r1 slot 1 (record search_gaussian_bh_angular_cluster_entropy_bound_r1_boundary_degenerate). Steps: split each cluster on {Z_{v_j}>beta_j} (cost barPhi(beta_j)); on the complement use the per-null Lei identity, so each null contributes (q/m)E[G_i; Z_{v_j}<=beta_j], G_i=sup_{t<=q}F_{i,Z}(t)/t. With Y=a_i^T Z/r_i: Lei integrated bound on Y<=u gives 1/2+gamma_i u/sqrt(2 pi); on Y>u use G_i<=1/barPhi(Y) (from barPhi(x)>=barPhi(Y) barPhi((x-rY)/s)); then int_u^{beta_j} phi/barPhi = log(q/barPhi(beta_j)) and the off-strip part int_{beta_j}^infty (y+1) Phi((beta_j-rho y)/sigma) dy <= A*(kappa)=2(kappa+1)(kappa Phi(kappa)+phi(kappa))+2((kappa^2+1)Phi(kappa)+kappa phi(kappa)), using beta_j(1-rho)/sigma<=beta_j sigma<=kappa and rho>=1/2. Zero loadings: G_i<=1.
