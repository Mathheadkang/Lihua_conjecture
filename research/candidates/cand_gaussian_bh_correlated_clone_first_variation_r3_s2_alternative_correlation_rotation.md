---
type: candidate
title: Two-score alternative rotation with a nonzero correlation derivative
status: failed
target_asset: gaussian_bh_correlated_clone_first_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  H9: pass
  H10: pass
  NOT: fail
mode: refute
round: 3
slot: 2
direction: small_cases
statement_digest: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
performed_by: unknown
created_at: '2026-11-08T22:18:52.511Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $K=1$, $q=1/4$, $d=2$, $\theta=(1,0)$, $\Sigma=I_2$, $v_1=e_1$, $v_2=e_2$, and $G=(Z,Y)$ with independent standard normal coordinates. Perturb the alternative coordinate $i=1$ with $w_1=e_2$ and $c_1=0$. Thus
$$
T_1=1+Z,\qquad T_2=Y,\qquad
T_{11}^{\varepsilon}=1+\frac{Z+\varepsilon Y}{\sqrt{1+\varepsilon^2}},\qquad
T_{21}^{\varepsilon}=Y.
$$
The fixed null set is $I_0=\{2\}$. Set
$$
u_1=\overline\Phi^{-1}(1/8),\qquad
u_2=\overline\Phi^{-1}(1/4),\qquad a=u_2-1.
$$
Here $u_1>u_2>0$. This tests a change of dependence driven by a single rotation of an alternative, with a nonconstant mark $g(y)=y$. It is distinct from the board's constant-drift signed-cancellation test: its first derivative is nonzero. No signal is treated as always rejected, and all original ranks remain present.

## Checks

### H1

The required integer sizes hold: $N=2\ge1$ and $K=1\ge1$.

### H2

The level satisfies $q=1/4\in(0,1/2)$.

### H3

The mean vector $(1,0)$ is finite and real. The original covariance $I_2$ has unit diagonal and is positive definite, since $x^{\mathsf T}I_2x=\|x\|^2>0$ for nonzero $x$.

### H4

The representation is finite dimensional, $G\sim\mathcal N_2(0,I_2)$, and the rows $v_1=e_1$, $v_2=e_2$ have unit norm and Gram matrix $I_2$. It gives precisely the displayed original scores.

### H5

Use the required one-sided p-values $\overline\Phi(T_j)$. The prescribed labels are exactly $I_0=\{j:\theta_j\le0\}=\{2\}$, so the varied coordinate is an alternative.

### H6

The chosen index $i=1$ belongs to $[2]$. Its orthogonal space is $E_1=\operatorname{span}(e_2)$, identified with the real coordinate $y$. In this representation the prescribed decomposition is $Z=G_1$, $Y=G_2e_2$, with independent standard Gaussian laws on the two orthogonal axes.

### H7

The fixed mark $w_1=e_2$ lies in $E_1$, and $c_1=0$ is real. The restriction on nonpositive drifts at zero mean does not apply because $\theta_1=1$; the chosen drift also satisfies it anyway.

### H8

The perturbed mean is $\theta_1+\varepsilon c_1=1$ for every $\varepsilon\ge0$, so its sign is preserved. The other mean remains zero, and the expanded actual null set is precisely $I_0\times[1]$.

### H9

The displayed expanded scores have exactly the required normalized form. They are jointly Gaussian. The first score has variance $(1+\varepsilon^2)/(1+\varepsilon^2)=1$, and the second has variance one.

### H10

Use ordinary largest-rank BH with non-strict inequalities on the two displayed p-values, and the target's prescribed fixed-coordinate faces and signed jumps. The thresholds are exactly $u_1,u_2$ above. All expectations, face measures, and the minimum mark are those of the statement, with $g(y)=y$ and no replacement of their signs or their ranks.

### NOT

This check fails: all four conclusions hold for this object, and the exact derivative is nonzero but agrees with the claimed signed face formula.

For conclusions 1 and 3, $K=1$ makes copying the identity operation and makes the reduced vector identical to the expanded vector, pointwise for every $\varepsilon$. Thus exact-copy invariance holds, and the exceptional event is empty. For example, any $A,a,\varepsilon_0>0$ gives the asserted bound.

