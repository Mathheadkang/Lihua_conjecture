---
type: candidate
title: Correlated mixed Gaussian pairs obey a Brownian innovation square-root budget
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
round: 4
slot: 2
direction: small_cases
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:20:56.688Z'
extension_version: 0.0.4
---

## Object

Consider every parameter choice
$$
0<q\le\overline\Phi(3),\qquad \nu\ge0,\quad \mu>0,\quad -1<\rho<1,\quad \rho\ne0.
$$
Take $N=d=2$, $\theta=(-\nu,\mu)$, $v_1=e_1$, and $v_2=\rho e_1+\sqrt{1-\rho^2}e_2$. Thus
$$
S_1(z)=z_1-\nu,\qquad S_2(z)=\mu+\rho z_1+\sqrt{1-\rho^2}z_2.
$$
This addresses the previously untested correlated mixed pair, including negative true-null means. The board's independent-pair sign argument does not apply: its heat factorization is lost when $\rho\ne0$. No sign of the correlated posterior derivative is assumed.

Put $U=\overline\Phi^{-1}(q)$, $A=\overline\Phi^{-1}(q/2)$, $H=h(U)$, $c=1/h(A)$, $b=1/H$, $\Delta=b-c>0$, and $r=Hc\in(0,1)$. Define disjoint regions
$$
E=\{S_1\ge A,\ S_2<U\},\qquad J=\{S_1\ge U,\ S_2\ge U\}.
$$
Their boundaries have Gaussian measure zero; the ordinary non-strict BH convention determines them there.

## Checks

### H1

The testing level is positive and at most $\overline\Phi(3)$, so $U\ge3$ and the proposed small-level regime is respected. All parameters may depend arbitrarily on $q$.

### H2

The dimensions are finite positive integers. Both observation vectors have norm one and
$$
\Sigma=\begin{pmatrix}1&\rho\\\rho&1\end{pmatrix}
$$
is positive definite. Taking $G\sim\gamma_2$ gives exactly the required jointly Gaussian model, with no marginal-to-joint substitution.

### H3

Use the required one-sided p-values $p_i=\overline\Phi(S_i)$. Since $\nu\ge0$ and $\mu>0$, the true-null set is exactly $I_0=\{1\}$. This includes every nonpositive mean for that null.

### H4

For two tests, rank two qualifies exactly when both statistics are at least $U$. In that region the largest rank is two and the FDP is $1/2$. When the null is rejected at rank one, its statistic must be at least $A$; rank two must fail, which, because $A>U$, is equivalent to $S_2<U$. Consequently the actual BH fields, with all ranks and multiplicities retained, are
$$
f=\mathbf1_E+\tfrac12\mathbf1_J,\qquad B=e_1\bigl(c\mathbf1_E+\tfrac b2\mathbf1_J\bigr).
$$
The regions where only the alternative is rejected have $f=B=0$.

### H5

On $\{S_1\ge A\}$ the null is rejected and $f\ge1/2$, while $\{f>0\}\subseteq\{S_1\ge U\}$. Thus
$$
0<\tfrac12\overline\Phi(A+\nu)\le F\le\overline\Phi(U+\nu)\le q.
$$
The prescribed tilt is therefore well defined. With $p=Q(E)$ and
$$
\xi=\mathbf1_E(W_1),\qquad \rho_t=\mathbb E_{\mathbb Q}[\xi\mid\mathcal F_t],
$$
Bayes' rule for the stipulated terminal tilt gives the exact heat posterior
$$
a_t=e_1(b-\Delta\rho_t),\qquad B/f=e_1(b-\Delta\mathbf1_E)\quad Q\text{-a.e.}
$$
Here $\rho_t$ is a conditional probability, distinct from the fixed correlation parameter $\rho$.

### NOT

This check fails: the entire displayed correlated family satisfies the stronger estimate
$$
M_+\le\frac qH\sqrt{1-x}\le\frac q3\sqrt{1-x}.
$$
The well-posedness and endpoint claims are proved first, as required by the target.

