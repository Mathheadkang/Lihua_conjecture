---
type: candidate
title: >-
  Clump with one rejected and one large non-rejected member (rank jump when
  clumpmate is zeroed)
status: failed
target_asset: bh_clump_bracket_pathwise_bound
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
statement_digest: 505283800a561693969245cf14db866c63b7fbf613631c942f088194185139db
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:34:40.168Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$N=3$, $q=1/2$, $p=(1/6,\,0.9,\,1/2+1/1000)$, $I_0=S=\{1,2\}$, one clump $K_1=\{1,2\}$. Here $R=1$ (only $p_1\le q/3$ qualifies), but zeroing the clump in $p^{(i,*)}$ raises the count: a rank jump. The non-rejected clump member $2$ could, in principle, have both a large $R_{2,*}$ and a small denominator.

## Checks

### H1

$N=3$, $q\in(0,1)$, $p\in[0,1]^3$: pass.

### H2

Sorted $1/6,\,0.501,\,0.9$ vs thresholds $1/6,1/3,1/2$: only $k=1$ qualifies, $R=1$, $\mathcal R=\{1\}$: pass.

### H3

$S\subseteq I_0$: pass.

### H4

$K_1=S$ nonempty: pass.

### NOT

LHS $=1/1=1$. $p^{(i,*)}=(0,0,0.501)$: $R_{i,*}=2$, threshold $qR_{i,*}/N=1/3$.
- $i=1$: indicator $1/6\le1/3$ holds; $p^{(1,0)}=(0,1,0.501)$, $R_{1,0}=1$; $D_1=1$; $Np_1/q=1$; $\Psi_1=1$.
- $i=2$: indicator $0.9\le 1/3$ fails; $\Psi_2=0$.

RHS $=1=$ LHS. Equality; NOT fails. The rank jump enlarges $R_{i,*}$, but $\Psi_2$ is killed by its own indicator, and the rejected member alone already gives $1/R$.

## Failure

NOT fails: the rejected member $i$ contributes $\Psi_i\ge 1/R$ on its own (nonnegative extra terms cannot hurt); equality here.
