---
type: search_round
title: Round 4 obstructions for the unrestricted two-sided Gaussian BH upper bound
target_asset: gaussian_bh_two_sided_sharp_upper
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates:
  - cand_gaussian_bh_two_sided_sharp_upper_r4_s1_vanishing_mean_dense_pairs
  - cand_gaussian_bh_two_sided_sharp_upper_r4_s2_independent_signed_triples
  - cand_gaussian_bh_two_sided_sharp_upper_r4_s3_exponentially_many_sparse_gates
  - cand_gaussian_bh_two_sided_sharp_upper_r4_s4_independent_growing_bad_blocks
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:30:37.908Z'
extension_version: 0.0.4
---

## Obstructions

These are scoped summaries of the four failed candidate reports, not independent verification of their proofs. Write $L=\log(1/q)$.

- The tested vanishing-mean dense-pair arrays are reported to have their largest global BH crossing dominated, outside an event of probability at most $q^2$, by BH on duplicated independent uniform p-values at level $e^3q$; this yields $O(q)=o(q\sqrt L)$ FDR and fails the asymptotic NOT check for those arrays.
- In the tested signed-triple arrays, independence between three-coordinate blocks is reported to restrict a null coordinate's possible global rejection counts to three deterministic values after conditioning on the outside data, giving FDR at most $2q$ despite rapid dimension growth and near-singularity; these independent triples fail the asymptotic NOT check.
- The prescribed orthogonal sparse-gate array with independent nulls, $s=\lceil\exp(a\sqrt L)\rceil$, $a=1/(4e\sqrt\pi)$, and $m=2\lceil e^{L^2}\rceil+2s+1$ is reported to obey an independent-null binomial envelope with normalized FDR limsup at most $1/(4\sqrt\pi)<1/(2\sqrt\pi)$; only this specified small-growth gate sequence is thereby excluded.
- Independent replication of the tested growing Gaussian blocks, with $d=\lceil L^{1/4}\rceil$ coordinates per block and $B=\lceil e^{L^2}\rceil$ blocks, is reported to have global BH FDR at most $dq=o(q\sqrt L)$; the replication obstruction requires block independence and block size $d=o(\sqrt L)$, rather than merely a large number of blocks.

## Limitations

- Larger sparse-gate growth constants $a$ remain unresolved. The reported comparison at $a=1/(4e\sqrt\pi)$ does not exclude the larger-$a$ family, and an upper envelope exceeding the conjectured constant would not itself establish a violating FDR.
- Dependence between blocks remains uncovered by the independent-block and signed-triple arguments. The growing-block bound $dq$ also does not give a vanishing normalized bound when $d$ is not $o(\sqrt L)$; larger blocks are not excluded by this obstruction.
- Weak common-gate coupling and richer interior or high-rank covariance models outside the tested arrays remain unresolved. An unfinished analysis is a coverage gap, not a failed candidate or a refutation of the target.
- All four candidates are reported to fail the asymptotic NOT check. This round supplies no counterexample and does not prove the unrestricted uniform upper bound; any later argument relying on these reported comparisons still requires the relevant independent verification.
