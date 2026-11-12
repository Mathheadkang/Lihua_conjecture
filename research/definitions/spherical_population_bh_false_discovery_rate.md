---
type: definition
title: >-
  Definition (largest spherical population BH threshold and false discovery
  rate)
status: approved
source:
  kind: original
depends_on:
  - spherical_isotropic_directional_population
tags:
  - gaussian_bh
  - spherical_population
  - first_contact
---

## Definition

Use the [isotropic spherical directional population](spherical_isotropic_directional_population.md), with dimension $d$, absolute-mean law $W$, null mass $\pi_0$, Gaussian survival function $Q$, spherical tails $H_r$, total rejection masses $F_r$, and random radius $R$. Fix a level $q\in(0,1)$ and put $u=Q^{-1}(q/2)$, where $Q^{-1}$ is the inverse of the strictly decreasing function $Q:\mathbb R\to(0,1)$.

For $r>0$ let the set of finite admissible Gaussian-statistic cutoffs be
$$
\mathcal C_r=\{x\in[u,\infty):F_r(x)\geq2Q(x)/q\}.
$$
If $\mathcal C_r$ is nonempty, define $x_r=\min\mathcal C_r$ and $t_r=2Q(x_r)$. The largest population BH p-value threshold is $t_r$, hence it corresponds to the smallest finite Gaussian-statistic cutoff $x_r$. Each $H_r$ is continuous for $r>0$, and dominated convergence makes $F_r$ continuous even when $W$ has atoms or unbounded support. Thus the minimum exists and satisfies the contact identity
$$
F_r(x_r)=2Q(x_r)/q.
$$
At the endpoint $x_r=u$, this identity follows from $F_r(u)\leq1=2Q(u)/q$. If $\mathcal C_r$ is empty, there is no finite contact and the population procedure makes no rejections; write $x_r=\infty$ and $t_r=0$ in that case.

At a finite contact the false-rejection mass is $2\pi_0H_r(x_r)$. Define the population false discovery proportion by
$$
\operatorname{FDP}_{\mathrm{pop}}(r;q,W,d)=
\begin{cases}
q\pi_0 H_r(x_r)/Q(x_r),&\mathcal C_r\ne\varnothing,\\
0,&\mathcal C_r=\varnothing.
\end{cases}
$$
The finite-contact expression equals $2\pi_0H_r(x_r)/F_r(x_r)$ by the contact identity. Set $\operatorname{FDP}_{\mathrm{pop}}(0;q,W,d)=0$ on the sampling event $R=0$, which has probability zero. The population false discovery rate is
$$
\operatorname{FDR}_{\mathrm{pop}}(q;W,d)
=\mathbb E_Z[\operatorname{FDP}_{\mathrm{pop}}(R;q,W,d)].
$$
The expectation is over the shared factor $Z$; population indices are integrated against $W\otimes\sigma_{d-1}$. These are population mass ratios rather than the finite counting ratios used for ordinary finite-vector BH.
