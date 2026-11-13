---
type: candidate
title: >-
  Rank-one sign-pattern covariance (all correlations plus or minus one),
  including the all-equal equality case
status: failed
target_asset: gaussian_simes_dense_crossing_tilt_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 6e714bc6bdb2353b928e977aa5b3c27aa068b24a6df42caf55510b6b8e0b24c8
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:14:45.821Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Fix any $N\ge1$, any sign vector $\varepsilon\in\{\pm1\}^N$ with $m=\#\{i:\varepsilon_i=+1\}$, and put $\Sigma=\varepsilon\varepsilon^{\mathsf T}$ (rank one). Realize $T_i=\varepsilon_iZ$ with $Z\sim\mathcal N(0,1)$. Any $q\in(0,1/4]$ and any $\delta\in(0,1]$. The family is meant to be run along $q\to0$ with $N$, $m$, $\delta$ arbitrary (possibly depending on $q$). The sub-case $\varepsilon=(1,\dots,1)$ (all p-values equal) is the equality case.

Since the constants $C_D,q_D$ are existential, a refutation needs a family with $q\to0$ along which $\mathbb P(D_{q,\delta})/q$ is unbounded; this is what `NOT` tests.

## Checks

### H1
$N$ is a positive integer. Pass.

### H2
$\Sigma=\varepsilon\varepsilon^{\mathsf T}$ is symmetric, $x^{\mathsf T}\Sigma x=(\varepsilon^{\mathsf T}x)^2\ge0$, and $\Sigma_{ii}=\varepsilon_i^2=1$; singular matrices are admitted. Pass.

### H3
$T=\varepsilon Z$ is centered Gaussian with covariance $\varepsilon\varepsilon^{\mathsf T}$; $p_i=\overline\Phi(T_i)$. Pass.

### H4
$\delta\in(0,1]$ by choice. Pass.

### H5
$q\in(0,q_D]$ is allowed for any $q_D$ by taking $q$ small. Pass.

### NOT
For $t\le q<1/2$ put $v=\overline\Phi^{-1}(t)>0$. Then $p_i\le t$ iff $\varepsilon_iZ\ge v$, so
$$
\#\{i:p_i\le t\}=m\,\mathbf 1\{Z\ge v\}+(N-m)\,\mathbf 1\{Z\le -v\},
$$
and at most one of the two terms is nonzero. On $D_{q,\delta}$ pick a witness $k$ (with $qk/N\le q$). Either $Z\ge \overline\Phi^{-1}(qk/N)$ and $m\ge k$, whence $\overline\Phi(Z)\le qk/N\le qm/N$; or $Z\le-\overline\Phi^{-1}(qk/N)$ and $N-m\ge k$, whence $\Phi(Z)\le q(N-m)/N$. Hence
$$
\mathbb P(D_{q,\delta})\le \frac{qm}{N}+\frac{q(N-m)}{N}=q .
$$
Equality case: for $\varepsilon=(1,\dots,1)$, $k=N$ is always admissible ($q\ge\overline\Phi(u_q+\delta)$), and $D_{q,\delta}=\{Z\ge u_q\}$, so $\mathbb P(D_{q,\delta})=q$ exactly. The ratio is at most $1$ uniformly, so the conclusion holds with any $C_D\ge1$. Fail.

## Failure

NOT fails: with all correlations $\pm1$ the count jumps only between $0$, $m$, $N-m$, and the dense event is contained in two one-dimensional tails of total mass $q$ (equality for the all-equal pattern).
