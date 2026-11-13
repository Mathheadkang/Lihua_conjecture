---
type: candidate
title: >-
  Huge loading A = 10^30 at the largest allowed q (extreme tail, h'(z) close to
  1)
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

$A=10^{30}$, $q=e^{-1}/A\approx3.6787944\times10^{-31}$, $N=4$. Two variants:

- (a) rank-1 crossing: $t_1=\overline\Phi^{-1}(q/4)\approx11.668828$, $t_2=t_3=t_4=-30$;
- (b) all tied at rank $N$: $t_1=\cdots=t_4=\overline\Phi^{-1}(q)\approx11.550285$.

This is the regime where the penalty $\tau_A(K)(\tau_A(K)-z_K)=h'(z_K)$ is closest to its supremum $1$ and the gain $\log(1/(Aq))=1$ is smallest, so the margin $\tau_A(K)(X_K-\tau_A(K))$ is as small as the statement allows.

## Checks

### H1
$N=4$, $t\in\mathbb R^4$.

### H2
$A=10^{30}\ge2$.

### H3
$q=e^{-1}/A$.

### H4
(a) $p_{(1)}=q/4$; (b) $p_{(4)}=q$; equality in both.

### NOT
Right side $=-\tfrac12$.
(a) $K=\{1\}$: $z_K=\overline\Phi^{-1}(1/(4A))\approx11.583438$, $\tau\approx11.668526$, $\tau(t_1-\tau)\approx0.0035190$.
(b) $K=[4]$: $z_K=\overline\Phi^{-1}(1/A)\approx11.464025$, $\tau\approx11.549974$, $\tau(u-\tau)\approx0.0035886$.
Exhaustive maxima over the 15 subsets (40-digit arithmetic): (a) $0.0035190$, (b) $0.0035886$. Both exceed $-\tfrac12$. NOT fails.

## Failure

NOT fails: $M_A(t)\approx0.0035>-1/2$; even as $z_K\to\infty$ the margin tends to about $0$, not below $-1/2$.
