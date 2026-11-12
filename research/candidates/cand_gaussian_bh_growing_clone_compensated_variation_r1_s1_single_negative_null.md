---
type: candidate
title: Single negative null at the minimal dimension
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
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T22:49:51.760Z'
extension_version: 0.0.4
---

## Object

Take $N=d=1$, $\theta_1=-1$, $\Sigma=(1)$, $v_1=1$, $i=1$, and $q=S(1/2)$. Use exactly the compensated private clones in the target, with $K$ copies and sufficiently small positive $\varepsilon$. Write $u=1/2$, $a=3/2$, and $h_0=\phi(u)/q$.

## Checks

### H1

Pass: $N=1$ is a finite positive integer.

### H2

Pass: the mean vector is the finite real vector $(-1)$.

### H3

Pass: $(1)$ is positive definite with unit diagonal.

### H4

Pass: $q=S(1/2)$ lies strictly between zero and $1/2$.

### H5

Pass: $i=1\in[1]$ and $\theta_i=-1\ne0$.

### H6

Pass: $G=Z\sim N(0,1)$ and the row $v_1=1$ has norm one and gives the prescribed covariance. The orthogonal space has dimension zero.

### H7

Pass: use the stipulated one-sided p-values and largest-rank BH with non-strict comparisons. The original true-null set is $\{1\}$, and $F=S(a)$.

### H8

Pass: every group has exactly $K$ copies (there is only one group), the private variables are independent standard normals independent of $Z$, and the displayed compensated formula is used without modification. Since $d_\varepsilon\to0$, restrict to $d_\varepsilon<1$; all actual clone means remain negative and all copies are true nulls.

### H9

Pass: use the common crossing and numerator from the definition. Here $H_s(x)=J_s(x)=S((S^{-1}(qx)-m)/s)$, where $m=-1+d_\varepsilon+\sqrt{1-s^2}Z$, and $0<x\le1$. The original face jump is $\Delta_{1,1}=1$ and the zero-dimensional signed measure has mass $\phi(a)$.

### NOT

Fail: both assertions hold, including the claimed coefficient. The following calculation retains the iterated order of limits.

At fixed $s\in(0,1)$ define
$$
c_s=\min_{0<x<1}\{S^{-1}(qx)-sS^{-1}(x)\}.
$$
The minimized expression tends to infinity at both endpoints. A positive population crossing exists exactly when $m\ge c_s$. Its largest crossing is a root: $H_s$ is continuous, $H_s(1)<1$, and any strict excess at a positive largest crossing would allow extending that crossing. Thus $H_s(\rho_s)=\rho_s$ whenever $\rho_s>0$, and $D_s=1$ there.

For $m>c_s$ there is a strict crossing, so uniform convergence of the conditional empirical distribution yields a finite-copy crossing with probability tending to one. For $m<c_s$ no macroscopic crossing survives. Microscopic crossings vanish as well: conditional Gaussian tails with variance $s^2<1$ give constants $C<\infty$, $\alpha>1$ and $\delta>0$ such that $H_s(x)\le Cx^\alpha$ for $0<x\le\delta$. At a rank $\ell\le\delta K$, the conditional probability of a crossing is at most
$$
\left(eC(\ell/K)^{\alpha-1}\right)^\ell.
$$
Choose $\delta$ so the base is below $1/2$. Summing this bound after splitting at $\sqrt K$ tends to zero: the lower part is a geometric bound with base tending to zero, and the upper part is at most $K2^{-\sqrt K}$. Away from zero the strict gap and uniform empirical convergence apply. The tangency event $m=c_s$ has probability zero under $Z$. Consequently bounded convergence, first in the private sampling and then in $Z$, gives
$$
F_{\infty,\varepsilon}=\mathbb P(m\ge c_s)=\mathbb E D_s
=S\left(\frac{c_s+1-d_\varepsilon}{\sqrt{1-s^2}}\right).
$$

For completeness the minimizing contact gives the compensated coefficient directly. Set $x_s=\Phi(\tau_s)$ at the minimum and $u_s=S^{-1}(qx_s)$. As $s\downarrow0$, any minimizer has $x_s\to1$: on $x\le1/2$ the expression is at least $(1-s)S^{-1}(q/2)$, and on any compact subinterval bounded away from one its limit exceeds $u$. A test point tending to one has value tending to $u$. Thus eventually $\tau_s>0$, and differentiating at the interior minimum yields
$$
\phi(\tau_s)=s\phi(u_s)/q.
$$
There is a unique stationary point in this negative-quantile region: for $w=S^{-1}(x)<0$ and $U(w)=S^{-1}(qS(w))>0$, the ratio $\phi(w)/\phi(U(w))$ is strictly increasing in $w$, since its logarithmic derivative is $-w+U(w)U'(w)>0$.

Gaussian tail expansion and Taylor expansion at $u$ now give
$$
u_s-u=\frac{s}{\tau_s}+O(s/\tau_s^3+s^2/\tau_s^2),\qquad
\tau_s^2=t_s^2-2\log h_0+o(1),
$$
and hence
$$
c_s=u+s(t_s+t_s^{-1})-\frac{s}{t_s}\log h_0+o(s/t_s).
$$
Indeed $u_s-u=S(\tau_s)/h_0+O(S(\tau_s)^2)$ and $S(\tau_s)=\phi(\tau_s)(\tau_s^{-1}+O(\tau_s^{-3}))$ justify the displayed error scale. Since $s^2=o(s/t_s)$, substitution into the exact fixed-$s$ limit gives
$$
\lim_{\varepsilon\downarrow0}\frac{F_{\infty,\varepsilon}-F}{s/t_s}
=\phi(a)\log h_0
=\log\{1\,h(u_1)\}\,\mu_{1,1}(\mathbb R^0).
$$

## Failure

NOT fails: the minimal-dimensional all-null boundary case satisfies the common-crossing assertion and exactly reproduces the compensated coefficient.
