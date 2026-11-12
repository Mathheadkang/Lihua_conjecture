---
type: candidate
title: Single central null at the largest allowed testing level
status: failed
target_asset: gaussian_bh_signed_label_halfline_stein_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:27:14.931Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $\theta_1=0$, $\Sigma=(1)$, and $q=S(1)$, where $S=1-\Phi$ is standard normal survival. Thus $Z_1\sim N(0,1)$ and the fixed original null set is $I_0=\{1\}$.

## Checks

### H1

The model has finite positive integer dimension $N=1$.

### H2

The mean vector is real and the original null rule gives $I_0=\{1\}$ because $\theta_1=0\le0$.

### H3

The covariance $(1)$ is positive definite and has unit diagonal.

### H4

The level satisfies $0<q\le S(1)$ with equality. Consequently $U=u_1=1$.

### H5

Use the one-sided p-value $S(Z_1)$ and ordinary BH at level $q$. The auxiliary path retains the fixed original null label.

### NOT

The asserted conclusions do not fail. For every scalar score $z$, the only record edge is $0\to1$, its time is $\tau=z-1$, its coefficient is $c=1$, its trigger is $i=1$, and $a=z-\tau=1$. Thus the pathwise false-discovery proportion is exactly $\mathbf1\{z\ge1\}$. There are no score-order or record-contact interfaces. The remaining kink at $z=1$ in $G(z)=H_1(z,1)$ is continuous, so it creates no surface distribution in the first weak derivative.

Direct integration of the defining centered indicator gives
$$
H_1(z,1)=\begin{cases}-S(1)\Phi(z)/\phi(z),&z<1,\\-\Phi(1)S(z)/\phi(z),&z\ge1.\end{cases}
$$
Its two values agree at $z=1$, and direct differentiation gives the stated scalar Stein equation. The standard elementary estimates $S(x)/\phi(x)\le\sqrt{\pi/2}$ for $x\ge0$ and $\Phi(x)/\phi(x)\le\sqrt{\pi/2}$ for $x\le0$ give $|H_1|\le\sqrt{\pi/2}$. At the fixed threshold $a=1$, the displayed threshold derivative has magnitude at most one: for $z\le0$ bound it by $\phi(1)\sqrt{\pi/2}<1$; for $0<z<1$ use $\phi(1)/\phi(z)\le1$; for $z>1$ use $S(z)/\phi(z)\le1/z$. The scalar Stein equation also gives $|H_x|\le\sqrt{\pi/2}|z|+1$.

The covariance factor is $d_{11}=1-\Sigma_{11}=0$. Therefore both correction terms, including the below-threshold remainder, vanish identically. The exact identity reduces to
$$
\operatorname{FDR}=\Pr\{Z_1\ge1\}=S(1)=q=\mathbb E B_1,
\qquad B_1=b_1(1)=q.
$$
The baseline chain bound is an equality $0\le b_0/N=B_1=b_0/k_0=q/N$. The above-threshold entry bound and old-label bound hold with actual contributions zero, and the final consequence reads $q\le5q$. This object therefore cannot refute the lemma.

## Failure

NOT fails: the one-null model has zero covariance correction and satisfies the exact identity and every stated budget.
