---
type: candidate
title: Escaping positive atom with fixed quadratic moment and vanishing mass
status: failed
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 4
slot: 2
direction: small_cases
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:54:43.765Z'
extension_version: 0.0.4
---

## Object

Fix $q=1/4$, $\sigma=1/2$, $d=1$, and the positive cap $C=1$. For integers $n\ge2$, set
$$
x_0=(0,1,1),\qquad x_n=(n,1,0),\qquad
\pi_n=(1-n^{-2})\delta_{x_0}+n^{-2}\delta_{x_n},\qquad \pi_0=\delta_{x_0}.
$$
The attempted obstruction is a two-atom sequence whose alternative mean escapes to infinity while its quadratic moment remains exactly one. Unlike the board's zero-cap example, the cap is positive; unlike its empty-null example, these laws have positive true-null mass. This tests compactness and lower semicontinuity, rather than approximation of one fixed empty-null law.

## Checks

### H1

Pass. The fixed parameters satisfy $0<q<1/2$, $0<\sigma<1$, and $d$ is a positive finite integer.

### H2

Pass. Every law is deterministic. Both directions are the unit vector $1\in\mathbb R$. The atom $x_0$ has a true tag and zero mean; $x_n$ has an alternative tag and strictly positive mean. All parameters lie in the prescribed closed tagged domain, with canonical finite-model labels.

### H3

Pass. Every law has finite first and second mean moments:
$$
\int|\theta|\,d\pi_n=1/n,\qquad M_2(\pi_n)=n^{-2}n^2=1=C,
\qquad M_2(\pi_0)=0.
$$
Thus the whole sequence belongs to the same fixed positive moment cap $\mathcal K_1$.

### NOT

Fail. Since the target law is a point mass, the only coupling with second marginal $\pi_0$ sends every source point to $x_0$. Consequently
$$
W_1(\pi_n,\pi_0)=n^{-2}c(x_n,x_0)
=n^{-2}(n+1)=1/n+1/n^2\longrightarrow0.
$$
The sequence therefore converges inside $\mathcal K_1$, and
$$
M_2(\pi_0)=0\le\liminf_n M_2(\pi_n)=1.
$$
Its loss of quadratic moment contradicts continuity of $M_2$, which the target does not assert; it satisfies the asserted lower semicontinuity.

For completeness the actual full largest-crossing FDR also converges explicitly. Write $G=\sqrt{1-\sigma^2}X(1)+\sigma Z\sim N(0,1)$. All true-null scores equal $G$ and the alternative score is $n+G$. A positive rank rejecting a true-null atom exists if and only if $S(G)\le q$: necessity follows because every BH cutoff is at most $q$, and sufficiency follows because then every score is rejected at rank one. Thus
$$
D_{\pi_n}=(1-n^{-2})\mathbf1_{\{S(G)\le q\}},\qquad
F(\pi_n)=(1-n^{-2})q\longrightarrow q=F(\pi_0).
$$
There is no conflicting FDR discontinuity or noncompactness in this sequence.

## Failure

NOT fails: the escaping atom has vanishing first-moment transport cost, so the sequence converges in $W_1$ inside the cap and its strict moment drop is consistent with lower semicontinuity.