Compute the actual BH FDP as a function of the alternative score $X$ and the null score $Y$. The only two regions contributing to its expectation are
$$
f(X,Y)=1\quad\text{if }Y\ge u_1,\ X<u_2,
$$
$$
f(X,Y)=\frac12\quad\text{if }X\ge u_2,\ Y\ge u_2.
$$
It is zero elsewhere, up to boundary conventions which are irrelevant to these Gaussian expectations. These regions retain both possible positive largest BH ranks.

Crossing the face $X=u_1$ never changes FDP, since either both coordinates already qualify at rank two or the null is never rejected. Crossing $X=u_2$ gives the signed jump
$$
\Delta_{1,1}(y)=0,\qquad
\Delta_{1,2}(y)=\frac12\mathbf 1_{[u_2,u_1)}(y)
-\frac12\mathbf 1_{[u_1,\infty)}(y).
$$
The endpoint choices may alter a jump value on a Gaussian-null set only. Therefore the signed measures are
$$
\mu_{1,1}=0,\qquad d\mu_{1,2}(y)=\phi(a)\Delta_{1,2}(y)\phi(y)\,dy.
$$
This also proves conclusion 2: $|\Delta_{1,2}|\le1/2\le1$, so
$$
\int(1+|y|)\,|\mu_{1,2}|(dy)
\le\phi(a)\int(1+|y|)\phi(y)\,dy<\infty.
$$
The integral of $g(y)=y$ is absolutely integrable for the same reason.

For an independent calculation of the derivative, write
$$
\rho_\varepsilon=\frac{\varepsilon}{\sqrt{1+\varepsilon^2}},\qquad
Q_\rho(a,b)=\mathbb P\{U\ge a,V\ge b\},
$$
where $(U,V)$ is a standard bivariate Gaussian pair of correlation $\rho$. The exact FDP regions above give, for every finite $\varepsilon$,
$$
F_1(\varepsilon)=\overline\Phi(u_1)-Q_{\rho_\varepsilon}(a,u_1)
+\frac12Q_{\rho_\varepsilon}(a,u_2).
$$
In particular $F_1(0)=q/2=1/8$. Conditioning on $V$ yields
$$
Q_\rho(a,b)=\int_b^\infty
\overline\Phi\!\left(\frac{a-\rho y}{\sqrt{1-\rho^2}}\right)\phi(y)\,dy.
$$
At $\rho=0$, differentiating this expression gives
$$
\left.\frac{d}{d\rho}Q_\rho(a,b)\right|_{\rho=0}
=\phi(a)\int_b^\infty y\phi(y)\,dy
=\phi(a)\phi(b).
$$
This differentiation is justified directly: for $|\rho|\le1/2$, the derivative of the integrand is bounded in absolute value by $C_a(1+|y|)\phi(y)$, since the standard normal density is bounded and the derivative of $(a-\rho y)/\sqrt{1-\rho^2}$ is bounded by $C_a(1+|y|)$. This is integrable. Since $\rho'_0=1$, the actual right derivative is
$$
F_1'(0+)=\phi(a)\left[\frac12\phi(u_2)-\phi(u_1)\right].
$$
Meanwhile the target's formula gives exactly
$$
\sum_{r=1}^2\int y\,\mu_{1,r}(dy)
=\frac{\phi(a)}2\left[\int_{u_2}^{u_1}y\phi(y)\,dy
-\int_{u_1}^\infty y\phi(y)\,dy\right]
=\phi(a)\left[\frac12\phi(u_2)-\phi(u_1)\right].
$$
Numerically $u_1=1.1503493803760079$, $u_2=0.6744897501960817$, and both derivative calculations give approximately $-0.01776963035990776$. Thus the nonconstant mark and changed correlation produce no discrepancy.

## Failure

NOT fails: the exact two-score Gaussian correlation derivative equals the prescribed signed coordinate-face derivative, while the other three conclusions hold pointwise or by the displayed integrable bound.
