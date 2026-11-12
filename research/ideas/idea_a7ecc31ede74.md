---
type: idea
title: >-
  Bounded FDP reweighting and conditional bridges for the full correlated
  two-test single-null family
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_entropy_coherence_trace_budget
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - conditional-bridge
  - bounded-reweighting
  - two-test
  - scoped-proof-ingredient
---

Round 2 supplies a new proof ingredient, presently only a draft candidate calculation, in cand_gaussian_bh_entropy_coherence_trace_budget_r2_s3_correlated_two_test. It has not undergone native independent proof verification and is not an approved dependency. Keep its full scope: N=2, one original null mean theta_0<=0, one alternative mean mu>0, any unit-diagonal covariance rho in [-1,1], including singular endpoints, and the actual largest-rank BH rule. No conclusion for arbitrary numbers of tests is asserted.

Let u_1=normal-survival-inverse(q/2), U=normal-survival-inverse(q), H=h(U), A=u_1-theta_0, c_1=1/h(u_1), c_2=1/H, d_0=c_2-c_1 and delta=H d_0. On the actual one-rejection null cell C_1 the terminal FDP is 1, and on the two-rejection cell C_2 it is 1/2. In particular, in the latent null coordinate Z the complete FDP f lies between 1/2 and 1 whenever Z>=A, independently of the alternative coordinate. If p=Q(C_1) and pi_t=Q(C_1|F_t), then b=e_null(c_2-d_0 1_{C_1}), a_t=e_null(c_2-d_0 pi_t), and 1-x=2delta p-delta^2 integral E_Q pi_t^2 dt >=delta(2-delta)p.

Write beta_t=gradient log(P_{1-t}f)(W_t) and W^Q_t=W_t-integral_0^t beta_s ds. The product-Ito identity for the bounded heat posterior gives M=-F d_0 p E_Q[e_null dot W^Q_1|C_1], with M=0 if p=0. This retains the complete signed trace rather than a single terminal interface.

For each heat state, compare the terminal null coordinate with its unweighted Gaussian law truncated at A. On that tail the FDP weight is in [1/2,1]; subtracting 3/4 in its covariance with the coordinate and using truncated variance at most 1-t raises its mean by at most sqrt(1-t)/2. Adding any lower-coordinate mass only lowers that mean. Therefore the complete drift in the null direction is at most the halfspace-A drift plus 1/(2 sqrt(1-t)). Given an actual terminal point of C_1, its null coordinate g>=A and its path remains the original Brownian bridge. Monotonicity and h(z)<=z_++h(0) then give E[integral beta_null dt-g|terminal g]<4. Combining these statements gives M_+<=4F d_0 p <=(4q/H)(1-x), uniformly over all parameters of this family.

A possible next proof step is to find an actual-rank decomposition that retains an analogous bounded-reweight comparison. The two-state calculation alone does not provide one: for N>2, neither its two-valued b nor the [1/2,1] tail reweighting holds unchanged, and transitions among several true-null directions bring additional vector terms. These are explicit unresolved obligations, not assumptions of the target lemma.
