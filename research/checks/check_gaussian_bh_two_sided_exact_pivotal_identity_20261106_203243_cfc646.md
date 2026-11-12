---
type: falsification_check
title: 'Falsification check: gaussian_bh_two_sided_exact_pivotal_identity'
target_asset: gaussian_bh_two_sided_exact_pivotal_identity
outcome: no_counterexample_found
statement_digest: 10fd42aac96d6f560ddc31272941b5f90f8a40eb9cbddd044801e18b7016e6b1
performed_by: unknown
created_at: '2026-11-06T20:32:43.353Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s1_singular_identical_nulls failed — NOT fails: perfect correlation and singularity preserve the forced-zero, baseline and FDR identities, including the threshold equality and zero-rejection cases.
- Round 1, small_cases: cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s2_rank_one_shifted_pair failed — NOT fails: singular negative dependence and a shifted alternative yield a small negative pivotal excess, but the exact FDR identity still holds.
- Round 1, small_cases: cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s2_singleton failed — NOT fails: the empty residual and zero-rejection cases satisfy the exact identity without an exceptional term.
- Round 1, drop_hypothesis: cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s3_singular_negative_pair failed — NOT fails: exact Gaussian tail integration gives the same FDR and pivotal decomposition, including the nonzero negative pivotal correction.
- Round 1, known_counterexamples: cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s4_countermonotone_magnitudes failed — H3 fails: the countermonotone magnitude copula has Gaussian marginals but is not jointly Gaussian, so it cannot refute the exact Gaussian identity.
- Round 1, extremal: cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s5_growing_perfect_dependence failed — NOT fails: the small forced-zero threshold occurs only when its numerator vanishes, so arbitrarily large perfectly tied null clusters give FDR exactly q and zero pivotal excess.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 2, small_cases: no plausible candidate.
- Round 2, drop_hypothesis: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 3, known_counterexamples: no plausible candidate.
- Round 3, extremal: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 4, known_counterexamples: no plausible candidate.
- Round 4, extremal: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Round 5, known_counterexamples: no plausible candidate.
- Round 5, extremal: no plausible candidate.
- Round 6, boundary_degenerate: no plausible candidate.
- Round 6, small_cases: no plausible candidate.
- Round 6, drop_hypothesis: no plausible candidate.
- Round 6, known_counterexamples: no plausible candidate.
- Round 6, extremal: no plausible candidate.
- Round 7, boundary_degenerate: no plausible candidate.
- Round 7, small_cases: no plausible candidate.
- Round 7, drop_hypothesis: no plausible candidate.
- Round 7, known_counterexamples: no plausible candidate.
- Round 7, extremal: no plausible candidate.
- Round 8, boundary_degenerate: no plausible candidate.
- Round 8, small_cases: no plausible candidate.
- Round 8, drop_hypothesis: no plausible candidate.
- Round 8, known_counterexamples: no plausible candidate.
- Round 8, extremal: no plausible candidate.
- Round 9, boundary_degenerate: no plausible candidate.
- Round 9, small_cases: no plausible candidate.
- Round 9, drop_hypothesis: no plausible candidate.
- Round 9, known_counterexamples: no plausible candidate.
- Round 9, extremal: no plausible candidate.
- Round 10, boundary_degenerate: no plausible candidate.
- Round 10, small_cases: no plausible candidate.
- Round 10, drop_hypothesis: no plausible candidate.
- Round 10, known_counterexamples: no plausible candidate.
- Round 10, extremal: no plausible candidate.
- Obstruction: Perfectly tied all-null Gaussian clusters, including singular covariance and arbitrarily large cluster size, do not refute the identity: the low forced-zero threshold occurs only where the numerator vanishes. The reported family has FDR exactly q and zero pivotal excess, so increasing dimension within this family does not produce a violation.
- Obstruction: The tested singular negatively dependent Gaussian pairs, including a shifted alternative, preserve the exact FDR decomposition even when the pivotal excess is negative. A negative excess by itself is compatible with the statement and is not a counterexample.
- Obstruction: Singleton models do not yield an exceptional correction: the empty residual and zero-rejection cases satisfy the reported identity.
- Obstruction: Countermonotone Gaussian-marginal magnitude copulas outside the jointly Gaussian class fail the joint-Gaussian hypothesis H3. They cannot refute this target regardless of any later check.
- Obstruction: No additional family obstruction was established this round. The existing board retains the round 1 obstructions; no repeated candidate calculation is counted as new evidence.
- Obstruction: Proposals that abandon joint Gaussianity, give a designated true null a nonzero mean, or use a non-Borel exogenous threshold leave the corresponding hypotheses. Such proposals cannot refute the stated identity without an admissible construction.
- Obstruction: No new family obstruction was established in round 3. The supplied board remains the record of previously excluded families; it is not enlarged by the absence of a new candidate.
- Obstruction: No new family obstruction was established in round 4. The existing board's exclusions remain prior search evidence; no repeated calculation or absence of a candidate is added as a new obstruction.
- Obstruction: No new family obstruction was established in round 5. The supplied board's earlier exclusions remain prior search evidence; the absence of a distinct plausible admissible candidate does not enlarge those exclusions.
- Obstruction: No new family obstruction was established in round 6. Previously excluded families remain prior search evidence; the absence of a new candidate does not enlarge those exclusions.
- Obstruction: No new family obstruction was established beyond the supplied board; previously excluded families were not repeated.
- Obstruction: No new family obstruction was established this round; the supplied board retains all prior exclusions.
- Obstruction: No new family obstruction was established this round; the supplied board retains its prior exclusions.
- Obstruction: No new family obstruction was established in round 10; the supplied board retains its prior exclusions.

## Limitations

All five completed workers reported no distinct plausible admissible candidate and wrote no candidate files. This nonexhaustive round adds no new calculations or search coverage. Earlier calculations and the cold-audit observation were not independently checked here. Absence of a candidate supplies no proof verdict, pivotal-excess bound, or unrestricted FDR control.

Object search: 6 candidate(s) in 10 round(s).
