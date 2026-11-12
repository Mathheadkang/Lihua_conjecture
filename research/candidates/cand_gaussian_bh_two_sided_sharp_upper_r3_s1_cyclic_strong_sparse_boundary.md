---
type: candidate
title: Sparse diverging signals paired with growing cyclic-difference nulls
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
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
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:19:50.244Z'
extension_version: 0.0.4
---

## Object

This candidate approaches the singular-covariance, vanishing-signal-proportion, and diverging-signal-mean boundaries simultaneously. Its growing number of distinct null p-values avoids the bounded-null-type obstruction. The initially concerning crude bound is of order $q m/k\asymp q\sqrt{\log(1/q)}$; the exact global-BH argument below gives a smaller order.

For every $q\in(0,e^{-4})$, define
$$
L=\log(1/q),\qquad m=\lceil q^{-2}\rceil,\qquad
k=\left\lceil\frac{m}{\sqrt L}\right\rceil,\qquad N=m+k.
$$
Let $Z_1,\ldots,Z_m$ be independent standard normal variables, write $Z_{m+1}=Z_1$, and set
$$
X_i=\frac{Z_i-Z_{i+1}}{\sqrt2},\qquad 1\le i\le m.
$$
Use the positive quantile $c$ and positive displacement $d$ given by
$$
2\overline\Phi(c)=\frac{qk}{N},\qquad
d=\sqrt{2\log(k/q^3)},\qquad \mu=c+d.
$$
The finite observation vector is
$$
T_i=X_i\quad(1\le i\le m),\qquad
T_{m+j}=\mu-X_j\quad(1\le j\le k).
$$
Thus $\theta=(0_m,\mu 1_k)$. Define the covariance explicitly as $\Sigma=AA^{\mathsf T}$, where the first $m$ rows of $A\in\mathbb R^{N\times m}$ are $(e_i-e_{i+1})/\sqrt2$ with cyclic indices, and row $m+j$ is the negative of row $j$. Compute $p_i=2\overline\Phi(|T_i|)$ and apply ordinary BH at level $q$ to the whole vector of $N$ p-values, retaining multiplicities.

## Checks

### H1

The dimension is a finite positive integer at every specified $q$, and all mean-vector entries are finite real numbers. Since $L>4$, $1\le k\le m$. Every displayed parameter is a deterministic function of $q$. The quantile exists because $qk/(2N)\in(0,1/2)$.

### H2

The representation $T=\theta+AZ$ proves exact joint Gaussianity. The matrix $AA^{\mathsf T}$ is symmetric positive semidefinite. Every row of $A$ has squared Euclidean norm one, so every diagonal entry of $\Sigma$ is one. The cyclic difference matrix has rank $m-1$; appending its negative rows preserves this rank. Hence the covariance is singular, as permitted, with rank tending to infinity. No limiting or non-Gaussian sampling approximation is used.

### H3

Because $c,d>0$, $\mu>0$ and the two-sided true-null set is exactly $I_0^{(2)}(\theta)=[m]$. Each $X_i$ is standard normal, so every null $p_i=2\overline\Phi(|X_i|)$ is exactly uniform on $(0,1)$. The formula for every nonnull p-value also uses the prescribed two-sided Gaussian transform.

### H4

Use the largest qualifying rank in ordinary BH, with thresholds $qr/N$, non-strict inequalities, and multiplicities. Write its global rejection count as $R$. Its false discoveries are $V=|\mathcal R_q\cap[m]|$. These are the quantities used below; no local block FDRs are added.

### H5

The candidate's FDR is the expectation under the preceding finite Gaussian law of $V/(R\vee1)$, with zero contribution when $R=0$. It therefore has exactly the target's sampling law and FDR convention. Here $k/N\to0$, while $\mu\to\infty$; the signal proportion and means genuinely approach their stated boundaries.

### NOT

The asymptotic conclusion does not fail. First define the event
$$
\mathcal A=\left\{p_{m+j}\le\frac{qk}{N}\text{ for every }1\le j\le k\right\}.
$$
For each nonnull coordinate, failure of its condition is equivalent to $|\mu-X_j|<c$, which implies $X_j>d$. Therefore the Gaussian Chernoff bound and a union bound give
$$
\mathbb P(\mathcal A^c)
\le k\overline\Phi(d)
\le k e^{-d^2/2}=q^3.
$$
On $\mathcal A$, there are at least $k$ p-values below $qk/N$, so the global BH crossing has $R\ge k$. For a null p-value $p$, introduce the deterministic envelope
$$
g(p)=
\begin{cases}
1/k,&0\le p\le qk/N,\\
1/r,&q(r-1)/N<p\le qr/N,\quad r=k+1,\ldots,N,\\
0,&p>q.
\end{cases}
$$
If that null is rejected on $\mathcal A$, then $p\le qR/N$ and $R\ge k$, hence its contribution $1/R$ to FDP is at most $g(p)$. This holds pointwise for the largest global crossing and does not assume any independence. With $H_n=\sum_{r=1}^n1/r$, exact null uniformity gives
$$
\mathbb E[g(p_i)]
=\frac qN\left(1+\sum_{r=k+1}^N\frac1r\right)
=\frac qN(1+H_N-H_k),\qquad i\in[m].
$$
Bounding FDP by one on $\mathcal A^c$, then summing the null contributions on $\mathcal A$, proves the finite-$q$ inequality
$$
\operatorname{FDR}_{\rm BH}^{(2)}
\le\frac{mq}{N}(1+H_N-H_k)+q^3
\le q\{1+\log(N/k)\}+q^3
\le q\{1+\log(\sqrt L+1)\}+q^3.
$$
The middle inequality uses $H_N-H_k\le\int_k^N dx/x$, and the last uses $k\ge m/\sqrt L$. Consequently
$$
0\le\frac{\operatorname{FDR}_{\rm BH}^{(2)}}{q\sqrt L}
\le\frac{1+\log(\sqrt L+1)+q^2}{\sqrt L}
\longrightarrow0.
$$
Thus this family cannot exceed the proposed positive leading constant asymptotically. The argument does not rule out inflation above $q$ at a fixed level. It excludes only the specified strong-signal boundary family, and supplies no conclusion about the unresolved weak common-gate construction.

## Failure

NOT fails: the global-BH truncated-harmonic envelope bounds this family's FDR by $q\{1+O(\log\log(1/q))\}+q^3=o(q\sqrt{\log(1/q)})$.
