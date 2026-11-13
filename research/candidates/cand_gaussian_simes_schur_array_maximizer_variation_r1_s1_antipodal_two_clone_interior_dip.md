---
type: candidate
title: >-
  Antipodal two-clone array (signed rank one), whose Schur path rises, dips
  below q, and recovers
status: failed
target_asset: gaussian_simes_schur_array_maximizer_variation
checks:
  H1: pass
  H2: pass
  H3: fail
  NOT: unknown
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: f01c086658ebe5ee56008da39f09da391f92f318f7cc20925eb9bfdef2f5102a
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T06:03:00.097Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

This is the equality case $C_{ij}=-1$ of the correlation bound, chosen to test narrow oscillations in $t$. Take $\varepsilon_i$ iid uniform on $\{\pm1\}$ and $C_{ij}=\varepsilon_i\varepsilon_j$. This is $P_\Sigma$ with $N=2$ and $\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$. Under the Schur path, opposite-sign entries become $g_t(-1)=2t-1$. By part 4,
$$
f(t)=F_q\bigl(N=2,\ r(t)=(1-\sigma^2)(2t-1)+\sigma^2\bigr).
$$
The candidate uses $q_*\in\{0.25,0.1,0.01\}$ and $\sigma\in\{0.1,0.01\}$.

## Checks

### H1

pass.

### H2

All-null and lawful: pass.

### H3

At $r=\pm1$, $F_q=q$ exactly: at $-1$ the events $\{p_i\le q/2\}$ are disjoint, and at $+1$ the coordinates coincide. A 401-point grid evaluation of $f$ (scipy bivariate CDF) gives the following.

| $q$ | $f(0)/q$ | $\max f/q$ | argmax $t$ | $\min f/q$ | argmin $t$ | $f(1)/q$ | $\mathcal V_-/q$ |
|---|---|---|---|---|---|---|---|
| 0.25 | 1.0000 | 1.0272 | 0.28 | 0.841 | 0.94 | 1 | 0.186 |
| 0.1 | 1.0000 | 1.0063 | 0.37 | 0.828 | 0.96 | 1 | 0.178 |
| 0.01 | 1.0000 | 1.0003 | 0.43 | 0.816 | 0.98 | 1 | 0.184 |

The values are the same to four digits for $\sigma=0.1$ and $\sigma=0.01$. The competitor $S_{t^\dagger}P\in\mathfrak P_0$ (part 1) has a larger value than $f(0)$, so $P$ is not a maximizer: fail.

### NOT

Unknown (not reached). The computed $q_*+\mathcal V_-\approx1.19q_*\le0.3$ would fail NOT anyway, consistent with the benchmark $\mathcal V_-\le q$ for signed rank one.

## Failure

H3 fails: $f$ rises above $f(0)$ along its own path, so the array is beaten by $S_{t^\dagger}P$. The interior dip with recovery is real but has amplitude only about $0.2q$.
