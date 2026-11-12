---
title: Frozen-ray maximal Gaussian likelihood-ratio bounds
type: conjecture
status: approved
source:
  kind: original
  note: Formalized from idea_9f8ffb204424; unproved finite-mixture conjecture.
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
serves:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags:
  - cross-discipline-brainstorm-20261110
  - frozen-ray
  - gaussian-likelihood-ratio
---

# Frozen-ray maximal Gaussian likelihood-ratio bounds

## Statement

Let $n\geq1$ be an integer, let $\Sigma\in\mathcal C_n$ be any correlation matrix in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), and let $Z=(Z_1,\ldots,Z_n)\sim\mathcal N_n(0,\Sigma)$. Singular matrices and correlations of either sign are allowed. Let $\omega=(\omega_1,\ldots,\omega_n)$ be any deterministic probability vector: $\omega_i\geq0$ for every $i$ and $\sum_{i=1}^n\omega_i=1$. Define, for every real $w\geq0$,
$$
L_w(Z)=\sum_{i=1}^n\omega_i\exp\!\left(wZ_i-\frac{w^2}{2}\right),\qquad
\Lambda(Z)=\sup_{w\geq0}L_w(Z).
$$
The same realization of $Z$ is used for every $w$ in this supremum. All probabilities and expectations below are with respect to this centered Gaussian law. The logarithm is natural.

The order assertion is that there is a universal finite constant $C_{\mathrm{ord}}>0$ such that, for every such $n,\Sigma,\omega$ and every real $c\geq2$,
$$
\mathbb E\min\{c,\Lambda(Z)\}\leq C_{\mathrm{ord}}\sqrt{\log c}.
$$
The sharp strengthening asserts that there is a universal finite constant $C_{\mathrm{sh}}>0$ such that, under the same quantifiers,
$$
\mathbb E\min\{c,\Lambda(Z)\}\leq\sqrt{\frac{\log c}{\pi}}+C_{\mathrm{sh}}.
$$
The maximal-tail assertion is that there is a universal finite constant $C_{\mathrm{tail}}>0$ such that, for every such $n,\Sigma,\omega$ and every real $\alpha\geq2$,
$$
\mathbb P\{\Lambda(Z)\geq\alpha\}\leq
\frac{C_{\mathrm{tail}}}{\alpha\sqrt{\log\alpha}}.
$$
Each constant must be independent of the dimension, covariance rank, correlation matrix, weights, and truncation or tail level. All three assertions are conjectural. The sharp strengthening and the maximal-tail assertion are recorded separately; neither is being inferred from the other. No infinite-dimensional Gaussian random element or general measure on a Hilbert ball is part of this finite-mixture statement.

## Motivation

The source idea [Frozen-ray maximal likelihood ratio: a maximal form of Gaussian L1-regularization for the null tail-ratio field](../ideas/idea_9f8ffb204424.md) proposes this field as the limit of conditional null tail ratios in a weak-loading Gaussian population regime. Its single-direction benchmark motivates the square-root-logarithmic truncated-moment scale and the coefficient $1/\sqrt\pi$. Its numerical examples motivate asking for a bound uniform over the weights and the geometry of all directions. Those diagnostics and the source idea's claimed intermediate identities have not been independently verified here and are not dependencies of this statement.

The conjecture could support structured-model progress toward the universal order upper bounds for [one-sided Gaussian BH](gaussian_bh_one_sided_universal_order_upper.md) and [two-sided Gaussian BH](gaussian_bh_two_sided_universal_order_upper.md). A transfer from the finite-mixture field to either testing problem would require its own justified reduction. In particular, the source idea's direct finite-model comparison retains a Gaussian hazard factor that can depend on the number of tests. Thus even a proof of the order assertion alone would leave the dimension-uniform mixed-null BH aggregation problem unresolved. The two entries in `serves` express this potential relevance; no required result is made dependent on the conjecture.

The first substantial mathematical obligation is control of the supremum over arbitrarily late values of $w$, uniformly over $n,\Sigma,\omega$. A fixed-$w$ estimate does not provide that control, and the source idea does not establish a uniform cost for late detection across many directions. This node contains no counterexample search, proof plan, or proof. Its literature novelty has not been established.
