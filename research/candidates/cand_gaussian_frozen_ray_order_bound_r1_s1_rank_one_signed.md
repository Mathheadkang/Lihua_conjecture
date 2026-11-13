---
type: candidate
title: >-
  Rank-one signed correlation (n=1, all-equal, antipodal, zero or deficient
  weights, c=2)
status: failed
target_asset: gaussian_frozen_ray_order_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 282dae85ea4644795f6594864fde635d6b47cfbb089d6aaaa5923db5d8b578ac
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T04:30:23.002Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

The degenerate boundary family of rank at most one. Take any $n\geq1$, signs $s_1,\ldots,s_n\in\{-1,+1\}$, one standard normal $\xi$, and $Z_i=s_i\xi$, so $\Sigma=ss^{\mathsf T}$ (rank one; $n=1$ gives $\Sigma=(1)$, all $s_i=+1$ gives the all-ones matrix, mixed signs give correlations $\pm1$). Weights: any $\omega_i\geq0$ with $\sum_i\omega_i=\beta\leq1$, including the endpoint $\omega\equiv0$ ($\beta=0$) and $\beta=1$. The level $c\geq2$ is arbitrary, including the endpoint $c=2$.

The same computation is recorded for arbitrary $\Sigma$ with few effective hypotheses (see NOT), since it rules out the whole small-$n$ boundary.

## Checks

### H1

$n\geq1$ is an integer.

### H2

$\Sigma=ss^{\mathsf T}$ is symmetric, $x^{\mathsf T}\Sigma x=(s^{\mathsf T}x)^2\geq0$, and $\Sigma_{ii}=s_i^2=1$. Singular for $n\geq2$, which is allowed; $Z=s\xi\sim\mathcal N_n(0,\Sigma)$.

### H3

$\omega_i\geq0$, $\sum\omega_i\leq1$ by choice.

### H4

$c\geq2$ real.

### NOT

Fails: the conclusion holds with an explicit constant.

Key one-variable fact: for real $z$, $\sup_{w\geq0}\exp(wz-w^2/2)=\exp(z_+^2/2)$. Hence for every $\Sigma$ and weights,
$$
\Lambda(Z)\leq\sum_i\omega_iX_i,\qquad X_i=\exp\big((Z_i)_+^2/2\big).
$$
Each $X_i$ has the law of $X=\exp(\xi_+^2/2)$: $P(X>s)=1$ for $s<1$, and for $s\geq1$, by Mills' ratio $P(\xi>x)\leq e^{-x^2/2}/(x\sqrt{2\pi})$ with $x=\sqrt{2\log s}$,
$$
P(X>s)\leq\frac1{s\sqrt{4\pi\log s}}.
$$
So for $M\geq1$, $\int_0^MP(X>s)\,ds\leq1+\int_1^M\frac{ds}{s\sqrt{4\pi\log s}}=1+\sqrt{\log M/\pi}$.

Rank-one case: $\Lambda\leq\beta_+e^{\xi_+^2/2}+\beta_-e^{\xi_-^2/2}\leq\max(e^{\xi_+^2/2},e^{\xi_-^2/2})$ where $\beta_\pm$ are the weight masses of the two sign classes ($\beta_++\beta_-\leq1$). Using $\min\{c,\max(a,b)\}\leq\min\{c,a\}+\min\{c,b\}$,
$$
\mathbb E\min\{c,\Lambda\}\leq2\Big(1+\sqrt{\log c/\pi}\Big)\leq\Big(\tfrac{2}{\sqrt{\log2}}+\tfrac2{\sqrt\pi}\Big)\sqrt{\log c}\approx3.53\sqrt{\log c}.
$$
For $\omega\equiv0$, $\Lambda\equiv0$. For $c=2$ the left side is at most $2\leq2.41\sqrt{\log 2}$ trivially, for every object. Sharpness: for $n=1$, $\omega_1=1$, $\mathbb E\min\{c,\Lambda\}\geq\int_1^cP(\xi>\sqrt{2\log t})\,dt\sim\sqrt{\log c/\pi}$, so the order $\sqrt{\log c}$ is attained but not exceeded; $C_{\mathrm{FR}}\geq\pi^{-1/2}$ is forced asymptotically, nothing more.

General small-$n$ bound (any $\Sigma$): with $\min\{c,\sum y_i\}\leq\sum\min\{c,y_i\}$ and $\mathbb E\min\{c,\omega X\}=\omega\int_0^{c/\omega}P(X>s)ds$,
$$
\mathbb E\min\{c,\Lambda\}\leq\sum_i\omega_i\Big(1+\sqrt{\log(c/\omega_i)/\pi}\Big)\leq1+\pi^{-1/2}\Big(\sqrt{\log c}+\sum_i\omega_i\sqrt{\log(1/\omega_i)}\Big)\leq1+\pi^{-1/2}\Big(\sqrt{\log c}+\sqrt{\log n+1/e}\Big),
$$
the last step by Cauchy-Schwarz and $\sum_i\omega_i\log(1/\omega_i)\leq\beta\log(n/\beta)\leq\log n+1/e$. So the conclusion holds with a universal constant whenever $\sum_i\omega_i\sqrt{\log(1/\omega_i)}\leq K\sqrt{\log c}$, in particular whenever $n\leq c^{K^2}$, whatever $\Sigma$ is.

## Failure

NOT fails: $\Lambda\leq\sum_i\omega_ie^{(Z_i)_+^2/2}$ and the weak-$L^1$ tail $1/(s\sqrt{4\pi\log s})$ give $\mathbb E\min\{c,\Lambda\}\leq2(1+\sqrt{\log c/\pi})$ for rank one, and $\leq1+\pi^{-1/2}(\sqrt{\log c}+\sqrt{\log n+1/e})$ for any $\Sigma$, so a counterexample needs weight entropy $\gg\log c$ (super-polynomially many hypotheses in $c$).
