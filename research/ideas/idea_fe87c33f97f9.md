---
type: idea
title: >-
  Recover signed mean complementarity from the difference of support functions
  at a smoothed cutoff maximum
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
  - gaussian_bh_exchangeable_array_variational_compactification
tags: []
---

Candidate next step AFTER the new private-noise cutoff variation is independently proved; this is not an assumed lemma or a proof of the main bound. At a fixed regularized maximum, write w_x(r)=(chi_a f_x)'(r). For mean velocities b, Qdot_b(t) is linear in b, while Mdot(r)=-max_{t in A_x(r)} Qdot_b(t)/sigma. Thus the actual derivative has the form L_bulk(b)+(1/sigma)E integral w_x(r) phi(M_x(r)) max_active Qdot_b(t)dr. Split w into its positive and negative parts, retaining their signs. The normalized objective's other terms (moment penalty and any q direction) are linear. Under measurable selection and closure checks this is a DIFFERENCE of two support functions sigma_A(b)-sigma_B(b), for convex sets of signed mean-gradient densities, rather than an arbitrary nonlinear expression that must be treated as linear by fiat.

At a genuine maximum the derivative is <=0 for every lawful b. For unrestricted directions this says sigma_A<=sigma_B and hence A subset B. For the lawful tangent cone K (b<=0 at zero-mean true nulls; arbitrary interior b), it should imply A subset B+K^polar, provided B is weakly compact and the sum is closed. Since K^polar is zero on interior means and nonnegative on zero-mean true-null parameters, choosing a matched pair yields an actual signed gradient Psi with Psi=2 eta theta on interior means and Psi>=0 at canonical zero-mean true nulls (with the appropriate qU normalization). This is a signed positive/negative branch pairing, not replacement of each face by its positive part. A simultaneous q direction can be included as one extra coordinate with active linear value lambda m(u(t)); at an upper q endpoint its tangent cone is one-sided.

The crucial countable-additivity/compactness gate has a possible proof. Each Qdot_b(t) is expectation of b under the conditional posterior measure with density k_{c(v)}(Q(t)-A(v))/h(Q(t)) relative to the directing law mu. Active t>=a and |M|<=B force Q(t)=u(qt)-sigma M into a deterministic compact interval. On the event integral A(v)^2 dmu<=K0, at least half the center mass lies in a bounded interval; private deviations c(v) lie in [s,sqrt(1-sigma^2)], giving a strictly positive uniform lower bound on h at this compact Q range. Posterior mass of a parameter set E is then <=C mu(E). The complement of the score-energy event has probability <=C/K0 from M2(mu)<infinity; the contribution |M|>B is <=C(a) exp(-B^2/2), because the branch weights include phi(M) and integral |w|<=1+log(1/a). This proposes UNIFORM ABSOLUTE CONTINUITY in L1(mu) of all active-selector gradients. The fixed bulk gradient and signed moment gradient are integrable as well. Dunford-Pettis and Hahn-Banach support-set separation, if correctly applicable, then yield weakly compact countably additive gradient sets; do not settle for a finitely additive L-infinity dual.

Legal bounded velocities supported on |theta|>=delta plus nonpositive velocities at true theta=0 approximate the desired tangent cone pointwise. The same uniform absolute continuity should extend support inequalities as delta->0, despite lack of L-infinity norm convergence. Check the measurable-selector interchange, weighted posterior bounds, weak closure/Minkowski sum, q coordinate, canonical false-zero removal and all signs before making this a theorem.

For a global diagnostic translation b=1, all posterior velocities equal1 and fdot=0, so every active selection has the SAME total mean-gradient Gamma_a=(1/sigma)E[Z chi_a(R)D]. Thus an established complementarity could identify its zero-null boundary mass rather than an arbitrary selected flux. This still does NOT give the required uniform C q U^2 upper bound, nor produce the paired inverse-Mills deformation. Those remain decisive main-proof obligations; no q-scaled payment is inferred from this proposed functional-analytic pairing.
