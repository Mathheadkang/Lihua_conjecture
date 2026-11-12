---
type: idea
title: 'Risk: constant-width Mehler smoothing may have the same ladder obstruction'
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_translated_cell_mehler_congestion
tags:
  - bandwidth-repair-risk
  - explicit-family
  - unverified-extension
---

Do not repair the deprecated gate merely by replacing tau=1/log(1/q) with a fixed positive time. The following STRONGER extension of the verified ladder calculation is unverified and needs a fresh independent check. It is not part of the approved counterexample and does not refute either BH root.

Fix any 0<q<=min{S(1),1/(8e)} and any fixed Mehler variance v in (0,1). Put s=sqrt(v),
$$
\delta=(1-s)/(4s),\qquad c=(3+s)/4.
$$
Then c>s(1+delta), so choose a fixed kappa strictly between (1+delta)^2/2 and c^2/(2v). Put U=S^{-1}(q), B=(1-s)U/8. For eta->0 set
$$
A=B/[(1+\delta)\eta^2],\quad m=\lceil e^{\kappa A^2}\rceil,\quad N=2m.
$$
Use the SAME finite loading pattern: m true scores eta G0+sqrt(1-eta^2)Gi, m alternative scores (1+eta)u_j-G0, with u_j=S^{-1}(qj/N). Evaluate H at independent N(0,v) latent coordinates and select k with A<=u_k<=(1+delta)A.

The same candidate rank intervals J_k and kernel integration would give
$$
E H(Y)\ge C(q,v)\,q\,\eta\sum_k\Delta_k/v
\asymp C(q,v)\,q\,\delta B/[(1+\delta)v\eta]\longrightarrow\infty.
$$
The checks to make rigorous are explicit: at source point Y+u_k a_i, the other true-null mean shift is <=B+eta on J_k. For eta small this is <=(1-s)U/4, so at ALL grid thresholds u_l>=U their Gaussian tail is <=S(u_l); their mean count/rank ratio is <=q/2. At thresholds >=cA, a union bound tends to zero by kappa<c^2/(2v). Below cA, a Binomial tail/union bound gives true count <=l/4, while false count is <=l exp[-U eta(1-c)A/(1+eta)]<=l/4. The minimal lower-grid rank grows exponentially because kappa> (1+delta)^2/2>c^2/2. Endpoint rounding and the scalar full-rank mask must still be checked independently.

If correct, this would defeat every fixed variance v<1 already at fixed q by taking eta sufficiently small and N sufficiently large. It would explain the failure structurally: smoothing shrinks the unmarked private-null variance, removes the null-population feedback that limits the original BH rank, and allows translated contributions from a long ladder to pile up. A legitimate successor route would have to preserve the unmarked background variance or control an integrated/signed object, not assume that a constant bandwidth alone repairs the pointwise gate.
