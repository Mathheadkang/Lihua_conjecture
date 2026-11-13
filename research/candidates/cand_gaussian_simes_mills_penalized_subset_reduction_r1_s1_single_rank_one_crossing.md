---
type: candidate
title: >-
  Single crossing at rank 1 exactly at its threshold, all other coordinates very
  negative
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

$A=2$, $q=e^{-1}/2$, $N=5$,
$$
t_1=\overline\Phi^{-1}(q/N)\approx1.7892418,\qquad t_2=\cdots=t_5=-30 .
$$
So $p_{(1)}=q/N$ exactly and $p_{(j)}=\overline\Phi(-30)\approx1$ for $j\ge2$; the only crossing is at rank $k=1$, with equality. The very negative coordinates make every subset containing them useless, which is the adversary's best choice for making $M_A$ small.

## Checks

### H1
$N=5$, $t\in\mathbb R^5$.

### H2
$A=2$.

### H3
$q=e^{-1}/A$.

### H4
$p_{(1)}=q\cdot1/N$, equality at $k=1$.

### NOT
Right side $=-\tfrac12$. For $K=\{1\}$: $\kappa_K=1/5$, $z_K=\overline\Phi^{-1}(0.1)\approx1.2815516$, $\tau_A(K)=h(z_K)\approx1.7549833$, $X_K=t_1$, so
$$
\tau_A(K)\bigl(t_1-\tau_A(K)\bigr)\approx1.75498\times0.034259\approx0.060123>-\tfrac12 .
$$
Exhaustive maximum over the 31 subsets: $M_A(t)=0.060123$. NOT fails.

## Failure

NOT fails: $M_A(t)\approx0.0601>-1/2$; the singleton $K=\{1\}$ already has $t_1>z_K$ and the penalty $\tau(\tau-z)=h'(z_K)<1$.
