---
type: idea
title: >-
  Fixed-level Gaussian Simes proof program: spectral count bounds and a
  positive-measure hinge acceptance region
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_simes_one_sided_uniform_linear_bound
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - global-null-simes
  - proof-program
  - fixed-level-acceptance
  - spectral-count-bound
  - not-an-executable-proof
---

Suggested by this chat after the researcher asked for an online literature search and a proof plan. This is an UNPROVED research program, not an executable proof plan. The general positive-measure estimate below is missing. It draws on [amplification](idea_7d0a17e5c13c.md), [the hinge formulation](idea_e1c816206945.md), [dense-crossing tilts](idea_a2ee64f07126.md), [random positive-correlation covers](idea_665151fb5a87.md), [the two-sided comparison](idea_0f23d32868ad.md), and [the common-loading continuity warning](idea_ed169268dd35.md).

## 1. Fix the weakest sufficient target

Let B(q) be the supremum of centered one-sided Gaussian Simes rejection probability over all finite correlation matrices. Formalize independent-block amplification, with epsilon-maximizers for the supremum. If B(alpha_0) <= 1-delta at one fixed alpha_0, then B(t) <= 2 log(1/delta) t/alpha_0 for t <= alpha_0/2. No sharp constant or direct linear tail estimate is necessary.

## 2. First concrete intermediate calculation: bounded covariance operator norm

For a correlation matrix Sigma with operator norm at most K, the proposed bound is P(E_q) <= 16 K q for q <= 1/4. Derivation to formalize and independently verify: for p=Phibar(u), expand 1_{G>=u}-p in Hermite polynomials. Every Schur power Sigma^{circ r} has operator norm at most K, since Schur multiplication by a correlation matrix is positive and unital. Consequently Var(sum_i 1_{T_i>=u}) <= K N p(1-p). A crossing at k in [2^j,2^{j+1}) implies a count at least 2^j at tail probability p_j=q min(2^{j+1},N)/N. Its mean is at most 2q 2^j. For q<=1/4, Chebyshev gives at most 8Kq/2^j, and summing j gives 16Kq. This treats growing N, arbitrary signs and singular matrices, but its K dependence leaves highly redundant loading populations uncovered. It is a derivation from this chat, not a sourced project theorem.

The full Hermite and dyadic proof is now saved as [the bounded-spectrum observation](idea_fc8702e63d1e.md). [The weighted-count observation](idea_1a909d8f1d0b.md) retains exact replication invariance and proves an elementary heavy-light budget for independent weighted carriers; its near-copy generalization remains open.

## 3. Exact analytic target from the hinge idea

Put psi(x)=E(G-x)_+=phi(x)-x Phibar(x), X(x)=N^{-1}sum_i(T_i-x)_+, and R_*=sup_{x>=0}X(x)/psi(x). Formalize the existing implication E_q => R_* >= c sqrt(log(1/q)). It suffices to find fixed A>=2 and delta>0 such that P(R_*<=A)>=delta for every finite model. The stronger uniform C/a tail and the sum of per-scale probabilities are NOT required.

For a>=2, R_*<=a is equivalent to all subset-average inequalities mean_{i in I} T_i <= h(Phibar^{-1}(|I|/(aN))), where h=phi/Phibar, over nonempty I. Thus the missing claim is a uniform positive Gaussian measure for an explicit convex region. Proving this general claim is the main unresolved research step, not a consequence of convexity alone.

[The convex-acceptance observation](idea_9dc45fd77c4b.md) records the exact geometry, the weaker fixed-level sufficient condition, and the reverse comparison with a Simes event. A stronger universal nonpositive-mean condition on the penalized subset maximum fails: [clones plus independent coordinates](idea_b57684f6c514.md) give a countercheck even with nonnegative correlations. That failure does not invalidate the positive-probability acceptance target.

## 4. Literature-informed attack on the high-redundancy case

Chi-Ramdas-Wang, https://arxiv.org/html/2212.09706v4#S3.SS3, Theorem 8 gives positive/nonpositive-correlation bounds and only fixed-model small-level asymptotics. X. Zhang, https://arxiv.org/html/2611.02513 (2 November 2026), Appendix D.1 constructs positive-probability no-crossing background events by marked small-p-value process approximation for early ranks and count tail bounds for later ranks. Its hypotheses restrict block sizes, correlations and covariance graph density; it is a proof prototype, not a theorem applicable to arbitrary covariance. The global-null comparison p_i^(2)<=2p_i^(1) allows bounded-loss transfer from two-sided rejection control if useful.

Investigate a threshold-dependent cluster/contraction argument preserving cluster masses and physical ranks, together with the spectral count estimate for suitably controlled remaining components. Candidate critical geometry is u^2(1-|rho|) for two-sided near-copies at threshold u. For one-sided testing signs must be retained; alternatively pass through the two-sided global-null comparison. Every error must be bounded over the whole rank range by a fixed budget, not a constant per window or per cluster. No general cluster decomposition with this property has been established. Dense high-rank signed frames must be included, not silently assigned to a bounded-degree or bounded-cover subclass.

A secondary experiment is threshold-dependent Hermite splitting: high Schur powers damp correlations away from +/-1, while near-copy groups retain multiplicities. This does not by itself control the low-chaos part or give constants uniform in the Hermite cutoff.

[The Hermite-splitting and OU-bridge note](idea_44d042a5d13f.md) makes the positivity and cutoff obstructions explicit. An alternative is [the hinge-upcrossing approach](idea_600a1016d3ef.md), which charges persistent excursions once, but still lacks a collective active-set surface estimate.

## 5. Tests and stop criteria

First test rank-one signed replication, independent coordinates, independent antipodal blocks, equicorrelation with small common loading, growing simplex blocks, and densely sampled signed spherical frames. Reject an argument that pays log N, a growing cluster/cover count, a covariance-graph degree, or a Hermite-cutoff-dependent constant. Do not assume a uniformly small effect of deleting a small covariance eigenmode: idea_ed169268dd35 records a relevant unverified discontinuity warning.

Lehec, https://arxiv.org/abs/1505.04083, controls a fixed smoothed density, not the required supremum. General OU maximal weak-(1,1), https://arxiv.org/abs/1901.04823, has dimension-dependent constants. Mulgund, https://arxiv.org/html/2607.14087, requires R-J/m positive semidefinite and common thresholds, and explicitly disallows a general unequal-threshold extension. None currently supplies the missing acceptance estimate.

Success means a fixed positive acceptance probability uniform in N, rank, signs, multiplicities and all singular limits; then amplification completes the precise linear Simes asset. Until that estimate has a concrete derivation, retain this as an approach idea rather than a pending executable proof plan.

The [scalar hinge and Gaussian-correlation counterchecks](idea_4d3b81529002.md) explain why a bounded expectation of the hinge supremum, or a simple product of per-scale acceptance estimates, cannot close the remaining step. The detailed fixed-level amplification proof has been added to [the all-or-nothing observation](idea_7d0a17e5c13c.md). All these side-chat notes remain draft; no proof, source, or counterexample was approved by this chat.
