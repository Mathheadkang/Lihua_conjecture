---
type: candidate
title: 'All coordinates form one exact null cluster (pi_G = 1, w_i = v)'
status: failed
target_asset: gaussian_bh_angular_cluster_partial_entropy_bound
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
statement_digest: 736750aaadb60109c2ce46215b308676bc7a0cd9e89173948fa97978fa8123b1
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:16:00.960Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Any $q\in(0,1/2)$, any $m\ge1$, $d=1$, $v=w_i=1$ for all $i$, $\theta_i=0$ for all $i$ (so $T_i=Z=Y_G$ for every $i$), $G=I_0=[m]$, any $\kappa\in(0,1]$, $C\ge1$. Variant: $\theta_i\le0$ arbitrary (some very negative). This is the degenerate end of every hypothesis: zero spread, full mass, empty strip.

## Checks

### H1
Unit loadings, no residual, singular covariance (all ones): allowed.

### H2
Any $q\le q_1$.

### H3
$\|w_i-v\|=0\le\kappa/u$; $G=I_0\ne\varnothing$.

### H4
$\pi_G=1\ge q^C$.

### NOT
$b_G=\overline\Phi^{-1}(q)=u$, so the strip $\{u<Y_G\le b_G\}$ is empty and (b) has left side $0$. All $p_i=\overline\Phi(Z)$ coincide, so BH rejects everything iff $\overline\Phi(Z)\le q$, i.e. $Z\ge u$; on $\{Y_G\le u\}$ a rejection needs $Z=u$, a null event, so the first term of (a) is $0$. The second term is at most $\mathbb P(Y_G>u)=q=q\pi_G$. With $\theta_i\le0$ mixed, $T_i\le Z$ and the same argument applies. So (a) holds with $A_1=1$; the conclusion holds.

## Failure

NOT fails: with zero spread and $\pi_G=1$ the strip is empty and the off-strip part is at most $\mathbb P(Y_G>u)=q\pi_G$.
