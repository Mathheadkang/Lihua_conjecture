---
type: candidate
title: 'Most negative equicorrelation (sum-zero projection, rank N-1)'
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

Fix $N\ge2$, $\xi\sim\mathcal N_N(0,I_N)$, $\bar\xi=N^{-1}\sum_j\xi_j$, $c=\sqrt{N/(N-1)}$, and $T_i=c(\xi_i-\bar\xi)$. Then $\Sigma=\frac{N}{N-1}(I-\frac1NJ)$ has $\Sigma_{ii}=1$ and $\Sigma_{ij}=-1/(N-1)$: the equality case of the bound $\rho\ge-1/(N-1)$ for equicorrelated matrices in $\mathcal C_N$, singular with $\sum_iT_i=0$. The level $q\in(0,1/4]$ is arbitrary.

## Checks

### H1

$N$ is a positive integer.

### H2

$\Sigma$ is $\frac{N}{N-1}$ times an orthogonal projection, hence symmetric positive semidefinite, with diagonal $\frac{N}{N-1}(1-\frac1N)=1$.

### H3

Any $q\in(0,q_S]$ with $q_S\le1/4$.

### NOT

$S_q$ is contained in the Simes rejection event $\{\exists k:p_{(k)}\le qk/N\}$. Asymptotically: on $\{|\bar\xi|\le N^{-1/3}\}$ (probability $1-o(1)$), $T_i\ge u$ implies $\xi_i\ge u/c-N^{-1/3}\ge u-\delta_N$ with $\delta_N=N^{-1/3}+u/N$, and for the relevant $u\le u_{1}=\overline\Phi^{-1}(q/N)=O(\sqrt{\log(N/q)})$ one has $u\delta_N\to0$, so $\overline\Phi(u-\delta_N)\le(1+o(1))\overline\Phi(u)$. Simes for i.i.d. $\xi$ at the inflated levels $(1+o(1))qk/N$ has probability $(1+o(1))q$. Hence $\mathbb P(S_q)\le q+o(1)$ as $N\to\infty$, and for bounded $N$ the event is empty unless $N>q/\overline\Phi(u_q+1)$, with $\mathbb P(S_q)\le\sum_{k\le K}q=qK$ by Markov at each rank. Monte Carlo (seed 1, $\mathbb P(S_q)$): $0.251,0.253$ at $q=1/4$; $0.100,0.100$ at $q=0.1$; $0.021,0.023$ at $q=0.02$ for $N=200,2000$, i.e. $\approx q$. The maximal negative equicorrelation is too weak (order $1/N$) to break the Simes level.

## Failure

NOT fails: the minimal equicorrelation $-1/(N-1)$ is an $O(N^{-1/2})$ common shift of i.i.d. coordinates, so $\mathbb P(S_q)\approx q\le1/4$.
