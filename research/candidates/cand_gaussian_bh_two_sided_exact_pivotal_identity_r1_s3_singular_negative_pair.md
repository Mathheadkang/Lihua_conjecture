---
type: candidate
title: Singular negatively correlated pair with a shifted alternative
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
slot: 3
direction: drop_hypothesis
statement_digest: 10fd42aac96d6f560ddc31272941b5f90f8a40eb9cbddd044801e18b7016e6b1
performed_by: unknown
created_at: '2026-11-06T20:02:43.032Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $q=1/10$, $u=\overline\Phi^{-1}(q/2)$,
$v=\overline\Phi^{-1}(q/4)$, and $Z\sim N(0,1)$.
Set $T_1=Z$, $T_2=2u-Z$, so
$\theta=(0,2u)$ and $\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$.
Use two-sided p-values and ordinary largest-qualifying-rank BH.
This puts Gaussianity, singular covariance, negative correlation and the
true-null mean at their allowed boundaries. The proposed mechanism was
that the alternative's reversed loading makes the forced-zero threshold
depend strongly on the null, potentially invalidating the decomposition.

## Checks

### H1

$N=2$ is a finite positive integer and $\theta\in\mathbb R^2$.

### H2

$T=\theta+(1,-1)^{\mathsf T}Z$ is jointly Gaussian, including its degenerate
directions. The covariance is symmetric, has unit diagonal, and has
eigenvalues $0,2$, hence is PSD and admissible.

### H3

$q=1/10\in(0,1)$, and it also satisfies the source fixed-notation small-level
restriction with $q_0=1/10<2\overline\Phi(1)$. The specified p-values are
$p_1=2\overline\Phi(|Z|)$ and $p_2=2\overline\Phi(|2u-Z|)$.

### H4

Exactly coordinate 1 is a true two-sided null: $I_0=\{1\}$ and $\pi_0=1/2$.
For that coordinate $c_1=-1$ and
$Y_1=T_2-\theta_2-c_1T_1=0$ identically.

### NOT

The proposed violation fails. Write $b=\overline\Phi(3u)>0$.
Since $u<v<3u$, forcing coordinate 1 to zero gives rank 2 on
$\{Z\le u\}\cup\{Z\ge3u\}$ and rank 1 on $\{u<Z<3u\}$.
The null's contribution to the actual FDP is $1/2$ on
$\{Z\le-u\}\cup\{Z\ge3u\}$, is 1 on $\{v\le Z<3u\}$,
and is zero elsewhere, apart from endpoints of Gaussian probability zero.
Therefore

$$
\operatorname{FDR}=\frac12(\overline\Phi(u)+b)
   +\overline\Phi(v)-b=\frac q2-\frac b2.
$$

The forced-zero threshold equals $q$ in the rank-2 region and $q/2$ in
the rank-1 region. Thus the defined pivotal expectation is

$$
1+\Delta_1=\frac{\overline\Phi(u)+b}{q}
  +\frac{\overline\Phi(v)-b}{q/2}=1-\frac bq.
$$

Consequently $q\pi_0+(q/N)\Delta_1=q/2-b/2=\operatorname{FDR}$ exactly.
Numerically $u\simeq1.64485362695$, $v\simeq1.95996398454$,
$b\simeq4.016\times10^{-7}$, so the correction is small but nonzero.
The singular negatively correlated mechanism does not violate the identity.

## Failure

NOT fails: exact Gaussian tail integration gives the same FDR and pivotal decomposition, including the nonzero negative pivotal correction.
