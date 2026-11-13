---
type: candidate
title: >-
  Schur-path fixed points (arrays with off-diagonal entries in {0,1}, including
  near-independent clone-block models)
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

The lemma's constants are existential, so a counterexample must defeat every triple $(q_*,\sigma_0,\delta)$ with $q_*\in(0,1/4]$. Fix such a triple and any $\sigma\in(0,\sigma_0]$ with $\sigma\le0.2$. Let $P\in\mathfrak P_0$ be any all-null law with $C_{ij}\in\{0,1\}$ for all $i\ne j$ almost surely. This degenerate family contains the identity array, the all-ones array, every clone-block array, and every finite independent model $P_{I_N}$ (part 4 of the compactification), in particular the near-independent sequence $P_{I_N}\to$ identity array that underlies the equicorrelated-limit risk of idea_ed169268dd35.

## Checks

### H1

$\sigma\in(0,\sigma_0]$ and $q_*\in(0,1/4]$ by choice: pass.

### H2

All marks are null, entries lie in $[-1,1]$, and a $\{0,1\}$-valued exchangeable unit-diagonal PSD array is lawful: pass.

### H3

Since $g_t(0)=0$ and $g_t(1)=1$, $S_tP=P$ for all $t$, so $f^\sigma_{P,q}$ is constant and equal to $f(1)=\Phi_\sigma(S_1P;q)\le q$ by part 3.

The maximum is larger. Take $N=2$, $\Sigma=\begin{pmatrix}1&-0.1\\-0.1&1\end{pmatrix}$. The loaded covariance has correlation $r=(1-\sigma^2)(-0.1)+\sigma^2\in[-0.1,-0.056]$ for $\sigma\le0.2$. With $a=\overline\Phi^{-1}(q/2)$ and $b=\overline\Phi^{-1}(q)$,
$$
F_q=q-\mathbb P(T_1\ge a,T_2\ge a)+\mathbb P(b\le T_1<a,\ b\le T_2<a).
$$
Bivariate normal CDF evaluation (scipy) gives $F_q/q-1$ at $r=-0.1$ and $r=-0.05$ of $1.08\cdot10^{-2},\ 5.7\cdot10^{-3}$ at $q=0.25$; $4.2\cdot10^{-3},\ 2.4\cdot10^{-3}$ at $q=0.1$; $3.0\cdot10^{-4},\ 2.2\cdot10^{-4}$ at $q=0.01$; and $1.9\cdot10^{-5},\ 1.8\cdot10^{-5}$ at $q=0.001$. Values were also positive at $r=-0.2$ and $r=-0.3$. So $B^\sigma(q)\ge F_q>q\ge\Phi_\sigma(P;q)$ by parts 4 and 5, and $P$ is not a maximizer. This is verified numerically at the four tested levels only. It is not proved for every $q_*$: fail.

### NOT

Unknown (not reached). Even if such a $P$ were a maximizer, $\mathcal V_-=0$ and $q_*\le1/4<1-\delta$ for $\delta<3/4$, so NOT would fail too.

## Failure

H3 fails. Schur fixed points have constant path value $\le q$ by part 3, while a bivariate model with mildly negative correlation gives $B^\sigma(q)>q$. They also have zero downward variation.
