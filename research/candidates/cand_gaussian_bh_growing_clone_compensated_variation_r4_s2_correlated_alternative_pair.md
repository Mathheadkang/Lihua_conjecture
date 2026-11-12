---
type: candidate
title: Correlated mixed pair with the alternative privately cloned
status: failed
target_asset: gaussian_bh_growing_clone_compensated_variation
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
  NOT: fail
mode: refute
round: 4
slot: 2
direction: small_cases
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T23:10:04.857Z'
extension_version: 0.0.4
---

## Object

Take $N=d=2$, $q=1/4$, $\theta=(1,0)$, $i=1$, $v_1=(1,0)$, and $v_2=(1/2,\sqrt3/2)$. Thus $\Sigma_{12}=1/2$ and the sole null is group 2. Clone the alternative using precisely the prescribed private Gaussian construction and compensation.

The previous independent uniform-null cancellation does not apply: conditional on $Z=G_1=z$, the null score has mean $z/2$, variance $3/4$, and is not independent of the alternative block. In fact the signed face mass computed below is strictly positive. This tests dependence rather than repeating a zero-coefficient independence benchmark.

## Checks

### H1

The original size $N=2$ is finite and positive, and all parameters are fixed independently of $\varepsilon$ and $K$.

### H2

The mean vector is real. The covariance is unit-diagonal and positive definite, with eigenvalues $1/2$ and $3/2$.

### H3

The level $q=1/4$ lies in $(0,1/2)$, and the chosen mean $\theta_1=1$ is nonzero.

### H4

The displayed vectors have unit norm, their inner product is $1/2$, and $G\sim\mathcal N_2(0,I_2)$ gives the required representation.

### H5

Use one-sided survival-function p-values and the actual labels $I_0=\{2\}$.

### H6

Each original group has exactly $K$ copies. Group 2 stays exact. Group 1 has scores $1+d_\varepsilon+\sqrt{1-s^2}Z+s\xi_b$, with independent standard Gaussian private marks, as required.

### H7

Use exactly $\phi(t_s)=s$, $t_s>0$, and $d_\varepsilon=s(t_s+t_s^{-1})$. For all sufficiently small positive $\varepsilon$ these are defined. The chosen mean $1+d_\varepsilon$ stays positive, so the actual expanded null set is $\{2\}\times[K]$.

### H8

All procedures use ordinary BH with its actual largest rank and non-strict thresholds. The population calculation below uses a single largest crossing; it does not optimize the null and alternative separately.

### H9

The order of limits below is $K\to\infty$ at fixed $\varepsilon>0$, followed by $\varepsilon\downarrow0$. The original-rank signed face jumps retain the actual original FDP.

### NOT

The candidate does not violate either assertion. Here is a reduction checking the finite-copy limit and the nonzero compensated coefficient.

Write $u(x)=S^{-1}(qx/2)$, $u_1=u(1)$, $u_2=u(2)$, $m=1+d_\varepsilon+\sqrt{1-s^2}z$, and

$$
g_s(x)=u(x)-sS^{-1}(x-1),\qquad 1<x<2.
$$

Let $x_s(m)$ be the largest crossing of $1+b_\varepsilon(x,z)\ge x$ on $[1,2]$. The endpoint values have opposite strict signs, so $1<x_s<2$ and $1+b_\varepsilon(x_s,z)=x_s$.

Temporarily replace the exact null group's p-value by zero and denote the finite-copy BH rank divided by $K$ by $X_K\in[1,2]$. The original null group is rejected if and only if its actual p-value is at most $qX_K/2$, and then its actual rank is exactly $KX_K$. This follows in both directions from the largest-rank convention: lowering that block cannot decrease the rank, and, if the block qualifies at the larger threshold, its count there is still exactly $K$. Consequently the actual finite-copy FDP is exactly

$$
\frac{\mathbf1\{T_2\ge u(X_K)\}}{X_K}.
$$

At fixed sufficiently small $s$, conditional empirical survival functions converge uniformly. Except at the finitely many critical values of $g_s$, the largest crossing is stable, so $X_K\to x_s(m)$. The exceptional $m$ values have zero Gaussian probability. These are isolated critical values: $g_s'=s/\phi(S^{-1}(x-1))-q/[2\phi(u(x))]$; near either endpoint the first term diverges, and for small $s$ its only changes of sign are the two endpoint extrema (on a fixed interior compact set the derivative is negative). Bounded convergence therefore gives

