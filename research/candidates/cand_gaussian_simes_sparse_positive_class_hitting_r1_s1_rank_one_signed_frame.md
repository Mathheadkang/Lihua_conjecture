---
type: candidate
title: 'Rank-one signed covariance (two antipodal all-equal clusters, singular)'
status: failed
target_asset: gaussian_simes_sparse_positive_class_hitting
checks:
  H1: pass
  H2: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 890cfc3a9c9940c136cc16ee0457d5a898e3cb8394ae61c9b578e3710d695ad7
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T21:27:45.478Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Fix any candidate constants $\delta_0\in(0,1]$, $c_{\mathrm{hit}},c_*\in(0,1]$, $\alpha_1\in(0,1/4]$ and any $\alpha\in(0,\alpha_1]$. Take $N\ge1$, a sign vector $v\in\{\pm1\}^N$, $P=\{i:v_i=1\}$, $M=\{i:v_i=-1\}$, $a=|P|$, $b=|M|$, and the rank-one matrix $\Sigma=vv^{\mathsf T}$. Then $T_i=v_iZ$ with $Z\sim\mathcal N(0,1)$. This is the degenerate extreme of signed frames: every correlation is $\pm1$, rank $1$. (With $b=0$ it is $\Sigma=J$.)

## Checks

### H1

$\Sigma=vv^{\mathsf T}$ is symmetric, positive semidefinite, with $\Sigma_{ii}=v_i^2=1$; so $\Sigma\in\mathcal C_N$ (singular for $N\ge2$, which is allowed).

### H2

$\alpha\in(0,\alpha_1]$ with $\alpha_1\le1/4$, $N$ a positive integer: pass for every choice.

### NOT

NOT requires, for every probability measure $\pi$ on positive classes, $\mathbb P(E_\alpha\setminus D_{\alpha,\delta_0},h<c_*)>1/4$. Compute $\mathbb P(E_\alpha)$. All $p_i$, $i\in P$, equal $x=\overline\Phi(Z)$, all $p_i$, $i\in M$, equal $1-x$. Every BH threshold is $\le\alpha<1/2$ and $\min(x,1-x)\le1/2$ with $\max(x,1-x)\ge1/2$, so only one cluster can be counted. If $Z>0$, the count $\#\{i:p_i\le\alpha k/N\}$ is $a$ if $x\le\alpha k/N$ and $0$ otherwise, so a crossing exists iff $x\le\alpha a/N$ (take $k=a$). Hence $\mathbb P(E_\alpha,Z>0)=\mathbb P(\overline\Phi(Z)\le\alpha a/N)=\alpha a/N$, similarly $\mathbb P(E_\alpha,Z<0)=\alpha b/N$, and $\mathbb P(E_\alpha)=\alpha\le1/4$. So the probability in the conclusion is at most $1/4$ for every $\pi$: NOT fails.

Independently of this, the explicit prior $\pi=\tfrac12\delta_P+\tfrac12\delta_M$ ($\delta_P$ alone if $b=0$) works: $P,M$ are positive classes; on $E_\alpha$ the rejection set is one cluster, say $\mathcal A_\alpha=P$, $r_\alpha=a$, and $|\mathcal A_\alpha\cap P|=a\ge\max(1,c\,a\cdot a/N)$ because $a\le N$, $c\le1$. So $h\ge1/2$ on $E_\alpha$, and the bound holds with $c_*\le1/2$ even without using $\mathbb P(E_\alpha)\le1/4$.

## Failure

NOT fails: for a rank-one signed $\Sigma$ the Simes/BH global-null rejection probability is exactly $\alpha\le1/4$, and the two sign clusters are positive classes that a two-point prior hits with probability $1/2$.
