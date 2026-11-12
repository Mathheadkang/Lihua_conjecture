---
type: search_round
title: 'Signed duplication search: null labels, endpoints, and rare events'
target_asset: gaussian_bh_two_to_one_signed_duplication
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: 987e0b4167580298c08435b5d415d205e1f3153780e8613a7e16afb82038f6a6
performed_by: unknown
created_at: '2026-11-07T02:43:58.314Z'
extension_version: 0.0.4
---

## Obstructions

- Attempts requiring zero tests, level zero, or nonfinite realized statistics fail the stated positive-dimension, positive-level, or real-valued hypotheses; floating-point tail underflow does not supply a real-valued counterexample.
- Changing a mean through zero cannot remove the rejected one-sided true-null copy associated with an original two-sided true null. The reported 54,240 mean-sign, observation-sign, and rejection-label configurations with dimensions one through four found no false-rejection reversal, conditional on the asserted rejection correspondence; this is a finite bookkeeping probe only.
- Selection-dependent true-null labels require random mean labels, whereas the model fixes its mean vector and both true-null sets before sampling. Such label constructions therefore fail the fixed-model hypotheses.
- Rare-event sequences and very unbalanced rejection counts cannot reverse an established pathwise FDP comparison: the rejection denominators coincide and each FDP is bounded by one, so expectation does not require an additional integrability assumption.

## Limitations

No concrete candidate was produced in this round. Endpoint exclusions, null-label checks, and bounded-FDP observations are not a proof of the theorem. The finite label probe assumes the proposed rejection correspondence and covers only the enumerated configurations. A complete proof must still establish the exact finite ordering and rejection sets for every realization, including all ties, zero statistics, and zero rejections, and then derive null-count domination and the unrestricted supremum comparison. Neither main uniform finite-constant FDR bound is proved or tested by this round. The elementary rank-separation approach was already recorded in the first round; no duplicate approach node is added here.
