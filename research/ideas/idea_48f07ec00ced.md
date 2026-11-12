---
type: idea
title: >-
  Antipodal Gaussian pairs force overconditioning and a logarithmic conditional
  envelope
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_conditional_compound_calibration
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - conditional_envelope_obstruction
---

Draft analytic obstruction to using conditional independence plus a pointwise conditional CDF envelope as a complete unrestricted Gaussian proof. This is NOT a counterexample to gaussian_bh_conditional_compound_calibration or to either main FDR bound.

For q in (0,1/8], let m=ceil(1/(4q)), N=2m, and take independent G_1,...,G_m standard normal. All means are zero and all hypotheses are true. Define T_{2j-1}=G_j, T_{2j}=-G_j. The covariance is block diagonal with blocks [[1,-1],[-1,1]], PSD unit-diagonal and singular.

For ANY conditioning variable Z making all original coordinates conditionally independent, conditional finite second moments and T_{2j-1}+T_{2j}=0 imply
0=Var(T_{2j-1}+T_{2j}|Z)=Var(T_{2j-1}|Z)+Var(T_{2j}|Z).
Thus every T_i, and hence every original p_i, is measurable with respect to Z (up to null sets). Its conditional CDF is the corresponding point mass, so M_q(Z)=sup_{0<t<=q} [#{i:p_i<=t}]/(N t). This holds for the common countable rational threshold set plus endpoint. Such conditioning exists: the whole finite vector can be encoded into one real by interleaving binary digits of independent continuous uniforms, outside the null set of dyadic ambiguities; all coordinates are then deterministic and conditionally independent.

Let U_j=2 PhiBar(|G_j|), iid Unif(0,1). The smaller one-sided p-value in pair j is U_j/2, the larger is 1-U_j/2>=1/2. Since q<1/2, ranks above m cannot qualify, and the actual largest BH rank on the original 2m p-values is exactly the largest rank of BH at level q on U_1,...,U_m. Therefore the actual all-null FDR is q, using the standard independent-uniform BH equality (to be re-proved by the leave-zero-out identity before formal use).

Write X=m min_j U_j=N min_i p_i. On X<=2mq, M_q>=1/X. Its exact density is f_X(x)=(1-x/m)^(m-1) on (0,m). For 0<x<=1/2, Bernoulli's inequality gives f_X(x)>=1-x>=1/2. Our finite m choice gives 2mq>=1/2. Hence, for K_q=max(1,M_q), the C=2 envelope bound itself has
E min(1,2q K_q) >= integral_{2q}^{1/2} (2q/x)*(1/2) dx
= q log(1/(4q)).
Its ratio to q sqrt(log(1/q)) diverges as q decreases to zero, uniformly for EVERY conditioning rendering the original coordinates independent, while the actual FDR remains q.

The fragile step disproved is a putative universal Gaussian estimate E min(1,2q K_q)=O(q sqrt(log(1/q))) for this conditional-independence envelope. The calibration lemma can still be true and useful in restricted or differently organized models; its RHS is simply too loose on this full-model counterfamily. The conclusion does not refute fixed positive-private-noise-floor estimates, since this construction has zero private variance, but it blocks unproved uniform removal to singular models using this envelope alone. No source result, existing node, statement or approval is changed. Needs a fresh independent mathematical check before being treated as established.
