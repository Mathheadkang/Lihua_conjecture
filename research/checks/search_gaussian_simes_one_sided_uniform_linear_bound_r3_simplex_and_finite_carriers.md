---
type: search_round
title: 'Round 3: simplex and finitely many carrier obstructions'
target_asset: gaussian_simes_one_sided_uniform_linear_bound
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_simes_one_sided_uniform_linear_bound_r3_s1_zero_sum_simplex
  - >-
    cand_gaussian_simes_one_sided_uniform_linear_bound_r3_s2_dependent_two_carrier_multiplicities
  - >-
    cand_gaussian_simes_one_sided_uniform_linear_bound_r3_s3_singular_regular_simplex
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:25:17.939Z'
extension_version: 0.0.4
---

## Obstructions

- Singular zero-sum regular-simplex Gaussian families, including their growing-dimensional instances, satisfy the reported bound $\mathbb P(E_q)\le 2eq$ for $0<q\le 1/(2e)$, where $E_q=\{\exists k:p_{(k)}^{(1)}\le qk/N\}$. The boundary-degenerate and drop-hypothesis candidates describe this same family; they are one obstruction, not two independent mechanisms. Singularity, increasing rank, and the negative dependence of this simplex family therefore do not produce the unbounded ratio required to refute an unspecified universal linear bound.
- Arbitrarily dependent pairs of standard Gaussian carriers with deterministic signed multiplicities produce at most four distinct coordinate p-value formulas. This family satisfies $\mathbb P(E_q)\le4q$ by the candidate failure line, irrespective of multiplicities and correlation. More generally, if coordinates consist of at most $L$ distinct standard-uniform p-value formulas, then rejection implies that at least one of those formulas is at most $q$: every BH threshold $qk/N$ is at most $q$. A union bound gives $\mathbb P(E_q)\le Lq$ without assuming independence. Thus every fixed number $m$ of Gaussian carriers used through signed repetitions has the bound $2mq$ and cannot refute the conjecture merely by increasing dimension or altering multiplicities.

## Limitations

- All three round-3 candidates passed the listed hypotheses and failed NOT. The conjecture remains unresolved: this round supplies no counterexample, proof, or optimal constant. The reported simplex estimates are taken from the supplied candidate summaries, not independently rechecked from their omitted derivations. The elementary finite-formula union bound above is derived directly here.
- The simplex obstruction addresses a special singular family with a specific correlation structure. It does not establish a bound for every covariance with nonpositive off-diagonal entries, every singular covariance, or general growing-rank Gaussian models.
- The finite-carrier bound grows with the number of carriers. Arbitrarily dependent Gaussian direction sets with an unbounded number of distinct p-value formulas, including general mixed-sign Gram configurations and nonuniform planar configurations, remain uncovered. The board's earlier independent-antipodal-block bound controls a growing number of carriers only under that special independence structure.
- A proof route would need a dimension- and carrier-count-independent estimate for the union of BH crossing events, or a justified Gaussian comparison reducing general dependence to a uniformly controlled family. Neither the simplex estimates nor the finite-formula union bound supplies that step. Dimension, covariance, and carrier count may vary with $q$; checking any fixed-dimensional configuration or keeping the number of formulas bounded does not resolve this uniformity requirement. Mixed-null FDR remains outside this all-null target.
