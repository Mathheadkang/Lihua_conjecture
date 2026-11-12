---
type: idea
title: >-
  Null-marked Gaussian rotation bound and an exact rank-summed positive-entry
  allocation
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - universal-order
  - marked-rotation
  - null-tail-density
  - rank-summation
  - draft-proof
---

DRAFT candidate partial allocation derived during the online marked-rotation investigation. It is not a main upper bound, native-approved lemma, or proof of a full contraction modulus. Reconstruct inline before use.

Let X,V,Y be jointly centered unit-variance Gaussian variables, X independent of V, and r=Cov(X,Y). This represents a unit-speed standardized Gaussian rotation with position X and velocity V. For any original true-null outsider T_j=theta_j+Y, theta_j<=0, any v>=U>=1 and any real active-coordinate centered threshold x (the active mean may be arbitrary),

$$
\phi(x)\mathbb E[|V|\mathbf1\{T_j\ge v\}\mid X=x]
\le\sqrt{2/\pi}\,\phi(v-\theta_j)\le\sqrt{2/\pi}\,\phi(U).
$$

For |r|<1, given X=x put xi=(Y-rx)/sqrt(1-r^2), a standard normal. Its covariance with V is gamma with |gamma|<=1. Write h=(v-theta_j-rx)/sqrt(1-r^2). Regression gives E[|V|1{xi>=h}]<=B(h), where B(h)=phi(h)+sqrt(2/pi)S(h) for h>=0 and B(h)=sqrt(2/pi) for h<0. Since S(h)exp(h^2/2) is decreasing on h>=0, B(h)<=sqrt(2/pi)exp(-h^2/2). The identity x^2+h^2>=(v-theta_j)^2 proves the claim there. If h<0 then rx>v-theta_j>=0, hence |x|>=v-theta_j and use B<=sqrt(2/pi). At |r|=1 the mark is deterministic given X, and the same bound follows directly from X independent of V. The estimate removes arbitrary alternative means from the ACTIVE threshold by charging a TRUE-NULL mark. It does not bound a naked union of many null marks without their exact FDP coefficients.

Concrete general-N partial allocation: exactly one original null outsider j and ONE rotating alternative coordinate i, with all other coordinates retained and all their means/covariances arbitrary. On a positive alternative-triggered cascade that newly selects j, predecessor FDP is0 and the FDP jump is exactly1/r at post-jump rank r; the event requires T_j>=u_(qr/N). Integrate the null-marked estimate with the exact active-face mask (bounding that mask by1 only for this single-row calculation). The POSITIVE null-entry flux per unit angle is at most

$$
\sqrt{2/\pi}\sum_{r=1}^N\frac{\phi(u_{qr/N})}{r}
\le\sqrt{2/\pi}\,q(U+2).
$$

Indeed h(z)=phi(z)/S(z), h(u_(qr/N)) decreases in r, and

$$
\sum_{r=1}^N\phi(u_{qr/N})/r
=(q/N)\sum_{r=1}^N h(u_{qr/N})
\le\int_0^q h(u_t)\,dt
=\int_U^\infty h(z)\phi(z)\,dz
\le\int_U^\infty(z+1)\phi(z)\,dz
=\phi(U)+q\le q(U+2).
$$

Here U>=1 and Mills gives h(z)<=z+1/z<=z+1, h(U)<=U+1. The full signed cascade is still A=[(1-f_b)a-f_b c]/r. A negative dilution jump times negative rotation velocity can increase FDR; it is NOT controlled by the displayed positive ENTRY budget. Nor does summing this single-row estimate over arbitrarily many rotating rows remove their count. These are explicit unresolved boundaries, not an implicit proof of a whole-line or whole-model gate.

This finite calculation suggests placing true-null marks, rather than strong-alternative marks, in a new Gaussian face allocation and preserving normalized label counts until after aggregation. It remains a candidate tool for future plans; original failed plans, target statements and approvals are unchanged.
