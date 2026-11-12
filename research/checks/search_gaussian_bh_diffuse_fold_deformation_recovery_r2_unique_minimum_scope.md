---
type: search_round
title: 'Round 2: equal-depth wells excluded and admissible competing wells unchecked'
target_asset: gaussian_bh_diffuse_fold_deformation_recovery
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - idea_6e2ba420d293
candidates:
  - cand_gaussian_bh_diffuse_fold_deformation_recovery_r2_s1_equal_depth_quartic
statement_digest: c94a3fdf2ffe058f0be84badf476c4d08154e9cac43cf7bcae563b030a494568
performed_by: unknown
created_at: '2026-11-09T01:49:45.109Z'
extension_version: 0.0.4
---

## Obstructions

- Equal-depth multiple-global-well constructions fail the unique-global-minimum hypothesis. The recorded quartic candidate first fails H5 because it has two global minimizers; H6 and NOT remain unknown. It is an inadmissible candidate, not a counterexample to the target.
- Approaching a boundary within a family of fixed admissible models does not by itself violate estimates whose constants and small-perturbation threshold may depend on the fixed model. Linking model parameters to the deformation size does not establish failure for any one fixed model. This observation alone proves none of the target's general crossing estimates.

## Limitations

- This round records one failed candidate and no survivor. Other scans produced no new candidate; absence of a candidate is not a proof of the target.
- The assigned negative-correlation linear test case was not completed as a rigorous NOT check. Earlier actual-rank checks and numerical evidence do not establish its signed variation or ordinary finite recovery; its unresolved conclusion checks remain unknown.
- The new admissible higher-local-well test case, idea_e795dbed36da, remains unchecked. Excluding equal-depth global wells does not dispose of higher local wells or establish the actual globally largest crossing for that test case.
- Compact-gap observations alone do not establish general control of all competing roots, non-strict boundary crossings, the birth/death window, or the common-active error. The full signed variation, finite recovery, conditional finite-comparison implication, and nonempty-hypothesis clause are not proved by this round.
- No genuinely new proof step was established by this summary. No duplicate or unsupported approach idea is recorded.
