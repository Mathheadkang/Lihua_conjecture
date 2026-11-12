---
type: falsification_check
title: 'Falsification check: gaussian_bh_diffuse_fold_deformation_recovery'
target_asset: gaussian_bh_diffuse_fold_deformation_recovery
outcome: no_counterexample_found
statement_digest: c94a3fdf2ffe058f0be84badf476c4d08154e9cac43cf7bcae563b030a494568
performed_by: unknown
created_at: '2026-11-09T02:02:38.682Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, small_cases: cand_gaussian_bh_diffuse_fold_deformation_recovery_r1_s2_orthogonal_negative_jump failed — NOT fails: both globally correct signed variations and their ordinary canonical finite recoveries agree with the target; the negative jump supplies a sign check rather than a counterexample.
- Round 2, known_counterexamples: cand_gaussian_bh_diffuse_fold_deformation_recovery_r2_s1_equal_depth_quartic failed — H5 fails: the equal-depth quartic has two global minimizers, whereas the target requires a unique global minimum.
- Round 3, idea_e795dbed36da: cand_gaussian_bh_diffuse_fold_deformation_recovery_r3_s1_higher_well_fixed_gap failed — NOT fails: the fixed higher local well and all globally largest-root switches preserve the asserted signed variations, sublinear cost, ordinary finite recovery, and remaining conclusion clauses for both deformation signs.
- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 2, idea_6e2ba420d293: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: **Negative-jump sign-based construction.** The fully checked positive-correlation, orthogonal-direction model in `cand_gaussian_bh_diffuse_fold_deformation_recovery_r1_s2_orthogonal_negative_jump` passes H1–H6 and fails NOT. Its negative conditional-FDP jump is compatible with the target: both admissible deformation signs give the stated globally correct signed variation, and both ordinary canonical finite recoveries agree with it. Thus a negative jump alone supplies no contradiction; the target retains the entire signed jump. This is a failed counterexample construction with all conclusion clauses checked, not a general proof for the surrounding parameter family.
- Obstruction: Equal-depth multiple-global-well constructions fail the unique-global-minimum hypothesis. The recorded quartic candidate first fails H5 because it has two global minimizers; H6 and NOT remain unknown. It is an inadmissible candidate, not a counterexample to the target.
- Obstruction: Approaching a boundary within a family of fixed admissible models does not by itself violate estimates whose constants and small-perturbation threshold may depend on the fixed model. Linking model parameters to the deformation size does not establish failure for any one fixed model. This observation alone proves none of the target's general crossing estimates.
- Obstruction: **Fixed-gap higher-well construction.** The admissible nonlinear model in `cand_gaussian_bh_diffuse_fold_deformation_recovery_r3_s1_higher_well_fixed_gap` passes H1–H6 and fails NOT: its higher competing local well and all globally largest-root switches preserve both signed variations, the sublinear deformation cost, ordinary canonical finite recovery, and the remaining conclusion clauses. For this checked object, sufficiently small deformations change the birth/death window near the unique lowest well while retaining the other global switches. These checks exclude this object as a counterexample; they do not prove the same assertions for every higher-well model. Any extension must identify the globally largest admissible root, rather than substitute the first local root.
- Obstruction: **Boundary-parameter constructions.** The boundary screens produced no new object. Approaching a boundary across fixed models, or coupling a model parameter to the deformation size, supplies no contradiction to a conclusion whose constants and sufficiently-small threshold may depend on the fixed model. This is an obstruction to that counterexample mechanism, not a general crossing estimate.
- Obstruction: **Small-case sign constructions.** The small-case screens produced no new object. The previously fully checked negative-jump model remains a failed counterexample because the target retains the signed jump and both deformation signs. That conclusion remains restricted to the previously checked model.
- Obstruction: The round-4 boundary, small-case, and relaxed-hypothesis screens produced no candidate beyond the families already on the board. Their existing obstructions remain unchanged: model-dependent boundary approaches alone contradict no fixed-model estimate; the checked negative-jump object respects the signed conclusion; equal-depth global wells violate uniqueness; and the checked fixed-gap higher-well object preserves the asserted globally largest-root behavior. This round establishes no additional family-wide obstruction.
- Obstruction: The final boundary and small-case screens supplied no new candidate or family-wide obstruction. The existing local derivative/nondegenerate-minimum and compact-gap screens did not reveal an additional mechanism in the families already considered. Their scope remains that of screening: parameter approaches across fixed models do not contradict model-dependent constants or perturbation thresholds, and the prior fixed-gap higher-well object already fails NOT. No general largest-crossing estimate follows from this round.
- Obstruction: Existing sign and multiple-well exclusions are unchanged: the checked negative-jump object respects the signed two-deformation conclusion, while equal-depth global wells violate uniqueness. No new conclusion check extends either observation to further models.

## Limitations

- No candidates were written in round 5. The local derivative and nondegenerate compact-gap screening adds no new rigorous conclusion checks or general proof coverage, and absence of a found object is not a proof that no counterexample exists.
- General localization for arbitrary admissible nonconvex barriers, all competing largest-root switches, non-strict boundary crossings, the birth/death window and the common-active error still requires a complete proof. The previously assigned negative-correlation linear test still lacks a complete rigorous NOT check in the supplied record.
- The full-FDR representation, signed variation, ordinary canonical finite recovery, conditional finite-comparison implication and nonempty-hypothesis clause receive no new proof support here. No genuinely new nonduplicate proof step was established, so no approach idea is recorded.

Object search: 3 candidate(s) in 5 round(s).
