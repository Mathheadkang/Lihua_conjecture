---
type: candidate
title: Two antipodal clone blocks (singular Gamma with Gamma_12 = -1)
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

$K=2$, $\Gamma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$ (singular, the equality case $|\Gamma_{12}|=1$), block sizes $n_1,n_2\ge1$ arbitrary, $N=n_1+n_2$, $a(i)=1$ for $i\le n_1$ and $a(i)=2$ otherwise, $\Sigma_{ij}=\Gamma_{a(i)a(j)}$, any $q\in(0,1/2)$. Then $\Sigma\circ\Sigma=J_N$ (all ones), so the path goes from two antipodal clone groups to a single clone group of size $N$; the block correlation is $\rho_t=-1+2t$.

## Checks

### H1

$N=n_1+n_2$ is a positive integer, $K=2$ a positive integer.

### H2

$\Gamma\in\mathcal C_2$ (eigenvalues $0,2$, unit diagonal), so $\Sigma\in\mathcal C_N$ is a clone-block covariance with at most $2$ blocks.

### H3

$q\in(0,1/2)$ by choice.

### NOT

Fails: $\mathcal V(f_{q,\Sigma})\le 2q<64q=K^24^Kq$.

Let $(X,Y)$ be the two block scores, correlation $\rho$, and put $u_j=\overline\Phi^{-1}(qn_j/N)$, $c=\overline\Phi^{-1}(q)>0$ (since $q<1/2$), so $c\le u_1,u_2$. With clones, Simes rejects iff $X\ge u_1$ or $Y\ge u_2$ or ($X\ge c$ and $Y\ge c$) (a block with p-value $p$ is rejected at multiplicity $n_j$ alone, or both at total multiplicity $N$). Inclusion-exclusion gives
$$
f(\rho)=\overline\Phi(u_1)+\overline\Phi(u_2)+P_\rho(c,c)-P_\rho(u_1,c)-P_\rho(c,u_2),\qquad P_\rho(x,y)=\mathbb P_\rho(X\ge x,Y\ge y).
$$
Endpoint values: at $\rho=-1$ the square is empty ($p_X+p_Y=1>2q$) and the two half-lines are disjoint, so $f=qn_1/N+qn_2/N=q$; at $\rho=1$ the $N$ p-values coincide and $f=q$.

By Plackett's identity $\partial_\rho P_\rho(x,y)=\varphi_2(x,y;\rho)\ge0$, so
$$
\mathcal V(f)\le\int_{-1}^{1}\bigl[\varphi_2(c,c;\rho)+\varphi_2(u_1,c;\rho)+\varphi_2(c,u_2;\rho)\bigr]d\rho ,
$$
and $\int_{-1}^1\varphi_2(x,y;\rho)\,d\rho=P_1(x,y)-P_{-1}(x,y)\le\overline\Phi(\max(x,y))$. Hence $\mathcal V(f)\le\overline\Phi(c)+\overline\Phi(u_1)+\overline\Phi(u_2)=q+qn_1/N+qn_2/N=2q$.

Numerical check (bivariate normal CDF, 120-point grid in $t$): $\mathcal V(f)/q\approx0.52,0.28,0.02,0.43$ for $(n_1,n_2)=(1,1),(1,5),(1,100),(3,7)$ at $q=0.49$, and $\approx0.37,0.20,0.012,0.31$ at $q=10^{-3}$; $\mathcal V_-/q$ is about half of these.

## Failure

NOT fails: Plackett's identity bounds the variation by the three corner tails, at most $2q$, far below $64q$.
