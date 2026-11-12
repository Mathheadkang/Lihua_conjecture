---
type: idea
title: >-
  Exogenous-pivotal decomposition: only threshold moves caused by the null's own
  correlation line can inflate the FDR
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - pivotality
  - new-route
---

New route, 2026-11-05, designed to avoid both obstructions in idea_0d2e69e0ba3b and the pointwise budget certificates refuted in the 2026-11-04 plans. (A) Exact decomposition, any admissible model, singular allowed. For a true null i regress the OTHER tests on T_i: T_{-i}=theta_{-i}+c_i (T_i-theta_i)+Y_i, c_i=Sigma_{-i,i}, Y_i independent of T_i. Let tau_i(x) be the forced-zero BH threshold when the others equal theta_{-i}+c_i x+Y_i; the actual LOO threshold is tau_i(T_i-theta_i), and the EXOGENOUS threshold tau_i^ex=tau_i(0) is independent of T_i. Then E[1{i in R}/(R v 1)]=(q/N){E[Qbar(v(tau_i^ex)-theta_i)/tau_i^ex]+Delta_i}, Delta_i=E[1{p_i<=tau_i(x)}/tau_i(x)-1{p_i<=tau_i(0)}/tau_i(0)], and the first bracket is at most 1 (one-sided theta_i<=0; equality two-sided). Hence FDR <= q pi0 + (q/N) sum_i Delta_i exactly. Delta_i is a one-dimensional threshold-sensitivity along the null's own covariance line; it vanishes unless moving the others by c_i x changes the BH rank (pivotality), and it is <=0 for purely positively correlated movers (duplicates do not inflate). Subset monotonicity: tau_i(x) >= BH threshold of any subset of the others (same denominator N), so floods from any subset are floors. (B) First proving ground, a genuinely broader class than one factor that defeats the dimension and entropy bounds: independent one-factor blocks, arbitrary number G(q) of blocks, arbitrary loadings, means and block sizes. Heuristics: (i) a block can move the union threshold only where the complement count lies within the block's own count of the BH line; (ii) a block whose nulls tilt up can lower the threshold only through negatively loaded alternatives, which are significant at typical factor values, so every adapting block floods at its own top threshold and the union threshold is at least the largest exogenous block contact; (iii) a non-adapting block is pivotal only through null self-rejection, whose capped likelihood-ratio tail costs about (q m_g/N) log(1/(1-c))/(kappa_g sqrt(2pi)) with c the complement's fraction of the line; (iv) a near-line exogenous background independent of a block gives FDP about the gap epsilon on an event of probability about q pi0/(epsilon kappa), hence no inflation. Target proposition for the block class: sum_i (q/N) Delta_i <= q pi0 u/sqrt(2pi) (1+o(1)) + O(q) uniformly in G. (C) General Sigma needs a global pivotality inequality summing Delta_i over nulls along their own lines; this is the open step and must not be replaced by per-cell coefficient budgets.
