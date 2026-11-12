---
type: candidate
title: Negative true singleton cannot be a normalized maximum
status: failed
target_asset: gaussian_bh_averaged_signed_mean_level_complementarity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  H9: fail
  H10: unknown
  NOT: unknown
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: e3dcfc508ee344fb52d4454b0676313187354eefcb69339fb28a33f503d7f350
performed_by: unknown
created_at: '2026-11-09T07:57:20.716Z'
extension_version: 0.0.4
---

## Object

Take the Hilbert space to be the real line, $\sigma=s=1/2$, $a=1/8$, $q=S(1)=q_{\max}$, and $\eta=\delta=1$. Let $\pi$ be the deterministic unit atom at $(\theta,v,\ell)=(-1,0,1)$. The cutoff is zero on $[0,a]$, one on $[2a,1]$, and $3z^2-2z^3$ for $z=(r-a)/a\in[0,1]$. This tests whether a negative-mean all-true boundary law can be used against the asserted off-$E_0$ complementarity. That conclusion requires an actual normalized global maximum.

## Checks

### H1

Pass: $0<\sigma=1/2<1$.

### H2

Pass: $s=1/2>0$ and $\sigma^2+s^2=1/2<1$.

### H3

Pass: $0<a=1/8<1/4$.

### H4

Pass: the specified cutoff has derivative $6z(1-z)/a\ge0$ on its transition interval and zero derivatives at both joins. Thus it is nondecreasing, $C^1$, takes values in $[0,1]$, and has the prescribed zero and one regions.

### H5

Pass: the deterministic Borel probability law has $\|v\|=0\le1$, true tag $\ell=1$ and mean $\theta=-1\le0$, and $M_2(\pi)=1<\infty$.

### H6

Pass: $0<q=q_{\max}$.

### H7

Pass: all parameters are fixed before independent Gaussian innovations. The private-smoothed model here has $c_s(0)^2=1-\sigma^2=3/4$, and $A_X=-1$.

### H8

Pass: $\eta=\delta=1>0$.

### H9

Fail: this is not an actual global maximizer of the normalized objective. For $0<\epsilon<1$, use the lawful competitor $\pi_\epsilon=\delta_{(-1+\epsilon,0,1)}$ at the same level. Its upper tail satisfies $H_\epsilon(y)=H(y-\epsilon)\ge H(y)$ for every real $y$. Hence its actual largest crossing satisfies $R_\epsilon(Z)\ge R(Z)$ pointwise. All tests are true, so $D=1$ whenever $R>0$, and the cutoff is nondecreasing; consequently $\mathcal F^a(\pi_\epsilon;q,\sigma,s)\ge\mathcal F^a(\pi;q,\sigma,s)$. Its moment is $(1-\epsilon)^2$. Writing $J$ for the normalized penalized objective, the fixed level and fixed logarithmic penalty give
$$
J(\pi_\epsilon,q)-J(\pi,q)\ge 1-(1-\epsilon)^2=2\epsilon-\epsilon^2>0.
$$
Thus the required maximizing hypothesis fails directly, without assuming any conditional-background maximizing property.

### H10

Unknown after the first failed check: canonical maximum selection is not evaluated.

### NOT

Unknown after the first failed check. No complementarity conclusion for this nonmaximizing law is tested as a claim of the target.

## Failure

H9: shifting the strictly negative true singleton mean toward zero weakly increases cutoff payoff and strictly lowers the positive mean penalty, so the law is not a normalized global maximum.
