---
type: lemma
schema_version: 2
title: Sign-split cluster steering bound for one-sided Gaussian BH outside the null-only crossing event
status: draft
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - current_phase
  - universal_order
  - one_sided
  - sign_split_route
---

# Sign-split cluster steering bound for one-sided Gaussian BH outside the null-only crossing event

## Statement

There exist universal constants $0<C_2<\infty$ and $q_2\in(0,1)$ such that the following holds.

Let $(N,\theta,\Sigma)$ be an admissible [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), singular $\Sigma$ allowed, with $T\sim\mathcal N_N(\theta,\Sigma)$, one-sided [Gaussian test p-values](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$ and true-null set $I_0=\{i:\theta_i\le0\}$, assumed nonempty. Let $0<q\le q_2$. Run the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at level $q$ on all $N$ p-values, with its largest qualifying rank, non-strict comparisons and multiplicities, and let $R$, $V=|\mathcal R_q\cap I_0|$ and $\operatorname{FDP}=V/(R\vee1)$ be as in the [false discovery rate](../definitions/false_discovery_rate.md) definition.

Let $Y$ be a random vector in $\mathbb R^m$ ($m\ge0$; $m=0$ means $Y$ is constant), defined on an extension of the probability space, such that $(T,Y)$ is jointly Gaussian. Let
$$
Q=\operatorname{Cov}(T_{I_0}\mid Y)
=\Sigma_{I_0I_0}-\operatorname{Cov}(T_{I_0},Y)\operatorname{Cov}(Y)^{+}\operatorname{Cov}(Y,T_{I_0})
$$
be the deterministic conditional covariance matrix, where $^{+}$ is the Moore-Penrose pseudo-inverse. Let $\mathcal C$ be a partition of $I_0$ into nonempty clusters satisfying the sign-split condition
$$
Q_{ij}\le0\qquad\text{whenever $i$ and $j$ lie in distinct clusters of }\mathcal C .
$$
Within a cluster no sign condition is imposed. Using the canonical Gaussian regular conditional law given $Y$, put, for $0<t\le q$,
$$
\Gamma(t;Y)=\frac1{Nt}\sum_{c\in\mathcal C}|c|\;\mathbb P\Bigl(\min_{i\in c}p_i\le t\Bigm| Y\Bigr),
\qquad
K(Y)=\max\Bigl\{1,\ \sup_{t\in(0,q]\cap(\mathbb Q\cup\{q\})}\Gamma(t;Y)\Bigr\}.
$$
Let $E_0$ be the null-only crossing event
$$
E_0=\Bigl\{\exists k\in\{1,\ldots,N\}:\ \#\{i\in I_0:p_i\le qk/N\}\ge k\Bigr\}.
$$
Then
$$
\mathbb E\bigl[\operatorname{FDP}\,\mathbf 1_{E_0^{c}}\bigr]\le C_2\,q+C_2\,\mathbb E\bigl[\min\{1,\,q\,K(Y)\}\bigr].
$$
The constants are independent of $N$, $\theta$, $\Sigma$, $m$, the law of $Y$, the partition and every other model parameter; all of these may depend on $q$. The right side is an explicit functional of the conditional null law given $Y$ and does not contain the [false discovery rate](../definitions/false_discovery_rate.md). No coordinate is deleted or relabelled, and the alternatives are not assumed to be measurable with respect to $Y$.

## Motivation

This is the steering half of the sign-split route of [the researcher-selected direction](../ideas/idea_afb46a36a429.md), recorded in [the route proposal](../ideas/idea_26f348b94400.md): once the positively associated null structure has been placed in a carrier $Y$ or inside clusters, nulls with nonpositive residual correlation across clusters should not be steerable by Gaussian alternatives beyond their conditional cluster intensity. On $E_0^c$ every nonempty BH rejection set contains an alternative, so this statement concerns steering only; the null-only crossing event is left to the linear Simes bound.

Two consistency checks, not proofs. With $Y$ containing the complete alternative vector and singleton clusters, the statement is implied by the approved [sub-Poisson calibration](gaussian_bh_conditional_subpoisson_calibration.md). With $Y$ constant, singleton clusters and mutually independent nulls, $K\equiv1$ and the statement becomes the class-E conjecture of [the two-class test proposal](../ideas/idea_33e7435632a7.md), which is open. Gaussian interpolation of the cross-cluster covariance from $0$ to $Q$ keeps every within-cluster block fixed and suggests that cluster-minimum events are negatively associated across clusters given $Y$; that suggestion is unproved here.
