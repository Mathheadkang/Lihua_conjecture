---
type: candidate
title: Deep negative null at an extremely small Gaussian BH level
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
slot: 5
direction: extremal
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:27:14.931Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $\theta_1=-10$, $\Sigma=(1)$, $q=S(10)$, and $Z_1=-10+X$ for $X\sim N(0,1)$. Thus $U=u_1=10$, and the original true-null set is $I_0=\{1\}$. The extremal feature is a very conservative negative null combined with an extremely small level; the same calculation applies with $10$ replaced by any fixed $M\ge1$.

## Checks

### H1

$N=1$ is a finite positive integer.

### H2

The mean $\theta_1=-10$ is an admissible real mean and satisfies the true-null condition $\theta_1\le0$.

### H3

$\Sigma=(1)$ is positive definite and has unit diagonal, and the stated law of $Z_1$ is exactly Gaussian with that mean and covariance.

### H4

$q=S(10)>0$ and $S(10)\le S(1)$ because $S$ is decreasing. The quantile definitions give $U=u_1=10$.

### H5

The p-value is $S(Z_1)$ and ordinary one-test BH rejects exactly when $Z_1\ge10$. The translation chain has the single edge $0\to1$, trigger $i_e=1$, record time $\tau_e=Z_1-10$, coefficient $c_{1e}=1$, threshold $a_{1e}=10$, and $d_{11}=1-\Sigma_{11}=0$. The original label is fixed along this path.

### NOT

The conclusion does not fail. The pathwise identity is simply $\mathbf1\{Z_1\ge10\}=\mathbf1\{\tau_e\ge0\}$. Moreover,
$$
\operatorname{FDR}=\mathbb P(X\ge20)=S(20)=B_1,
\qquad 0<B_1=S(20)\le S(10)=q.
$$
Both correction terms and $D_<$ vanish because $d_{11}=0$, so (SF), (B), and the final displayed inequality all hold. There are no old-label terms or record or ordering interfaces. The sole potential is $G_1(z)=H_1(z,10)$, whose two explicit branches are continuous at $z=10$. For the bound on its magnitude, each branch is bounded by $\Phi(X)S(X)/\phi(X)\le\sqrt{\pi/2}$, using the elementary half-line integral formula for the Gaussian Mills ratio and reflection. Its derivative away from that threshold satisfies $H_{1,x}=XH_1+\mathbf1\{z\ge10\}-S(20)$, and hence grows at most linearly in $|X|$. These bounds imply local Lipschitz continuity across the single threshold and absolute Gaussian integrability. Finally, $A=20$; below threshold the explicit formula gives $|H_{1,a}|\le1$ by splitting $X\le0$ and $0<X<20$, and above threshold the Mills bound gives $|H_{1,a}|=\phi(20)S(X)/\phi(X)\le\phi(20)/X<1$. Thus the remaining regularity assertions also hold for this object.

## Failure

NOT fails: the extremely small level and deeply negative null preserve the identity exactly, with every correction term zero.
