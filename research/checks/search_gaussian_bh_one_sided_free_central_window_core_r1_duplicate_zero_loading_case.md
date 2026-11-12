---
type: search_round
title: Round 1 zero-loading boundary case for the one-sided central-window core
target_asset: gaussian_bh_one_sided_free_central_window_core
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - >-
    cand_gaussian_bh_one_sided_free_central_window_core_r1_s2_single_zero_loading
  - >-
    cand_gaussian_bh_one_sided_free_central_window_core_r1_s3_zero_loading_ce_edge
statement_digest: 779c4649ca5118819e8dfa6dbce8e2a5f940384b9968185d078f02aeffa659b9
performed_by: unknown
created_at: '2026-11-06T22:41:01.675Z'
extension_version: 0.0.4
---

## Obstructions

- The single tested zero-loading null with N=d=1, r=0, theta=0, and q=0.1 does not refute the claim: its kernel bounds hold and Ce=0.1 is below the reported bound approximately 0.10112651040103891.

## Limitations

The two failed files in small_cases and drop_hypothesis describe the same object and count as one actual case, not two independent numerical observations. This summary uses the supplied failure lines without independently recomputing candidate bodies. Other reported screens at r=1 and empty I_0 produced no surviving object. No general kernel or multifactor central-contribution proof, exhaustive coverage, or independent verification verdict follows from these limited checks.
