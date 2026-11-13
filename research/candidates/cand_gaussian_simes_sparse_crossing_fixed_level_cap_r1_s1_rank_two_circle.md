---
type: candidate
title: Rank-two covariance with loadings spread uniformly on the circle
status: failed
target_asset: gaussian_simes_sparse_crossing_fixed_level_cap
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: e02ea4068f860cd39643c688ca2deec7a6b3a9f5aedc920fd92281c915d2d7f4
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:21:29.974Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Fix $N\ge2$, $G=(G_1,G_2)\sim\mathcal N_2(0,I_2)$, $\phi_i=2\pi i/N$, and $T_i=G_1\cos\phi_i+G_2\sin\phi_i$, so $\Sigma_{ij}=\cos(\phi_i-\phi_j)$ (rank two; all signs of correlation occur, including exact antipodes when $N$ is even). This is the next degenerate rank after the rank-one case and maximizes angular spread, so that every direction of $G$ meets a cap of loadings. The level $q\in(0,1/4]$ is arbitrary.

## Checks

### H1

$N$ is a positive integer.

### H2

$\Sigma=VV^{\mathsf T}$ with rows $v_i=(\cos\phi_i,\sin\phi_i)$, so $\Sigma$ is symmetric positive semidefinite with $\Sigma_{ii}=|v_i|^2=1$.

### H3

Any $q\in(0,q_S]$ with $q_S\le1/4$.

### NOT

A crossing at a sparse rank $k$ requires some $p_i\le qk/N<\overline\Phi(u_q+1)$, i.e. $T_i>u_q+1$. By Cauchy-Schwarz $T_i=\langle v_i,G\rangle\le|G|$, so
$$
S_q\subset\{|G|>u_q+1\},\qquad \mathbb P(S_q)\le\mathbb P(\chi^2_2>(u_q+1)^2)=e^{-(u_q+1)^2/2}.
$$
For $q\le1/4$ this is at most $e^{-(1.674)^2/2}<0.247$, uniformly in $N$ and in the loadings (the bound uses only rank two, not the uniform spacing). Monte Carlo (seed 1) for the uniform circle gives $\mathbb P(S_q)\approx0.135$ to $0.140$ at $q=1/4$, $\approx0.051$ at $q=0.1$, $\approx0.008$ at $q=0.02$, for $N=200$ and $N=2000$, below the bound $0.246$, $0.074$, $0.0094$.

## Failure

NOT fails: in rank two a sparse crossing forces $|G|>u_q+1$, so $\mathbb P(S_q)\le e^{-(u_q+1)^2/2}<0.247$ for every $N$ and every rank-two $\Sigma$.
