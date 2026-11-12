---
type: candidate
title: Negative-correlation two-null BH model retains the Mills variation
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
round: 2
slot: 1
direction: known_counterexamples
statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
performed_by: unknown
created_at: '2026-11-09T00:05:18.154Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $q=S(1)$, $\theta=(0,0)$, and
$$
\Sigma=\begin{pmatrix}1&-9/10\\-9/10&1\end{pmatrix}.
$$
Use $G\sim N_2(0,I_2)$, $v_1=(1,0)$, $v_2=(-9/10,\sqrt{19}/10)$, and chosen coordinate $i=1$. Both original labels are one. Use precisely the offset law and midpoint quantiles in the definition, without changing their dependence on $\varepsilon$ or the order of limits. This tests negative dependence in an all-null BH rejection event, rather than repeating the scalar boundary family. No literature assertion about a counterexample is assumed.

Write $U=1$, $u_1=S^{-1}(q/2)$, $u_2=1$, $m=S/\phi$, and $L=2\{h(1)-1\}$. All assertions below concern $0<\varepsilon<1/L$, made smaller when an asymptotic statement requires it.

## Checks

### H1

$N=2$ is a positive finite integer.

### H2

$q=S(1)\simeq0.1586552539$ belongs to $(0,1/2)$.

### H3

Both means are the finite real number zero, explicitly allowed by the target.

### H4

$\Sigma$ has unit diagonal and eigenvalues $1/10$ and $19/10$, so the original covariance is positive definite.

### H5

The displayed two directions have unit norm and dot product $-9/10$. Thus the specified finite Gaussian representation has exactly the required covariance.

### H6

The chosen coordinate $i=1$ is valid and both original true-null labels are $\mathbf1_{\{0\le0\}}=1$. Every clone mean is zero or a nonpositive number, so all actual clone labels are also one.

### H7

For $0<\varepsilon<1/L$ the required smallness inequality holds. The additional condition for a positive chosen mean is inapplicable. The following normalization calculation proves $0<L<\infty$, so this interval is nonempty.

### NOT

This object does not violate the conclusions. Here are the normalization, actual population limit, derivative, and cost checks.

Integration of $(\phi(v)/v)'=-\phi(v)-\phi(v)/v^2$ gives
$$
\int_1^\infty\frac{\phi(v)}{v^2}\,dv=\phi(1)-S(1)>0.
$$
Consequently $L=2\{\phi(1)/q-1\}$ is positive and finite and the continuous part of $P_\varepsilon$ has mass $\varepsilon L$. Its map $a=\varepsilon(1-1/v)$ sends $[1,\infty)$ continuously and strictly increasingly onto $[0,\varepsilon)$; the integral gives no atoms, including at either endpoint. Together with the atom $1-\varepsilon L$ at zero, these facts prove the claimed support and normalization. The left inverse is zero at $p=1-\varepsilon L$ and all midpoint quantiles lie in $[0,\varepsilon)$. The finite clone array is an affine function of $G$ with the displayed unit directions, so it is jointly Gaussian with unit marginal variances. At zero offset, each original p-value is repeated $K$ times and the largest qualifying rank is multiplied by $K$; the rejection event and all-null FDP are unchanged.

For the actual finite-copy limit, extend $Q_\varepsilon$ continuously by $Q_\varepsilon(0)=0$ and $Q_\varepsilon(1)=\varepsilon$. This extension is continuous on $[0,1]$, including the transition from its zero plateau to the continuous part. Put $u(x)=S^{-1}(qx/2)$ and
$$
A_\varepsilon=\inf_{0<x\le1}\{u(x)+Q_\varepsilon(x)\}.
$$
If $t_2<1$, the background group is never eligible at any rank in $(0,2]$, and the population rejection event is precisely $t_1\ge A_\varepsilon$. If $1\le t_2<u_1$, put $x_2=2S(t_2)/q\in(1,2]$ and
$$
B_\varepsilon(t_2)=\min_{x_2\le x\le2}\{u(x)+Q_\varepsilon(x-1)\}.
$$
The population rejection event is $t_1\ge\min\{A_\varepsilon,B_\varepsilon(t_2)\}$. If $t_2\ge u_1$, the background alone gives a crossing at rank one, regardless of $t_1$. These are tests for one common crossing: the background count is exactly zero before $x_2$ and exactly one thereafter.

These thresholds are also the limits of the finite BH thresholds. For $t_2<1$, the finite threshold is
$$
\min_{1\le k\le K}\{u(k/K)+Q_\varepsilon((k-1/2)/K)\}.
$$
For $1\le t_2<u_1$, the background-assisted threshold is the minimum over integers $\lceil Kx_2\rceil\le k\le2K$ of
$$
u(k/K)+Q_\varepsilon((k-K-1/2)/K).
$$
Uniform continuity of the extended quantile and density of these grids give the asserted limits. The first minimum can be restricted away from zero because $u(x)\to\infty$ there and $Q_\varepsilon\ge0$. Conditional on $T_2$, $T_1$ has positive variance $19/100$, so equality to any displayed threshold has probability zero. Bounded convergence therefore proves finite-copy convergence of the rejection probability, which is the FDR because all labels are one.

