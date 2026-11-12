---
type: idea
title: >-
  Capped conditional density envelope controls the supplied one-factor spike
  family
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - one-sided
  - gaussian-bh
  - conditional-envelope
  - family-specific
  - search-round-5
---

## Scope and hypotheses

This supporting calculation concerns exactly the centered true-null one-factor family supplied by idea_54d9dcf9a649, not arbitrary Gaussian covariance. For even N with L=log N>=2, take q=L^{-2}, a=L^{-1/2}, sigma=sqrt(1-a^2), m_0=m_1=N/2, independent standard normals G, epsilon_1,...,epsilon_{m_0}, true nulls T_i=aG+sigma epsilon_i, and alternatives T_{m_0+j}=(1+a)c_j-G, where c_j=overlinePhi^{-1}(qj/N). Use ordinary BH at its largest qualifying rank, including ties. In particular sigma>=1/sqrt(2). This establishes a family-specific bound on actual FDR; it neither verifies nor refutes the separate claimed conditional-moment spike calculation.

## Conditional density and BH bound

Given G=g, the true-null p-values are independent, and all alternative p-values are deterministic. At u=overlinePhi(x), their conditional density relative to the uniform density is
$$
f_g(u)=\frac1{\sigma}\exp\left\{\frac{x^2}{2}-\frac{(x-ag)^2}{2\sigma^2}\right\}
=\frac1{\sigma}\exp\left\{\frac{g^2}{2}-\frac{a^2}{2\sigma^2}(x-g/a)^2\right\}
\le\frac1{\sigma}e^{g^2/2}.
$$
The identity uses a>0 and a^2+sigma^2=1. Set p_i=0 and denote the resulting BH rejection count by R_i>=1. The ordinary step-up identity gives that i is rejected exactly when p_i<=qR_i/N, and on that event the original rejection count equals R_i. Given G, R_i depends only on the other p-values and is independent of p_i. Hence the density bound yields E[1{i rejected}/(R vee 1)|G=g]<=q sigma^{-1}e^{g^2/2}/N. Summing the m_0=N/2 true nulls and retaining FDP<=1 gives
$$
\operatorname{FDR}\le\mathbb E\min\{1,b e^{G^2/2}\},\qquad b=\frac{q}{2\sigma}.
$$
No assertion that the unconditional p-values or arbitrary Gaussian models are independent is used.

## Exact cap integration

For any 0<b<1 put t=sqrt(2 log(1/b))>0. Direct integration against the standard Gaussian density gives
$$
\mathbb E\min\{1,b e^{G^2/2}\}=\sqrt{\frac2\pi}\,b t+2\overline\Phi(t)
\le\sqrt{\frac2\pi}\,b\left(t+\frac1t\right).
$$
The last step is the elementary Mills bound overlinePhi(t)<=phi(t)/t together with exp(-t^2/2)=b. The constant is sqrt(2/pi). The uncapped envelope has infinite expectation, so dropping the cap loses this conclusion.

For the supplied family, q<=1/4, sigma in [1/sqrt(2),1), and b in (0,q/sqrt(2)], so t>1; also b>=q/2 and t<=sqrt(2 log(2/q)). Consequently
$$
\operatorname{FDR}\le\frac{2}{\sqrt\pi}\,q\sqrt{2\log(2/q)}
=O\!\left(q\sqrt{\log(1/q)}\right),
$$
with a numerical constant uniform over this supplied family. This rules out that family's auxiliary moment divergence as a refutation of the universal actual-FDR target. It supplies no dimension-uniform bound for general signed covariance, multiple null directions, or other factor models. This is a draft approach and calculation, not an approved supporting theorem.
