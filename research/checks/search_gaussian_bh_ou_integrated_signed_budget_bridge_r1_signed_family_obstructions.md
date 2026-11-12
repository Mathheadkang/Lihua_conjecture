---
type: search_round
title: First-round obstructions for the OU signed-budget bridge
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_ou_integrated_signed_budget_bridge_r1_s1_antipodal_null_pair
  - >-
    cand_gaussian_bh_ou_integrated_signed_budget_bridge_r1_s1_independent_null_dust
  - cand_gaussian_bh_ou_integrated_signed_budget_bridge_r1_s1_no_null_zero_fdp
  - cand_gaussian_bh_ou_integrated_signed_budget_bridge_r1_s1_scalar_null
  - cand_gaussian_bh_ou_integrated_signed_budget_bridge_r1_s2_antipodal_two_test
  - >-
    cand_gaussian_bh_ou_integrated_signed_budget_bridge_r1_s3_singular_opposed_blocks
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T21:58:38.083Z'
extension_version: 0.0.4
---

## Obstructions

- Boundary and cancellation families do not produce positive excess: the scalar true-null family has nonpositive excess, while the tested antipodal all-null pair and full mixed-label independent-null dust attain the baseline. Their bridge ratios are zero. The empty-null zero-FDP construction has $F=J(f)=0$ and fails the gate hypothesis $F>0$; it cannot supply a positive-numerator zero-budget counterexample.
- The tested two-test antipodal mixed-label family has full FDP $f=\tfrac12\mathbf 1_{[a,c]}+\mathbf 1_{[b,\infty)}$, with net jumps $(+\tfrac12,-\tfrac12,+1)$ after ordering its distinct jump locations. Its signed-mixture lower bound $J(f)\geq aF$ gives bridge ratio at most $1/(4a)\leq1/4$. Retaining the full signed mixture therefore rules out this family as a refutation, despite its negative jump.
- The tested singular opposed-block family, including negative true-null means, has $f=p\mathbf 1_{[b,\infty)}+(1-p)\mathbf 1_{[c,\infty)}$, $F=qp(2-p)$ and $J(f)=p\phi(b)+(1-p)\phi(c)$. Its bridge ratio is at most $p(1-p)\leq1/4$, uniformly over the admissible block imbalance and means. Singularity and these negative-null perturbations alone do not yield an unbounded ratio.

## Limitations

All six recorded candidates failed to refute the target. These calculations cover only the specified scalar, independent and antipodal block families; they neither establish a dimension-free bridge nor control arbitrary higher-rank covariance, means, rank switches or simultaneous ties. No general mechanism establishing the BH-specific gate was obtained. The generic analytic estimate, its permitted source verification, the signed-mixture reduction outside the checked families and the target's general quantitative gate remain proof obligations; the required FDR consequence remains conditional. No proposed rank-at-most-two extension is treated as a worker result or an established obstruction here.
