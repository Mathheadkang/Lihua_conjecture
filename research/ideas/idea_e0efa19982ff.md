---
type: idea
title: >-
  Aggregate control needs a bound on inflated null mass; negative cancellation
  saves only order q
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - two-sided
  - aggregate-control
  - negative-budget
  - teaching-handoff
---

Agent-generated correction to the teaching discussion; finite algebra checked locally, but not an independently verified research asset. The researcher authorized autonomous idea handoff.

The suggestion that negative contributions might restore the missing leading factor 1/2 should NOT be adopted as the mechanism. Let Delta_i=E a(T_i;t_i)-1 for the actual forced-zero BH threshold. Since a>=0, Delta_i>=-1, and hence
(q/N) sum_{i in I0} (Delta_i)_- <= q pi0 <= q.
Thus negative expected contributions across nulls cannot compensate an order-qU excess, U=p^{-1}(q)->infinity.

The same obstruction applies to the negative part discarded in the present ordered-baseline inequality. Write b_i=tau_i^flat<=t_i=tau_i and
G_i=1{b_i<p_i<=t_i}/t_i,
D_i=1{p_i<=b_i}(1/b_i-1/t_i).
Pointwise a(T_i;t_i)-a(T_i;b_i)=G_i-D_i. The baseline is independent of the null and calibrated, so E a(T_i;b_i)=1; also 0<=D_i<=a(T_i;b_i). Consequently
0 <= (q/N) sum_i E G_i - (FDR-q pi0)
   = (q/N) sum_i E D_i <= q pi0.
These facts use no nonsingularity or conditional Poisson-binomial approximation. Retaining these particular negative terms cannot by itself produce the sharp leading constant. This observation does not rule out cancellation within some other signed representation whose pieces have different sizes; that would need a separate quantitative argument.

What a useful aggregate route must instead control:
How many nulls (or how much total null multiplicity) can simultaneously have a large positive Delta_i under the SAME Gaussian model, means and actual BH maximum-rank rule. Large isolated Delta_i is compatible with the target if its mass 1/N is tiny. Do not substitute a uniform per-null O(U) theorem for this task.

A particularly clean scope check for candidate idea_32b2df6da76f:
In that model all N-n background nulls equal X, and the active block has exactly one null. On {p(X)>q}, background nulls cannot be rejected, the actual BH count is at most n, and rejecting the active null requires p_i<=alpha:=qn/N. Since the active null p-value is exactly uniform, its FDR on that event is at most alpha. On the complementary event, FDP<=1 and its probability is q. Therefore the elementary bound is
FDR <= q + alpha = q + p(u_n).
Thus a far-tail per-null inflation candidate with u_n=A>>U can still have total FDR at most q+o(q). This makes it an unusually useful test of proof-strength versus target-strength, rather than a promising main-target counterexample. Recheck this elementary bound independently along with the rank construction.

Recommended use: keep this correction beside the high-priority padding diagnostic, and prioritize null-mass/selection constraints over a generic positive-negative cancellation argument. It corrects the assistant's earlier tentative intuition; it is not a claim made by the researcher.
