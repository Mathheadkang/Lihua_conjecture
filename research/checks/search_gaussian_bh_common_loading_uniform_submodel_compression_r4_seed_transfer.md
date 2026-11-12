---
type: search_round
title: 'Round 4: sparse-seed cascades and mixed-pair switching'
target_asset: gaussian_bh_common_loading_uniform_submodel_compression
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r4_s2_sparse_false_seed_two_null_blocks
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r4_s3_paired_mixed_zero_completion
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:32:40.515Z'
extension_version: 0.0.4
---

## Obstructions

- In the tested sparse false-seed/two-null-block family, omitting the false seed does not preserve a fixed expected error: the reported macroscopic null-cascade disagreement is confined to common-Gaussian-shift windows of expected width $O(m^{-1/2})$, while seed-only rejection has zero FDP and vanishing normalized rank. This rules out the supplied family, not arbitrary cascades with growing numbers of blocks or vanishing block masses.
- In the tested growing antithetic mixed-zero family, mixed tags do not leave a fixed discrepancy: the reported antithetic symmetry controls the true numerator, the common Gaussian shift controls sampled ranks, and the approved microscopic estimate removes the remaining small-rank contribution. This does not extend antithetic symmetry to arbitrary mixed score laws.
- A deterministic proof step makes macroscopic seed-induced root switching subject to the same transfer regardless of the number of atoms. For a finite empirical tail $H_n$, any continuous crossing $H_n(u_q(r)-\sigma z)\ge r$ produces a grid crossing $k/n\ge r$, where $k=nH_n(u_q(r)-\sigma z)$: decreasing $u_q$ gives $H_n(u_q(k/n)-\sigma z)\ge k/n$. Thus the supremum of continuous crossings is exactly the actual largest non-strict BH rank. At a positive actual rank $r=k/n$, a count $j=nH_n(u_q(r)-\sigma z)>k$ would produce a larger grid crossing, so exact self-consistency holds. If two total tails differ by at most $\gamma$, a source crossing $r\ge a$, with $0<\gamma<a/2$, transfers to a continuous crossing $r-\gamma$ of the other tail at $z+h$, because $h=L_{q,a}\gamma/\sigma$ implies $u_q(r-\gamma)-\sigma(z+h)\le u_q(r)-\sigma z$. The grid identification converts this to an actual-rank lower bound, in either direction. This step permits atoms, exact copies, ties and terminal rank one. It is recorded as approach `idea_66450d6f4c7f`; it does not by itself establish the expectation bound or microscopic FDP comparison.

## Limitations

- Only the supplied current-stage pack and its two round-4 failure summaries were read. Candidate bodies, detailed constants and their microscopic arguments were not independently audited; no survivor or confirmed counterexample was supplied.
- The round does not cover arbitrary many-atom mixed populations, unstructured growing residual dimension, or arbitrary seed cascades and near-tangent competing roots. Antithetic symmetry is specific to the tested family.
- The deterministic grid identification, self-consistency and transfer step above leave the distribution-free simultaneous empirical total/tagged-tail maximal bound and its bad-event estimate to be proved, followed by the expected rank comparison using the board's Gaussian smoothing bound.
- Arbitrary mixed-label events with one or both actual ranks microscopic still require the approved microscopic estimate combined with rank control. The candidate failure summaries do not prove this full comparison.
- Uniform vanishing of the microscopic bound over compact sets of $q$ remains a proof obligation. Nothing here gives uniformity as $\sigma\downarrow0$, relative-$q$ approximation, derivative recovery, optimizer existence, or the main universal-order upper bound.
