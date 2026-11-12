---
type: search_round
title: Independent antipodal block calibration and the joint Gaussian obstruction
target_asset: gaussian_simes_one_sided_uniform_linear_bound
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_simes_one_sided_uniform_linear_bound_r2_s1_harmonic_copula_normal_marginals
  - >-
    cand_gaussian_simes_one_sided_uniform_linear_bound_r2_s2_independent_antipodal_multiscale_blocks
  - >-
    cand_gaussian_simes_one_sided_uniform_linear_bound_r2_s3_independent_antithetic_blocks
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:21:57.905Z'
extension_version: 0.0.4
---

## Obstructions

- Independent Gaussian antipodal blocks, with arbitrary sign multiplicities and arbitrarily unequal block masses, satisfy the uniform bound $\mathbb P(E_q)\le 2q$ according to this round's extremal candidate. This covers growing rank and exponentially separated masses within that family, so varying those parameters cannot yield an unbounded ratio $\mathbb P(E_q)/q$. The balanced antithetic subfamily reduces exactly to independent-uniform Simes and has probability $q$ for $0<q<1/2$, according to the boundary-degenerate candidate. These are one nested family of obstructions, not two independent mechanisms.
- A normal-marginal construction in which a coordinate difference has both an atom at zero and positive probability of being nonzero cannot be jointly Gaussian: every Gaussian difference is either deterministic or has an atom-free normal law. The harmonic-copula construction fails the joint Gaussian hypothesis for this reason. Transforming its marginals to standard normal does not put this object inside the target model; its later checks remain unknown.

## Limitations

- All three round-2 candidates failed. Two meet the hypotheses but fail the conclusion-violation check; the harmonic-copula candidate fails the joint Gaussian hypothesis before its later checks. This round provides neither a counterexample nor a proof of the conjecture, and does not identify an optimal constant.
- The independent-block obstruction does not cover correlated Gaussian carriers, arbitrary nonuniform planar directions, or general growing-rank mixed-sign Gram configurations. Dependence across carriers and geometric scales remains uncovered, including covariance and dimension varying with $q$.
- Only candidate summaries and failure lines were supplied in this stage's context pack. The block bounds and exact reduction are reported from those lines, not independently verified here from candidate derivations.
- A proof route would need an additional dependence comparison or a direct Gaussian-geometric argument controlling the union over BH crossing ranks. Calibration of independent carriers alone supplies no such comparison. Fixed-dimension results also leave the required dimension uniformity unresolved, and mixed-null FDR is outside this all-null target.
