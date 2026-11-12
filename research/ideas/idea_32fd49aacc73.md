---
type: idea
title: >-
  Source lead for S2: conditional compound-p-value control keeps the level
  supremum outside the null sum
status: resolved
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_private_noise_floor_order
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - cross-discipline-brainstorm-20261110
  - primary-source-lead
  - pending-import-verification
resolved_by: gaussian_bh_conditional_compound_calibration
---

## Verified source lead, not yet imported or adopted
Scoped primary-source check using verify-citations: Rina Foygel Barber and Richard J. Samworth, False discovery rate control with compound p-values, arXiv:2507.21465v2 (official revision 5 August 2026), https://arxiv.org/html/2507.21465v2 , official record https://arxiv.org/abs/2507.21465v2 . Directly read Section 2.1, Theorems 1 and 3, definition (2), and appendix A.3's proof passage. Under null independence and independence from alternatives, Theorem 3 with delta=0 bounds ordinary BH FDR by 1.93 alpha(1+epsilon) if sum of null CDFs is at most N(1+epsilon)t. Full PDF import, native node extraction and independent verification remain REQUIRED before any proof relies on it. No citation asset, approval or bibliography entry is created by this idea. The HTML header and document title carry different dates; preserve actual version provenance at import. Native library search found no matching result; similarly named Simes/OU entries do not cover this theorem. This is a scoped primary-source check, not a retraction or bibliography-wide audit.

## Proposed application: the sum stays outside the free level
New inference, NOT a statement from the source paper and NOT yet verified. In class S, fix G=g; the original null p-values are mutually independent and independent of the alternative vector, including deterministic conditional alternative coordinates. Set
M_q(g)=sup_{0<t<=q} [sum_{i in I0} P(p_i<=t | G=g)]/(N t),
M'(g)=max(1,M_q(g)).
Only thresholds <=q matter for original BH. Replace every original p_i>q by1 and keep all others unchanged, for q<1; BH's largest nonstrict rank and labels are unchanged pointwise. The transformed coordinates remain conditionally independent. For t<=q their summed null CDF is <=N M' t; for q<t<1 it is the constant count probability at q, at most N M' q<=N M't; at t=1 it is N0<=N M'. Therefore the transformed original p-values satisfy Theorem 3 conditionally with epsilon=M'-1 and delta=0. Subject to exact source verification this yields
E[FDP_BH | G] <= min(1,1.93 q max(1,M_q(G))).
No replacement of BH by an arbitrary level selector is made. No individual conditional supremum is summed, and no random leave-one-out threshold synchronization is assumed.

For one-sided nulls with theta_i<=0, M_q is bounded by the zero-mean conditional tail-ratio field in the existing S1 proposal, with the usual N0/N factor. Thus an independently proved averaged Mehler maximal envelope estimate at fixed s0 would imply S up to a fixed constant loss, without separately proving the leave-one-out-window synchronization proposed in S2. That MAY replace one unpaid S2 aggregation gate by a known result. It does NOT prove S1, T, or either original unrestricted BH target. Uniform removal of the noise floor and a common small-q interval remain separate obligations.

## Reuse and next action
Reuse [structured S](idea_7727ae2d6679.md), [the tail calibration](idea_76d8bdfb8584.md), and [the common-interval warning](idea_72355836a88b.md). Do not duplicate this source/theorem if later extracted. Import into a source-permitted native stage or supported library workflow with paper indexing, then independent verify-node before reliance. If the current stage cannot admit the import, preserve this lead and explain the stage limitation instead of editing protected state or driver. A plan may prove the needed independent-average-CDF bound inline by adapting a verified original proof, but cannot merely cite an abstract.

## Resolution

Promoted to the lemma gaussian_bh_conditional_compound_calibration, a dependency of gaussian_bh_one_sided_universal_order_upper.
