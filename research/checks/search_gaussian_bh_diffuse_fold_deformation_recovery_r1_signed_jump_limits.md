---
type: search_round
title: Signed negative-jump checks and boundary limitations in fold recovery round 1
target_asset: gaussian_bh_diffuse_fold_deformation_recovery
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_diffuse_fold_deformation_recovery_r1_s2_orthogonal_negative_jump
statement_digest: c94a3fdf2ffe058f0be84badf476c4d08154e9cac43cf7bcae563b030a494568
performed_by: unknown
created_at: '2026-11-09T01:42:29.090Z'
extension_version: 0.0.4
---

## Obstructions

- **Negative-jump sign-based construction.** The fully checked positive-correlation, orthogonal-direction model in `cand_gaussian_bh_diffuse_fold_deformation_recovery_r1_s2_orthogonal_negative_jump` passes H1–H6 and fails NOT. Its negative conditional-FDP jump is compatible with the target: both admissible deformation signs give the stated globally correct signed variation, and both ordinary canonical finite recoveries agree with it. Thus a negative jump alone supplies no contradiction; the target retains the entire signed jump. This is a failed counterexample construction with all conclusion clauses checked, not a general proof for the surrounding parameter family.

## Limitations

- The round contains one recorded failed candidate and no survivor. Its complete checks do not establish the full statement for arbitrary admissible quantiles, bumps, correlations, or competing-crossing configurations.
- The antipodal negative-correlation boundary case has actual-rank checks and numerical derivative evidence only. It is not a rigorously completed NOT check and does not establish the signed derivative or finite recovery for negative correlations. The existing observation `idea_6e20eb74d787` records the distinction between the forced-true auxiliary rank and an actual false-only BH rank; no duplicate idea is introduced here.
- General control of all globally competing roots, non-strict boundary crossings, uniform birth/death-window behavior, and the common-active error remains to be proved. Numerical convergence in a boundary example does not resolve these obligations or the unrestricted first-variation claim.
- No genuinely new proof step was established by this summary, so no approach idea is recorded. The conditional finite-comparison conclusion and the nonempty-hypothesis clause remain statements of the target rather than consequences proved by this round record.
