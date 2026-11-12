---
type: candidate
title: Scalar zero-mean boundary with zero-dimensional face
status: failed
target_asset: gaussian_bh_rare_clone_mills_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
performed_by: unknown
created_at: '2026-11-08T23:56:28.396Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $q=S(1)$, $\theta_1=0$, $\Sigma=(1)$, $d=1$, $v_1=1$, $G\sim N(0,1)$, and $i=1$. Thus $U=u_1=1$, $\ell_1=1$, $E_1=\{0\}$ and $L=h(1)-1$. Use exactly the offset law and midpoint clones of the target, for $0<\varepsilon<\min\{1/(2L),1/2\}$. This tests the smallest dimension, equality in the null-mean boundary, a zero-dimensional Gaussian face, and endpoint rank one.

## Checks

### H1

The original dimension is the fixed positive integer $N=1$.

### H2

$q=S(1)\in(0,1/2)$ is fixed.

### H3

The mean vector $\theta=(0)$ is finite and permitted, including its boundary null label.

### H4

$\Sigma=(1)$ is positive definite with unit diagonal.

### H5

The finite representation $T_1=G$ has unit row $v_1=1$ and the required covariance.

### H6

The chosen index $i=1$ lies in $[N]$.

### H7

Mills' strict inequality $S(1)<\phi(1)$ gives $0<L<\infty$. The stated range of $\varepsilon$ implies $\varepsilon L<1$. There is no positive-mean restriction because $\theta_1=0$.

### NOT

Fail: the conclusions hold in this object, as the following direct scalar calculation shows.

First, differentiation of $\phi(v)/v$ gives
$$
\int_1^\infty\phi(v)/v^2\,dv=\phi(1)-q=qL.
$$
Consequently the offset law has zero atom $1-\varepsilon L$ and continuous mass $\varepsilon L$ on $(0,\varepsilon)$. The mapping $v\mapsto\varepsilon(1-1/v)$ is strictly increasing on $[1,\infty)$; its endpoint $\varepsilon$ is unattained and $v=1$ has zero integration mass. The quantile is zero at $1-\varepsilon L$, continuous thereafter, and all midpoint offsets lie in $[0,\varepsilon)$. Every clone is $G-d_b$ and is an actual true null with unit variance. At zero offset its FDP is $\mathbf1_{\{G\ge1\}}$, giving $F=q$ for every $K$.

For any fixed $\varepsilon$ put
$$
t_{K,\varepsilon}=\min_{1\le b\le K}\left\{S^{-1}(qb/K)+Q_\varepsilon((b-1/2)/K)\right\}.
$$
All clones are null, so exact finite BH gives $F_{K,\varepsilon}=S(t_{K,\varepsilon})$. Extend $Q_\varepsilon$ continuously to $[0,1]$ by $Q_\varepsilon(0)=0$ and $Q_\varepsilon(1)=\varepsilon$. Its uniform continuity and divergence of $S^{-1}(qx)$ as $x\downarrow0$ show
$$
t_{K,\varepsilon}\longrightarrow t_\varepsilon
=\inf_{0<x\le1}\{S^{-1}(qx)+Q_\varepsilon(x)\}.
$$
This is the actual common-crossing onset: $H_\varepsilon(x;t)\ge x$ is equivalent to $t\ge S^{-1}(qx)+Q_\varepsilon(x)$ for $0<x<1$, with the endpoint obtained by the continuous extension. Any endpoint equality exceptional to this characterization has zero probability under $G$. Whenever the supremum crossing $\rho$ is positive, monotonicity gives $H(\rho)\ge\rho$ by taking qualifying points from below; right continuity excludes $H(\rho)>\rho$ when $\rho<1$, while $H(1)\le1$ handles $\rho=1$. Hence $V(\rho)/\rho=1$ on the crossing event, even for $\rho<1$, and the claimed population expectation equals $S(t_\varepsilon)$.

To calculate its derivative define
$$
z(v)=q^{-1}\{\phi(v)/v-S(v)\},\qquad v\ge1.
$$
The continuous branch satisfies $P_\varepsilon([0,\varepsilon(1-1/v)])=1-\varepsilon z(v)$. Thus
$$
t_\varepsilon=\inf_{v\ge1}\{S^{-1}(q(1-\varepsilon z(v)))+\varepsilon(1-1/v)\},
$$
where the endpoint $v=\infty$ can be included by continuity; the zero-atom branch is minimized at $v=1$. Since $0\le z(v)\le L$, Taylor expansion is uniform in $v$ and gives
$$
t_\varepsilon=1+\varepsilon\inf_{v\ge1}\{m(1)z(v)+1-1/v\}+O(\varepsilon^2).
$$
The derivative of the minimized expression is
$$
\frac{1-m(1)\phi(v)/q}{v^2}
=\frac{1-\phi(v)/\phi(1)}{v^2}\ge0.
$$
Its minimum is at $v=1$ and equals $m(1)L=1-m(1)$. It follows that
$$
\lim_{\varepsilon\downarrow0}\frac{\lim_KF_{K,\varepsilon}-q}{\varepsilon}
=-\phi(1)\{1-m(1)\}.
$$
The original scalar face jump is $\Delta_{1,1}(0)=1$, so $\mu_{1,1}(E_1)=\phi(1)$, exactly the target coefficient.

Finally, the original parameter measure is one atom. Its continuous perturbed TV distance is exactly $\varepsilon L$; the discrete perturbed TV distance is the nonzero midpoint fraction, at most $\varepsilon L+1/K$. Coupling each shifted atom to its original location costs at most $\varepsilon$ per nonzero atom, giving both stated $W_1$ bounds. Thus neither label preservation nor the population fractional denominator nor the iterated derivative nor the comparison costs fail in this boundary object.

## Failure

NOT fails: the scalar zero-mean boundary satisfies all four conclusions, with iterated derivative $-\phi(1)\{1-m(1)\}$.
