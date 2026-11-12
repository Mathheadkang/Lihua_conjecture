---
type: candidate
title: Singular identical nulls with threshold equality
status: failed
target_asset: gaussian_bh_two_sided_exact_pivotal_identity
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
statement_digest: 10fd42aac96d6f560ddc31272941b5f90f8a40eb9cbddd044801e18b7016e6b1
performed_by: unknown
created_at: '2026-11-06T20:02:43.032Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $q=1/4$, $\theta=(0,0)$ and $\Sigma=\begin{pmatrix}1&1\\1&1\end{pmatrix}$. Let $Z\sim N(0,1)$ and $T=(Z,Z)$. Both two-sided p-values equal $P=2\overline\Phi(|Z|)$, a uniform random variable. Test the extreme singular covariance, identical p-values, zero-rejection region and equality $P=q$.

## Checks

### H1

$N=2$ is finite and positive, and $q=1/4\in(0,1)$. It also obeys the fixed-notation small-q range because $1/4<2\overline\Phi(1)$.

### H2

$\theta\in\mathbb R^2$. The symmetric matrix $\Sigma$ has unit diagonal and eigenvalues $0,2$, hence is PSD and singular. The specified vector is jointly Gaussian with this covariance.

### H3

The p-values are exactly the two-sided Gaussian p-values, with ordinary largest-qualifying-rank BH at $q=1/4$.

### H4

For either chosen coordinate $i$, $\theta_i=0$, so $i\in I_0^{(2)}$. Both are true nulls and $\pi_0=1$.

### NOT

The original rank is $R=2\mathbf1\{P\le q\}$. For either $i$, $c_i=1$ and the regression residual is identically $Y_i=0$, independent of $T_i$. The forced-zero rank is
$$
\rho_i(x,0)=\begin{cases}2,&2\overline\Phi(|x|)\le q,\\1,&2\overline\Phi(|x|)>q.\end{cases}
$$
Thus $\tau_i(x,0)=q$ on the first region and $q/2$ on the second. On the second region $P>q>q/2$, so the numerator of $a$ vanishes. Consequently
$$
a(T_i;\tau_i(T_i,0))=q^{-1}\mathbf1\{P\le q\},\qquad \mathbb Ea=1,\qquad\Delta_i=0.
$$
At the equality $P=q$, ordinary BH uses its non-strict comparison and both sides of the pointwise identity equal $1/2$; on $P>q$ both vanish. The exogenous baseline $\tau_i(0,0)=q/2$ also has mean-one $a$. Both branches have $\Psi=\int_{p(s)\le q}2\phi(s)\,ds/q=1$. Hence $\operatorname{FDR}=q=q\pi_0+(q/N)\sum_i\Delta_i$, with $\Delta_i\ge-1$ and the sum of null rejection contributions equal to $q\le1$. Repeating all identical coordinates $M$ times gives rank $2M$ on $\{P\le q\}$ and zero otherwise, with the same threshold, FDP and per-null mean-one value. No stated conclusion fails.

## Failure

NOT fails: perfect correlation and singularity preserve the forced-zero, baseline and FDR identities, including the threshold equality and zero-rejection cases.
