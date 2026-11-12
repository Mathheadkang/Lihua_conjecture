---
type: candidate
title: Signed rank-one Gaussian replication at arbitrary imbalance
status: failed
target_asset: gaussian_simes_one_sided_uniform_linear_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:15:08.641Z'
extension_version: 0.0.4
---

## Object

For each integer j >= 3 choose any integers a_j >= 1 and b_j >= 0, with no growth restriction, and set N_j = a_j + b_j and q_j = exp(-j). Let s have a_j entries +1 and b_j entries -1. Put Sigma_j = s s^T and T_i = s_i Z for one standard normal Z. This tests singularity, correlations +1 and -1, arbitrary imbalance, and dimension depending on the level.

## Checks

### H1

Pass. N_j is a positive integer.

### H2

Pass. Sigma_j is symmetric, x^T Sigma_j x = (s^T x)^2 >= 0, and every diagonal entry equals 1. Rank is one.

### H3

Pass. q_j > 0 and q_j tends to zero, so it eventually lies below any proposed fixed q_0 > 0. Also q_j < 1/2 throughout the family.

### H4

Pass. T is exactly jointly centered Gaussian with covariance Sigma_j, since every linear combination is a scalar multiple of Z.

### H5

Pass. With U = barPhi(Z), the one-sided p-values are a_j copies of U and b_j copies of 1-U; U is uniform on (0,1). The event is the ordinary Simes event with multiplicities and non-strict comparisons.

### NOT

Fail. Since q_j < 1/2, only the group with p-value below 1/2 can qualify at a Simes threshold. The event is exactly

$$
\{U\le q_j a_j/N_j\}\ \cup\ \{1-U\le q_j b_j/N_j\}.
$$

The two intervals are disjoint and have total length q_j. Thus the rejection probability is exactly q_j, uniformly in the replication counts. Its ratio to q_j is 1, so this entire edge family cannot violate any uniform linear bound with C >= 1.

## Failure

NOT fails: arbitrary signed rank-one replication has exact rejection probability q, including arbitrarily imbalanced and growing dimensions.
