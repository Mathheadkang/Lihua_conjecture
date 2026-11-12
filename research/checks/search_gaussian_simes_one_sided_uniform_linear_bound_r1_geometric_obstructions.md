---
type: search_round
title: 'Round 1: low-rank and bounded-dimension obstructions for Gaussian Simes'
target_asset: gaussian_simes_one_sided_uniform_linear_bound
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_simes_one_sided_uniform_linear_bound_r1_s1_rank_one_signs
  - >-
    cand_gaussian_simes_one_sided_uniform_linear_bound_r1_s2_bounded_three_coordinates
  - >-
    cand_gaussian_simes_one_sided_uniform_linear_bound_r1_s2_rank_one_sign_blocks
  - >-
    cand_gaussian_simes_one_sided_uniform_linear_bound_r1_s3_regular_polygon_rank_two
  - cand_gaussian_simes_one_sided_uniform_linear_bound_r1_s3_signed_rank_one
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:17:48.124Z'
extension_version: 0.0.4
---

## Obstructions

- Every signed rank-one Gaussian family, including arbitrary multiplicities, sign imbalance, and dimension growing with the testing level, has Simes rejection probability exactly $q$ for $0<q<1/2$, according to the three rank-one failures in the round pack. These are one family, not three independent obstructions. Writing $T_i=s_i Z$, with $m_+$ positive signs and $m_-$ negative signs, rejection occurs in the disjoint tails $\overline\Phi(Z)\le qm_+/N$ or $\overline\Phi(Z)\ge1-qm_-/N$ (omit an absent sign class). Their probabilities sum to $q$. Replication or sign imbalance in this family therefore cannot produce an unbounded rejection-probability-to-level ratio.
- Every model with $N\le3$ obeys $\mathbb P(E_q)/q\le11/6$, as reported by the bounded-three-coordinate candidate. More generally, a bounded dimension cannot refute a conjecture allowing an unspecified finite universal constant: the harmonic Simes bound gives $\mathbb P(E_q)\le qH_N$ for arbitrary uniform marginals, where $H_N=\sum_{k=1}^N1/k$. A refuting sequence must have unbounded dimension.
- The regular-polygon rank-two Gaussian family has a dimension-uniform rejection bound below $4q$, as reported by the regular-polygon candidate. Increasing the number of equally spaced directions, even to arbitrarily dense directions, cannot refute the conjecture within this family. This obstruction does not cover arbitrary rank-two Gram configurations.

## Limitations

- All five candidates failed the conclusion-violation check. This round supplies neither a counterexample nor a proof of the target, and it does not determine an optimal constant.
- The workers covered signed rank-one models, dimensions at most three, and regular-polygon rank-two models. They did not cover general nonuniform planar directions, growing-rank Gram configurations, or covariance families with multiple geometric scales; such families may vary with $q$.
- The pack contains only candidate failure lines rather than their full checks. The polygon and three-coordinate bounds above summarize those lines; this round record is not an independent verification of their derivations.
- Fixed-dimension small-level results do not establish the required uniformity over $N$, rank, and covariance. The recorded literature observation identifies an open-problem context, and does not resolve that gap. Mixed-null FDR is outside this all-null target.
