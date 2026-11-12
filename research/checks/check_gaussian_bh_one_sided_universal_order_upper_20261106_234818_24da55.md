---
type: falsification_check
title: 'Falsification check: gaussian_bh_one_sided_universal_order_upper'
target_asset: gaussian_bh_one_sided_universal_order_upper
outcome: no_counterexample_found
statement_digest: 334aaf8c5303a807be8f3b8e641f2fb7a35d5a6a6a5fe8080f4f22262e996d7f
performed_by: unknown
created_at: '2026-11-06T23:48:18.772Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_bh_one_sided_universal_order_upper_r1_s1_perfect_duplicate_nulls failed — NOT fails: even arbitrarily fast growth of the duplicated test count leaves exact FDR equal to $q$; the normalized FDR tends to zero.
- Round 2, small_cases: cand_gaussian_bh_one_sided_universal_order_upper_r2_s2_two_sign_null_blocks failed — NOT fails: the two opposed null blocks have exact FDR $q$, even with growing dimension and unbalanced block sizes.
- Round 1, small_cases: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 1, known_counterexamples: no plausible candidate.
- Round 1, extremal: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
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
- Obstruction: Perfectly duplicated true-null Gaussian coordinates do not refute the order bound: the reported family has exact FDR=q for every finite test count, including arbitrarily fast growth with decreasing q, so its normalization by q sqrt(log(1/q)) tends to zero.
- Obstruction: Families with a uniformly bounded finite test count cannot give the required divergence: any false rejection requires a true-null p-value at most q, so the union bound gives FDR<=Nq. This dimension-dependent observation does not control the supremum over N.
- Obstruction: The tested positive- and negative-unit-loading null blocks have reported exact FDR=q, including growing dimension and unbalanced block sizes, so they do not produce the normalized divergence needed to refute the universal order bound.
- Obstruction: No new family obstruction was established beyond the board's duplicated-null, opposed-null-block, and bounded-N exclusions. A finite-q FDR excess alone cannot refute the existential small-q order bound; non-Gaussian arbitrary-dependence constructions do not satisfy its model hypotheses.
- Obstruction: No new family obstruction was established. Prior finite-q excesses, non-Gaussian dependence constructions, and proxies for adaptive ranks without a legal Gaussian-coordinate realization do not supply the required admissible normalized-divergent family.
- Obstruction: Prior exclusions only: perfectly duplicated true-null coordinates and the tested opposed unit-loading null blocks have reported exact FDR equal to q, so they do not yield divergence after normalization by q sqrt(log(1/q)). These were not newly checked this round.
- Obstruction: Prior exclusion only: uniformly bounded test counts satisfy FDR <= Nq and cannot yield the required normalized divergence. This does not control growing N.
- Obstruction: All five directions returned NONE: no new object, candidate file, or family obstruction was established. Finite-q excess, non-Gaussian dependence, and unrealized adaptive-rank proxies remain insufficient to refute the stated small-q Gaussian order bound.
- Obstruction: Prior calculations exclude the perfectly duplicated true-null family and tested opposed unit-loading null blocks: their reported FDR equals q. The bounded-N union bound FDR <= Nq excludes uniformly bounded test counts. These scoped exclusions were not newly checked and do not cover arbitrary growing models.
- Obstruction: No new family exclusion was established: all five directions returned NONE, with no new object or candidate file.
- Obstruction: Existing exclusions remain scoped: duplicated true-null coordinates and the tested opposed unit-loading null blocks have reported FDR=q, while FDR <= Nq excludes uniformly bounded test counts. These prior calculations were not repeated this round and do not cover arbitrary growing models.
- Obstruction: All five main-target search directions returned NONE. No new candidate file or main-target family exclusion was established.
- Obstruction: No new main-target family exclusion: all five directions returned NONE with no new object or candidate file. The existing duplicated-null, opposed-unit-loading-block, and bounded-test-count exclusions retain only their previously reported scope; they are not new evidence from this round.
- Obstruction: No new main-target exclusion was established: all five directions returned NONE, with no new object, candidate file, or calculation. Earlier duplicated-null, opposed-unit-loading-block, and bounded-test-count exclusions retain their existing scope and are not new evidence.
- Obstruction: No new object, candidate file, or main-target exclusion: all five directions returned NONE. Earlier duplicated-null and tested opposed-unit-loading-block calculations (reported FDR=q), and the bounded-N union bound (FDR <= Nq), retain only their existing scope; they were not newly established this round.

## Limitations

Arbitrary growing Gaussian models, including singular covariance, mixed means, and increasing covariance complexity, remain open. The auxiliary centered-flux gate failure concerns a proof route and does not refute the FDR target or exclude a new family; the actual-mean weighted route remains unproved. Completing the configured nonexhaustive search without a counterexample is not a proof or verification of the universal order bound.

Object search: 2 candidate(s) in 10 round(s).
