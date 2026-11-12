---
type: idea
title: Exclude low radii using weak-mean caps and a bound on mean-tail mass
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
tags:
  - spherical-population-bh
  - weak-means
  - radial-exclusion
  - round-six
---

Round-six candidates cand_spherical_isotropic_population_bh_bound_r6_s7_d4_microscopic_positive_mean and cand_spherical_isotropic_population_bh_bound_r6_s8_ultraweak_exponential_unbounded give a restricted radial-exclusion step that complements the existing null-envelope and admissible-cutoff-interval approaches. All assertions below fix d=4, u=104 and q=2Q(u); no uniform dimension or level conclusion is claimed.

For any allowed mean law, the even density f_r(z)=2/(pi*r)*sqrt(1-z^2/r^2) on |z|<r is nonincreasing in |z|. Therefore H_r(x-mu)+H_r(x+mu)>=2H_r(x) for mu>=0, so F_r(x)>=2H_r(x) and the prescribed contact mass ratio satisfies FDP_pop<=pi_0. The no-contact FDP is zero.

For every Borel W supported on [0,u^(-2)], let b=sqrt(u^2+6*log(u)), m=u^(-2), k=3/2 and C=4*sqrt(2)/(3*pi)<2/3. For u<=r<=b and u<=x<=r+m, put Delta=r+m-x. The cap bound and Mills inequalities give
$$
F_r(x)Q(u)/Q(x)\leq 2C(k/e)^k e^{bm+m^2/2}(b+m+u^{-1})/u < (4/5)(100/99)(53/52)<1.
$$
For x>r+m the total rejection mass is zero. Thus no finite contact exists for u<=r<=b. FDP is also zero for r<=u because nulls cannot exceed the cutoff. Since R has the chi_4 law, FDR_pop<=pi_0*P(R>b), and the exact tail e^(-b^2/2)*(1+b^2/2) is strictly below q. Hence FDR_pop<q*pi_0 when pi_0>0; it is zero when pi_0=0.

A mean-tail split extends this style of argument to a specified unbounded-law family. Put a=e^(-2u^2) and assume W((a,infinity))<=Q(2u)/q. Then F_r(x)<=2H_r(x-a)+W((a,infinity)). For 2<=t<=r the cap/Mills envelope gives H_r(t)/Q(t)<(5/2)e^(r^2/2)/r^2. Also Q(x-a)/Q(x)<2 for u<=x<=2u. At any prescribed contact having positive FDP and r<=2u, these inequalities force e^(r^2/2)/r^2>1/(10q). If s>u solves e^(s^2/2)/s^2=1/(10q), positive FDP in this range requires r>s. The exact chi_4 tails give P(R>=s)=10q(1/s^2+1/2)<6q and P(R>2u)<q. Consequently FDR_pop<7q*pi_0 for pi_0>0; it is zero for pi_0=0. The exponential alternative with scale e^(-4u^2), and every mixture p*delta_0+(1-p)*nu with that alternative law, meets the mean-tail premise since its tail above a is at most exp(-exp(2u^2))<Q(2u)/q.

Possible proof step: combine a bound on the mean-law tail with a cap envelope to prove that nonzero null FDP requires an explicitly large radius, then apply the exact radial tail. This step requires the displayed support or tail-mass premises. It supplies neither those premises for arbitrary W nor the global first-contact/transport argument required by the unrestricted draft theorem.
