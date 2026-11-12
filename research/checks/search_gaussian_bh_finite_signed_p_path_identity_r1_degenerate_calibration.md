---
type: search_round
title: Finite signed p-path identity round 1 degeneracy calibrations
target_asset: gaussian_bh_finite_signed_p_path_identity
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_finite_signed_p_path_identity_r1_s1_negative_singleton
  - cand_gaussian_bh_finite_signed_p_path_identity_r1_s1_rankone_removable_spike
  - cand_gaussian_bh_finite_signed_p_path_identity_r1_s2_one_negative_null
  - >-
    cand_gaussian_bh_finite_signed_p_path_identity_r1_s2_three_removable_rank_spike
  - >-
    cand_gaussian_bh_finite_signed_p_path_identity_r1_s2_two_anticorrelated_downjump
  - >-
    cand_gaussian_bh_finite_signed_p_path_identity_r1_s3_singular_negative_null_simultaneous
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:26:27.213Z'
extension_version: 0.0.4
---

## Obstructions

- Strictly negative singleton nulls do not refute the identity: for $N=1$, $A_i(t)=t/q$ and there are no net jumps. The weighted baseline gives $q[g_i(q)-\int_{(0,q)}(t/q)\,dg_i(t)]=\int_0^q g_i(t)\,dt=S(u(q)-\theta_i)$, exactly the direct rejection probability. The two singleton candidates therefore fail NOT; a nonconstant negative-null weight alone does not break the formula.
- An isolated rank-count spike with equal left and right limits of $A_i$ cannot create a net jump contribution. The two explored removable-spike candidates fail NOT when isolated point values are omitted and genuine jumps are counted once; their exact formulas reproduce the direct rejection contributions. Counting the spike as an extra jump attacks a different formula from the target.
- Singular anticorrelation and simultaneous crossings do not by themselves remove a genuine downward jump. In the explored anticorrelated and singular negative-null candidates, merging the coincident event leaves one downward jump with exactly the coefficient required by the signed identity. Both candidates fail NOT. This is a calibration of the tested objects, not an assertion for all singular models.

## Limitations

The round has six failed candidates: two from slot 1, three from slot 2, and one from slot 3. Every candidate fails NOT; there is no survivor or confirmed counterexample. Exact scalar formulas agree in these examples; displayed decimal evaluations are approximate.

These low-dimensional examples do not prove the general statement. Joint measurability, a measurable finite event construction, arbitrary simultaneous crossings and constant threshold ties, the endpoint and derivative assertions in every admissible model, conditional change of variables, and absolute integrability of the random signed jump sum still require general arguments. No quantitative bound on the positive jump budget is established.

The distinction between removable point discrepancies and actual net jumps is useful for later proofs, but it is already explicit in the target statement; this round supplies examples of that distinction rather than a new proof approach.
