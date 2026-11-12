---
type: idea
title: >-
  A constant-ratio radial core improves the regular angular population bound to
  order q
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - radial-transport
  - constant-core
  - restricted-class
  - needs-independent-check
---

Draft refinement, conditional on the previously derived signed-gradient/all-pairs comparison and radial transport, not a proof of the unrestricted Gaussian conjectures. Let d>=4, A>=1, u>=104A; A=1 in the current isotropic theorem, and A=K/kappa for regular angular conditional densities. Replace only the proof's radial split by a=max{u,52A sqrt(d)/u,sqrt(d)-2u}, b=sqrt(d)+2u. Then a<b, the core still has Lambda<=26A sqrt(d)/r<=u/2 and ell=r/(2sqrt(d))<=u. Also a^2-u^2<=d-3: the u term gives zero; the 52A term gives at most d/4-u^2<=d-3; if sqrt(d)-2u is maximal then sqrt(d)>=3u, so its square minus u^2 is d-4u sqrt(d)+3u^2<=d-9u^2<=d-3. Therefore the existing exact lower-radius Gaussian reference-density envelope still integrates to at most one. Crucially b/a<=5: if sqrt(d)<=3u, b<=5u<=5a; otherwise a>=sqrt(d)-2u and (sqrt(d)+2u)/(sqrt(d)-2u)<=5. Thus the same transport argument gives FDR_population<=q pi0 K [2+4A M_d(1+u^-2)log(5)]+exp(-2u^2), with K=1 isotropic. This is uniform O(q) in d and W for fixed angular bounds, stronger than the currently frozen isotropic q log u bound. It needs no statement change to prove the latter, since log5<=log(3u). For the previously derived both-tests ordered finite-array transfer, retain the same fixed-q-before-N order, null labels, and CDF convergence; rederive the MT core bound using the new endpoints instead of assuming a population scalar bound implies it. No native asset statement or approval is changed here. Independent checking of all split/end-point conditions is still required.
