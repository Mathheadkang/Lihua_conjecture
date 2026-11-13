---
type: candidate
title: >-
  Comonotone null block with equal null means as one cluster, constant carrier,
  adversarial Gaussian alternatives
status: failed
target_asset: gaussian_bh_sign_split_cluster_steering_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 4f504776ef9d05ca6e613df26ad574964aa50a24ff5098db3d1c7b8692792457
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T21:45:47.957Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$N\ge1$, $1\le n_0\le N$, $I_0=\{1,\ldots,n_0\}$, all null coordinates identical: $T_i=\mu+Z$ for $i\in I_0$ with a common $\mu\le0$ and $Z\sim\mathcal N(0,1)$ (so $\Sigma_{I_0I_0}=J$, the all-ones block). The alternatives $T_j$, $j>n_0$, are arbitrary with $\theta_j>0$ and arbitrary (possibly singular, possibly negative) correlation with $Z$, e.g. the classical steering choice $T_j=\theta_j-Z$ designed so that the number of rejected alternatives shrinks as the null p-value decreases. $Y$ constant ($m=0$), $\mathcal C=\{I_0\}$ (one cluster, the coarsest partition, so the sign-split condition is vacuous). Any $q\in(0,q_2]$.

This is the degenerate extreme "all nulls in one cluster, perfectly tied".

## Checks

### H1

$\Sigma$ is a Gram matrix with unit diagonal, $\theta_i=\mu\le0$ on $I_0$; admissible, $I_0\ne\varnothing$.

### H2

By choice.

### H3

$Y$ constant is jointly Gaussian with $T$.

### H4

One cluster: there are no pairs in distinct clusters, so the sign-split condition holds vacuously. $Q=\Sigma_{I_0I_0}=J$.

### NOT

Right side: all null p-values equal $p=\overline\Phi(\mu+Z)$, and $\mathbb P(p\le t)\le t$. So $\Gamma(t)=n_0\mathbb P(p\le t)/(Nt)\le n_0/N\le1$ and $K\equiv1$; the right side equals $C_2q+C_2q=2C_2q$.

Left side (bounded without even using $E_0^c$): nulls are rejected all together, $V\in\{0,n_0\}$, and $V=n_0$ forces $R=k\ge n_0$ and $p\le qk/N$. With bands $B_j=(q(j-1)/N,qj/N]$,
$$
\mathbb E[\operatorname{FDP}]=\sum_{k\ge n_0}\frac{n_0}{k}\mathbb P(p\le qk/N,R=k)
\le\sum_{j=1}^N\frac{n_0}{\max(j,n_0)}\mathbb P(p\in B_j)
\le\frac qN\Bigl(n_0+\sum_{j=n_0+1}^N\frac{n_0}{j}\Bigr)\le q\,x(1+\ln(1/x))\le q,
$$
with $x=n_0/N$ (the first inequality uses $j\le k\Rightarrow n_0/k\le n_0/\max(j,n_0)$ and disjointness of $\{R=k\}$). So $\mathbb E[\operatorname{FDP}\mathbf 1_{E_0^c}]\le q\le 2C_2q$ for any $C_2\ge1/2$, whatever the alternatives. The conclusion holds.

## Failure

NOT fails: a perfectly tied null block contributes at most $q\,x(1+\ln(1/x))\le q$ to the FDR (band/BY argument), while $K\equiv1$ keeps the right side at $2C_2q$.