$$
F_{\infty,\varepsilon}
=\mathbb E_Z\frac{P_z\{T_2\ge u(x_s(m))\}}{x_s(m)},
\qquad T_2\mid Z=z\sim\mathcal N(z/2,3/4).
$$

This is the prescribed population FDP: if the null satisfies $T_2\ge u(x_s)$, the common largest root is $x_s$; otherwise no crossing containing the null exists and the population numerator is zero. At any positive population largest crossing, $H=x$: continuity gives equality within a block-count interval, while an upward jump with $H>x$ at its threshold would also give crossings immediately to its right. Thus the first assertion is satisfied, including equality at the common root.

For the expansion put $A(x)=q/[2\phi(u(x))]$ and $A_2=A(2)=1/[2h(u_2)]$. Let $x_c=2-S(t_c)$ be the upper local minimum of $g_s$ and $M_s=g_s(x_c)$. Its exact stationarity equation and value are

$$
\phi(t_c)=s/A(x_c),\qquad M_s=u(x_c)+st_c.
$$

Since $x_c\to2$, Gaussian tail asymptotics and this exact equation give

$$
t_c=t_s+\frac{\log A_2}{t_s}+o(t_s^{-1}),\qquad
M_s=u_2+s(t_s+t_s^{-1})+\frac{s}{t_s}\log A_2+o(s/t_s).
$$

For $m<M_s$, the largest root is exponentially close to 1. Indeed $M_s\to u_2<u_1$, and any root below the upper saddle must lie in a fixed small neighborhood of 1, where $u(x)-m$ is bounded below by a positive constant; then $x-1=S((u(x)-m)/s)=O(e^{-c/s^2})$. For $m\ge M_s$, the largest root lies on the upper branch. With $\delta=2-x_s$ and $\delta_c=S(t_c)=O(s/t_s)$, one has

$$
0\le\delta\le\delta_c\exp\{-t_c(m-M_s)/s\}.
$$

To see this, parameterize that branch by $x=2-S(t)$, $t\ge t_c$. Since $u(x)\le u(x_c)$, $m-M_s\le s(t-t_c)$; the Gaussian survival ratio is at most $\exp\{-t_c(t-t_c)\}$. Integrating the displayed bound against the bounded Gaussian density of $m$ gives $\mathbb E[\delta\mathbf1\{m\ge M_s\}]=O(s^2/t_s^2)$. Conditional null tail probabilities have uniformly bounded derivative in their threshold, so replacing the upper-root FDP by $P_z(T_2\ge u_2)/2$ has this same integrated error. The lower-root replacement by $P_z(T_2\ge u_1)$ has exponentially small error.

Hence, up to $o(s/t_s)$, the original piecewise conditional FDP has its dividing point $a=u_2-1$ shifted to

$$
z_c=\frac{M_s-1-d_\varepsilon}{\sqrt{1-s^2}}
=a+\frac{s}{t_s}\log A_2+o(s/t_s).
$$

At the original $u_1$ face the FDP jump is zero. At the original $u_2$ face the jump is $-1/2$ when $T_2\ge u_1$, $+1/2$ when $u_2\le T_2<u_1$, and zero otherwise. Therefore

$$
\mu_{1,1}(\mathbb R)=0,\qquad
\mu_{1,2}(\mathbb R)
=\frac{\phi(a)}2\left[P_a(T_2\ge u_2)-2P_a(T_2\ge u_1)\right].
$$

Shifting the dividing point gives exactly

$$
\lim_{\varepsilon\downarrow0}\frac{F_{\infty,\varepsilon}-F}{s/t_s}
=-\log A_2\,\mu_{1,2}(\mathbb R)
=\log\{2h(u_2)\}\,\mu_{1,2}(\mathbb R).
$$

For numerical orientation, $u_1=1.1503493803760079$, $u_2=0.6744897501960817$, $P_a(T_2\ge u_1)=0.0647290251946191$, and $P_a(T_2\ge u_2)=0.1668302353947856$. Thus $\mu_{1,2}(\mathbb R)=0.007070014537774618$ and the coefficient is $0.006596569578441303$. These elementary normal-tail values are diagnostics; the preceding reduction supplies the comparison.

## Failure

NOT fails: dependence produces a nonzero signed face mass, but the common largest-root calculation and its fractional FDP still give exactly the asserted compensated coefficient.
