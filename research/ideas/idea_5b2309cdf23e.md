---
type: idea
title: >-
  Round of 2026-11-05/06: proved lemmas awaiting extraction and verification,
  and the common obstruction
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - round-summary
---

Status: neither target proved; no refutation candidate. Six plans failed this round (five two-sided, one one-sided), all at the same core.

Proved in full inside plan Progress sections, NOT yet independently verified (the researcher chose to extract them as separate draft assets in the targets' dependency chain and verify each; extraction was not started when the session stopped):
1. Exact exogenous-pivotal identity, two-sided, any Sigma incl. singular: FDR = q*pi0 + (q/N)*sum_{i in I0} Delta_i. Source: plan_two_sided_exogenous_pivotal_blocks_20261105, Progress (P0, A0-A4; also B1-B3, B4-a for the block class).
2. Baseline-subtracted pivotal identity: Delta_i = E[a(T_i;tau_i) - a(T_i;tau_i^flat)] <= E[1{tau^flat < p_i <= tau_i}/tau_i]; zero when the null is alone in its block. Source: plan_two_sided_baseline_subtracted_pivotal_probe_20261105, Progress step 3.
3. Deficit-curve reduction in the block class: R = max{k: M_z(k) >= D*(k)}, R^flat = max{k: D*(k) <= 0}, D* nondecreasing with increments in {0,1}. Source: plan_two_sided_central_deficit_curve_lei_20261105, Progress step 3.
4. Exact two-sign curve exclusion EX-Q (curve version of Lei Lemma 4.5). Source: plan_two_sided_averaged_flatness_exclusion_20261105, Progress step 7; same plan also proves MLR monotonicity 6b, the rigidity rate 6c and subcritical flatness 6d (r >= U^{-1/5}).
5. One-sided Lemma C (free central window): central contribution <= (q/N) sum (1/2 + gamma_i U/sqrt(2 pi)) for every multifactor model. Source: plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106, Progress steps 1-3.
6. Radial strip refinement RS: FDR <= (3/2) q pi0 + (qU/sqrt(2 pi)) gamma_bar_0 + strip term; corollary: the one-sided sharp constant holds whenever E_s = (1/N) sum_h sum_{i in G_h} log(1/pi_h)/s_i = o(log(1/q)). Same plan, Progress step 4; also carrier lemma 5b and tilt localization 5c(ii).

Common obstruction: control of the threshold for nulls in a block whose factor is extreme, against arbitrarily many other blocks. Two-sided form: supercritical flatness bound uniform in the number d of heavy loading-one background blocks (6e) and small loadings (6f). One-sided form: budget telescoping in the pooled shell lemma (5c(v)): the carrier lower bound holds only on a counterfactual event whose background contains the extreme block. Beyond the block class, no mechanism for arbitrary Sigma (a decoupling lemma with o(qU) error uniform in N is missing). The sibling project Lihua_conjecture_claude parked its one-sided block theorem at the same step.

Evidence (not proof): every probe decreased in q; deterministic-curve DCL is false two-sided (2 gamma_r factor, both signs track) but realisable backgrounds gave ratios <= 0.70 of the slope; the one-sided 5a probe with a perfect line-hugging background gave full FDR/target <= 0.40, decreasing. Scripts: session scratchpad exec5/, exec6/, exec7/, os1/, plan6/ (temporary; key code is reproduced in the plan files).