For completeness, whenever the population largest crossing $\rho$ is positive, monotonicity of $H_\varepsilon$ ensures $H_\varepsilon(\rho)\ge\rho$ by approaching its supremum from below. If $\rho<2$ and this inequality were strict, monotonicity would give another qualifying crossing immediately to its right. At $\rho=2$, the bound $H_\varepsilon\le2$ gives equality directly. Thus $H_\varepsilon(\rho)=\rho$, and $V_\varepsilon=H_\varepsilon$ makes the stated fractional population FDP exactly the indicator of a positive crossing, including at endpoint two.

To compute the right derivative, set
$$
z(v)=\frac2q\{\phi(v)/v-S(v)\},\qquad a(v)=1-1/v\quad(v\ge1).
$$
The continuous quantile graph is
$$
Q_\varepsilon(1-\varepsilon z(v))=\varepsilon a(v),
$$
with its endpoint interpreted by continuity. The zero-quantile plateau contributes its largest rank at $v=1$. Hence, for $r=1,2$, define
$$
D_{r,\varepsilon}=\inf_{v\ge1}\{u(r-\varepsilon z(v))+\varepsilon a(v)\}.
$$
Then $A_\varepsilon=D_{1,\varepsilon}$, and $D_{2,\varepsilon}$ is the unrestricted background-assisted threshold. Taylor expansion is uniform over $v\ge1$, because $0\le z(v)\le L$ and $r\ge1$. With $A_r=1/(r h(u_r))$,
$$
D_{r,\varepsilon}=u_r+\varepsilon\inf_{v\ge1}\{A_r z(v)+1-1/v\}+O(\varepsilon^2).
$$
The derivative of the function inside this infimum is
$$
\frac{1-\phi(v)/\phi(u_r)}{v^2}.
$$
It has its minimum at $v=u_r$, giving exactly
$$
D_{r,\varepsilon}=u_r+\varepsilon\alpha_r+O(\varepsilon^2),\qquad \alpha_r=1-m(u_r).
$$
The constraint defining $B_\varepsilon(t_2)$ cannot affect this infimum when $x_2\le2-\varepsilon L$: all potentially minimizing clone fractions are at least $1-\varepsilon L$. Consequently it can matter only in the strip
$$
1\le t_2<u(2-\varepsilon L)=1+O(\varepsilon).
$$
Both its constrained and unrestricted thresholds are in $[1,1+\varepsilon]$. Since the bivariate normal density is bounded, replacing $B_\varepsilon(T_2)$ by $D_{2,\varepsilon}$ changes the rejection probability by $O(\varepsilon^2)$. Also $B_\varepsilon\le1+\varepsilon<A_\varepsilon$ for sufficiently small $\varepsilon$. Therefore the actual iterated limit satisfies
$$
\lim_{K\to\infty}F_{K,\varepsilon}
=\mathbb P(T_2\ge u_1)
+\mathbb P(T_2<1,T_1\ge D_{1,\varepsilon})
+\mathbb P(1\le T_2<u_1,T_1\ge D_{2,\varepsilon})
+O(\varepsilon^2).
$$
Writing $s=\sqrt{19}/10$ and $\rho=-9/10$, differentiation gives
$$
\lim_{\varepsilon\downarrow0}\frac{\lim_K F_{K,\varepsilon}-F}{\varepsilon}
=-\alpha_1\phi(u_1)\Phi\!\left(\frac{1-\rho u_1}{s}\right)
-\alpha_2\phi(1)\left\{\Phi\!\left(\frac{u_1-\rho}{s}\right)-\Phi\!\left(\frac{1-\rho}{s}\right)\right\}.
$$
The original BH FDP jumps are exactly $\Delta_{1,1}=\mathbf1_{\{T_2<1\}}$ on the $T_1=u_1$ face and $\Delta_{1,2}=\mathbf1_{\{1\le T_2<u_1\}}$ on the $T_1=1$ face, up to null sets. The two coefficients multiplying $-\alpha_r$ above are thus precisely $\mu_{1,r}(E_1)$. This is the proposed signed variation, with no separate rank optimization used to define the actual crossing. A supplementary standard-library numerical check gives $u_1\simeq1.4096087093$, $\mu_{1,1}(E_1)\simeq0.1477199560$, $\mu_{1,2}(E_1)\simeq1.5673841\cdot10^{-6}$, and derivative $-0.0683928764$. The symbolic argument establishes the equality; these decimals only check its evaluation.

Finally let $M_K$ be the number of nonzero midpoint offsets. Counting grid midpoints gives $|M_K/K-\varepsilon L|\le1/(2K)$. Only group one moves, and its direction differs from group two, so
$$
d_{\mathrm{TV}}(\pi_{K,\varepsilon},\pi)=\frac{M_K}{2K}
\le\frac{\varepsilon L}{2}+\frac1{4K}
\le\varepsilon\{h(1)-1\}+\frac1{2K}.
$$
Coupling each copy to its original coordinate costs less than $\varepsilon$ per moved mass, proving the stated $W_1$ bound. For the continuous-offset measure the moved mass is exactly $\varepsilon L/2$, giving the corresponding continuous TV and transport bounds.

## Failure

NOT fails: this positive-definite negatively correlated two-null model satisfies the population limit, both nonzero face coefficients, normalization and cost conclusions; mixed labels and larger models remain unchecked here.
