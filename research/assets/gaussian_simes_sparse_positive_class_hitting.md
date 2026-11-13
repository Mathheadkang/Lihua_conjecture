---
type: lemma
title: Sparse Simes crossings are proportionally hit by a random positive class at a fixed level
status: draft
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
tags:
  - simes_positive_cover_route
---

# Sparse Simes crossings are proportionally hit by a random positive class at a fixed level

## Statement

For a positive integer $N$ and $\Sigma\in\mathcal C_N$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) (singular matrices allowed), let $T\sim\mathcal N_N(0,\Sigma)$ and $p_i=\overline\Phi(T_i)$ be the [one-sided Gaussian p-values](../definitions/gaussian_test_pvalues.md). For $\alpha\in(0,1)$ let $\mathcal A_\alpha=\mathcal R_\alpha(p)$ be the rejection set of the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), $r_\alpha=|\mathcal A_\alpha|$, $E_\alpha=\{r_\alpha\ge1\}$, $u_\alpha=\overline\Phi^{-1}(\alpha)$, and for $\delta>0$
$$
D_{\alpha,\delta}=\Bigl\{\exists k\in[N]:\ \frac{\alpha k}{N}\ge\overline\Phi(u_\alpha+\delta)\ \text{ and }\ \#\Bigl\{i:p_i\le\frac{\alpha k}{N}\Bigr\}\ge k\Bigr\}.
$$
A positive class of $\Sigma$ is a nonempty $S\subseteq[N]$ with $\Sigma_{ij}\ge0$ for all $i,j\in S$. For a probability measure $\pi$ on the positive classes of $\Sigma$ and $c\in(0,1]$, put
$$
h_{\alpha,\pi,c}(T)=\pi\Bigl(\Bigl\{S:\ |\mathcal A_\alpha\cap S|\ge\max\Bigl(1,\ \frac{c\,|S|\,r_\alpha}{N}\Bigr)\Bigr\}\Bigr)\ \text{ on }E_\alpha,
\qquad h_{\alpha,\pi,c}(T)=0\ \text{ off }E_\alpha.
$$

There exist universal constants $\delta_0\in(0,1]$, $c_{\mathrm{hit}}\in(0,1]$, $c_*\in(0,1]$ and $\alpha_1\in(0,1/4]$ such that for every $\alpha\in(0,\alpha_1]$, every positive integer $N$ and every $\Sigma\in\mathcal C_N$ there is a probability measure $\pi=\pi_{\alpha,N,\Sigma}$ on the positive classes of $\Sigma$, depending only on $(\alpha,N,\Sigma)$ and not on $T$, with
$$
\mathbb P_{N,0,\Sigma}\Bigl(E_\alpha\setminus D_{\alpha,\delta_0},\ h_{\alpha,\pi,c_{\mathrm{hit}}}(T)<c_*\Bigr)\le\frac14 .
$$
The constants do not depend on $\alpha$, $N$, $\Sigma$, the signs of the correlations, or the rank of $\Sigma$.
