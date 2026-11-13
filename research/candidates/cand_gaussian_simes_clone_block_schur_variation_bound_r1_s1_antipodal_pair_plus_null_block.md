---
type: candidate
title: >-
  Antipodal block pair plus an uncorrelated third block (singular Gamma with
  entries in {0, -1, 1})
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

$K=3$, $\Gamma=\begin{pmatrix}1&-1&0\\-1&1&0\\0&0&1\end{pmatrix}$ (singular, eigenvalues $0,1,2$; one entry at the equality value $-1$, two at the zero value), block sizes $n_1,n_2,n_3\ge1$ arbitrary, $N=n_1+n_2+n_3$, $\Sigma_{ij}=\Gamma_{a(i)a(j)}$ for a map $a$ with these block sizes, any $q\in(0,1/2)$. Since $0^2=0$, only the pair $(1,2)$ moves: its correlation is $\rho_t=-1+2t$, and block 3 stays independent of blocks 1, 2 along the whole path.

## Checks

### H1

$N$ and $K=3$ are positive integers.

### H2

$\Gamma\in\mathcal C_3$ (unit diagonal, eigenvalues $0,1,2$), so $\Sigma\in\mathcal C_N$ is a clone-block covariance with at most $3$ blocks.

### H3

$q\in(0,1/2)$ by choice.

### NOT

Fails: $\mathcal V(f_{q,\Sigma})\le5q<576q=K^24^Kq$.

For a nonempty set $S$ of blocks put $w(S)=\sum_{b\in S}n_b/N$ and $\ell_S=\overline\Phi^{-1}(qw(S))\ge c:=\overline\Phi^{-1}(q)>0$. With clones, Simes rejects iff some nonempty $S$ has $Y_b\ge\ell_S$ for all $b\in S$, where $Y$ is the vector of block scores. Condition on $Y_3=z$ (independent of $(Y_1,Y_2)$ for every $t$). The section of the rejection set is either the whole plane (if $z\ge\ell_{\{3\}}$; then it does not depend on $\rho$) or the union of $A=\{y_1\ge\alpha\}$, $B=\{y_2\ge\beta\}$, $C=\{y_1\ge s,y_2\ge s\}$, with $\alpha,\beta,s$ minima of admissible levels (possibly $+\infty$), all $\ge c$. Inclusion-exclusion writes $1_{A\cup B\cup C}$ as half-planes (independent of $\rho$) plus five quadrant indicators with coefficients $\pm1$ and corners $(s,s)$, $(\alpha,\beta)$, $(\alpha\vee s,s)$, $(s,\beta\vee s)$, $(\alpha\vee s,\beta\vee s)$. By Plackett's identity, the conditional profile $h_z(\rho)$ satisfies $|h_z'(\rho)|\le\sum_{\text{5 corners}}\varphi_2(x,y;\rho)$, and $\int_{-1}^1\varphi_2(x,y;\rho)d\rho\le\overline\Phi(\max(x,y))\le\overline\Phi(c)=q$. As $\rho_t$ runs monotonically over $[-1,1]$, $\mathcal V(f)\le\mathbb E\,\mathcal V(h_{Y_3})\le5q$.

## Failure

NOT fails: only one block pair moves, the conditional section has at most five finite corners each with tail at most $q$, so the variation is at most $5q$, far below $576q$.
