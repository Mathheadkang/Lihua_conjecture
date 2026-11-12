---
type: idea
title: Universal one-sided order via conditional Gaussian rank-drop flux
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

New route for the nonsharp phase: for each true null use X_i=T_i-theta_i and regress all other coordinates on X_i, leaving an independent jointly Gaussian residual vector (singular allowed). Force p_i to zero and write the largest BH rank R_i(x)>=1 as a finite piecewise-constant function of x. For tau_i(x)=q R_i(x)/N and h_i(x)=min{barPhi(x)/tau_i(x),1}, integration by parts on rank intervals should express the centered coordinate contribution as a baseline plus signed jumps of h_i; negative true-null means admit a coordinatewise indicator domination with this forced rank, without invoking global mean monotonicity. Check the exact identity and tie/degenerate boundaries first. The first unproved substantive gate is a bound on the sum of positive rank-drop fluxes, averaged over all nulls and Gaussian residuals, by C N [1+barPhi^{-1}(q)] with C universal. No logN/rank/direction term is allowed, no decoupling or block assumption is made. This gate is a proposed intermediate, not a proved fact; stop and record the exact obstruction if it cannot be established. Compared with prior routes it uses direct conditional regression and finite jumps, allowing fixed constants and bypassing sharp block-flatness gates.
