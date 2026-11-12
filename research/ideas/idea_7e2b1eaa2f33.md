---
type: idea
title: Universal order via actual-mean weighted conditional rank flux
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

Unproved replacement route for the universal one-sided order target; no proof or approval is claimed. This supersedes only the counterfactual-centered positive-flux gate in [the earlier route](idea_f2adba6d4a2d.md), whose auxiliary obstruction is recorded with independent cold-review provenance in [the negative-null harmonic-flux risk](idea_bb18a2b30414.md). Preserve both earlier records.
For each true null i with theta_i<=0, set X_i=T_i-theta_i. Condition the other coordinates by Gaussian regression on X_i=x, retaining their independent jointly Gaussian residual vector even when its covariance is singular. Let R_i(x)>=1 be the ordinary largest-qualifying BH rank after forcing only p_i to zero, and tau_i(x)=q R_i(x)/N. This rank should be a finite step function of x; ties, constant affine coordinates, and simultaneous jumps must be handled explicitly.
Retain the actual negative mean by defining g_i(x)=barPhi(x)/barPhi(x+theta_i) and h_i^theta(x)=min{barPhi(x)/tau_i(x),g_i(x)}. On a rejection cell, barPhi(x+theta_i)<=tau_i(x), so h_i^theta=barPhi(x)/tau_i(x) and its ordinary derivative is -phi(x)/tau_i(x). On a nonrejection cell it equals g_i(x); Gaussian hazard monotonicity suggests g_i'(x)<=0. Both limits and all integrals require proof.
Candidate bounded-variation identity: I_i=integral phi(x) 1{barPhi(x+theta_i)<=tau_i(x)}/tau_i(x) dx equals 1 + sum of signed jumps of h_i^theta + integral over nonrejection cells of g_i'(x) dx. It would imply I_i<=1+sum of positive jumps of h_i^theta. This avoids the previous ghost jumps when the actual negative-null coordinate is rejected on neither side of a rank drop.
The first substantive gate is a uniform bound on the sum over all true nulls, averaged over their regression residuals, of these positive ACTUAL-mean jumps by C N(1+U), U=barPhi^{-1}(q), for a finite universal C and a universal small-q interval. No uncontrolled logN, rank, factor count, or direction entropy is allowed. First establish the force-zero identity, exact BV identity, boundaries, singular cases, and constants. Then attempt this aggregate gate; stop at the first unproved essential proposition and save the precise obstruction. Do not replace it by separately centered null counterfactuals.
If proved, this gate plus the coordinate decomposition would give a universal q[1+sqrt(log(1/q))] bound and hence the exact current acceptance criterion after a universal restriction on q. All these implications and dependencies require formal execution and fresh independent verification before approval.
