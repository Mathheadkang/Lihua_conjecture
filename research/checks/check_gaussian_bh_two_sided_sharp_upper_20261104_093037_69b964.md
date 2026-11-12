---
type: falsification_check
title: 'Falsification check: gaussian_bh_two_sided_sharp_upper'
target_asset: gaussian_bh_two_sided_sharp_upper
outcome: no_counterexample_found
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:30:37.921Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_bh_two_sided_sharp_upper_r1_s1_growing_singular_blocks failed — NOT fails: the entropy bound rules out this growing-rank singular family and every grouped-null family with subexponential-in-square-root-log block count.
- Round 1, boundary_degenerate: cand_gaussian_bh_two_sided_sharp_upper_r1_s1_near_rank_one_exponential_dimension failed — NOT fails: exponentially growing dimension and a vanishing independent Gaussian perturbation still give FDR $O(q)$ for this family.
- Round 1, boundary_degenerate: cand_gaussian_bh_two_sided_sharp_upper_r1_s1_rank_one_growing_dimension failed — NOT fails: exact rank-one dependence gives FDR at most $q$, uniformly over growing dimension and arbitrary nonnull means.
- Round 1, small_cases: cand_gaussian_bh_two_sided_sharp_upper_r1_s2_dense_rank_two_ring failed — NOT fails: the exact growing finite Gaussian arrays have FDR asymptotic to $\sqrt{2/(\pi e)}q$, which is smaller than the conjectured scale by a factor tending to zero.
- Round 1, small_cases: cand_gaussian_bh_two_sided_sharp_upper_r1_s2_signed_finite_types failed — NOT fails: only three distinct random null p-values occur, forcing the normalized FDR to zero even with arbitrarily large repeated-group multiplicities.
- Round 2, idea_28ab51ce8127: cand_gaussian_bh_two_sided_sharp_upper_r2_s1_finite_type_residual_arrays failed — NOT fails: both prescribed residual families have global FDR at most $16q$, uniformly in their diverging dimension, means, and vanishing tail masses.
- Round 2, idea_9692ea16c23a: cand_gaussian_bh_two_sided_sharp_upper_r2_s2_common_gate_primary_cap failed — NOT fails: at $B\asymp q^{-2}$ and $\epsilon=1/\sqrt2$, a global primary cap controls FDR by $q\{1+o(1)\}$ except on a $q^{2+o(1)}$ gate event; secondary-source detail cannot remove this obstruction.
- Round 2, extremal: cand_gaussian_bh_two_sided_sharp_upper_r2_s3_high_dimensional_spherical_entropy failed — NOT fails: the exact, growing-rank, high-entropy spherical Gaussian arrays have global all-null BH FDR at most \((1+o(1))q_j\), hence zero on the conjectured square-root-log normalization.
- Round 2, boundary_degenerate: cand_gaussian_bh_two_sided_sharp_upper_r2_s4_growing_negative_simplex failed — NOT fails: this growing-rank singular negative-equicorrelation family has global BH FDR at most $q(1+o(1))$, so its normalized FDR tends to zero.
- Round 3, boundary_degenerate: cand_gaussian_bh_two_sided_sharp_upper_r3_s1_cyclic_strong_sparse_boundary failed — NOT fails: the global-BH truncated-harmonic envelope bounds this family's FDR by $q\{1+O(\log\log(1/q))\}+q^3=o(q\sqrt{\log(1/q)})$.
- Round 3, small_cases: cand_gaussian_bh_two_sided_sharp_upper_r3_s2_opposite_signal_ladders failed — NOT fails: the earlier of the two global signal-ladder crossings bounds the null cutoff by an independent Gaussian factor; the resulting integrated null-tail envelope is finite, giving FDR $O(q)$ despite growing mean-type count and arbitrary changing loading angle.
- Round 3, drop_hypothesis: cand_gaussian_bh_two_sided_sharp_upper_r3_s3_sparse_global_gate failed — NOT fails: independent nulls and at most one arbitrarily dependent alternative force FDR $O(q)$, even at exact covariance singularity and the prescribed superpolynomial dimension and diverging mean.
- Round 3, known_counterexamples: cand_gaussian_bh_two_sided_sharp_upper_r3_s4_harmonic_normal_marginals failed — H2 fails: the harmonic-event construction has exact standard-normal marginals and covariance $I_N$, but its dependent absolute-value events exclude joint Gaussianity.
- Round 4, boundary_degenerate: cand_gaussian_bh_two_sided_sharp_upper_r4_s1_vanishing_mean_dense_pairs failed — NOT fails: the largest global BH crossing is dominated outside an event of probability at most $q^2$ by duplicate-independent-uniform BH at level $e^3q$, giving FDR $O(q)=o(q\sqrt{\log(1/q)})$.
- Round 4, small_cases: cand_gaussian_bh_two_sided_sharp_upper_r4_s2_independent_signed_triples failed — NOT fails: independence between the three-coordinate blocks restricts each null's possible global rejection counts to three deterministic values after conditioning on the outside data, forcing FDR at most $2q$ despite the rapidly growing near-singular Gaussian array.
- Round 4, drop_hypothesis: cand_gaussian_bh_two_sided_sharp_upper_r4_s3_exponentially_many_sparse_gates failed — NOT fails: an independent-null binomial envelope bounds this exponentially growing, exactly singular sparse-gate family's normalized FDR by $1/(4\sqrt\pi)$, strictly below the proposed constant.
- Round 4, known_counterexamples: cand_gaussian_bh_two_sided_sharp_upper_r4_s4_independent_growing_bad_blocks failed — NOT fails: independent replication with the specified growing block size has global BH FDR at most $dq=o(q\sqrt{\log(1/q)})$, regardless of the enormous number of blocks.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 1, known_counterexamples: no plausible candidate.
- Obstruction: These are summaries of the five failed candidate reports, not independent certification of their calculations. No candidate survived the asymptotic NOT check.
- Obstruction: Exact rank-one Gaussian dependence is reported to give FDR at most q, uniformly over dimension and nonnull means; repetition alone therefore cannot produce the proposed square-root-log inflation.
- Obstruction: The tested near-rank-one family, with exponentially growing dimension and vanishing independent Gaussian noise, is reported to retain FDR of order q. This obstruction is specific to that perturbation regime.
- Obstruction: The grouped-null entropy argument is reported to exclude the tested growing singular-block family when the logarithm of the number of distinct null blocks is negligible relative to the square root of log(1/q). A bounded number of null p-value types, including the signed finite-type candidate with arbitrary multiplicities, falls in the same regime.
- Obstruction: The tested dense rank-two circle is reported to have FDR asymptotic to sqrt(2/(pi e)) times q. Increasing angular density in that construction does not reach the conjectured normalization.
- Obstruction: These are scoped summaries of the four failed candidate reports in the round's context pack, not independent verification of their calculations or proofs. Each reported bound gives zero after division by $q\sqrt{\log(1/q)}$.
- Obstruction: The two prescribed finite-type repeated-signal residual families are reported to have global BH FDR at most $16q$, uniformly over their specified diverging dimensions, means, and vanishing tail masses; repetition and residual noise in these two families therefore fail the asymptotic NOT check.
- Obstruction: The tested growing common-gate regime with $B\asymp q^{-2}$ and $\epsilon=1/\sqrt2$ is reported to admit a global primary cap giving FDR at most $q\{1+o(1)\}$ apart from a gate event of probability $q^{2+o(1)}$; changing secondary-source details within this capped regime cannot produce a counterexample.
- Obstruction: The tested exact, growing-rank, high-entropy spherical Gaussian arrays are reported to have global all-null BH FDR at most $(1+o(1))q_j$ along their specified level sequence; growing rank and angular entropy in these arrays fail the asymptotic NOT check.
- Obstruction: The tested growing-rank singular negative-equicorrelation simplex family is reported to have global BH FDR at most $q\{1+o(1)\}$; its dimension growth and negative dependence fail the asymptotic NOT check.
- Obstruction: The following summarizes the four candidate failure reports in this round's context pack. It does not independently verify their calculations or proofs.
- Obstruction: The tested cyclic strong sparse-signal boundary arrays are reported to obey a global-BH truncated-harmonic envelope $\operatorname{FDR}\leq q\{1+O(\log\log(1/q))\}+q^3=o(q\sqrt{\log(1/q)})$; their specified sparse-signal and boundary scaling therefore fails the asymptotic NOT check.
- Obstruction: The tested opposed signal-ladder arrays are reported to have an earlier global ladder crossing that bounds the null cutoff by an independent Gaussian factor with an integrable null-tail envelope, giving $O(q)$ FDR despite their growing mean-type count and arbitrary changing loading angle; this ladder mechanism fails the asymptotic NOT check.
- Obstruction: The tested independent-null arrays with at most one arbitrarily dependent alternative are reported to have $O(q)$ FDR, including the prescribed superpolynomial dimension, diverging mean, and exactly singular covariance regime; this sparse global-gate mechanism fails the asymptotic NOT check.
- Obstruction: Harmonic-event constructions with standard-normal marginals and covariance $I_N$, but dependent absolute-value events, fail joint Gaussianity: a jointly Gaussian vector with covariance $I_N$ would have independent coordinates. The tested construction therefore fails H2, leaving the later checks and NOT unknown.
- Obstruction: These are scoped summaries of the four failed candidate reports, not independent verification of their proofs. Write $L=\log(1/q)$.
- Obstruction: The tested vanishing-mean dense-pair arrays are reported to have their largest global BH crossing dominated, outside an event of probability at most $q^2$, by BH on duplicated independent uniform p-values at level $e^3q$; this yields $O(q)=o(q\sqrt L)$ FDR and fails the asymptotic NOT check for those arrays.
- Obstruction: In the tested signed-triple arrays, independence between three-coordinate blocks is reported to restrict a null coordinate's possible global rejection counts to three deterministic values after conditioning on the outside data, giving FDR at most $2q$ despite rapid dimension growth and near-singularity; these independent triples fail the asymptotic NOT check.
- Obstruction: The prescribed orthogonal sparse-gate array with independent nulls, $s=\lceil\exp(a\sqrt L)\rceil$, $a=1/(4e\sqrt\pi)$, and $m=2\lceil e^{L^2}\rceil+2s+1$ is reported to obey an independent-null binomial envelope with normalized FDR limsup at most $1/(4\sqrt\pi)<1/(2\sqrt\pi)$; only this specified small-growth gate sequence is thereby excluded.
- Obstruction: Independent replication of the tested growing Gaussian blocks, with $d=\lceil L^{1/4}\rceil$ coordinates per block and $B=\lceil e^{L^2}\rceil$ blocks, is reported to have global BH FDR at most $dq=o(q\sqrt L)$; the replication obstruction requires block independence and block size $d=o(\sqrt L)$, rather than merely a large number of blocks.

## Limitations

- Larger sparse-gate growth constants $a$ remain unresolved. The reported comparison at $a=1/(4e\sqrt\pi)$ does not exclude the larger-$a$ family, and an upper envelope exceeding the conjectured constant would not itself establish a violating FDR.
- Dependence between blocks remains uncovered by the independent-block and signed-triple arguments. The growing-block bound $dq$ also does not give a vanishing normalized bound when $d$ is not $o(\sqrt L)$; larger blocks are not excluded by this obstruction.
- Weak common-gate coupling and richer interior or high-rank covariance models outside the tested arrays remain unresolved. An unfinished analysis is a coverage gap, not a failed candidate or a refutation of the target.
- All four candidates are reported to fail the asymptotic NOT check. This round supplies no counterexample and does not prove the unrestricted uniform upper bound; any later argument relying on these reported comparisons still requires the relevant independent verification.

Object search: 17 candidate(s) in 4 round(s).
