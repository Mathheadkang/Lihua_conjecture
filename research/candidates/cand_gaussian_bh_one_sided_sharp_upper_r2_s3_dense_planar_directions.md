---
type: candidate
title: Dense planar Gaussian directions at a growing dimension
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
round: 2
slot: 3
direction: extremal
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:13:28.581Z'
extension_version: 0.0.4
---

## Object

For every $q\in(0,1/4)$ let $N=\lceil q^{-3}\rceil$. For $j=1,\ldots,N$ put
$$
\gamma_j=\frac{2\pi j}{N},\qquad
\nu_j=(\cos\gamma_j,\sin\gamma_j),\qquad
\theta_j=0.
$$
Take independent $Z_1,Z_2\sim\mathcal N(0,1)$, set
$$
T_j=\nu_j^{\mathsf T}(Z_1,Z_2),\qquad
\Sigma_{ij}=\nu_i^{\mathsf T}\nu_j=\cos(\gamma_i-\gamma_j),
$$
and apply ordinary one-sided BH at level $q$ to $p_j=\overline\Phi(T_j)$. This family tests whether a dense, growing collection of differently oriented Gaussian tails can create an asymptotic counterexample beyond rank-one models.

## Checks

### H1

Pass: $N=\lceil q^{-3}\rceil$ is a finite positive integer for every $q\in(0,1/4)$ and tends to infinity as $q\downarrow0$.

### H2

Pass: $\theta=0\in\mathbb R^N$. All coordinates are true nulls under the composite-null convention $I_0^{(1)}=\{j:\theta_j\leq0\}$. No boundary restriction is imposed on the target; this object chooses the permitted boundary means.

### H3

Pass: $\Sigma$ is a real symmetric Gram matrix, so for every $a\in\mathbb R^N$,
$$
a^{\mathsf T}\Sigma a=\left\|\sum_{j=1}^N a_j\nu_j\right\|^2\geq0,
\qquad \Sigma_{jj}=\|\nu_j\|^2=1.
$$
Its rank is two, which is admissible even though $N$ grows.

### H4

Pass: every linear combination of $T$ is the linear combination
$$
\sum_j a_jT_j=\left(\sum_ja_j\cos\gamma_j\right)Z_1+
\left(\sum_ja_j\sin\gamma_j\right)Z_2,
$$
which is centered normal with variance $a^{\mathsf T}\Sigma a$. Thus the entire vector is exactly jointly Gaussian.

### H5

Pass: $p_j=\overline\Phi(T_j)$ and $I_0^{(1)}=[N]$ are the prescribed one-sided p-values and null set. Each $T_j$ is marginally standard normal, so $\mathbb P(p_j\leq x)=x$ for $x\in[0,1]$.

### H6

Pass: use the largest qualifying BH rank, including multiplicities and non-strict thresholds, exactly as defined in the context pack.

### H7

Pass: all rejections are false discoveries, hence $V=R$ and
$$
\operatorname{FDR}=\mathbb P(R>0).
$$
The expectation is under the joint law specified in the object.

### NOT

Fail: in fact $\operatorname{FDR}\leq5q$ for every $q\in(0,1/4)$, so its ratio to $q\sqrt{\log(1/q)}$ tends to zero. The following argument bounds the exact finite arrays rather than only a continuum approximation.

Put $W=\sqrt{Z_1^2+Z_2^2}$ and, for $t>0$, define the fraction of a continuous circle exceeding threshold $t$ at radius $w$ by
$$
g(t,w)=\begin{cases}
\pi^{-1}\arccos(t/w),&w\geq t,\\
0,&w<t.
\end{cases}
$$
For every realization and every $t>0$, the equally spaced angular grid satisfies
$$
\frac1N\#\{j:T_j\geq t\}\leq g(t,W)+\frac2N.
$$
Indeed the exceeding directions form one closed circular arc, and the number of equally spaced grid points in such an arc differs from its length times $N/(2\pi)$ by at most two.

First bound the continuous-circle crossing event
$$
E_\alpha=\{\exists t>0:\overline\Phi(t)\leq\alpha g(t,W)\},\qquad 0<\alpha<1.
$$
For a crossing it is necessary that $t>z_{\alpha/2}$, where $z_x=\overline\Phi^{-1}(x)$, and elementary inversion gives
$$
E_\alpha=\{W\geq w_\alpha\},\qquad
w_\alpha=\min_{t>z_{\alpha/2}}
\frac{t}{\cos(\pi\overline\Phi(t)/\alpha)}.
$$
The minimum is attained at some $t_\alpha$: the displayed continuous function tends to infinity at both ends of its domain. At a minimizer,
$$
g(t_\alpha,w_\alpha)=\frac{\overline\Phi(t_\alpha)}{\alpha}.
$$
An independent uniform direction has a standard normal projection of $(Z_1,Z_2)$, so
$$
\mathbb E[g(t_\alpha,W)]=\overline\Phi(t_\alpha).
$$
Since $g(t_\alpha,w)$ is nondecreasing in $w$,
$$
\overline\Phi(t_\alpha)
\geq \mathbb P(W\geq w_\alpha)
\frac{\overline\Phi(t_\alpha)}{\alpha},
\qquad\text{and hence}\qquad
\mathbb P(E_\alpha)\leq\alpha.
$$

Return to the finite BH procedure. If a qualifying rank $k\geq4$ exists, put $t_k=z_{qk/N}>0$. Then at least $k$ coordinates exceed $t_k$, and the angular discrepancy gives
$$
g(t_k,W)\geq\frac{k-2}{N}\geq\frac{k}{2N}
=\frac{\overline\Phi(t_k)}{2q}.
$$
Thus this event is contained in $E_{2q}$, whose probability is at most $2q$. Otherwise a positive largest qualifying rank is at most three, which implies $\min_j p_j\leq3q/N$. The union bound and marginal uniformity give probability at most $3q$. Combining the cases proves
$$
\operatorname{FDR}=\mathbb P(R>0)\leq2q+3q=5q,
\qquad
\limsup_{q\downarrow0}
\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}=0.
$$
This obstruction covers the balanced planar grid only. It does not address arbitrary angular weights, heterogeneous means, alternatives, or general higher-rank covariance.

## Failure

NOT fails: the exact growing-dimensional rank-two angular-grid family has FDR at most $5q$, which is negligible on the proposed asymptotic scale.
