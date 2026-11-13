---
type: candidate
title: Comonotone all-ones Sigma (all p-values tied) with c near q
status: failed
target_asset: gaussian_simes_positive_class_cover_transfer
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 6f5e1db93cf32b89012029bd947a756bef6f729d9d2aea6b980ed9894daae7fb
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:26:12.201Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$N\ge2$, $\Sigma=J$ (all entries $1$, rank one), so $T_1=\dots=T_N=Z$ and all p-values equal $u=\overline\Phi(Z)\sim\mathrm U(0,1)$. Every nonempty $S\subseteq[N]$ is a positive class. Take $\pi$ any probability measure on these (e.g. uniform on singletons, or $\delta_{[N]}$). Parameters: $q\in(0,1)$, $c\in(q,1]$ arbitrary (including $c\downarrow q$), $c_*\in(0,1]$.

## Checks

### H1

$J$ is symmetric PSD with unit diagonal; singular allowed.

### H2

All-null law, one-sided p-values.

### H3

Every nonempty $S$ is a positive class ($J\ge0$ entrywise); $\pi$ deterministic.

### H4

$q\in(0,1)$, $c\in(0,1]$, $q<c$.

### H5

$c_*\in(0,1]$.

### NOT

Ties: $p_{(k)}=u$ for all $k$. $E_q=\{u\le q\}$ (the rank $k=N$ qualifies iff $u\le q$, and smaller ranks need $u\le qk/N\le q$). On $E_q$, $\widehat k=N$, $\mathcal A=[N]$, $r=N$, and for every $S$: $|\mathcal A\cap S|=|S|\ge\max(1,c|S|)$. So $h=1$ on $E_q$ and $\mathbb P(E_q\cap\{h\ge c_*\})=q\le q/(cc_*)$. Holds; equality only when $c=c_*=1$.

## Failure

NOT fails: with all p-values tied, the event is just $\{u\le q\}$ of probability $q$, never above $q/(cc_*)$; letting $c\downarrow q$ only loosens the bound.
