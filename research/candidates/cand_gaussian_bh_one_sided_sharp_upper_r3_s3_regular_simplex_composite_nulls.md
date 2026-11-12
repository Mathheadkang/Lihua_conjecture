---
type: candidate
title: Growing regular-simplex Gaussian array with composite nulls
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
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
round: 3
slot: 3
direction: drop_hypothesis
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:24:30.984Z'
extension_version: 0.0.4
---

## Object

For $q\in(0,1/4)$ set
$$
N=\lceil q^{-6}\rceil,\qquad
c=\sqrt{1-1/N},\qquad
\theta_i=\begin{cases}0,&i\text{ odd},\\-q,&i\text{ even}.\end{cases}
$$
Take independent $Z_1,\ldots,Z_N\sim\mathcal N(0,1)$, put $\overline Z=N^{-1}\sum_iZ_i$, and define
$$
T_i=\theta_i+\frac{Z_i-\overline Z}{c}.
$$
The covariance has diagonal one and every off-diagonal entry $-1/(N-1)$, exactly the lower positive-semidefinite boundary for an equicorrelation matrix. Apply ordinary one-sided BH at level $q$ with $p_i=\overline\Phi(T_i)$.

This is a growing-rank boundary test: the centered observations sum to zero, the pairwise correlations are maximally negative among equicorrelation matrices of this size, and $\lfloor N/2\rfloor$ true-null means are strictly negative. It is different from a rank-one or balanced planar array.

## Checks

### H1

Pass: $N=\lceil q^{-6}\rceil$ is a finite positive integer at each $q\in(0,1/4)$ and tends to infinity as $q\downarrow0$.

### H2

Pass: $\theta\in\mathbb R^N$, and every coordinate belongs to the composite true-null set $\{i:\theta_i\leq0\}$. The strictly negative means are not reclassified as alternatives.

### H3

Pass: direct covariance calculation gives
$$
\Sigma_{ii}=1,\qquad \Sigma_{ij}=-\frac1{N-1}\quad(i\ne j),\qquad
\Sigma=\frac{N}{N-1}\left(I-\frac{\mathbf1\mathbf1^{\mathsf T}}{N}\right).
$$
The matrix is symmetric, with eigenvalue zero in the direction $\mathbf1$ and eigenvalue $N/(N-1)>0$ on its orthogonal complement. It is therefore positive semidefinite, has unit diagonal, and has rank $N-1$.

### H4

Pass: $T-\theta$ is a deterministic linear transformation of the independent standard normal vector $Z$. Every linear combination is centered normal with the specified covariance, so the full vector is exactly jointly Gaussian, including its single degenerate direction.

### H5

Pass: the p-values are exactly $p_i=\overline\Phi(T_i)$ and the true-null set is $[N]$. Every marginal observation has unit variance and the stated nonpositive mean.

### H6

Pass: use the ordinary BH largest qualifying rank, non-strict inequalities, and multiplicities exactly as in the definition.

### H7

Pass: every rejection is a false discovery, so $V=R$ and
$$
\operatorname{FDR}=\mathbb P(R>0)
$$
under the exact Gaussian sampling law given in the object.

### NOT

Fail: for all sufficiently small $q$,
$$
\operatorname{FDR}\leq2q+e^{-1/(2q^2)},
$$
so the normalized FDR tends to zero. The argument uses a simultaneous comparison of the exact finite Gaussian array with independent null p-values.

Let $U_i=\overline\Phi(Z_i)$, which are independent uniform random variables, and use the event
$$
G_q=\{\overline Z\geq-q^2\}.
$$
As $\overline Z\sim\mathcal N(0,1/N)$, the exponential Gaussian bound gives
$$
\mathbb P(G_q^c)\leq e^{-Nq^4/2}\leq e^{-1/(2q^2)}.
$$
We next verify uniformly over all BH rank thresholds that the comparison costs a factor of at most two. Define
$$
b_q=\sqrt{2\log(N/q)},\qquad d_q=q^2+(1-c)b_q.
$$
For $x\in[q/N,q]$ write $z_x=\overline\Phi^{-1}(x)$. For sufficiently small $q$,
$$
1<z_q-d_q\leq z_x-d_q,\qquad
z_x\leq b_q,\qquad d_q(b_q+1)\longrightarrow0.
$$
Here the upper quantile bound follows from $\overline\Phi(t)\leq e^{-t^2/2}$ for $t\geq0$. Also $N\leq2q^{-6}$ and $1-c\leq1/N$, so $b_q=O(\sqrt{\log(1/q)})$ and $d_q\leq q^2+b_q/N$.

For $s\geq1$, integration by parts gives
$$
\overline\Phi(s)\geq\frac{s\phi(s)}{s^2+1},\qquad
\frac{\phi(s)}{\overline\Phi(s)}\leq s+1.
$$
Consequently,
$$
\log\frac{\overline\Phi(cz_x-q^2)}{\overline\Phi(z_x)}
=\int_{cz_x-q^2}^{z_x}\frac{\phi(s)}{\overline\Phi(s)}\,ds
\leq d_q(b_q+1)\leq\log2
$$
for all sufficiently small $q$, uniformly in $x\in[q/N,q]$. In particular,
$$
\overline\Phi(cz_x-q^2)\leq2x.
$$

On $G_q$, if $T_i\geq z_x$ then $\theta_i\leq0$ implies
$$
Z_i=\overline Z+c(T_i-\theta_i)\geq cz_x-q^2,
\qquad U_i\leq2x.
$$
Suppose a rank $k\geq1$ qualifies for the original BH procedure. At least $k$ observations satisfy $T_i\geq z_{qk/N}$. On $G_q$, at least the same $k$ independent p-values satisfy $U_i\leq2qk/N$. Therefore the independent BH procedure at level $2q$ has a positive qualifying rank.

For completeness, the all-null independent BH procedure at a level $a\in(0,1)$ has rejection probability $a$. Let $R_i^0$ be its number of rejections after setting $U_i$ to zero. Setting an already rejected p-value to zero leaves the largest qualifying rank unchanged, and the converse threshold test gives
$$
\frac{\mathbf1\{i\text{ rejected}\}}{R\vee1}
=\frac{\mathbf1\{U_i\leq aR_i^0/N\}}{R_i^0}.
$$
The random variable $R_i^0\geq1$ depends only on the other p-values, so conditioning on those p-values makes the expectation of the right side equal to $a/N$. Summing over $i$ gives FDR $a$, which equals the rejection probability because all coordinates are null.

Taking $a=2q$ in the coupling proves
$$
\operatorname{FDR}=\mathbb P(R>0)
\leq\mathbb P(\text{independent BH at level }2q\text{ rejects})+\mathbb P(G_q^c)
\leq2q+e^{-1/(2q^2)}.
$$
Hence
$$
\limsup_{q\downarrow0}
\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}=0.
$$
The comparison covers this specified equicorrelation boundary and all-null mean pattern. It does not cover mixed alternatives, arbitrary covariance matrices, or a general reduction of negative true-null means to zero.

## Failure

NOT fails: the maximally negative equicorrelation boundary with the displayed growing dimension and composite-null means has FDR $O(q)$.