For completeness let $m_t=\mathcal H(t,W_t)/F$. This is the positive density martingale under $\mathbb P$, with $m_t\le1/F$ and $m_1=f(W_1)/F$. Relative entropy gives
$$
0\le D=\mathbb E_{\mathbb P}[m_1\log m_1]\le\log(1/F)<\infty.
$$
Ito's formula for $m_t\log m_t$, localized away from zero and then passed to the limit, gives
$$
\mathbb E_{\mathbb Q}\int_0^\tau\|\beta_t\|^2dt
=2\mathbb E_{\mathbb P}[m_\tau\log m_\tau].
$$
As $\tau\uparrow1$, boundedness of $m_t$, continuity of $s\log s$ at zero and martingale convergence give
$$
\mathbb E_{\mathbb Q}\int_0^1\|\beta_t\|^2dt=2D.
$$
Girsanov's formula on each $[0,\tau]$, and this finite energy, therefore yield a standard two-dimensional Brownian innovation under $\mathbb Q$ extending to time one:
$$
Z_t=W_t-\int_0^t\beta_sds.
$$
The field $a_t$ is the bounded conditional-expectation martingale of $B/f(W_1)$. Its heat equation or Ito's formula gives $da_t=K_t\,dZ_t$ for $t<1$. Martingale convergence and Ito isometry give
$$
\mathbb E_{\mathbb Q}\int_0^1\|K_t\|_{\rm HS}^2dt
=\mathbb E_Q\|B/f\|^2-\|a_0\|^2\le b^2.
$$
Only the first row of $K_t$ is nonzero. Hence $|\operatorname{tr}K_t|=|(K_t)_{11}|\le\|K_t\|_{\rm HS}$, and Cauchy--Schwarz proves absolute trace integrability on $[0,1)$. Also $\|a_t\|\le b$, so $0\le x\le H^2b^2=1$ and
$$
\mathbb E_{\mathbb Q}\int_0^1|a_t\cdot\beta_t|dt\le b\sqrt{2D}<\infty.
$$
The endpoint integral is absolutely finite because $\|B\|\le b$ and the Gaussian first absolute moment is finite.

Write $b_1=(B/f)(W_1)$, which is a bounded vector under $\mathbb Q$. Conditional expectation and the established drift integrability imply
$$
\mathbb E_{\mathbb Q}\left[b_1\cdot\int_0^1\beta_tdt\right]
=\mathbb E_{\mathbb Q}\int_0^1a_t\cdot\beta_tdt.
$$
Ito isometry, applied to $a_1=a_0+\int_0^1K_t\,dZ_t$, then yields
$$
\mathbb E_{\mathbb Q}[b_1\cdot Z_1]
=\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_tdt.
$$
Since $W_1=Z_1+\int_0^1\beta_tdt$ and $F\mathbb E_{\mathbb Q}[b_1\cdot W_1]=\int z\cdot B(z)\gamma_2(dz)$, these equations establish exactly the target's endpoint identity and its equality with $\lim_{\tau\uparrow1}M_\tau$. Absolute trace integrability justifies that limit. No endpoint identity has been assumed in obtaining the estimates.

Now $\mathbb E_{\mathbb Q}Z_{1,1}=0$ and $\mathbb E_{\mathbb Q}Z_{1,1}^2=1$. The just-proved trace representation gives
$$
M=F\mathbb E_{\mathbb Q}[(b-\Delta\xi)Z_{1,1}]
=-F\Delta\mathbb E_{\mathbb Q}[\xi Z_{1,1}],\qquad |M|\le F\Delta\sqrt p.
$$
Conditional Jensen, integrated over time, independently gives
$$
x\le H^2\mathbb E_Q\|B/f\|^2
=H^2\bigl((1-p)b^2+pc^2\bigr)
=1-p(1-r^2).
$$
Combining these bounds, without dividing by a possibly zero $p$, yields
$$
M_+\le\frac FH\sqrt{\frac{1-r}{1+r}}\sqrt{1-x}
\le\frac qH\sqrt{1-x}.
$$
Finally $h(U)\ge U\ge3$, by the elementary upper Mills bound $\overline\Phi(U)\le\phi(U)/U$. This proves the displayed estimate with a universal constant, independently of correlation, means or their dependence on $q$. The additional entropy-linear term in the proposed budget is nonnegative.

## Failure

NOT fails: the correlated one-null pair obeys a square-root budget through its one-direction terminal mark and the Brownian innovation covariance, even without a posterior derivative sign.
