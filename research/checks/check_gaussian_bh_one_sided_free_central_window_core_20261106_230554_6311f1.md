---
type: falsification_check
title: 'Falsification check: gaussian_bh_one_sided_free_central_window_core'
target_asset: gaussian_bh_one_sided_free_central_window_core
outcome: no_counterexample_found
statement_digest: 779c4649ca5118819e8dfa6dbce8e2a5f940384b9968185d078f02aeffa659b9
performed_by: unknown
created_at: '2026-11-06T23:05:54.438Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, small_cases: cand_gaussian_bh_one_sided_free_central_window_core_r1_s2_single_zero_loading failed — NOT fails: both kernel bounds and the central-contribution consequence hold for this single zero-loading null.
- Round 1, drop_hypothesis: cand_gaussian_bh_one_sided_free_central_window_core_r1_s3_zero_loading_ce_edge failed — NOT fails: the zero-loading endpoint has central contribution $0.1$, below the claimed bound by approximately $0.00112651040103891$.
- Round 2, known_counterexamples: cand_gaussian_bh_one_sided_free_central_window_core_r2_s4_negative_correlation_simes failed — NOT fails: the negative-correlation BH pathology has central contribution below the claimed central bound.
- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, known_counterexamples: no plausible candidate.
- Round 1, extremal: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 2, small_cases: no plausible candidate.
- Round 2, drop_hypothesis: no plausible candidate.
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
- Obstruction: The single tested zero-loading null with N=d=1, r=0, theta=0, and q=0.1 does not refute the claim: its kernel bounds hold and Ce=0.1 is below the reported bound approximately 0.10112651040103891.
- Obstruction: The tested negative-correlation Simes configuration does not refute the central-contribution claim: although its reported total FDR is approximately 0.1003023, its reported Ce is approximately 0.0413543, below the central bound approximately 0.0711773. An excess of total FDR above q does not by itself violate a bound on Ce.
- Obstruction: No new family-level obstruction beyond the supplied board emerged; no distinct admissible candidate was reported.
- Obstruction: No new admissible family beyond the supplied board emerged; non-Gaussian arbitrary-dependence examples violate the Gaussian multifactor hypothesis and cannot refute this target.
- Obstruction: No new family-level obstruction beyond the supplied board emerged; no distinct admissible candidate was reported.
- Obstruction: No new family-level obstruction beyond the supplied board emerged; no distinct admissible candidate was reported.
- Obstruction: No new family-level obstruction beyond the supplied board emerged; no distinct admissible candidate was reported.
- Obstruction: No new family-level obstruction beyond the supplied board emerged; no distinct admissible candidate was reported.
- Obstruction: No new family-level obstruction beyond the supplied board emerged; no distinct admissible candidate was reported.
- Obstruction: No new family-level obstruction beyond the supplied board emerged; no distinct admissible candidate was reported.

## Limitations

Five bounded checks in boundary_degenerate, small_cases, drop_hypothesis, known_counterexamples, and extremal returned no candidate files in the final configured round. Previously recorded cases and parameter variants were not repeated or counted as new coverage. The kernel claim retains 0<q<1/2 and the central-contribution consequence retains 0<q<=1/10. This nonexhaustive round adds no numerical calculation, candidate evidence, proof coverage, or verification verdict; prior candidate bodies and numerical approximations were not independently checked here.

Object search: 3 candidate(s) in 10 round(s).
