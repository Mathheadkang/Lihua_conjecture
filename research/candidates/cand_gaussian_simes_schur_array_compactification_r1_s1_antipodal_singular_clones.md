---
type: candidate
title: 'Singular antipodal two-type model with ties and clones, against parts 3 and 4'
status: failed
target_asset: gaussian_simes_schur_array_compactification
checks:
  H1: pass
  H2: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 3ff8e143d2d88073822e605c70956af7082d952917d813001866b18b04299581
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T05:51:19.466Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$\sigma=1/2$, $q=1/4$ (the boundary value), $N=2$, $\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$. This $\Sigma$ is singular, it lies on the boundary of $\mathcal C_2$, and the value $C_{ij}=-1$ is the edge of the allowed range. In $P_\Sigma$, equal indices $I_a=I_b$ give exact clones ($C_{ab}=1$), so $p$-values are tied with multiplicity. The path is $R^\Sigma_t$ with off-diagonal entry $2t-1$: it passes through $I_2$ at $t=1/2$ and reaches the rank-one $J$ at $t=1$.

## Checks

### H1

$\sigma=1/2\in(0,1)$: pass.

### H2

$q=1/4\in(0,1/4]$: pass.

### NOT

Fails. Each part was checked on this object.

- **Part 1.** For $x\in[-1,1]$, $g_t(x)\in[-1,1]$: $g_t(-1)=2t-1$ and $g_t(1)=1$. Where $t\ge1/3$ the interior minimum is $-(1-t)^2/(4t)\ge-1/3$. Also $(1-t)C+t\,C\circ C$ is PSD with unit diagonal (Schur product theorem), so $S_tP\in\mathfrak P_0$.
- **Part 4.** For $I_a\ne I_b$, $g_t(-1)=2t-1=(R^\Sigma_t)_{12}$. For clones, $g_t(1)=1=(R^\Sigma_t)_{11}$, so $S_tP_\Sigma=P_{R^\Sigma_t}$. Given type multiplicities $w_j=m_j/n\to1/2$, the clone Simes event is $\max_{j\text{ present}}[\sum_iw_i\mathbf 1\{p_i\le p_j\}-p_j/q]\ge0$. This is continuous in $w$ except where $p_j=qk/2$, which is a null set. So $\Phi_{n,\sigma}(P_\Sigma)\to F_q(\text{loaded }\Sigma)$ by dominated convergence, and ties inside $\Sigma$ itself (here $T_1=-T_2$ gives no ties, while clones give exact ties) are counted with multiplicity on both sides. Monte Carlo ($2\times10^5$ draws for $F_q$; 60 index draws $\times$ 4000 for $\Phi_n$): $F_q(\text{loaded }\Sigma)\approx0.2551$, and $\Phi_n\approx0.2540, 0.2573, 0.2568$ at $n=5,40,400$. These agree within error.
- **Part 3.** $S_1P_\Sigma=P_J$, the loaded covariance is $J$, all $p$-values are equal, and $F_q=q$ exactly (Monte Carlo $0.2494$). This is consistent with $\le q$. The loaded midpoint $t=1/2$ gives equicorrelation $\sigma^2$ in dimension 2, with value about $0.241$.
- **Parts 5 and 6.** $F_q(\text{loaded }\Sigma)\approx0.255>q$ is attained by $P_\Sigma$, and it is at most $B^\sigma(q)$ by inclusion in $\mathcal C_2$.

## Failure

NOT fails: the singular antipodal boundary, the exact clone ties, and the endpoint $q=1/4$ all satisfy parts 1, 3 and 4. The clone-weighted Simes event converges off the null set $\{p_j=qk/N\}$.
