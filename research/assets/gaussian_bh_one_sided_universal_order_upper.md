---
type: theorem
schema_version: 2
title: Universal order upper bound for one-sided Gaussian BH
status: draft
source:
  kind: original
  location: Researcher-authorized current-phase goal revision of 6 November 2026
depends_on:
  - gaussian_bh_fractional_frame_surface_kernel
  - gaussian_bh_conditional_compound_calibration
  - gaussian_bh_negative_null_boundary_strip
  - gaussian_bh_conditional_subpoisson_calibration
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_worst_case_bh_fdr
tags:
  - current_phase
  - universal_order
  - one_sided
---

# Universal order upper bound for one-sided Gaussian BH

## Statement

For the [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md) $F_1(q)$ defined below, there exist constants $0<C_1<\infty$ and $q_{0,1}\in(0,1)$ such that
$$
F_1(q)\le C_1 q\sqrt{\log(1/q)}
\qquad\text{for every }0<q\le q_{0,1}.
$$
The logarithm is natural. Both constants are universal: they are independent of the number of tests, means, covariance, null proportion, covariance rank, factor dimension, number of directions, and every other model-complexity parameter. No particular value or optimality of the constants is asserted.

Precisely, for every positive integer $N$, every $\theta\in\mathbb R^N$, and every symmetric positive-semidefinite matrix $\Sigma\in\mathbb R^{N\times N}$ with $\Sigma_{ii}=1$ for all $i\in\{1,\ldots,N\}$, let $T\sim\mathcal N_N(\theta,\Sigma)$. This is the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), including singular $\Sigma$. Define the [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) by
$$
p_i^{(1)}=\overline\Phi(T_i),\qquad
I_0^{(1)}(\theta)=\{i\in\{1,\ldots,N\}:\theta_i\le0\},
$$
where $\overline\Phi(t)=(2\pi)^{-1/2}\int_t^\infty e^{-u^2/2}\,du$ is the standard normal survival function. Apply the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) with ordered p-values, including multiplicities,
$$
\widehat k_q^{(1)}=\max\bigl(\{0\}\cup\{k\in\{1,\ldots,N\}:p_{(k)}^{(1)}\le qk/N\}\bigr),
$$
$$
\mathcal R_q^{(1)}=\begin{cases}
\{i:p_i^{(1)}\le q\widehat k_q^{(1)}/N\},&\widehat k_q^{(1)}>0,\\
\varnothing,&\widehat k_q^{(1)}=0.
\end{cases}
$$
Put $R_q^{(1)}=|\mathcal R_q^{(1)}|$ and $V_q^{(1)}=|\mathcal R_q^{(1)}\cap I_0^{(1)}(\theta)|$. The [false discovery rate](../definitions/false_discovery_rate.md) and its original worst-case envelope are
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)
=\mathbb E_{N,\theta,\Sigma}\!\left[\frac{V_q^{(1)}}{R_q^{(1)}\vee1}\right],
$$
$$
F_1(q)=\sup_{N\ge1}\ \sup_{\theta\in\mathbb R^N}
\sup_{\substack{\Sigma=\Sigma^{\mathsf T}\succeq0\\\Sigma_{ii}=1\ (1\le i\le N)}}
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma),
$$
where $N$ ranges over positive integers and $R\vee1=\max\{R,1\}$. Equivalently, the displayed order upper bound must hold for every such finite model at every $0<q\le q_{0,1}$. The supremum is taken anew at each $q$: $N$, $\theta$, $\Sigma$, and the true-null proportion $|I_0^{(1)}(\theta)|/N$ may all vary arbitrarily with $q$. There is no restriction on the signs or magnitudes of the remaining means, the covariance rank, or the order in which dimension and $q$ vary. Ordinary BH always uses the largest qualifying rank and non-strict threshold inequalities.

## Acceptance criterion

A complete proof must control the entire displayed supremum uniformly. A bound with an uncontrolled dependence on $\log N$, rank, factor count, or direction entropy does not prove this statement; results for a factor model, block model, spherical population, or a dimension limit alone remain supporting results. All unverified steps and dependencies require proof and fresh independent verification, separately from the other testing track.

A sufficient finite-level conclusion is $F_1(q)\le A_1 q[1+\sqrt{\log(1/q)}]$ for a finite universal $A_1$ on a universal interval $0<q\le\widetilde q_{0,1}<1$. Indeed, take $q_{0,1}=\min\{\widetilde q_{0,1},e^{-1}\}$ and $C_1=2A_1$, since $1+\sqrt{\log(1/q)}\le2\sqrt{\log(1/q)}$ there. This criterion makes no sharp-constant claim.
