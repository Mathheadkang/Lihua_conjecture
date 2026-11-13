---
type: candidate
title: >-
  Equality case Q_ij=0 across clusters with entrywise nonnegative covariance
  (null twins of alternatives)
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

$Y$ constant. Any admissible model whose covariance is entrywise nonnegative, $\Sigma_{ij}\ge0$ for all $i,j$, with $\Sigma_{ij}=0$ for nulls $i\ne j$ in distinct clusters of the chosen partition $\mathcal C$ of $I_0\neq\varnothing$ (equality case of sign-split). Concrete instance: $N=2n_0$, independent nulls $T_i=Z_i$ ($i\le n_0$, $\theta_i=0$), each with a perfectly correlated alternative twin $T_{n_0+i}=Z_i+\delta$, $\delta>0$ ($\Sigma_{i,n_0+i}=1$), singleton clusters. Any $q\in(0,q_2]$.

The twin makes every null rejection come with extra rejections that are perfectly tied to it, the degenerate correlation $+1$ between a null and an alternative.

## Checks

### H1

$\Sigma$ is a unit-diagonal Gram matrix (singular in the instance), null means $\le0$, $I_0\ne\varnothing$.

### H2

By choice.

### H3

$Y$ constant.

### H4

$Q=\Sigma_{I_0I_0}$; cross-cluster entries are $0\le0$ (in the instance $Q=I_{n_0}$).

### NOT

Right side $\ge C_2q+C_2q$, since $K\ge1$ gives $\min\{1,qK\}\ge q$.

Left side: for Gaussian $T$ with $\Sigma\ge0$ entrywise, the law of $T$ given $T_i=x$ is $\mathcal N(\theta+\Sigma_{\cdot i}(x-\theta_i),\Sigma-\Sigma_{\cdot i}\Sigma_{i\cdot})$: a shift by the nonnegative vector $\Sigma_{\cdot i}(x-\theta_i)$ with $x$-free covariance, hence stochastically increasing in $x$. Since $p=\overline\Phi(T)$ is coordinatewise decreasing, the p-values are PRDS on $I_0$, and null p-values are superuniform. Benjamini-Yekutieli (2001, Theorem 1.2; the proof only uses $\mathbb P(p_i\le qk/N)\le qk/N$ and PRDS) gives $\operatorname{FDR}\le qn_0/N\le q$. Hence $\mathbb E[\operatorname{FDP}\mathbf 1_{E_0^c}]\le q\le C_2q$ for $C_2\ge1$. The conclusion holds.

## Failure

NOT fails: entrywise nonnegative $\Sigma$ (which covers every zero-cross-covariance null partition whose alternatives load nonnegatively) is PRDS, so FDR $\le q n_0/N$.
