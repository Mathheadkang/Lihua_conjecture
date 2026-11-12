---
type: candidate
title: Shifted singular negatively correlated pair test of the pivotal identity
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
slot: 2
direction: small_cases
statement_digest: 10fd42aac96d6f560ddc31272941b5f90f8a40eb9cbddd044801e18b7016e6b1
performed_by: unknown
created_at: '2026-11-06T20:02:43.032Z'
extension_version: 0.0.4
---

## Object

Let $q=0.05$, $u=\overline\Phi^{-1}(q/2)$, $v=\overline\Phi^{-1}(q/4)$, $N=2$, $\theta=(0,2u)$, and
$$
\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix},\qquad T_1=X,\quad T_2=2u-X,\quad X\sim N(0,1).
$$
Only coordinate $1$ is a true null. The proposed contradiction uses maximal negative dependence and a nonzero alternative mean, which produce a genuinely nonconstant forced-zero rank.

## Checks

### H1

Pass: $N=2$, $0<q<1$, and $q<2\overline\Phi(1)$. Numerically $u=1.9599639845400534$, $v=2.2414027276049464$, so $u<v<3u$.

### H2

Pass: $\Sigma$ is symmetric with eigenvalues $0,2$ and unit diagonal. The specified affine Gaussian vector has exactly mean $\theta$ and covariance $\Sigma$, including its singularity.

### H3

Pass: $\theta_1=0$ and $\theta_2=2u>0$, so $I_0=\{1\}$. Both p-values are the prescribed two-sided normal p-values.

### H4

Pass: use ordinary BH at its maximum qualifying rank. For the focal null, $c_1=-1$ and $Y_1=T_2-2u+T_1=0$. Define $A=\{|X|\ge u\}$, $C=\{|X|\ge v\}$, and $B=\{|2u-X|\ge u\}$. The forced-zero rank equals $2$ on $B$ and $1$ on $B^c$, hence $\tau_1=q$ on $B$ and $q/2$ on $B^c$. Up to Gaussian-null endpoints,
$$
A\cap B=\{X\le-u\}\cup\{X\ge3u\},\qquad C\cap B^c=\{v\le X<3u\}.
$$

### NOT

Fail: writing $b=\overline\Phi(3u)$ gives
$$
\mathbb E\,a(T_1;\tau_1)=\frac{q/2+b}{q}+\frac{q/4-b}{q/2}=1-\frac bq,\qquad\Delta_1=-\frac bq.
$$
Directly, the true null is rejected at rank $2$ on $A\cap B$, with FDP $1/2$, and at rank $1$ on $C\cap B^c$, with FDP $1$. Consequently
$$
\mathrm{FDR}=\frac12(q/2+b)+(q/4-b)=\frac q2-\frac b2
=q\pi_0+\frac qN\Delta_1.
$$
Here $b\approx2.052671848974701\cdot10^{-9}$ and $\mathrm{FDR}\approx0.024999998973664075$. The exogenous threshold $\tau_1(0,0)=q$ has mean-one ratio. The branches have finitely many jumps within the claimed bound. Duplicating coordinates preserves the BH threshold and divides each null FDP contribution by the duplication count, so it also preserves each $\Delta_i$. No conclusion is violated.

## Failure

NOT fails: singular negative dependence and a shifted alternative yield a small negative pivotal excess, but the exact FDR identity still holds.
