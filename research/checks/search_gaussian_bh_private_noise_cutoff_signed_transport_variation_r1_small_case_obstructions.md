---
type: search_round
title: Small-case obstructions for signed private-noise cutoff transport
target_asset: gaussian_bh_private_noise_cutoff_signed_transport_variation
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r1_s2_single_true_translation
  - >-
    cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r1_s2_two_equal_centers_opposed_means
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T06:43:58.046Z'
extension_version: 0.0.4
---

## Obstructions

- The checked single-true common-translation family fails NOT: its exact translation response agrees with the full signed cutoff derivative and its domination bound; common translation alone therefore supplies no counterexample in this family.
- The checked equal-center, opposed-mean mixed-label family fails NOT: cancellation of the total-tail first variation does not cancel the true-numerator variation, and the stated formula retains exactly this numerator loss.

## Limitations

Only two small-case families in the small_cases direction were tested. No worker covered multiple competing suffix minima, tied-minimum switches, births of crossings, or complicated changes of the globally largest rank. The round also did not test joint level-and-mean perturbations, extremizer attainment and representation, finite approximation and microscopic bounds, regularizer value limits, or domination for general directing laws. Both candidates failed NOT; these checks establish neither the target lemma nor a counterexample. The round summary uses the supplied failure lines, not an independent verification of candidate calculations. No new proof-step approach is recorded: the retained numerator term is already explicit in the target statement.
