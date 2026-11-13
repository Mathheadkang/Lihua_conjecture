---
type: lemma
title: Uniform Schur-path downward-variation budget at loaded all-null Simes maximizers
status: draft
source:
  kind: original
depends_on:
  - gaussian_simes_schur_array_compactification
related_assets:
  - gaussian_bh_exchangeable_array_variational_compactification
  - gaussian_simes_dense_crossing_tilt_bound
uses_definitions:
  - gaussian_bh_marked_exchangeable_parameter_array
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
tags:
  - simes
  - global_null
  - one_sided
  - schur_square_path
  - compactness
---

# Uniform Schur-path downward-variation budget at loaded all-null Simes maximizers

## Statement

Use the notation and conclusions of [the Schur-path array compactification](gaussian_simes_schur_array_compactification.md): the compact set $\mathfrak P_0$ of all-null exchangeable arrays, the Schur-path maps $S_t$, the population all-null Simes functional $\Phi_\sigma(\cdot\,;q)$ at common loading $\sigma$, and the continuous path function $f^\sigma_{P,q}(t)=\Phi_\sigma(S_tP;q)$. For a real function $f$ on $[0,1]$, define its downward variation
$$
\mathcal V_-(f)=\sup_{0=t_0<t_1<\cdots<t_m=1}\ \sum_{l=1}^m\bigl[f(t_{l-1})-f(t_l)\bigr]_+,\qquad a_+=\max(a,0),
$$
over all finite partitions. It may be infinite.

There exist constants $q_*\in(0,1/4]$, $\sigma_0\in(0,1)$ and $\delta\in(0,1)$ such that the following holds. Let $\sigma\in(0,\sigma_0]$, and let $P^*\in\mathfrak P_0$ satisfy
$$
\Phi_\sigma(P^*;q_*)=\max_{P\in\mathfrak P_0}\Phi_\sigma(P;q_*).
$$
Then
$$
q_*+\mathcal V_-\bigl(f^\sigma_{P^*,q_*}\bigr)\le1-\delta .
$$
The constants do not depend on $\sigma$, on the maximizer $P^*$, or on any dimension.

## Motivation

This is the crux of a contradiction or compactness route to [the uniform linear Simes bound](gaussian_simes_one_sided_uniform_linear_bound.md). It is the weak variant "$q_*+\mathcal V_-<1$ at one level" of the variation assertion (SV) in [the Schur-square tensor-lift idea](../ideas/idea_6b48b2fe25e1.md). It is required only at loaded population maximizers, and only uniformly as the loading $\sigma$ tends to zero. Finite models are special cases by part 4 of the compactification. Because $f(0)\le f(1)+\mathcal V_-(f)$ and $f(1)\le q_*$, the statement caps the attained maximum by $1-\delta$.

Suggested proof architecture. This is unverified guidance, not a proof.

- **Contradiction sequence.** If the statement fails at a small fixed $q_*$, take $\sigma_n\downarrow0$ and maximizers $P_n$ with $q_*+\mathcal V_-(f_n)\to1$. Select deterministic directing measures $\mu_n$ on the unit ball of a Hilbert space, using the marked directing representation of part 6 of [the approved array compactification](gaussian_bh_exchangeable_array_variational_compactification.md), specialized to all-null arrays. The population Schur path is then the push-forward of $\mu_n$ under the tensor lift $v\mapsto(\sqrt{1-t}\,v,\sqrt t\,v\otimes v)$, with private noise absorbing the loss of norm. Extract a limit in the $\sigma$-free compact topology and record the part of the Simes mass that escapes to vanishing population rank (the sparse crossings) as a defect.
- **Dense part.** In every conditional finite model, crossings at thresholds within one unit of $\overline\Phi^{-1}(q_*)$ cost at most $C_Dq_*$, by [the dense tilt bound](gaussian_simes_dense_crossing_tilt_bound.md).
- **Population Price formula.** In population form, the pair terms of the three-face identity become a double integral over $\mu\otimes\mu$ of $\rho(1-\rho)$ against the second variation of the mean-field crossing functional at the touching rank. There the quadratic form of the kernel $\rho^2-\rho$ is
$$
\Bigl\|\int a(v)\,v\otimes v\,d\mu(v)\Bigr\|^2-\Bigl\|\int a(v)\,v\,d\mu(v)\Bigr\|^2 .
$$
The pair terms must be summed with their signs before any positive part is taken. The factors $\rho$ and $1-\rho$ must be kept, and $\rho^2-\rho$ must not be replaced by an unrelated positive-semidefinite matrix.
- **Maximality.** The proof may use every lawful competitor: the inequality $f(t)\le f(0)$ along the whole path, partial tensor lifts of sub-populations, and dilution by independent coordinates. These give first-order and global comparison inequalities at $P^*$.
- **Benchmarks.** The exact benchmarks of [the partial variation calculation](../ideas/idea_a0805e98f90d.md) must be consistent with any proposed rigidity step. They are $\mathcal V_-\le2q$ for two clone groups, $\mathcal V_-\le q$ for signed rank one, and $\mathcal V_-\le16q$ for three coordinates.

A failure of this lemma at one chosen $q_*$ refutes only that choice. It refutes neither the Simes endpoint conjecture nor the existence of another level.
