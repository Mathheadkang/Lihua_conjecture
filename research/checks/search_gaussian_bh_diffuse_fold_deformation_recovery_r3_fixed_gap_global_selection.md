---
type: search_round
title: 'Round 3: fixed higher-well test preserves global fold recovery'
target_asset: gaussian_bh_diffuse_fold_deformation_recovery
mode: refute
round: 3
directions:
  - idea_e795dbed36da
  - boundary_degenerate
  - small_cases
candidates:
  - >-
    cand_gaussian_bh_diffuse_fold_deformation_recovery_r3_s1_higher_well_fixed_gap
statement_digest: c94a3fdf2ffe058f0be84badf476c4d08154e9cac43cf7bcae563b030a494568
performed_by: unknown
created_at: '2026-11-09T01:56:52.515Z'
extension_version: 0.0.4
---

## Obstructions

- **Fixed-gap higher-well construction.** The admissible nonlinear model in `cand_gaussian_bh_diffuse_fold_deformation_recovery_r3_s1_higher_well_fixed_gap` passes H1–H6 and fails NOT: its higher competing local well and all globally largest-root switches preserve both signed variations, the sublinear deformation cost, ordinary canonical finite recovery, and the remaining conclusion clauses. For this checked object, sufficiently small deformations change the birth/death window near the unique lowest well while retaining the other global switches. These checks exclude this object as a counterexample; they do not prove the same assertions for every higher-well model. Any extension must identify the globally largest admissible root, rather than substitute the first local root.
- **Boundary-parameter constructions.** The boundary screens produced no new object. Approaching a boundary across fixed models, or coupling a model parameter to the deformation size, supplies no contradiction to a conclusion whose constants and sufficiently-small threshold may depend on the fixed model. This is an obstruction to that counterexample mechanism, not a general crossing estimate.
- **Small-case sign constructions.** The small-case screens produced no new object. The previously fully checked negative-jump model remains a failed counterexample because the target retains the signed jump and both deformation signs. That conclusion remains restricted to the previously checked model.

## Limitations

- Round 3 records one failed candidate and no survivor. The admissible nonlinear higher-well test is now checked, resolving that test case's previously open conclusion checks; absence of a survivor is not a proof of the target.
- No general argument has yet been established for arbitrary admissible nonconvex barriers, all competing roots and switches, non-strict boundary crossings, the birth/death window, or the common-active error. The higher-well object's checks cannot be promoted to such an argument.
- The previously assigned negative-correlation linear test still lacks a complete rigorous NOT check. Earlier actual-rank checks and numerical evidence do not establish its signed variation or ordinary finite recovery.
- The general full-FDR representation, signed variation, finite recovery, conditional finite-comparison implication, and nonempty-hypothesis clause remain unproved by this search summary. Equal-depth competing global wells remain inadmissible under the unique-global-minimum hypothesis.
- No genuinely new proof step beyond the recorded test-case checks is established here; no duplicate or unsupported approach idea is recorded.
