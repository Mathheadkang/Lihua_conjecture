---
type: candidate
title: Staircase p-values at the BH boundary with one clump equal to all coordinates
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

$N=3$, $q=1/2$, $I_0=S=\{1,2,3\}$, one clump $K_1=S$, and the staircase vector $p=(q/3,\,2q/3,\,q)=(1/6,1/3,1/2)$, where every order statistic sits exactly on its BH threshold $qk/N$. Removing (setting to $1$) any rejected coordinate makes the BH count collapse, which is the mechanism that could make $R_{i,0}$ small.

## Checks

### H1

$N=3\ge1$, $q=1/2\in(0,1)$, $I_0\subseteq\{1,2,3\}$, $p\in[0,1]^3$: pass.

### H2

$\mathcal R_q(p)$ is ordinary BH: $p_{(k)}=qk/3$ for $k=1,2,3$, so $\widehat k=3$ and $R=3$: pass.

### H3

$S\subseteq I_0$: pass.

### H4

$K_1=S$ is a nonempty partition of $S$: pass.

### NOT

LHS $=3/3=1$. For every $i$, $p^{(i,*)}=(0,0,0)$, so $R_{i,*}=3$ and the indicator $p_i\le qR_{i,*}/N=1/2$ holds.
- $i=1$: $p^{(1,0)}=(0,1,1)$, $R_{1,0}=1$; $D_1=1$; $Np_1/q=1$; $\Psi_1=1$.
- $i=2$: $p^{(2,0)}=(1,0,1)$, $R_{2,0}=1$; $D_2=2$; $Np_2/q=2$; $\Psi_2=1/2$.
- $i=3$: $p^{(3,0)}=(1,1,0)$, $R_{3,0}=1$; $D_3=3$; $Np_3/q=3$; $\Psi_3=1/3$.

RHS $=11/6>1=$ LHS. The collapse $R_{i,0}=1$ only enlarges $\Psi_i$; the conclusion holds, so NOT fails.

## Failure

NOT fails: a small $R_{i,0}$ makes $\Psi_i$ larger, not smaller; and for each rejected $i$ one has $R_{i,0}\le R$, $D_i\le R$, $Np_i/q\le R$, $R_{i,*}\ge R$, so $\Psi_i\ge1/R$.
