---
type: search_round
title: Positive p-path budget round 1 family obstructions
target_asset: gaussian_bh_positive_p_path_jump_budget
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_positive_p_path_jump_budget_r1_s1_antipodal_nonpositive_nulls
  - >-
    cand_gaussian_bh_positive_p_path_jump_budget_r1_s1_nonnegative_equicorrelation
  - >-
    cand_gaussian_bh_positive_p_path_jump_budget_r1_s1_zero_null_opposite_alternatives
  - >-
    cand_gaussian_bh_positive_p_path_jump_budget_r1_s2_antipodal_two_test_tied_onset
  - >-
    cand_gaussian_bh_positive_p_path_jump_budget_r1_s3_negative_null_clone_against_opposite_alternatives
  - >-
    cand_gaussian_bh_positive_p_path_jump_budget_r1_s3_signed_rank_one_negative_nulls
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:27:08.885Z'
extension_version: 0.0.4
---

## Obstructions

- The tested nonnegative equicorrelation family has nondecreasing selected-null conditional paths and therefore $B_i=0$. The tested antipodal nonpositive-null clone family and the signed rank-one all-null family, including heterogeneous negative null means, also have zero positive charge. These zero-charge families cannot refute the budget.
- For a single identical true-null clone block of mass $\alpha$ against arbitrary positive-mean opposite-sign clone groups, the tested zero-null and strictly negative-null families have null-averaged original weighted positive budget at most $\alpha\log(1/\alpha)\leq1/e$. The negative-null calculation retains the original weights. Since $q\leq S(1)<1$, their normalized budgets are at most $1/(e\sqrt{\log(1/S(1))})$ uniformly in their parameters, so these families cannot provide an unbounded refuting sequence.
- The antipodal two-test family with negative true-null means and tied onset has normalized positive budget at most $1/(4\sqrt{\log(1/S(1))})<0.185$. Simultaneous events are merged into actual net jumps. This parameter-uniform bound rules out this two-test family as a refutation.

## Limitations

All six candidates failed the NOT check. These are bounds for the specified parameterized families, not a universal positive-budget theorem. Generic mixed, higher-rank covariance models with heterogeneous groups remain uncontrolled; this round establishes no dimension-independent bound for them. The finite signed identity remains a separate dependency, and failure to find a counterexample does not verify it or the target. The family obstructions reproduce the target's proposed calibrations or their negative-null extensions; no new proof-step approach beyond those calibrations is asserted.
