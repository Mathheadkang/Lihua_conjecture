---
type: idea
title: Elementary partition proof of the radial conditional transport bound
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
tags:
  - proof-simplification
  - all-pairs-comparison
  - no-bv-black-box
---

A simpler self-contained replacement for invoking the BV chain rule in candidate idea_3a7bdf91eb0c; NOT a new statement or a relaxation of all-pairs control. Suppose x(r) in[u,infinity] satisfies finite-contact all-pairs x(r2)^2<=x(r1)^2+8Md log(r2/r1) wheneverx(r1)finite; rootabsencecannotfollowfinitecontact. On[a,b] clip y=min(x,T), T>b,u, so allpairs y(r2)^2-y(r1)^2<=8Md log(r2/r1). Hence y²-8Md logr is nonincreasing; y is bounded and regulated, with at most countably many discontinuities. Let C(r,s)=P(||Z||<=r|Z1>=s), k=C_r=f_chid(r)H_r(s)/Q(s), C_s∈[-h(s),0], h(s)<=s+1/s.

For a partitiona=r0<...<rn=b setyi=y(ri). Exact telescoping gives C(ri,yi)-C(ri-1,yi-1)=integral_ri-1^ri k(r,yi)dr +[C(ri-1,yi)-C(ri-1,yi-1)]. Ifyi<=yi-1 the bracket is nonnegative. Ifyi>yi-1, its negative is <=integral_yi-1^yi h(s)ds <=.5(yi²-yi-1²)+log(yi/yi-1) <=.5(1+u^-2)(yi²-yi-1²) <=4Md(1+u^-2)log(ri/ri-1). Summing over only upwardincrements costs no more than4Md(1+u^-2)log(b/a), since eachlog(ri/ri-1)>0. C endpoints differbyatmost1. Thus allpartitions obey sum_i integral_ri-1^ri k(r,yi)dr<=1+4Md(1+u^-2)log(b/a). Asmesh→0, regulatedy gives right-endpointstepfunctions→y almosteverywhere; k iscontinuous andbounded on compact[a,b]×[u,T], so dominatedconvergence proves the desiredtransportintegralbound. Where originalx>=T or∞, T>b makes C(r,T)=k(r,T)=0, so clippingintroducesnomass. This directlyhandlesjumpsandCantorsingularbehaviorwithoutassumingan a.e.derivativeboundorusinganunprovedgeneralBVtheorem. Allpairscomparisonremainsessential. Root derivedthisfinitepartitionargument; nativeexecute/freshverifyshouldcheckitbeforeadoption.
