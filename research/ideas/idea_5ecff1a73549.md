---
type: idea
title: >-
  After the tail-gate diagnostic, test null-mass amplification with weighted
  atoms and fresh residual copies
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - two-sided
  - aggregate-control
  - multiplicity
  - diagnostic
  - teaching-handoff
---

Priority: follow-up AFTER independently checking the whole-line gate risk idea_32b2df6da76f and the negative-budget correction idea_e0efa19982ff. Agent-generated; a proposed diagnostic and route-selection criterion, not a theorem. Do not alter the current plan's statement or bypass its stop rule.

Decision:
Keep central-region geometry and total FDR as separate objects. Do not require every null's whole-line Delta_i=O(U); do not pursue negative Delta cancellation as the leading mechanism. Test whether making a large positive contribution common among many nulls necessarily changes the actual BH threshold enough to suppress its amplification.

Phase 0: finish the concrete gate diagnostic efficiently.
For the two-block staircase in idea_32b2df6da76f, a second independent scratch check suggests the following clean parameters: r=1/2; take A=u_n with A/U ->4; choose finite N,n so K_min=N p(2A)/q >= A^2. On z in [A/2,A], k=Np(z/r)/q and R=floor(k), and Gaussian hazard h(v)>v should give
0<=u_R-z/r <= log(k/R)/(z/r) <= 1/[A(k-1)].
The uniform Mills calculation then suggests
liminf Delta_i / [U/(2 sqrt(2pi))] >= 4/sqrt(3)>1.
This is a detailed candidate verification recipe, not a native verified result. The contributing window is [2U,4U], and the elementary full-model bound FDR<=q+p(A) still applies. Check endpoint/integer choices and all uniform constants before using it.

Phase 1: exact duplication is a calibration test, not a source of new null opportunities.
Replace selected coordinates by M exact copies, including shared private noise, and represent the resulting ordinary BH procedure using rational atomic weights. For sorted atomic p-values, test p_(j)<=q S_j where S_j is cumulative multiplicity divided by total multiplicity, using the last position in every tie group and the largest qualifying prefix. Compute FDP from rejected null weight divided by rejected total weight. Full duplication of every coordinate must leave FDR unchanged.
For an atom of identical null p-values, the suitable leave-out operation forces the WHOLE atom to zero; verify its contribution identity at the atomic weight, rather than reuse the old individual-coordinate Delta or conditional independence.
Important limitation: the padding example has only two distinct null p-value atoms. Even after arbitrary exact duplication, FDR<=P(any true null rejected)<=2q. Such duplication cannot generate qU leading behavior. Use it to check normalization and mass dilution only.

Phase 2: grow the number of genuinely distinct nulls.
In the active factor block replace the one active null by m nulls
T_l=r Z+sqrt(1-r^2) epsilon_l, l=1,...,m,
with independent private noises, and keep loading-one mean-staircase alternatives plus the independent background block. Use the actual new total N and recompute the actual maximum BH rank. This remains a legal Gaussian target model (and an independent-block model), but for m>1 it is not the old E gate's restriction that all mates have loading one. Label the scope change explicitly.
Scan null mass, r, the staircase's tail location A/U and its finite mesh, and both-sign alternatives. First use modest finite models and analytic conditional counts; any expensive simulation belongs on the configured compute server, not the Mac.

At every parameter point report together:
- full FDR/(qU), target leading coefficient 1/(2 sqrt(2pi));
- central and far-tail contributions separately;
- positive per-null Delta distribution and its null-mass weights;
- the change in the actual selected BH rank as m or weights increase.
Optimize the FULL FDR after the null population changes, not the old per-null objective while pretending the threshold stayed fixed. Distinguish original covariance copies from independent-private-noise copies.

Decision criteria:
If extreme per-null inflation persists only at negligible null mass, seek a bound on the aggregate mass of high-inflation nulls under the common BH selection constraints. A possible bookkeeping variable is H_q(t)=N^{-1} #{i in I0: Delta_i>t}; its integral is N^{-1} sum_i (Delta_i)_+. This is only bookkeeping, not a bound: the next plan must supply a concrete mass/selection inequality from Gaussian geometry and actual maximum-rank feasibility.
If many distinct nulls retain inflation at enough total mass to make full FDR exceed the target along decreasing q, preserve the exact finite models for independent asymptotic counterexample review.
A fixed-q exceedance or a large single Delta is insufficient. If neither regime gives a stable structural pattern, do not turn the bookkeeping identity into another purported proof plan.

The dense-covariance residual-refresh baseline was also considered in this teaching discussion, but it is lower priority: it gives a calibrated identity without yet identifying the missing sharp constraint, and the current context already warns that free two-copy optimization loses a factor of two. Do not spend the next attempt on that identity alone.
