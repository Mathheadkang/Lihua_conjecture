---
type: candidate
title: N=1 singleton model at c=c_*=1 (equality case)
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

$N=1$, $\Sigma=(1)$, $T=T_1\sim\mathcal N(0,1)$, $p_1=\overline\Phi(T_1)\sim\mathrm{U}(0,1)$. The only positive class is $\{1\}$; $\pi=\delta_{\{1\}}$. Parameters: any $q\in(0,1)$, $c=1$, $c_*=1$.

## Checks

### H1

$N=1$ is a positive integer and $\Sigma=(1)\in\mathcal C_1$.

### H2

$p_1=\overline\Phi(T_1)$ with $T\sim\mathcal N_1(0,\Sigma)$ (all-null law $\mathbb P_{1,0,\Sigma}$).

### H3

$\{1\}$ is nonempty with $\Sigma_{11}=1\ge0$, so it is a positive class; $\pi=\delta_{\{1\}}$ is deterministic.

### H4

$q\in(0,1)$, $c=1\in(0,1]$, $q<c$.

### H5

$c_*=1\in(0,1]$.

### NOT

$E_q=\{p_1\le q\}$ has probability $q$. On $E_q$, $\mathcal A=\{1\}$, $r=1$, and $|\mathcal A\cap\{1\}|=1\ge\max(1,c\cdot1\cdot1/1)=1$, so $h=1\ge c_*$. Hence $\mathbb P(E_q\cap\{h\ge c_*\})=q=q/(c\,c_*)$. The bound holds with equality; it is not violated.

## Failure

NOT fails: the probability equals $q$, exactly the bound $q/(cc_*)$ at $c=c_*=1$ (the bound is sharp but not exceeded).
