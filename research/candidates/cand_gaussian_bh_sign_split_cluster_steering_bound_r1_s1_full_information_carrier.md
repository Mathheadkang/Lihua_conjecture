---
type: candidate
title: >-
  Full-information carrier Y=T with singleton clusters (Q=0, sign-split holds
  with equality)
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

Any admissible one-sided model $(N,\theta,\Sigma)$ with $I_0\neq\varnothing$, any $q\in(0,q_2]$, the carrier $Y=T$ ($m=N$), and the partition $\mathcal C$ of $I_0$ into singletons. This is the boundary case where the conditional null covariance vanishes, so every cross-cluster entry satisfies the sign-split condition with equality.

## Checks

### H1

Admissible model, one-sided p-values, $I_0$ nonempty: by choice.

### H2

$0<q\le q_2$: by choice.

### H3

$(T,Y)=(T,T)$ is jointly Gaussian.

### H4

$\operatorname{Cov}(T_{I_0},Y)=\Sigma_{I_0,[N]}$ and $\operatorname{Cov}(Y)=\Sigma$, so $Q=\Sigma_{I_0I_0}-(\Sigma\Sigma^{+}\Sigma)_{I_0I_0}=0$ because $\Sigma\Sigma^{+}\Sigma=\Sigma$. Hence $Q_{ij}=0\le0$ for all $i\ne j$; singletons are an admissible partition.

### NOT

Given $Y=T$ the canonical conditional law is the point mass at $T$, so $\mathbb P(p_i\le t\mid Y)=\mathbf 1\{p_i\le t\}$ and
$\Gamma(t;Y)=\#\{i\in I_0:p_i\le t\}/(Nt)$.
On $\{V\ge1\}$ put $\tau=qR/N\in(0,q]$. Every rejected null has $p_i\le\tau$. For rational $t\in(\tau,q]$ (or $t=q$ if $\tau=q$) we have $\Gamma(t;Y)\ge V/(Nt)$, and letting $t\downarrow\tau$ gives $K(Y)\ge V/(N\tau)=V/(qR)$. Thus $\min\{1,qK(Y)\}\ge \min\{1,V/R\}=\operatorname{FDP}$ pointwise (also trivially when $V=0$). Therefore
$\mathbb E[\operatorname{FDP}\mathbf 1_{E_0^c}]\le\mathbb E[\min\{1,qK(Y)\}]$,
so the conclusion holds with any $C_2\ge1$. The conclusion is not violated.

## Failure

NOT fails: with $Q=0$ the conditional intensity dominates the realized FDP pointwise, $\operatorname{FDP}\le\min\{1,qK(T)\}$.
