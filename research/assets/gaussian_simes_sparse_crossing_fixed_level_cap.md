---
type: lemma
title: Fixed-level cap for sparse one-sided Gaussian Simes crossings
status: draft
source:
  kind: original
depends_on: []
related_assets:
  - gaussian_simes_dense_crossing_tilt_bound
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
tags:
  - simes
  - global_null
  - one_sided
  - sparse_crossings
---

# Fixed-level cap for sparse one-sided Gaussian Simes crossings

## Statement

There exist universal constants $q_S\in(0,1/4]$ and $\eta\in(0,1)$ such that the following holds. Let $N$ be a positive integer, let $\Sigma\in\mathcal C_N$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) (singular matrices allowed), let $T\sim\mathcal N_N(0,\Sigma)$, and let $p_i=\overline\Phi(T_i)$ be the [one-sided Gaussian p-values](../definitions/gaussian_test_pvalues.md). For $q\in(0,1)$ put $u_q=\overline\Phi^{-1}(q)$ and define the sparse-crossing event
$$
S_q=\Bigl\{\exists k\in\{1,\ldots,N\}:\ \frac{qk}{N}<\overline\Phi(u_q+1)\ \text{ and }\ \#\Bigl\{i\in\{1,\ldots,N\}:p_i\le\frac{qk}{N}\Bigr\}\ge k\Bigr\}.
$$
Then for every $q\in(0,q_S]$,
$$
\mathbb P_{N,0,\Sigma}(S_q)\le1-\eta .
$$
The constants $q_S$ and $\eta$ do not depend on $N$, $\Sigma$, $q$, the signs of the correlations, or the rank of $\Sigma$. All comparisons in the count are non-strict.

## Motivation

Only a dimension-free bound strictly below one is asked for, uniformly over small levels; no rate in $q$ is required. Equivalently, with $u_k=\overline\Phi^{-1}(qk/N)$, the event says that some subset $I$ with $u_{|I|}>u_q+1$ has $\min_{i\in I}T_i\ge u_{|I|}$: a penalized supremum over null sub-populations with the hard (min-entropy) penalty $\overline\Phi^{-1}(q|I|/N)$, restricted to the sparse thresholds that the [dense log-convex tilt](gaussian_simes_dense_crossing_tilt_bound.md) leaves open.

Unproved heuristics for an attack, recorded so that the proof stage can test them:

- Rank-one crossings cost at most $q$ by a union bound, so only ranks $k\ge2$ at sparse thresholds are at issue.
- The exponential (Kullback) form of the [Gibbs variational formula](../ideas/idea_c36aadbe5f06.md) is not usable as it stands: at threshold $x$ the passage from the indicator kernel to the exponential kernel costs the inverse Mills factor $h(x)\ge u_q+1$ per unit threshold window, and summing over the roughly $\sqrt{2\log N}$ sparse windows loses that factor in $N$. The hard penalty of the [convex hinge acceptance region](../ideas/idea_9dc45fd77c4b.md) does not lose it: by [the scalar calibration](../ideas/idea_4d3b81529002.md) the supremum over thresholds is free for a single coordinate.
- At a sparse threshold $x$, the Hermite variance in [the bounded-spectrum estimate](../ideas/idea_fc8702e63d1e.md) is carried by Schur powers of order about $x^2$, which damp correlations below $1-c/x^2$. Low chaoses then enter only through directions with large covariance eigenvalues.
- By [the all-or-nothing law](../ideas/idea_7d0a17e5c13c.md), failure would require Hommel-type accumulation of nearly independent crossings over many sparse dyadic scales sharing coordinates. Gaussian geometry should force near-clone clumps at different sparse scales to nest, so that a fine-scale crossing triggers coarser crossings with conditional probability bounded below.
