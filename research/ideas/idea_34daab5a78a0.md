---
type: idea
title: >-
  Orthogonal exposure cancellation as a restricted-family surface-kernel proof
  step
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_fractional_frame_surface_kernel
tags:
  - fractional-frame
  - surface-kernel
  - search-obstruction
---

Target: gaussian_bh_fractional_frame_surface_kernel. Round 1 only establishes restricted-family steps, not the arbitrary-dimensional result. For an orthonormal constraint family v_i=e_i (n<=d) with exposure w=e_1 and a_i>=u>=1, canonical conditioning gives K(y)=phi(y)1_{y>=a_1} product_{i=2}^n S(a_i)<=phi(u)S(u)^(n-1). The frame hypothesis gives c_i<=1 and beta<=n. Consequently K(y)/(sqrt(e)h(u)S(u)^beta)<=exp(-1/2)S(u)^(n-beta)<=exp(-1/2), including zero weights. This exact cancellation explains the failed orthogonal candidate and may guide a proof that controls the loss of one Gaussian tail under general exposure. Aligned rank-one exposure similarly has beta<=1 and K(y)<=phi(u), while opposite positive-threshold constraints are empty. No argument currently extends these steps to arbitrary nonorthogonal frames and arbitrary w; neither search failure nor this proposed approach proves the full target or a BH FDR bound.
