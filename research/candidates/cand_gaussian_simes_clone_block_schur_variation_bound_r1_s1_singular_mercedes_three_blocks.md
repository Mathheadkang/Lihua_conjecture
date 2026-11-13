---
type: candidate
title: Three clone blocks with singular equiangular Gamma (off-diagonal -1/2)
status: failed
target_asset: gaussian_simes_clone_block_schur_variation_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 9745c7f1d8f7ae5518e033eec521fe69f3dee7d75adf2262924621d839195795
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T00:55:54.198Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$K=3$, $\Gamma=\begin{pmatrix}1&-\tfrac12&-\tfrac12\\-\tfrac12&1&-\tfrac12\\-\tfrac12&-\tfrac12&1\end{pmatrix}$. This is the Gram matrix of three unit vectors at $120^\circ$ in $\mathbb R^2$; it is singular (eigenvalues $0,\tfrac32,\tfrac32$), and the block scores satisfy $Y_1+Y_2+Y_3=0$ at $t=0$. Any block sizes $n_1,n_2,n_3\ge1$, $N=n_1+n_2+n_3$, any $q\in(0,1/2)$. Here, unlike the antipodal candidates, all three pair correlations move along the path, each $\rho_t=-\tfrac12+\tfrac34t$.

## Checks

### H1

$N$ and $K=3$ are positive integers.

### H2

$\Gamma\in\mathcal C_3$ (unit diagonal, eigenvalues $\ge0$), so $\Sigma_{ij}=\Gamma_{a(i)a(j)}$ is a clone-block covariance with at most $3$ blocks.

### H3

$q\in(0,1/2)$ by choice.

### NOT

Fails. Numerically (orthant inclusion-exclusion with trivariate normal CDFs, 21-point grid in $t$, $n=(1,1,1)$):

- $q=0.45$: $f(0)\approx0.4844$, $f(1)\approx0.4162$, one turning point, $\mathcal V/q\approx0.18$;
- $q=0.01$: $f(0)\approx0.0100$, $f(1)\approx0.00991$, one turning point, $\mathcal V/q\approx0.0095$.

Both values are far below $K^24^K=576$. Rigorously, the profile is continuous with values in $[0,3q]$. The pairwise Plackett corner bound (each pair correlation is linear in $t$; each corner of a two-dimensional section costs at most $\int\varphi_2\,d\rho\le\overline\Phi(\max(x,y))\le q$) gives $\mathcal V\le\binom32\cdot7^2q=147q<576q$. This argument is sketched in idea_83407c80a0c7 and was not checked in full.

## Failure

NOT fails: all three pairs move, but the profile has one turning point, and its variation is about $0.2q$ or less in the computed cases, far below $576q$.
