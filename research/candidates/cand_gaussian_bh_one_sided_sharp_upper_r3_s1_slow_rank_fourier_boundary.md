---
type: candidate
title: Slowly growing Fourier covariance rank with heterogeneous composite-null means
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:24:30.984Z'
extension_version: 0.0.4
---

## Object

For sufficiently small $q$, put
$$
L=\log(1/q),\quad M=2\lfloor L^{1/4}\rfloor+1,\quad
d=2M,\quad N=6\lceil e^{L^2}\rceil.
$$
For $i=0,\ldots,N-1$, let $\alpha_i=2\pi i/N$ and define the unit loading
$$
a_i=\frac1{\sqrt M}
(\cos\alpha_i,\sin\alpha_i,\ldots,
\cos M\alpha_i,\sin M\alpha_i)\in\mathbb R^d.
$$
Use deterministic means
$$
\theta_i=\begin{cases}
0,&i\equiv0\pmod3,\\
-(L+i/N),&i\equiv1\pmod3,\\
\sqrt L+i/N,&i\equiv2\pmod3.
\end{cases}
$$
Let $Z\sim\mathcal N_d(0,I_d)$ and $T_i=\theta_i+a_i^{\mathsf T}Z$. Apply ordinary BH once to $\overline\Phi(T_i)$ at level $q$.

This boundary family has exactly singular covariance of diverging rank, rather than rank one or a perturbation of rank one. Its testing dimension is superpolynomial in $1/q$; its null means include values diverging to $-\infty$; and its alternative means diverge positively. No residual-noise approximation or source-quantile design is used.

## Checks

### H1

$M,d,N$ are finite positive integers at each $q$, $N$ is divisible by three, and $d\to\infty$ with $d=O(L^{1/4})$ while $N/d\to\infty$.

### H2

All means are deterministic real numbers. Exactly the indices congruent to zero or one modulo three are true nulls under $I_0^{(1)}=\{i:\theta_i\leq0\}$, so $N_0=2N/3$. The negative means have not been replaced by zero or omitted.

### H3

Each $a_i$ has squared norm $M^{-1}\sum_{\ell=1}^M(\cos^2\ell\alpha_i+\sin^2\ell\alpha_i)=1$. Therefore $\Sigma=AA^{\mathsf T}$ is positive semidefinite with unit diagonal. Discrete Fourier orthogonality, since $N>2M$, gives $A^{\mathsf T}A=(N/d)I_d$, so its rank is exactly $d$ and it has $N-d$ zero eigenvalues.

Explicitly
$$
\Sigma_{ij}=\frac1M\sum_{\ell=1}^M
\cos\{\ell(\alpha_i-\alpha_j)\}.
$$
For antipodal indices the correlation equals $-1/M<0$ because $M$ is odd; nearby distinct indices have positive correlations. The family is not being reduced to an everywhere nonnegative-correlation model.

### H4

$T=\theta+AZ$ is exactly jointly Gaussian with the deterministic mean and covariance above, including its singular linear relations.

### H5

Use $p_i^{(1)}=\overline\Phi(T_i)$, the largest qualifying global BH rank, all ties, and $\mathbb E[V/(R\vee1)]$. The following bound applies to these exact arrays and includes the strictly negative null means.

### NOT

Fail. The exact family obeys
$$
\operatorname{FDR}^{(1)}=O(qL^{1/4}\log L)=o(q\sqrt L).
$$
Apply the approved node `multifactor_radial_fdr_bounds` in the stated multifactor representation, with factor dimension $d$, all row norms $r_i=1$, and no independent residuals. Its endpoint $r_i=1$ is explicitly included, so every null coefficient $\gamma_i=\sqrt{(1-r_i)/(1+r_i)}$ is zero. The approved one-sided assertion covers every $\theta_i\leq0$. With $b_d(q)$ the upper-$q$ chi-radius quantile, it gives
$$
\operatorname{FDR}^{(1)}\leq
q+q\pi_0\{1/2+\Delta_1(d,q)\},\qquad
\Delta_1(d,q)=\log\frac q{\overline\Phi(b_d(q))}.
$$
It remains to control this radial strip term for the growing dimension. Here is a direct quantile calculation, with no fixed-$d$ asymptotic substitution. Let $X\sim\chi_d^2$, choose $t=(1-1/L)/2$, and set $x=2L+2d\log L+4$. Its Gaussian moment generating function gives
$$
\begin{aligned}
\log\mathbb P(X\geq x)
&\leq-tx+\tfrac d2\log L\\
&=-L-\tfrac d2\log L-1+
\frac{d\log L+2}{L}\leq-L
\end{aligned}
$$
for sufficiently large $L$, since $d\log L/L\to0$. Thus $b_d(q)^2\leq x$.

The elementary lower Mills bound
$\overline\Phi(b)\geq\phi(b)b/(b^2+1)$ implies
$$
\begin{aligned}
\Delta_1(d,q)
&\leq-L+\frac{b_d(q)^2}2+
\frac12\log(2\pi)+
\log\frac{b_d(q)^2+1}{b_d(q)}\\
&\leq d\log L+O(\log L).
\end{aligned}
$$
The logarithmic remainder is uniform here: $b_d(q)\to\infty$ and its square is at most $2L+o(L)$. Substitution in the approved finite-level radial bound proves the displayed FDR order. Consequently
$$
\lim_{q\downarrow0}
\frac{\operatorname{FDR}^{(1)}}{q\sqrt{\log(1/q)}}=0.
$$

The conclusion uses exact zero residual variance together with this growth of covariance rank. It does not identify covariance rank with factor dimension for models having nonzero independent residuals, or exclude ranks growing at arbitrary rates.

## Failure

NOT fails: the exact rank-$O(L^{1/4})$ Gaussian Gram representation has zero null loading coefficients and a radial strip cost only $O(d\log L)$, which is negligible relative to $\sqrt L$ even with heterogeneous diverging negative true-null means.
