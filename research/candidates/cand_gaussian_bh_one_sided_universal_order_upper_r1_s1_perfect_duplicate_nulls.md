---
type: candidate
title: Singular perfectly duplicated null family with rapidly growing test count
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 334aaf8c5303a807be8f3b8e641f2fb7a35d5a6a6a5fe8080f4f22262e996d7f
performed_by: unknown
created_at: '2026-11-06T23:27:18.964Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le e^{-1}$, take the finite integer $N(q)=\lceil\exp(1/q)\rceil$, set $\theta=0\in\mathbb R^{N(q)}$, let $Z\sim\mathcal N(0,1)$, and put $T_i=Z$ for all $i$. Thus $\Sigma=\mathbf 1\mathbf 1^{\mathsf T}$ is singular of rank one and every hypothesis is a true null. Apply the ordinary largest-qualifying-rank BH procedure at level $q$.

## Checks

### H1

For each displayed $q$, $N(q)$ is a positive finite integer. It grows with $q\downarrow0$, which is permitted by the target.

### H2

The vector is exactly jointly Gaussian: for every $a\in\mathbb R^{N(q)}$, $a^{\mathsf T}T=(\sum_i a_i)Z$ is centered normal, with variance zero allowed. The mean vector is the finite real vector zero.

### H3

For every $a$, $a^{\mathsf T}\Sigma a=(\sum_i a_i)^2\ge0$, and $\Sigma_{ii}=1$. Singularity is explicitly admissible.

### H4

Each true-null mean is zero and hence satisfies the one-sided convention $\theta_i\le0$. All one-sided p-values equal $P=\overline\Phi(Z)$, which is uniform on $(0,1)$.

### H5

Use the target's non-strict, largest-rank BH rule, including multiplicities. If $P\le q$, rank $N(q)$ qualifies and $R=V=N(q)$. If $P>q$, no rank can qualify because $qk/N(q)\le q<P$ for every $k$; then $R=V=0$. This calculation covers equality at $P=q$ as well, an event of probability zero.

### NOT

The exact FDR is $\Pr(P\le q)=q$. Therefore
$$
\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}=\frac1{\sqrt{\log(1/q)}}\longrightarrow0.
$$
In particular, this family's FDR is bounded by $q\sqrt{\log(1/q)}$ for every $q\le e^{-1}$ and does not refute existence of a finite universal constant. This check makes no statement about other covariance structures.

## Failure

NOT fails: even arbitrarily fast growth of the duplicated test count leaves exact FDR equal to $q$; the normalized FDR tends to zero.
