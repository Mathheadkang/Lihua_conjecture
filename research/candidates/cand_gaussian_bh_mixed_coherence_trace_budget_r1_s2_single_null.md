---
type: candidate
title: Single null test has exactly unit coherence and zero trace
status: failed
target_asset: gaussian_bh_mixed_coherence_trace_budget
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
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T09:57:49.237Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$, take $N=d=1$, $v_1=1$, and arbitrary $\theta_1=\theta\le0$. Write $U=\overline\Phi^{-1}(q)$, $H=h(U)$, and $c=U-\theta$. This is a family in $q$ and $\theta$, rather than a single numerical test.

## Checks

### H1

The dimensions $N=d=1$ are positive finite integers and the sole mean is real.

### H2

The vector has unit length. Its Gram covariance is the admissible matrix $(1)$, and $T_1=\theta+G$ has precisely the required jointly Gaussian law.

### H3

The level lies in $(0,\overline\Phi(3)]$, so $U\ge3$. All quantities use the target's one-sided p-values and Mills ratio.

### H4

The sole index is a true null. Ordinary BH has $R=V=1$ on $\{z\ge c\}$ and $R=V=0$ elsewhere. Thus $f=\mathbf1_{[c,\infty)}$ and $B=f/H$, with all threshold multiplicities and non-strict conventions respected.

### H5

$F=\overline\Phi(c)>0$. Use exactly the target's terminal and path tilts and heat fields. Then

$$
D=\log(1/F),\qquad a(t,z)=1/H,\qquad K(t,z)=0,\qquad x=1.
$$

In particular $\beta=\nabla\log P_{1-t}f$ is the drift of Brownian motion conditioned on $W_1\ge c$. The heat-entropy identity gives $\mathbb E_{\mathbb Q}\int_0^1\beta_t^2dt=2\log(1/F)<\infty$; it follows directly by applying Ito to $\log P_{1-t}f(W_t)$ up to localized times and taking its terminal entropy limit. Hence the absolute mixed drift integral is finite by Cauchy--Schwarz. Also $\mathbb E_{\mathbb Q}\int_0^1\beta_tdt=\mathbb E_QW_1=h(c)$. Therefore

$$
\int z B(z)\,d\gamma_1(z)=\frac{\phi(c)}H
=\frac{Fh(c)}H
=F\mathbb E_{\mathbb Q}\int_0^1a_t\beta_tdt.
$$

All asserted endpoint and trace identities are well posed and give $M_*=M=0$.

### NOT

Fail. For this whole family, $M_+=0$ and $1-x=0$, so the proposed bound is the equality $0\le0$ for every positive $C$. Negative null means, including means depending on $q$, do not change this conclusion.

## Failure

NOT fails: a single null produces a constant posterior Mills field, exactly unit coherence, and identically zero Jacobian trace.
