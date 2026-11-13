---
type: idea
title: >-
  Termwise proof of the clump-bracket bound: each rejected i in S has Psi_i >=
  1/R
status: draft
idea_kind: approach
origin: agent
related_assets:
  - bh_clump_bracket_pathwise_bound
tags: []
---

For i in R_q(p) cap S: p^{(i,*)} <= p gives R_{i,*} >= R, so the indicator holds; Np_i/q <= R; D_i <= R since clumpmates with p_j <= p_i are rejected; R_{i,0} <= R because zeroing an already rejected p_i keeps khat, and raising clumpmates to 1 cannot raise the BH count. Summing over rejected i and dropping the nonnegative other terms gives the pathwise bound. Found in refute search round 1 slot 1.
