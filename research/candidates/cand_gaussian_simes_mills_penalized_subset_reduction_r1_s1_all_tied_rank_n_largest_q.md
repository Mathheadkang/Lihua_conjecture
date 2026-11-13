---
type: candidate
title: >-
  All p-values tied exactly at the threshold q (crossing at rank N, A = 2,
  largest allowed q)
status: failed
target_asset: gaussian_simes_mills_penalized_subset_reduction
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
statement_digest: d8696dc0ee5040d69e3a44c44fe818131df421b54610842f2b5ca99f0ec56f89
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T21:31:15.606Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$A=2$, $q=e^{-1}/A=e^{-1}/2\approx0.18393972$ (the largest allowed $q$, so $\log(1/(Aq))=1$), $N=5$ (also $N=1$), and every coordinate equal to the threshold value
$$
t_1=\cdots=t_N=u:=\overline\Phi^{-1}(q)\approx0.9004526 .
$$
All p-values are tied, $p_{(1)}=\cdots=p_{(N)}=q$, and the crossing holds with equality at rank $k=N$ (for $N=1$ also at rank $1$).

## Checks

### H1
$N=5$ is a positive integer and $t\in\mathbb R^5$.

### H2
$A=2\ge2$, the boundary value.

### H3
$q=e^{-1}/A>0$ and equals the upper bound $e^{-1}/A$.

### H4
$p_{(N)}=q=qN/N$, so $p_{(k)}\le qk/N$ holds with equality at $k=N$.

### NOT
The right side is $\tfrac12\sqrt{1}-1=-\tfrac12$. Take $K=\{1,\ldots,N\}$: $\kappa_K=1$, $z_K=\overline\Phi^{-1}(1/2)=0$, $\tau_A(K)=h(0)=2\phi(0)=\sqrt{2/\pi}\approx0.79788456$, $X_K=u$, so
$$
M_A(t)\ge\tau_A(K)\bigl(u-\tau_A(K)\bigr)\approx0.79788\times0.10257\approx0.08184>-\tfrac12 .
$$
An exhaustive maximum over all $31$ nonempty subsets (40-digit arithmetic) gives $M_A(t)=0.0818375$, attained at $K=[N]$. The conclusion holds; NOT fails. The case $N=1$ gives the same number.

## Failure

NOT fails: $M_A(t)\approx0.0818>-1/2$; at $q=e^{-1}/A$ the bound is negative while the full-set term is positive because $u>z_K$.
