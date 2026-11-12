---
type: idea
title: >-
  Centering a two-mark scalar posterior retains the thin-band mass in the
  coherence budget
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_mixed_coherence_trace_budget
tags:
  - gaussian-bh
  - mixed-coherence-budget
  - scoped-proof-step
  - thin-rank-band
---

## Scoped proof step

The failed coalescing-rank-band search suggests centering at the larger terminal Mills mark before applying entropy Cauchy--Schwarz. This is a local proof tool, not a proof of the unrestricted target.

In the precisely checked family from [the coalescing-band candidate](../candidates/cand_gaussian_bh_mixed_coherence_trace_budget_r3_s1_coalescing_rank_band.md), let N=2, d=1, v_1=v_2=1, theta=(0,-c), U=barPhi^{-1}(q), A=barPhi^{-1}(q/2), 0<delta<1/A, c=A-U+delta, and T=A+delta. The actual largest-rank BH rule has R=1 on E=[A,T) and R=2 on [T,infinity); f=1_{Y>=A}, F=q/2 and D=log(2/q). Put b_2=1/H, b_1=1/h(A), Delta=b_2-b_1>0, r=Hb_1, p=Q(E), and rho_t=Q(Y in E | F_t). Then a_t=b_2-Delta rho_t. This is the prescribed FDP-tilted heat posterior.

Once the candidate's absolute integrability and endpoint identity have been checked, subtract the constant b_2 in that identity. The constant cancels using E_Q Y=E_Q int_0^1 beta_t dt, leaving
$$
M=-F\Delta\mathbb E_Q[Y\mathbf1_E]+F\Delta\mathbb E_{\mathbb Q}\int_0^1\rho_t\beta_t\,dt\le F\Delta\sqrt{2Dp}.
$$
Here Y>=A>0 on E, E int rho_t^2 dt<=p by conditional Jensen, and E int beta_t^2 dt=2D. Conditional Jensen for a_t also gives
$$
1-x\ge p(1-r^2).
$$
Thus the shrinking band mass cancels only after taking its square root on both sides:
$$
\frac{M_+}{q\sqrt{1-x}}\le\frac{\sqrt{2D}}{2H}\sqrt{\frac{1-r}{1+r}}\le\frac1{\sqrt2}<1
$$
for U>=3, using H>=U and D<=U^2. The monotonicity calculation in the candidate establishes K_t>=0, its absolute trace integrability, and the endpoint identity before this estimate is used.

## Scope and unresolved extension

This argument covers only the displayed two-null, same-direction, two-mark family, including delta tending to zero with q. It prevents loss of the vanishing band probability in this local positive-trace calculation. It does not control signed vector marks, several interacting bands, arbitrary dimension, the entropy-linear term, or universal absolute trace integrability. Extending the centered-mass cancellation to those settings is unresolved.
