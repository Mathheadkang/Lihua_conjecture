---
type: candidate
title: >-
  Small or positive common loading over many coordinates (mixed-sign and
  equicorrelated-limit paths)
status: failed
target_asset: gaussian_simes_schur_variation_few_block_compression
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: ae49babfdb545830e8ad7375a17d918e1fb1ba20e49b625bd07dbdd7738fee3a
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T05:45:35.188Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

(a) Mixed-sign small loading: $\Sigma=(1-\varepsilon^2)I+\varepsilon^2vv^{\mathsf T}$ with $v_i=+1$ for $i\le N/2$ and $v_i=-1$ otherwise. Then $\Sigma\circ\Sigma=(1-\varepsilon^4)I+\varepsilon^4J$ and $R(t)$ is realized by
$$
Z_i=\alpha v_iG_1+\beta G_2+\gamma\varepsilon_i,\qquad \alpha^2=\varepsilon^2(1-t),\ \beta^2=t\varepsilon^4,\ \gamma^2=1-\alpha^2-\beta^2 .
$$
Tested $(N,\varepsilon,q)=(1000,0.3,0.05)$ and $(2000,0.15,0.01)$.

(b) Equicorrelated-limit path (the regime of the risk idea idea_ed169268dd35): $\Sigma$ equicorrelated with $\rho_0\ge0$, so $R(t)$ is equicorrelated with $\rho(t)=(1-t)\rho_0+t\rho_0^2$, decreasing from $\rho_0$ to $\rho_0^2$. Tested $N=2000$, $q=0.01$, $\rho_0\in\{0.5,0.1,0.03\}$, where the large-$N$ size drops well below $q$ at moderate $\rho$ and returns to $q$ as $\rho\to0$.

## Checks

### H1

The family is taken along $q\to0$ (tested at $q=0.05,0.01$; the variation scales with $q$, see NOT).

### H2

$N$ is a positive integer.

### H3

Both matrices are PSD with unit diagonal (convex combinations of $I$ with $vv^{\mathsf T}$ or $J$), so they lie in $\mathcal C_N$.

### NOT

NOT requires $\mathcal V_-(f_{q,\Sigma})>1/8$, since $\mathcal M(q)\ge0$.

(b) Rigorous part: all entries of $R(t)$ are $\rho(t)\ge0$, so $f(t)\le q$ for every $t$ by [the positive Gaussian Simes inequality](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md). Numerical (Monte Carlo, $2\times10^5$ reps, common random numbers, 26-point grid): $\rho_0=0.5$: $f/q=0.51,0.60,0.69,0.77,0.84,0.90$ at $t=0,0.2,\ldots,1$, increasing, grid $\mathcal V_-=0$. $\rho_0=0.1$ and $0.03$: $f/q\in[1.00,1.035]$ (excess over $1$ is Monte Carlo noise, relative standard error about $2\%$), grid $\mathcal V_-/q=0.02,0.03$. Along the Schur path $\rho$ decreases, so the path climbs out of the equicorrelated dip toward independence: the dip makes $f$ increase, not decrease, in $t$.

(a) Numerical: $f\in[0.0486,0.0506]$, $\mathcal V_-/q\approx0.06$ at $(1000,0.3,0.05)$; $f\in[0.0102,0.0104]$, $\mathcal V_-/q\approx0.06$ at $(2000,0.15,0.01)$, both at noise level.

So $\mathcal V_-\le0.06\,q\ll1/8$. NOT fails (numerically; the bound $f\le q$ in (b) is rigorous).

## Failure

NOT fails: in (b) the Schur path moves the equicorrelation toward $0$, so the profile rises out of the dip below $q$; in (a) it stays within noise of $q$. In both, $\mathcal V_-\le0.06q$.
