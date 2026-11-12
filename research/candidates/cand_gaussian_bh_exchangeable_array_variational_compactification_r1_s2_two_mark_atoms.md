---
type: candidate
title: Singular common score with two zero-mean marks
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:46:20.121Z'
extension_version: 0.0.4
---

## Object

Fix any $0<\sigma<1$ and $0<q\le S(1)$. Let $\theta_i=0$, let $\ell_i$ be iid Bernoulli$(1/2)$ variables, and set $C_{ij}=1$ for every $i,j$. All these parameters are independent of standard Gaussian variables $G,Z$. Conditional observations are
$$
T_i=\sqrt{1-\sigma^2}G+\sigma Z=:Y
$$
for every $i$, with $Y\sim N(0,1)$. This tests the smallest residual rank, a singular covariance already for $n=2$, and the two different lawful tags at the same zero mean. The proposed failure mechanism was that false-zero marks or exact ties might obstruct the claimed completion, canonical retagging, or marked representation.

## Checks

### H1

Pass. The loading and level are in the statement's domains; in particular $q\le S(1)<1/2$.

### H2

Pass. Both $(0,0)$ and $(0,1)$ belong to the closed marked domain. The constant all-ones residual array has unit diagonal, entries in $[-1,1]$, and every finite quadratic form is $(\sum_i x_i)^2\ge0$. Its law together with iid tags is jointly exchangeable. The parameter randomness is independent of the Gaussian innovations, as required.

### H3

Pass. The moment restriction required by the penalized conclusions holds with $M_2(P)=\mathbb E\theta_1^2=0$.

### NOT

Fail. Direct evaluation gives no claimed failure. For $n=1$, rejection is precisely $Y\ge S^{-1}(q)$, and the tagged FDR is $q/2$. For $n=2$, both p-values are $S(Y)$; if this value is at most $q$, rank two qualifies, and otherwise neither rank qualifies. Thus the tagged FDP is $(\ell_1+\ell_2)/2$ on this event and zero off it, again giving $q/2$. The same argument holds for every $n$:
$$
R_n=n\mathbf1_{\{Y\ge S^{-1}(q)\}},\qquad
D_n=\frac1n\sum_{i=1}^n\ell_i\,\mathbf1_{\{Y\ge S^{-1}(q)\}},\qquad
\mathcal F_n(P;q,\sigma)=\frac q2.
$$
Consequently the completion already agrees with every finite value. Retagging the false zeros changes the FDR from $q/2$ to $q$, preserves every score, rank and moment, and supplies rather than contradicts the claimed canonical lower bound. Here $\mathcal F\le q$, so this object cannot violate the preliminary logarithmic estimate. Its normalized objective is exactly
$$
\mathcal L_{\eta,\delta}(P,q;\sigma)=\frac1{2S^{-1}(q)}-\delta\log(1/q),
$$
which tends to $-\infty$ as $q\downarrow0$ for every $\delta>0$.

The proposed marked representation also exists explicitly in the one-dimensional Hilbert space: take the deterministic directing measure
$$
\mu=\tfrac12\delta_{(0,1,0)}+\tfrac12\delta_{(0,1,1)}.
$$
Then all off-diagonal inner products are one, the diagonal correction is zero, and the observation formula reproduces the common score above. These computations refute the proposed small-case failure mechanism; they do not establish the target for arbitrary laws.

## Failure

NOT fails: the singular two-mark zero-mean family has exactly constant finite FDR $q/2$, lawful canonical improvement to $q$, and an explicit marked directing representation.
