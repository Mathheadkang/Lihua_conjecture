---
type: idea
title: >-
  Priority diagnostic: independent padding may invalidate the whole-line
  per-null pivotal gate
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - two-sided
  - pivotal
  - per-null-gate
  - effective-level
  - teaching-handoff
---

Priority: first diagnostic for the current plan plan_two_sided_baseline_subtracted_pivotal_probe_20261105, step 5. Agent-generated in the teaching discussion after the researcher explicitly requested autonomous idea handoff. This is a concrete counterexample candidate to the WHOLE-LINE PER-NULL gate, not an independently verified result, not a refutation of gaussian_bh_two_sided_sharp_upper, and not an instruction to silently weaken the plan.

Candidate finite Gaussian model, entirely inside the plan's class E:
Let p(v)=2 barPhi(v), U=p^{-1}(q), fix r=1/2, s=sqrt(1-r^2), and integers 2<=n<N. Write u_k=p^{-1}(qk/N). The active block consists of a single null T_1=rZ+s epsilon and n-1 loading-one nonnull mates
T_j=Z-(1+r)u_j,  j=2,...,n.
The other N-n coordinates are all identical copies of X, an independent standard Gaussian. Z, epsilon and X are independent. Thus there are only two independent factor blocks; the covariance is PSD with unit diagonal and allowed singularities. The background copies are TRUE NULLS; include them in any full-model FDR calculation. The active block's only null has the allowed loading r<=3/5.

Exact rank diagnostic to verify:
On E0={p(X)>q}, probability 1-q, no background coordinate can be rejected at any BH rank. Force the active null's p-value to zero. For positive z<(1+r)u_n, all mates are negative, their order is fixed, and for every 2<=ell<=n the ell-th forced-zero p-value is p((1+r)u_ell-z). Rank ell qualifies iff z<=r u_ell. Ranks ell>n cannot qualify. Consequently
R(z)=max{1,min{n,floor(N p(z/r)/q)}}
(on rank-boundary ties use the original non-strict inequalities).
This keeps the ACTUAL largest qualifying rank, rather than an admissible outer set.

Why this attacks uniformity:
Choose A>>U and N,n so u_n is arbitrarily close to A and N p(2A)/q is arbitrarily large. One finite choice scheme is to take n sufficiently large and N=ceil(q n/p(A)); then take n larger as necessary for the mesh. On z in [A/2,A], up to harmless endpoint adjustment for u_n, all mates remain negative and u_R approximates z/r uniformly. The exact Gaussian conditional ratio is
rho_r(v,z)=[barPhi((v-rz)/s)+barPhi((v+rz)/s)]/[2 barPhi(v)].
At z=rv, Mills asymptotics give
phi(z) rho_r(z/r,z) -> 1/[2 sqrt(2pi) s]
as v->infinity. Thus the rank-tracking window should contribute c A to E rho_r(u_R,Z), with universal c>0. Since E0 is independent of Z and the integrand rho is nonnegative, the whole-line quantity obeys the candidate lower estimate
Delta_1=E rho_r(u_R,Z)-1 >= (1-q)c A-1.
If the finite-mesh and uniform Mills bounds are completed, taking A/U arbitrarily large contradicts step 5's uniform Delta_i <= U/(2 sqrt(2pi))+eta(q)U. In particular the needed scale can depend on the effective level q n/N, not just the global q.

Checks already performed in this teaching discussion:
Two independent agents checked the rank algebra and Gaussian construction. A small pure-Python deterministic sanity check compared the actual sorted forced-zero BH rank with the floor formula at 120 interior probes, q in {0.05,0.001}, r in {0.3,0.5}, N=10000,n=30, with inactive background p=1: zero mismatches. This checks only finite rank algebra; it is neither an asymptotic numerical result nor independent research-loop verification.

Required next checks in the proving chat:
1. Choose a finite integer sequence explicitly and bound u_floor-z/r uniformly on a window of length proportional to A; keep every constant uniform.
2. Prove a uniform positive lower bound on phi(z)rho_r(u_R,z) there using elementary Gaussian tail bounds.
3. Separate whole-line Delta, the central |Z|<=U contribution, the weighted term (q/N)Delta_1, and FULL FDR including the duplicated background nulls.
4. For A>2U the proposed large contribution is wholly outside the central region. This does NOT refute the central-region gate or the full FDR target.
5. If confirmed, obey the existing plan's stop rule: this is a failure of its stated per-null whole-line gate. Any central-plus-aggregate replacement must be a separate new idea/plan, not an edited statement during execution. If the candidate fails, identify the precise rank, mesh, or tail calculation that fails before returning to the old gate.
