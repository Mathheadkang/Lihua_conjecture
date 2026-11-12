---
type: search_round
title: Round 4 obstruction from bounded partitions into controlled Simes classes
target_asset: gaussian_simes_one_sided_uniform_linear_bound
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_simes_one_sided_uniform_linear_bound_r4_s2_adjacent_gaussian_differences
  - >-
    cand_gaussian_simes_one_sided_uniform_linear_bound_r4_s3_signed_onefactor_fullrank
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:30:19.146Z'
extension_version: 0.0.4
---

## Obstructions

- A deterministic partition into a bounded number of classes with uniformly controlled classwise Simes probabilities prevents an unbounded rejection-probability-to-level ratio. Precisely, let nonempty classes have sizes $n_j$ summing to $N$, and let $E_{q,j}$ be the Simes crossing event within class $j$ at level $q$. For a full crossing at rank $k$, count $r_j$ class-$j$ p-values at most $qk/N$. Since $\sum_j r_j\ge k$, some class satisfies $r_j/n_j\ge k/N$. Its $r_j$-th order statistic is at most $qk/N\le qr_j/n_j$, so $E_q\subseteq\bigcup_j E_{q,j}$. Consequently, classwise bounds $\mathbb P(E_{q,j})\le C_jq$ give $\mathbb P(E_q)\le q\sum_j C_j$, with no independence assumption between classes. This deterministic implication is checked here directly; the classwise probability inputs below are the supplied candidate reports.
- Growing-dimensional adjacent Gaussian difference chains fail to refute the target because their odd and even coordinates separately have independent uniform p-values. The supplied round-4 candidate therefore has two classes with $C_j=1$, yielding $\mathbb P(E_q)\le2q$. Growth in the chain length does not escape this fixed-partition obstruction.
- Signed one-factor full-rank Gaussian models fail to refute the target because partitioning by loading sign gives at most two nonnegatively correlated Gaussian subvectors. Using the classwise Simes bounds reported in the supplied candidate summary yields $\mathbb P(E_q)\le2q$. Full rank, arbitrary loading magnitudes, and increasing dimension do not remove this two-class reduction.

## Limitations

- Both round-4 candidates passed the listed hypotheses and failed NOT. There is no counterexample, proof of the general conjecture, or determination of an optimal constant. Candidate bodies were not included in the pack and were not read; the asserted model-specific class structures and classwise probability bounds are reported inputs, not independently audited here.
- The deterministic partition implication is general, but its bound scales with the sum of class constants. It does not give a universal estimate for covariance families whose number of controlled classes grows with dimension or with $q^{-1}$, nor establish that every Gaussian covariance has a bounded such partition.
- Arbitrary mixed-sign Gaussian Gram configurations with an unbounded number of distinct p-value formulas remain uncovered. The round does not address all nonuniform planar configurations, all singular covariances, or arbitrary growing-rank dependence. Earlier finite-carrier and special-family obstructions remain special cases and cannot be combined into an unrestricted covariance comparison without another argument.
- A possible proof step is to obtain a dimension-independent replacement for the partition union bound, or a justified reduction to classes with uniformly bounded total Simes constants. This round establishes only the partition implication, not either missing reduction. Dimension and covariance may vary with $q$; mixed-null FDR remains outside this all-null target.
