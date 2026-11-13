---
type: candidate
title: All p-values tied at the level q with a two-point clump (equality case)
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

$N=3$, $q=1/2$, $p=(1/2,1/2,1/2)$ (all tied at $q$), $I_0=S=\{1,2\}$, one clump $K_1=\{1,2\}$. Ties make $D_i=|K_1|$ for both members, and the non-strict threshold $p_{(3)}\le 3q/3$ is attained with equality.

## Checks

### H1

$N=3$, $q\in(0,1)$, $p\in[0,1]^3$: pass.

### H2

All order statistics equal $1/2$; only $k=3$ qualifies ($1/2\le 1/2$), so $\widehat k=3$, $R=3$: pass.

### H3

$S\subseteq I_0$: pass.

### H4

$K_1=S$ nonempty: pass.

### NOT

LHS $=2/3$. For $i\in K_1$: $p^{(i,*)}$ has two zeros and one $1/2$, so $R_{i,*}=3$ and $p_i=1/2\le qR_{i,*}/N=1/2$ holds. $p^{(1,0)}=(0,1,1/2)$: order statistics $0,1/2,1$ with thresholds $1/6,1/3,1/2$; only $k=1$ qualifies, $R_{1,0}=1$; similarly $R_{2,0}=1$. $D_1=D_2=2$ (tie). $Np_i/q=3$. So $\Psi_1=\Psi_2=1/3$ and RHS $=2/3=$ LHS. Equality, not violation; NOT fails.

(Exhaustive check: this tied configuration also gives equality for the full clump $S=K_1=\{1,2,3\}$, LHS $=$ RHS $=1$.)

## Failure

NOT fails: equality holds; the term $Np_i/q$ equals $R$ exactly when $p_i$ is on the final threshold, which is the tight case of $\Psi_i\ge 1/R$.
