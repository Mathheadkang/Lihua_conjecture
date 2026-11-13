---
type: candidate
title: 'Antipodal pair Sigma_12=-1 with singleton classes, q in [1/2,1)'
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

$N=2$, $\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$ (singular), so $T_2=-T_1$ and $p_2=1-p_1$ with $u:=p_1\sim\mathrm U(0,1)$. Positive classes: exactly $\{1\}$ and $\{2\}$ (the set $\{1,2\}$ is excluded since $\Sigma_{12}=-1$). $\pi=\tfrac12\delta_{\{1\}}+\tfrac12\delta_{\{2\}}$. Parameters: $c=1$, $q\in[1/2,1)$, $c_*\in\{1/2,1\}$ (every $c_*\in(0,1]$ reduces to one of these two since $h\in\{0,1/2,1\}$). Variant: $\pi=\delta_{\{1\}}$.

This is the degenerate mixed-sign case in which $\mathbb P(E_q)$ exceeds $q$ (it equals $3q-1$ for $q\in[1/2,2/3)$ and $1$ for $q\ge2/3$), so it tests whether the positive-class restriction really rescues the bound.

## Checks

### H1

$\Sigma$ is symmetric, PSD (eigenvalues $0,2$), unit diagonal; singular matrices are allowed.

### H2

All-null law, $p_i=\overline\Phi(T_i)$.

### H3

$\{1\},\{2\}$ are positive classes; $\pi$ is deterministic.

### H4

$c=1$, $q\in[1/2,1)$, $q<c$.

### H5

$c_*\in(0,1]$.

### NOT

Since $|S|=1$ and $r\le N=2$, $c|S|r/N\le1$, so $S=\{i\}$ is hit iff $i\in\mathcal A$. BH: $p_{(1)}=\min(u,1-u)$, $p_{(2)}=\max(u,1-u)$. Two rejections iff $\max(u,1-u)\le q$, i.e. $u\in[1-q,q]$ (probability $2q-1$). Otherwise one rejection iff $\min(u,1-u)\le q/2$.

- $c_*\in(1/2,1]$: $h\ge c_*$ iff $r=2$; probability $2q-1\le q$ since $q\le1$. Bound $q/c_*\ge q$. Holds.
- $c_*\in(0,1/2]$: $h\ge c_*$ iff $r\ge1$. For $q\in[1/2,2/3)$ the sets $[0,q/2]$, $[1-q,q]$, $[1-q/2,1]$ are disjoint, total probability $3q-1$; the bound is $q/c_*\ge2q>3q-1$. For $q\ge2/3$ the probability is $1$ and the bound $2q\ge4/3$ is vacuous. Holds.
- Variant $\pi=\delta_{\{1\}}$, $c_*\in(0,1]$: event $\{1\in\mathcal A\}=\{u\le q/2\}\cup\{u\in[1-q,q]\}$, probability $q/2+2q-1<q$ for $q<2/3$ and exactly $q$ for $q\ge2/3$ (the union is $[0,q]$). Bound $q/c_*\ge q$. Holds (equality at $q\ge2/3$, $c_*=1$).

Monte Carlo ($2\cdot10^5$ draws, $q=0.55,0.6,0.7$) reproduced $P(r\ge1)=0.650,0.800,1.000$ and $P(r=2)=0.100,0.200,0.400$.

## Failure

NOT fails: although $\mathbb P(E_q)>q$, each singleton is hit with probability at most $P(p_i\le q)=q$ (BH thresholds never exceed $q$), so the averaged hitting mass obeys $q/(cc_*)$.
