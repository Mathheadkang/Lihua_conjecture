---
type: candidate
title: >-
  Rank-two circulant covariance with directions equally spaced on the full
  circle
status: failed
target_asset: gaussian_simes_dense_crossing_tilt_bound
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
statement_digest: 6e714bc6bdb2353b928e977aa5b3c27aa068b24a6df42caf55510b6b8e0b24c8
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:14:45.821Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$N\ge1$ arbitrary (intended $N\to\infty$ with $q\to0$), $\varphi_i=2\pi i/N$, $\Sigma_{ij}=\cos(\varphi_i-\varphi_j)$ (rank $\le2$, signs of correlations of both kinds). Realize $T_i=R\cos(\Theta-\varphi_i)$ with $R^2\sim\chi^2_2$ and $\Theta\sim\mathrm{Unif}[0,2\pi)$ independent. Any $q\in(0,1/4]$, $\delta\in(0,1]$ (the largest $\delta=1$ is the hardest boundary value; the bound below does not use $\delta$ at all).

Motivation: rank two is the smallest rank where the angular freedom gives $\mathbb P(R\ge u_q)=e^{-u_q^2/2}\asymp u_q\,q$, a factor $u_q$ above $q$; the question is whether the dense counting condition can harvest it.

## Checks

### H1
Pass.

### H2
$\Sigma=AA^{\mathsf T}$ with rows $a_i=(\cos\varphi_i,\sin\varphi_i)$, unit diagonal; singular for $N\ge3$, admitted. Pass.

### H3
$T=Ag$ with $g=R(\cos\Theta,\sin\Theta)\sim\mathcal N_2(0,I_2)$. Pass.

### H4
Pass.

### H5
Pass.

### NOT
Let $v_k=\overline\Phi^{-1}(qk/N)\ge u_q>0$. For $c\in(0,1]$ the indices with $\cos(\Theta-\varphi_i)\ge c$ lie in a closed arc of length $2\arccos c<\pi$, so their number is at most $N\arccos(c)/\pi+1$. Hence $\#\{i:T_i\ge v_k\}\ge k$ forces $\arccos(v_k/R)\ge x_k:=\pi(k-1)/N$, which needs $x_k<\pi/2$ and $R\ge m_k:=v_k/\cos x_k$. Using $\cos x\le1-4x^2/\pi^2$ on $[0,\pi/2]$ (convex-then-concave difference vanishing at both ends with zero initial slope), $m_k^2\ge v_k^2(1+8(k-1)^2/N^2)$. So
$$
D_{q,\delta}\subset\{\min_ip_i\le q/N\}\cup\{R\ge \min_{k\ge2}m_k\},\qquad
\mathbb P(D_{q,\delta})\le q+\max_{k\ge2}e^{-m_k^2/2}.
$$
By the Mills bound $\varphi(v)\le(v+1/v)\overline\Phi(v)$, $e^{-v_k^2/2}\le\sqrt{2\pi}(v_k+1/v_k)\,qk/N$. With $y=v_k(k-1)/N$ and $k\le2(k-1)$,
$$
\frac{e^{-m_k^2/2}}{q}\le\sqrt{2\pi}\Bigl(2y+\frac1{u_q}\Bigr)e^{-4y^2}
\le\sqrt{2\pi}\Bigl(2\cdot\tfrac{e^{-1/2}}{2\sqrt2}+\tfrac1{\overline\Phi^{-1}(1/4)}\Bigr)\le 4.8 .
$$
Hence $\mathbb P(D_{q,\delta})\le 5.8\,q$ for all $N$, $q\le1/4$, $\delta$: the ratio is bounded. Fail.

## Failure

NOT fails: on the uniform circle a $k$-fold crossing at angle width $\pi(k-1)/N$ costs the radial factor $e^{-4y^2}$ with $y=v_k(k-1)/N$, which exactly cancels the angular gain $v_kk/N$; the Rayleigh excess $u_q$ is never collected.
