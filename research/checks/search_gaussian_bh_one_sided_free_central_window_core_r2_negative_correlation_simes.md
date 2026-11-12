---
type: search_round
title: Round 2 negative-correlation Simes test for the one-sided central-window core
target_asset: gaussian_bh_one_sided_free_central_window_core
mode: refute
round: 2
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - >-
    cand_gaussian_bh_one_sided_free_central_window_core_r2_s4_negative_correlation_simes
statement_digest: 779c4649ca5118819e8dfa6dbce8e2a5f940384b9968185d078f02aeffa659b9
performed_by: unknown
created_at: '2026-11-06T22:45:19.159Z'
extension_version: 0.0.4
---

## Obstructions

- The tested negative-correlation Simes configuration does not refute the central-contribution claim: although its reported total FDR is approximately 0.1003023, its reported Ce is approximately 0.0413543, below the central bound approximately 0.0711773. An excess of total FDR above q does not by itself violate a bound on Ce.

## Limitations

The known_counterexamples candidate passed H1 through H4 and failed NOT; the other reported directions produced no candidate files, and no survivor was reported. This summary uses the supplied reports without independently recomputing the candidate body or certifying its numerical approximations. Total FDR and the central contribution remain distinct quantities. This limited, nonexhaustive test supplies no general kernel or multifactor central-contribution proof and no independent verification verdict.
