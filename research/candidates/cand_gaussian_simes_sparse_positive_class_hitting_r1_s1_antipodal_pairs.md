---
type: candidate
title: Independent antipodal pairs (correlation exactly -1 within pairs)
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

Any candidate constants and any $\alpha\in(0,\alpha_1]$. $N=2m$, $Y_1,\dots,Y_m$ iid $\mathcal N(0,1)$, $T_{2j-1}=Y_j$, $T_{2j}=-Y_j$. So $\Sigma$ is block diagonal with $m$ blocks $\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$ (rank $m$). The positive classes are exactly the nonempty sets containing at most one index from each pair (the equality case $\Sigma_{ij}=-1$ of the sign restriction).

## Checks

### H1

Block diagonal with PSD rank-one blocks $ww^{\mathsf T}$, $w=(1,-1)$, unit diagonal: $\Sigma\in\mathcal C_N$.

### H2

$\alpha\in(0,\alpha_1]$, $N=2m$ positive: pass.

### NOT

Within a pair the p-values are $x_j=\overline\Phi(|Y_j|)\le1/2$ and $1-x_j\ge1/2$; since thresholds are $\le\alpha<1/2$ only the $x_j$ can be counted, at most one per pair. Put $U_j=2x_j$, iid uniform on $[0,1]$. Then $\#\{i:p_i\le\alpha k/(2m)\}=\#\{j:U_j\le\alpha k/m\}$, so $E_\alpha$ is the Simes event for $m$ iid uniforms at level $\alpha$ and $\mathbb P(E_\alpha)=\alpha\le1/4$ (Simes equality under independence). Hence the probability in the conclusion is $\le1/4$ for every $\pi$: NOT fails.

The natural prior also works directly: $\pi$ uniform on the $2^m$ transversals (one index per pair, $|S|=m$). On $E_\alpha$ the $r_\alpha$ rejected indices lie in distinct pairs, so $|\mathcal A_\alpha\cap S|\sim\mathrm{Bin}(r_\alpha,1/2)$ under $\pi$, and the requirement is $|\mathcal A_\alpha\cap S|\ge\max(1,c\,m\,r_\alpha/(2m))=\max(1,c r_\alpha/2)$. For $r_\alpha=1$ this has $\pi$-probability $1/2$; for $r_\alpha\ge2$ it is implied by $\mathrm{Bin}(r_\alpha,1/2)\ge\lceil r_\alpha/2\rceil$, which has probability $\ge1/2$. So $h\ge1/2$ on $E_\alpha$.

## Failure

NOT fails: antipodal pairs halve the effective dimension and leave an exact independent Simes problem with $\mathbb P(E_\alpha)=\alpha$; uniform transversals are hit with probability at least $1/2$.
