---
type: candidate
title: Zero-one correlation matrices are fixed points of the Schur-square path
status: failed
target_asset: gaussian_simes_schur_square_sparse_variation_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 86f7bdd265309432fe20f975ae839c30202be6cc9ff8b792c372f7c4362c61e9
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T00:43:09.753Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Any $q\in(0,1/4]$, any $N\ge1$, and any $\Sigma\in\mathcal C_N$ with all entries in $\{0,1\}$. This covers the degenerate extremes $\Sigma=I_N$ (independence), $\Sigma=J_N$ (all clones, rank one), $N=1$, and every exact-clone partition (block-diagonal $J$ blocks, singular allowed).

Checks: H1 is $q\in(0,q_V]$ (any $q_V\le 1/4$ may be met by choosing $q$ small), H2 is $N\ge1$, H3 is $\Sigma\in\mathcal C_N$. NOT asks that $\mathcal V_-(f_{q,\Sigma})>1-\eta$ for the given universal $\eta$; to refute the existential statement a family must make $\mathcal V_-$ approach $1$ at arbitrarily small $q$.

## Checks

### H1

$q$ is free in $(0,1/4]$, so it can be taken below any proposed $q_V$.

### H2

$N\ge1$ by choice.

### H3

A $\{0,1\}$ correlation matrix with unit diagonal that is positive semidefinite is exactly the matrix of an equivalence relation (clone classes), $\Sigma=\sum_c \mathbf 1_{B_c}\mathbf 1_{B_c}^{\mathsf T}$, which is PSD with unit diagonal. So $\Sigma\in\mathcal C_N$.

### NOT

Since $\rho_{ij}\in\{0,1\}$, $\rho_{ij}^2=\rho_{ij}$, so $\Sigma\circ\Sigma=\Sigma$ and $R_t^\Sigma=\Sigma$ for every $t\in[0,1]$. Hence $f_{q,\Sigma}$ is constant and $\mathcal V_-(f_{q,\Sigma})=0\le1-\eta$. The conclusion holds.

Additional degenerate remark: the sparse-rank condition $qk/N<\overline\Phi(u_q+1)$ needs $k<N\overline\Phi(u_q+1)/q$, and $\overline\Phi(u_q+1)<\overline\Phi(u_q)=q$. So for $N=1$, and more generally whenever $N\le q/\overline\Phi(u_q+1)$, there is no sparse rank, $S_q=\emptyset$, $f_{q,\Sigma}\equiv0$ and $\mathcal V_-=0$ for every $\Sigma$. Fixed $N$ with $q\to0$ therefore never gives a counterexample.

## Failure

NOT fails: $\Sigma\circ\Sigma=\Sigma$ for $\{0,1\}$ entries, so the path is constant and $\mathcal V_-=0$.
