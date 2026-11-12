---
type: definition
title: Definition (common-loading tagged Gaussian population and Wasserstein metric)
status: approved
source:
  kind: original
depends_on:
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - common_loading
  - population_bh
  - wasserstein
---

## Definition

Fix $q\in(0,1/2)$, $\sigma\in(0,1)$, and a nonzero separable real Hilbert space $\mathcal H$ with inner product $\langle\cdot,\cdot\rangle$ and norm $\|\cdot\|$. Put $\tau=\sqrt{1-\sigma^2}$ and $\mathbb S(\mathcal H)=\{v\in\mathcal H:\|v\|=1\}$. The closed tagged parameter space is
$$
\mathcal E=\{(\theta,v,\ell)\in\mathbb R\times\mathbb S(\mathcal H)\times\{0,1\}:\ell=1\Longrightarrow\theta\le0,\ \ell=0\Longrightarrow\theta\ge0\}.
$$
The tag $\ell=1$ records a true null. The point $(0,v,0)$ is admitted only in the analytic completion; a finite ordinary testing model must instead use its canonical one-sided label $\ell=\mathbf1_{\{\theta\le0\}}$ from the [Gaussian p-value and true-null convention](gaussian_test_pvalues.md). Equip $\mathcal E$ with its Borel sets and the metric
$$
c((\theta,v,\ell),(\theta',v',\ell'))=|\theta-\theta'|+\|v-v'\|+\mathbf1_{\{\ell\ne\ell'\}}.
$$
Write $\mathcal P_1(\mathcal E)$ for deterministic Borel probability laws $\pi$ on $\mathcal E$ with $\int |\theta|\,\pi(d\theta,dv,d\ell)<\infty$. The laws are fixed independently of all Gaussian randomness. For $\alpha,\beta\in\mathcal P_1(\mathcal E)$, let $\Gamma(\alpha,\beta)$ be their probability couplings and define
$$
W_1(\alpha,\beta)=\inf_{\lambda\in\Gamma(\alpha,\beta)}\int_{\mathcal E\times\mathcal E}c(x,x')\,\lambda(dx,dx').
$$

An isonormal Gaussian process $X$ over $\mathcal H$ has centered jointly Gaussian finite-dimensional distributions with $\mathbb E[X(v)X(w)]=\langle v,w\rangle$. Use the following jointly measurable evaluation representative. Choose an orthonormal basis $(e_k)_{k\in J}$ of $\mathcal H$, where $J=\{1,\ldots,d\}$ when $\dim\mathcal H=d<\infty$ and $J=\mathbb N$ otherwise, and independent standard normal variables $(\xi_k)_{k\in J}$. Set
$$
X(v,\omega)=\sum_{k\in J}\langle v,e_k\rangle\xi_k(\omega)
$$
where the series converges, and set $X(v,\omega)=0$ otherwise. The finite sum convention applies when $J$ is finite. For every deterministic $v$, the series converges almost surely; its exceptional set may depend on $v$. Joint measurability and the probability-one, parameter-almost-everywhere validity needed for each stated law, and simultaneously for a countable family of laws, are obligations of the associated asset. No Gaussian random vector with identity covariance in infinite-dimensional $\mathcal H$ is postulated.

Let $Z$ be a standard normal variable independent of all $\xi_k$, and let $\mathbb P$ and $\mathbb E$ refer to this full Gaussian randomness. For $x=(\theta,v,\ell)\in\mathcal E$, define its score and one-sided p-value by
$$
T(x)=\theta+\tau X(v)+\sigma Z,\qquad p(x)=S(T(x)),\qquad S=\overline\Phi,
$$
using the [standard normal survival function](gaussian_test_pvalues.md). Each deterministic parameter has a score of mean $\theta$ and variance one; finite score families are jointly Gaussian, with residual dependence unrestricted.

For $\pi\in\mathcal P_1(\mathcal E)$, the candidate population count functions, rank and full fractional FDP are
$$
H_\pi(r)=\int_{\mathcal E}\mathbf1_{\{p(x)\le qr\}}\,\pi(dx),\qquad
V_\pi(r)=\int_{\mathcal E}\ell\mathbf1_{\{p(x)\le qr\}}\,\pi(dx)\quad(0<r\le1),
$$
$$
H_\pi(0)=V_\pi(0)=0,\qquad
\rho_\pi=\sup\bigl(\{0\}\cup\{r\in(0,1]:H_\pi(r)\ge r\}\bigr),
$$
$$
D_\pi=
\begin{cases}
V_\pi(\rho_\pi)/\rho_\pi,&\rho_\pi>0,\\
0,&\rho_\pi=0,
\end{cases}
\qquad F_\pi=\mathbb E D_\pi.
$$
All functions and the rank depend on the same Gaussian realization. This uses the globally largest non-strict crossing, in the convention of [ordinary BH](benjamini_hochberg_step_up.md), and a fractional denominator at every positive rank. Its well-definedness, measurability and finite-model approximation are assertions to prove, not assumptions of this definition. For a finite empirical parameter law with canonical labels, the relevant comparison is the original [false discovery rate](false_discovery_rate.md) of ordinary finite Gaussian BH.

For a fixed real $z$, define the conditional zero-mean marginal p-value distribution by
$$
F_z(t)=S\!\left(\frac{S^{-1}(t)-\sigma z}{\tau}\right)\quad(0<t<1),\qquad F_z(0)=0,\quad F_z(1)=1,
$$
where $S^{-1}$ is the decreasing inverse of $S$ on $(0,1)$. The notation $dF_z(t)$ denotes its Lebesgue-Stieltjes probability measure. This scalar distribution makes no conditional independence assertion about distinct residual evaluations $X(v)$.
