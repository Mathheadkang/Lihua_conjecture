---
type: idea
title: Common-rank Gaussian Stein field for the complete finite BH payoff
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

A proposed finite, conditioning-free starting gate for the unrestricted one-sided order theorem; no uniform FDR bound is asserted.

Write T_i=theta_i+v_i.G with unit v_i in R^d and G standard Gaussian; choose a Gram representation even when Sigma is singular. Let X_i=v_i.G and m(x)=barPhi(x)/phi(x). Partition R^d by the distinct affine hyperplanes H_{jk}={v_j.G=barPhi^{-1}(qk/N)-theta_j}, merging coincident hyperplanes, including opposite orientations. On each open cell use the original largest BH rank R, original null labels, and actual rejected set. Put U=R^{-1} sum_{i in I0 and rejected} m(X_i)v_i, with U=0 when R=0.

Inside each cell, m'(x)=xm(x)-1 gives G.U-div U=V/R exactly. Since every selected true null has X_i>=barPhi^{-1}(qR/N)-theta_i>=barPhi^{-1}(q), U is bounded by m(barPhi^{-1}(q)) when q<1/2. Gaussian Gauss-Green on the cells suggests the exact GLOBAL identity
FDR=sum_F integral_F phi_d(g) n_F.(U_+(g)-U_-(g)) dH^{d-1}(g),
where each interface is counted once. For each distinct supporting hyperplane its disjoint facet pieces have total absolute contribution at most 2 m(barPhi^{-1}(q)) phi(a), where a is its signed distance to zero. Thus finite absolute integrability and vanishing outer boundary terms can be proved without a nonsingular approximation. Values on interfaces are Gaussian-null; coincident crossings retain complete traces rather than artificial individual jumps.

This is a concrete common-rank signed numerator/denominator representation to prove inline, not the missing estimate. The remaining open gate is a rank-compatible allocation of its NET Gaussian flux at cost O(q sqrt(log(1/q))) uniform in N and means. Bounding each facet's positive part, replacing Mills values or conditional kernels by one scalar exposure, or summing all ranks would repeat known losses. Compare existing signed p-path results before claiming this representation is materially new.
