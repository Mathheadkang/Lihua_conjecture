---
type: lemma
title: Universal positive conditional p-path jump budget for Gaussian BH
status: deprecated
source:
  kind: original
depends_on:
  - gaussian_bh_finite_signed_p_path_identity
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - universal_budget
  - positive_jumps
  - teaching_route
---

## Statement

Use the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [one-sided Gaussian p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary BH](../definitions/benjamini_hochberg_step_up.md), and [FDR](../definitions/false_discovery_rate.md). For every finite $N\geq1$, $\theta\in\mathbb R^N$, positive semidefinite unit-diagonal $\Sigma$, and $0<q\leq S(1)$, let $S=\overline\Phi$, $I_0=\{i:\theta_i\leq0\}$, and define $B_i$ by the [exact finite signed conditional p-path identity](gaussian_bh_finite_signed_p_path_identity.md):
$$
B_i(\xi)=\sum_{t\in J_i(\xi)}g_i(t)
[A_i(t^-)-A_i(t^+)]_+.
$$
Here $J_i$ contains only the actual net discontinuities of $A_i$, with simultaneous crossings merged, not every element of the auxiliary finite event set. The asserted quantitative gate is that there exists one finite universal constant $C_B$ such that
$$
\frac1N\sum_{i\in I_0}\mathbb E B_i
\leq C_B\sqrt{\log(1/q)}.
$$
The constant is independent of $N$, means, covariance, rank, and null proportion; all model parameters may depend arbitrarily on $q$. There is no fixed-dimension restriction, direction bound, attained-extremizer assumption, smoothing or rank cutoff, nor reduction of negative true-null means to zero. Empty true-null sets have zero left side. Singular covariance and $N=1$ are included.

## Role and falsification criterion

This is a draft sufficient strengthening, separate from the exact identity. If proved, that identity gives
$$
F\leq q\pi_0+C_Bq\sqrt{\log(1/q)}.
$$
A refutation requires a legal family for which
$$
\frac{N^{-1}\sum_{i\in I_0}\mathbb E B_i}{\sqrt{\log(1/q)}}
$$
is unbounded. A large fixed-model value or finite numerical grid does not suffice. The finite identity is declared as a dependency before the first search; it is not assumed proved merely by this declaration.

## Initial calibration obligations

Reconstruct and test, rather than assume, the proposed calibrations: nonnegative correlations to a selected null should make its $A_i$ nondecreasing and $B_i=0$; antipodal all-null clone groups should have zero positive charge; a single zero-null clone group of mass $\alpha$ against arbitrary positive-mean opposite-sign clone groups should obey $B_i\leq\log(1/\alpha)$ and hence $\alpha\log(1/\alpha)\leq1/e$. Here a clone group consists of identical scores, and $\alpha$ is its integer multiplicity divided by $N$. These are search tests, not approved auxiliary results or extra assumptions. Retain actual largest ranks, signed cancellations and all labels. Failure of this stronger budget leaves the main FDR targets and the finite identity unchanged; the net signed charges remain a distinct possible route.
