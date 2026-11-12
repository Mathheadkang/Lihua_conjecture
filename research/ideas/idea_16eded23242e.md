---
type: idea
title: Near-null mass dilution with a localized contact envelope
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
tags:
  - spherical-population
  - bh
  - round-10
  - restricted-family
---

A branch-independent restricted-family step extracted from the round-10 dilution test. Suppose W has true-null mass pi_0 and total mass 1-epsilon on [0,a], with 0<=a<=u. For d>=4 the spherical upper tail H_r is convex on [0,infinity), including its zero extension beyond r. Thus, at every permitted x>=u and every mu in [0,a], H_r(x-mu)+H_r(x+mu)>=2H_r(x). It follows that F_r(x)>=2(1-epsilon)H_r(x), and the finite-contact FDP is at most pi_0/(1-epsilon), with FDP zero at no contact.

For a separate dimension-four localized upper envelope, suppose L>u, epsilon<=Q(L)/q, and for every u<=x<r<=L one has F_r(x)<=2A Q(x)e^{r^2/2}/r^2+epsilon, where A>0 is constant over that region. A positive-FDP contact there satisfies 2Q(x)/q=F_r(x), hence g(r):=r^2 e^{-r^2/2}<=2Aq. If g(u)>2Aq, let b>u be the unique solution g(b)=2Aq. Every positive-FDP radius is then in {R>=b} union {R>L}. For R~chi_4, Pr(R>=b)=Aq(1+2/b^2). Combining the two bounds gives FDR<=pi_0/(1-epsilon) [Aq(1+2/b^2)+Pr(R>L)]. This requires the explicit upper-envelope and mass premises and supplies no global contact-variation bound.

The recorded round-10 family W=u^{-2}delta_0+(1-u^{-2}-eta)delta_eta+eta delta_{u+u^{-1}}, eta=e^{-u^4}, satisfies these premises with a=eta, L=2u, A=2(1+u^{-2}); its shifted-cap estimate proves Pr(FDP>0)<3q and FDR<4q pi_0 for every u>=104. This is an approach for restricted near-null mixtures, not a proof or verification of the unrestricted target.
