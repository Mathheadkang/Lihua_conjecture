---
type: plan
title: Universal one-sided order through FDP entropy and Mills-field coherence
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by:
  - idea_7f6256457479
tags:
  - universal-order
  - fdp-tilt
  - gaussian-entropy
  - mills-field
  - signed-trace
  - coherence-deficit
---

# Universal one-sided order through FDP entropy and Mills-field coherence

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged finite-model statement: finite universal C and q0>0 such that ordinary one-sided Gaussian BH has FDR at most C q sqrt(log(1/q)) for every 0<q<=q0, every finite N, every mean vector theta and every unit-diagonal PSD Sigma, including singular matrices. Preserve I0={i:theta_i<=0}, every alternative mean, all multiplicities, non-strict comparisons and the largest qualifying rank. Every parameter may vary with q. No dimension, covariance-rank, factor-count, direction-entropy, null-proportion or eigenvalue restriction is permitted; no sharp constant is sought.

The [FDP entropy proposal](../ideas/idea_7f6256457479.md) is UNPROVED guidance. Its signed trace-versus-total-deficit certificate below is a stronger sufficient gate to attempt or refute, never an assumed theorem. It may fail without refuting the main target. A mandatory first adversarial test is the source's small-null-loading lower family: its explicit geometry may refute this certificate even though it matches the main target's permitted order. Do not describe the certificate as supported before that test. Native library searches for Gaussian BH entropy transport and Mills posterior trace variance coherence returned no analogue. No library or external conclusion is a black-box dependency. The workspace root is not Git. Before exclusive creation the source idea SHA256 was 126c0bf4c3ce8b353a05cbe2b4ce22ad0d67a14944a5e98b16dae857bd89be12 and target SHA256 was 7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305.

Primary-source inspiration, read at planning time: Russo and Zou, *Controlling Bias in Adaptive Data Analysis Using Information Theory*, PMLR 51 (2016), Proposition 1 and supplementary Fact 1/Proof of Proposition 1, https://proceedings.mlr.press/v51/russo16.pdf and https://proceedings.mlr.press/v51/russo16-supp.pdf ; Gigli and Ledoux, *From Log Sobolev to Talagrand: A Quick Proof*, DCDS 33(5) (2013), DOI 10.3934/dcds.2013.33.1927, smooth-case equations (4)--(7), pp.1930--1931, https://www.math.univ-toulouse.fr/~ledoux/OttoVillani.pdf ; Mikulincer, *Stability of Talagrand's Gaussian transport-entropy inequality via the Follmer process*, arXiv:1906.05904v2, Section 3 equations (7), (10), (12), PDF pp.8--9, https://arxiv.org/pdf/1906.05904v2 . Reconstruct all needed identities inline. These sources supply no BH trace estimate. The marginal FDP tilt has dimension-free entropy; adding a selected index changes the measure and can add index entropy, which must never be dropped.

Save the first completed derivation into Progress immediately. Later checkpoints require a fresh read of the insertion region and source/target/plan hash checks, with patches of at most 6000 tokens. Parent owns native reports, transitions and approvals. Stop at the first essential unpaid estimate after the explicit allocation below; preserve its exact signed kernel, masks and coefficients in Failure. Do not replace it by another declaration of the desired FDR bound.

## Plan

1. [ ] **Reconstruct the finite original model, Mills field and actual face packets.** Let gamma be standard Gaussian on a finite latent space, T_i=theta_i+v_i dot G, ||v_i||=1, v_i dot v_j=Sigma_ij. Such a Gram representation includes singular Sigma. Use original ordinary BH R, V and f=V/(R vee1); F=E_gamma f. F=0 is trivial. For 0<q<=S(1), write U=S^{-1}(q)>=1, h=phi/S, hU=h(U), u_k=S^{-1}(qk/N), and w_k=1/[k h(u_k)]. Put

   $$
   B(g)=w_R\sum_{i\in\mathcal R\cap I_0}v_i,\qquad b=B/f\quad(f>0),
   $$

   and B=0 at R=0; Q gives f=0 zero mass. Prove h increasing, u<=h(u)<=u+1/u for u>0, and u/h(u) increasing by

   $$
   uS(u)/\phi(u)=\int_0^\infty\exp[-s-s^2/(2u^2)]\,ds.
   $$

   Hence ||B||<=f/hU and J:=E_gamma[G dot B]>=[U/hU]F, since each selected true null has v_i dot G=T_i-theta_i>=u_R. Derive d log[k h(u_k)]/d log k=u_k/h(u_k)>0 for continuous k, so w_k decreases.

   First work in positive-definite models. Fix other scores and prove from largest-rank BH that replacing p_i by 0 gives a rank k and replacing it by 1 gives r<k; varying p_i produces exactly one switch r to k at p_i=qk/N. Give the full old and new rejection sets, not just their ranks. On an actual face T_i=u_k with old set S and new set S union A, compute

   $$
   \Delta B=w_k\sum_{j\in A\cap I_0}v_j+(w_k-w_r)\sum_{j\in S\cap I_0}v_j,
   $$

   with old vector zero at r=0. Its normal contraction is

   $$
   C_{i,r,k}=w_k\mathbf1_{i\in I_0}+w_k\sum_{j\in(A\cap I_0)\setminus\{i\}}\Sigma_{ij}
      +(w_k-w_r)\sum_{j\in S\cap I_0}\Sigma_{ij}.
   $$

   Prove J=E_gamma div B as a distributional Gaussian Stein identity, with the complete face mask and marginal density phi(u_k-theta_i). The diagonal factor is w_k phi(u_k-theta_i)=(q/N)exp(theta_i u_k-theta_i^2/2) for a true-null trigger. Its conditional face masks at DIFFERENT u_k do not automatically partition under dependence. Keep the other-new-null Gram terms and all old-null dilution. B is not asserted to be a scalar gradient. Handle coincident faces by direct grouping or a justified finite-model regularization, never by repeated counting.

2. [ ] **Derive the FDP tilt, heat posterior and signed Ito product without index selection.** Define dQ=f(G_1)dP/F on Brownian paths G_t under P and prove D(Q||P)=D(Q_1||gamma)<=log(1/F). For P_s the heat semigroup with covariance sI, H(t,z)=P_{1-t}f(z), L(t,z)=P_{1-t}B(z), and v_t=grad log H(t,G_t), reconstruct the change of measure and dG_t=dW_t+v_t dt under Q. Derive

   $$
   D:=D(Q_1\|\gamma)=\tfrac12E_Q\int_0^1\|v_t\|^2dt.
   $$

   Work first on time intervals [epsilon,1-epsilon] and positive smooth approximations when necessary. Justify all limits for bounded piecewise constant f and B, including zeros of f; terminal Fisher information is not assumed finite. Reprove T2, if used as a diagnostic only, by coupling G_1 with W_1 and Cauchy-Schwarz: W2(Q_1,gamma)^2<=2D. No conclusion about BH follows from T2 alone.

   Let a_t=L(t,G_t)/H(t,G_t)=E_Q[b(G_1)|F_t]. Derive da_t=K_t dW_t with K_t=grad_z(L/H)(t,G_t), ||a_t||<=1/hU, and

   $$
   J=F E_Q\int_0^1[a_t\mathbin\cdot v_t+\operatorname{tr}K_t]dt.
   \tag{EP}
   $$

   Define the signed M=F E_Q int tr K_t dt, A=E_Q int||a_t||^2dt and x=hU^2 A in[0,1]. Define M also by EP if separate improper trace integrals need a limit; prove agreement. Record the explicit posterior derivative

   $$
   K_t=(\nabla L)/H-L\otimes\nabla H/H^2
       ={\operatorname{Cov}_Q(b(G_1),G_1\mid G_t)\over1-t}.
   \tag{PC}
   $$

   Establish the endpoint covariance formula and its conditional two-replica expression, retaining the full FDP weight. Do not treat conditional posterior coordinates or random BH ranks as independent.

3. [ ] **Prove the exact total resource split and the sufficient-gate algebra.** By the bounded vector martingale identity and Fubini show

   $$
   E_Q\|b\|^2-A=E_Q\int_0^1t\|K_t\|_{HS}^2dt.
   $$

   On f>0 put vbar0=V^{-1}sum_{i in RcapI0}v_i and b=vbar0/h(u_R). Deduce the exact nonnegative split

   $$
   1-x=E_Q\left[1-(hU/h(u_R))^2
       +(hU/h(u_R))^2 V^{-2}\sum_{i,j\in\mathcal R\cap I_0}(1-\Sigma_{ij})\right]
       +hU^2 E_Q\int_0^1t\|K_t\|_{HS}^2dt.
   \tag{TD}
   $$

   Keep rank slack, ACTUAL selected-null Gram dispersion, and Jacobian energy. None can be discarded without a separate estimate. In particular replacing TD by Jacobian energy alone is not justified in iid examples. No independent Gram maximization is permitted.

   The NEW UNPROVED certificate to try is, for finite universal C and a universal small-q interval,

   $$
   M_+\le Cq\sqrt{1-x}.
   \tag{TC}
   $$

   Show exactly how it would suffice: EP, Step 1 and Cauchy-Schwarz give

   $$
   U\le\sqrt{2Dx}+(Cq hU/F)\sqrt{1-x}
       \le\sqrt{2\log(1/F)+C^2q^2hU^2/F^2}.
   $$

   For z=F/(q hU), use exp(-U^2/2)=sqrt(2pi)q hU to obtain 2log[z/sqrt(2pi)]<=C^2/z^2, hence z<=max{sqrt(2pi e),C}. Reprove hU<=U+1/U and U<=sqrt(2log(1/q)) on U>=1, so F<=2sqrt(2)max{sqrt(2pi e),C} q sqrt(log(1/q)). This is only a conditional implication until TC is proved.

4. [ ] **First test the finite lower-family obstruction, and execute the explicit calibrations.** Reconstruct every item below rather than citing this checklist as evidence. Item (a0) is the FIRST substantive test of TC after Steps 1--3; if it rigorously refutes TC, save the finite witness logic, record Failure, and do not attempt Step 5 as though TC survived. The other finite formulas remain explicit calibration obligations, not unproved evidence imported into the target.

   (a0) Read and reconstruct the exact immutable source bh_fdr_research/reference_arxiv/FDR_BH_v4.tex, Section 3.3 equations one-br, one-Wr, one-tau-mu, one-pi-cr and one-nu (planning-time lines 3876--3957), the three population regimes of Section 3.4, and Section 3.5 finite bracketing/DKW argument (lines 5090--5210). The approved node lei2026_one_sided_fdr_lower has no Proof section and is not in the target's dependencies; neither its Statement nor the source's theorem can be used as a new black box. Reproduce the needed population crossings and finite transfer inline. The exact source, rather than flagged PDF OCR, has null type (theta,B)=(0,r), primary alternatives (c_r+b_r,-1), secondary alternatives (a/r+a,-1), masses pi0=1-r-tau, r, tau, with b_r=r S^{-1}(r^2), tau~[(1-q)/q]r^2, and secondary survival law proportional to [1-q exp(a^2/2)]S(a/r)/q on [b_r,sqrt(2log(1/q))]. All non-null means are positive. Here r is chosen sufficiently small for EACH fixed q; no loading fixed across q is asserted.

   Derive the population limit Dstar(z)=q for z<=0, q exp(z^2/2) for 0<z<sqrt(2log(1/q)), and 1 above. Its expectation is ell(q)=q sqrt(log(1/q))/sqrt(pi)+q/2+S(sqrt(2log(1/q))). Reconstruct compact crossing brackets and finite empirical approximation to produce, for arbitrarily large finite N at a chosen fixed q and sufficiently small fixed r>0, deterministic type realizations with F>=c q U for one universal c>0. Keep the original largest BH crossing; the conditional population limit alone is insufficient.

   In these original latent models every selected true-null normal is r e0+sqrt(1-r^2)e_i. Hence prove, EXACTLY for every finite selection,

   $$
   \|b\|^2={r^2+(1-r^2)/V\over h(u_R)^2},\qquad
   x\le r^2+(1-r^2)E_Q(1/V).
   \tag{LF-geometry}
   $$

   Do not assume large V from a population heuristic. For any fixed integer L>=1, prove

   $$
   E_Q(1/V)={E_\gamma[\mathbf1_{V>0}/R]\over F}
       \le {P_\gamma(V>0,R<L)+1/L\over F}.
   $$

   When R<L and V>0 some null has T_i>=u_L=S^{-1}(qL/N). Conditional on Z=z, a union bound is at most min{1,N S((u_L-rz)/sqrt(1-r^2))}, which tends to zero for every fixed z as N tends to infinity at fixed q,r,L. Prove this by Gaussian tail asymptotics, then apply dominated convergence over Z. The bound is uniform over deterministic alternative-type layouts, so the large-N deterministic realization with high F can also have E_Q(1/V) arbitrarily small: choose q, then r, then L, then a sufficiently large finite N, in that order. Singular alternative loading -1 is already legal; if positive definiteness is desired, justify any perturbation separately with its effect on the resource estimate.

   Try to complete the resulting TC obstruction: choose r and N so x<=1/4. EP and entropy imply

   $$
   M\ge {F\over hU}\left[U-\tfrac12\sqrt{2\log(1/F)}\right].
   \tag{LF-trace}
   $$

   From F>=c qU, U/sqrt(2log(1/q))->1 and hU/U->1, derive M>=c'F>=c''qU for sufficiently small q, whereas TC gives M<=Cq sqrt(1-x)<=Cq. For EACH proposed universal C choose q small, then r,L,N finitely as above. If every transfer and inequality is reconstructed, this is a legal finite counterfamily to TC, not a counterexample to the main target; stop there and preserve all entropy/Mills identities. If the construction or finite realization cannot be justified, name its exact missing bracket or selection estimate rather than claim the certificate was disproved.

   (a) N=1: with theta<=0, f is a single Gaussian-tail indicator, b=v_1/hU is constant under Q and K=0, M=0, x=1. Give its exact H and v_t= v_1 phi(z_t)/[sqrt(1-t)S(z_t)]. Check theta<0 separately in the entropy and J inequalities.

   (b) N=2 with one null X of mean zero and alternative Y of positive mean, u1=S^{-1}(q/2)>u2=U, h_j=h(u_j), rho=Sigma12. Derive f=1_{X>=u1,Y<u2}+(1/2)1_{X>=u2,Y>=u2} and

   $$
   \operatorname{div}B={\delta(X-u_1)\mathbf1_{Y<u_2}\over h_1}
     +{\delta(X-u_2)\mathbf1_{Y>=u_2}\over2h_2}
     +\rho\delta(Y-u_2)\left[{\mathbf1_{X>=u_2}\over2h_2}-{\mathbf1_{X>=u_1}\over h_1}\right].
   $$

   Compute conditional Gaussian integrals for H,L,K,M,x with the actual rho, means, labels and covariance, covering rho near both singular endpoints. For posterior probabilities A1=P(rank1 null), A2=P(rank2), write a_t=v_1[c1+(c2-c1)pi_t], c_j=1/h_j, pi_t=(A2/2)/(A1+A2/2). Check that tr K=(c2-c1)pi(1-pi) v_1 dot grad log(A2/A1), including both cell boundaries. Independent rho=0 gives nonpositive trace; positivity at some tilted posterior means cannot be silently excluded for rho>0. In the legal singular model X=G, Y=u1+u2-G, compute F=3q/4 and J=q[1-h1/(4h2)]>q/2 for sufficiently small q: the per-null diagonal J<=q/N shortcut fails.

   (c) Iid all-null: prove F=q and J=q by the actual leave-one-out rank partition, without an independence assumption on selected ranks. For q<1/e, prove P_Q(R>=m)<=(eq)^m/[q(1-eq)]. Splitting R<m versus its tail yields E_Q||b||^2 ->0 as N->infinity at fixed q; entropy Cauchy-Schwarz then gives the EP drift ->0 and M->q. Thus the simpler gate M<=0 is false. For N=2 compute directly

   $$
   \operatorname{tr}K_0=1-\tfrac12[(1-q)/h_1+q/h_2][(1-q)h_1+q h_2],
   $$

   positive near q=0; reconstruct its value rather than inferring the integrated sign from a pointwise check.

   (d) Unweighted perimeter: for iid all-null, the genuine rank0-to1 face p_i=q/N has mask #{j!=i:p_j<=qk/N}<=k-2 for every k>=2. Bound its probability below by 1-2q-b0^2/(1-b0)>=0.9 for q<=1/(16e), b0=3eq/2, so Gaussian perimeter >=0.9 N phi(u1)>=0.9q u1. KL=log(1/q) stays fixed as N grows. This refutes an unweighted absolute-perimeter payment, not TC or the target.

   (e) Rank-one one-null harmonic families: orient its normal +1; every same-direction alternative has higher mean and is selected whenever the null is. Prove selected R is nonincreasing between any two latent points where the null is selected: if a later larger rank qualified, the earlier selected null and the earlier larger opposite-direction scores would already make that rank qualify. Preserve gaps where the null is unselected. Thus b=1/h(u_R) is nonincreasing on Q-support and PC gives tr K<=0. Prove this support-order claim before using it. Also test mixed-null rank-one models, antipodal nulls, unequal null means, clone blocks, weak correlations and almost common-factor models against TC. A numerical absence of violations is not a proof; no heavy local workload is authorized.

5. [ ] **Only if TC survives the finite obstruction test, try an explicit finite-cell/replica allocation to TD, keeping the first unpaid term visible.** On the finite Gaussian threshold cells let A_c be the exact full rejection set, k_c=|A_c|, v_c=|A_c cap I0|, f_c=v_c/(k_c vee1), B_c=w_{k_c}sum_{i in A_c cap I0}v_i, and b_c=B_c/f_c when f_c>0. For the Gaussian kernel of covariance s=1-t, compute cell probabilities P_c(t,z), first moments m_c(t,z), and boundary densities using the complete face masks from Step 1. Write

   $$
   H=\sum_c f_cP_c,\quad L=\sum_c B_cP_c,\quad
   M=\int_0^1\!\int p_t(z)\left[\operatorname{div}L-{L\cdot\nabla H\over H}\right]dz\,dt,
   \tag{FC}
   $$

   where p_t is the latent centered Gaussian density of covariance tI. Derive the two-replica covariance expression PC from these same cells; use TD for its squared-oscillation resource. Retain f_c f_d, b_c-b_d, all rank jumps and the actual Sigma coefficients. Do not bound |tr K| by sqrt(d)||K||, discard negative dilution, or invoke an eigenvalue inverse.

   Attempt the following actual allocation: pair ordered replica cells c,d at their FIRST differing actual BH threshold comparison; group the whole resulting rank jump, including old-null dilution and the change h(u_r) to h(u_k). Allocate a change of 1/h(u_R) to the rank-slack term of TD; allocate a change of selected-null direction to its actual Gram-dispersion term; allocate remaining time/posterior variation to int t||K||_HS^2. Explicitly show Gaussian coarea densities and conditional means for each assigned packet, then apply Cauchy-Schwarz only after summing the signed packets. Prove a universal square budget for the partner coefficients giving TC, or construct a legal finite-model violation. No dimension, log N, direction-count, inverse-variance or mean-dependent constants may remain. An allocation that only rewrites FC=J-drift has not supplied a budget.

   If payment fails, stop and record the FIRST remaining fully displayed cell-pair/face integral, its masks, sign, hazard and covariance coefficients, which of the three resources was tried, and the exact needed bound. Distinguish a proved false auxiliary shortcut, a counterexample to TC, and an unproved TC. Do not mark the target false from failure of this stronger certificate. If a modified certificate is attempted within this plan, first state and prove its exact implication for the unchanged target; do not silently change TC or omit a deficit component.

6. [ ] **Only after a universal certificate, transfer and conclude.** Give the uniform interval and constant from Step 3. Justify the entropy/posterior limits without a dimension-dependent loss. For any singular original Sigma use direct latent-cell grouping or Sigma_epsilon=(Sigma+epsilon I)/(1+epsilon), with the SAME original means and labels. Each univariate threshold boundary has probability zero, so original finite BH sets converge almost surely; dominated convergence gives the FDR limit. No supremum-limit exchange is required when constants are already universal. Recheck every target quantifier, including negative null means, arbitrary positive alternative means, singularity, non-strict inequalities, all finite N and q-dependent parameters. Do not proceed here if TC or its substitute is unproved.

## Verification

Steps 1--3 establish a concrete finite Mills-weighted geometry and an exact entropy/posterior resource identity; none alone proves the target. Step 4 first checks whether the exact finite small-loading lower construction already refutes TC, and separately gives simpler-gate counterexamples and finite calibrations. A verified TC counterfamily ends this plan as an auxiliary-gate failure; it does not falsify the main target. Only if TC survives may Step 5 seek its external square budget using ALL resources in TD, without dimension or eigenvalue loss. Only a proved certificate permits Steps 3 and 6 to establish the target. A fresh independent proof audit is required before any main proof can be accepted; no approval is asserted here.

## Assumed definitions

Only the target's approved definitions gaussian_multiple_testing_model, gaussian_test_pvalues, benjamini_hochberg_step_up, false_discovery_rate and gaussian_worst_case_bh_fdr are assumed. There are no draft-definition assumptions or unproved black-box dependencies. The source idea, external papers and all previous calculations are proof obligations or technique inspiration, not approved premises.

## Difference from failed plans

- plan_252211621cea: replaces an unbounded signed half-line occupation remainder by an explicit bounded posterior field and total variance/coherence resource; no switch-sum estimate is inherited.
- plan_503f8fddcbb5: uses the marginal FDP tilt and posterior martingale instead of global-shift record/entrant allocation; actual labels and hazard dilution remain in finite cells.
- plan_ee2f7b97740a: does not assert a conservative rank-chain potential or pay compatible Hall cuts by endpoint telescoping; the proposed new payment is the fully stated TC.
- plan_one_sided_order_actual_mean_global_flux_20261106: never envelopes all affine critical levels; every coarea packet has an actual largest-rank face mask.
- plan_one_sided_order_common_anchor_rotation_20261107: replaces Abel saturation at an unknown FDR derivative by a new entropy-versus-coherence split, whose missing trace budget must still be proved.
- plan_one_sided_order_convex_proxy_label_curvature_20261107: works with the actual BH field and its complete signed jumps rather than an isotonic proxy with an unpaid FDP-transfer term.
- plan_one_sided_order_gaussian_interpolation_sdp_20261106: uses the actual selected-null Gram dispersion and posterior Jacobian; no independent diagonal PSD completion or raw row-sum dimension factor is asserted.
- plan_one_sided_order_negative_contact_transport_20261106: no inverse-noise contact allocation is imported; the exact signed cell pair is retained through entropy conditioning.
- plan_one_sided_order_peeling_history_kernel_20261107: posterior averaging is over the full FDP-tilted Gaussian law, with a new quantified variance resource rather than another terminal compensation identity.
- plan_one_sided_order_three_face_noise_packing_20261106: the Gram matrix is always the original covariance; it is never optimized independently, and TD retains rank slack as well as null-direction dispersion and Jacobian energy.

## Progress

### P1. Finite Mills field and the exact threshold faces (Step 1)

Fix a finite admissible original model and a Gram realization in finite dimension d, with unit vectors v_i. Write S for the standard normal survival function, phi for its density, and h=phi/S. Take 0<q<=S(1), U=S^{-1}(q), and H=h(U). Only this section uses H as a constant; the heat posterior below is denoted H_t(z). On a realized BH rejection set let R be its size, V its true-null count, and f=V/(R vee 1). Put B=(R h(u_R))^{-1} sum_selected-null v_i when R>0 and zero otherwise, with u_k=S^{-1}(qk/N). The value of b=B/f is needed only on f>0; set it to zero elsewhere when taking ordinary Gaussian convolutions.

For u>0, integration by parts gives S(u)<phi(u)/u and S(u)>=phi(u)u/(1+u^2). Indeed S=phi/u-int_u^infty phi(t)/t^2 dt and the last integral is at most S/u^2. Thus u<h(u)<=u+1/u and h'=h(h-u)>0. Substituting t=u+s/u gives

$$
{uS(u)\over\phi(u)}=\int_0^\infty e^{-s-s^2/(2u^2)}\,ds.
$$

The integrand increases in u, so u/h(u) increases. Consequently ||B||<=f/H and ||b||<=1/H. A selected true null obeys v_i dot G=T_i-theta_i>=u_R-theta_i>=u_R. Therefore

$$
J:=E_\gamma[G\cdot B]\ge E_\gamma[f\,u_R/h(u_R)]\ge (U/H)F,
\qquad F=E_\gamma f.
\tag{P1.1}
$$

For real k in [1,N], differentiating S(u_k)=qk/N yields du_k/dlog k=-1/h(u_k), and hence dlog[kh(u_k)]/dlog k=u_k/h(u_k)>0. The weights w_k=1/[k h(u_k)] are decreasing.

Here is the finite face partition, with no implicit partition across conditional Gaussian laws. Fix i and all other p-values. Let k be the BH rank when p_i=0 and r the rank when p_i=1. Since q<1, the latter procedure excludes i, so r<k. To see both the single switch and r<k, use the following standard deterministic implication, proved directly: if i is selected at a rank l, replacing its p-value by any smaller value leaves every comparison above l false and the l-th comparison true, so the rank remains l. Thus every selected-i configuration has rank k, and i is selected exactly when p_i<=qk/N. In every unselected-i configuration, changing only p_i to 1 cannot alter the rejection set, so its rank is r. At the switching value the old set is S_i={j!=i:p_j<=qr/N}, and the new set is S_i union A_i={i} union {j!=i:p_j<=qk/N}, of size k. In particular k>r. The case r=0 uses an empty old set and no w_0.

For positive-definite score covariance, outside intersections of threshold hyperplanes and other null sets, this gives the full face mask E_{i,r,k}, determined by the preceding two BH computations on the other coordinates. Crossing T_i=u_k from below to above changes B by

$$
\Delta B=w_k\sum_{j\in A_i\cap I_0}v_j
 +(w_k-w_r)\sum_{j\in S_i\cap I_0}v_j,
$$

where the second term is absent at r=0. Contracting with the latent normal v_i gives

$$
C_{i,r,k}=w_k\mathbf1_{i\in I_0}
 +w_k\sum_{j\in(A_i\cap I_0)\setminus\{i\}}\Sigma_{ij}
 +(w_k-w_r)\sum_{j\in S_i\cap I_0}\Sigma_{ij}.
\tag{P1.2}
$$

The union of finitely many thresholds T_i=u_k partitions latent space into finitely many polyhedra on which B is constant. Distributional integration by parts against the Gaussian density, with a compact radial cutoff sent to infinity, is legitimate because B is bounded. Thus

$$
J=E_\gamma\operatorname{div}B
 =\sum_{i=1}^N\sum_{0\le r<k\le N}
 \phi(u_k-\theta_i)
 E[C_{i,r,k}\mathbf1_{E_{i,r,k}}\mid T_i=u_k].
\tag{P1.3}
$$

The diagonal true-null density coefficient is exactly

$$
w_k\phi(u_k-\theta_i)
 ={q\over N}\exp(\theta_i u_k-\theta_i^2/2).
$$

Neither the probabilities in (P1.3) at different u_k nor their conditional laws form a common partition. The other-new-null covariance and old-null dilution terms in (P1.2) remain present. No assertion that B is a gradient was used. For singular scores, distinct index-labelled hyperplanes may coincide; form their actual geometric union first and use its full one-sided jump, not the sum of fictitious individual jumps. The direct finite polyhedral distributional identity remains true in the latent Gram space. The arguments below use only the bounded B and (P1.1), so require no face formula or limiting inverse covariance at singularity.

### P2. The FDP tilt and finite-energy heat posterior (Step 2)

The case F=0 is trivial; assume F>0. Under Wiener measure P let G_t be standard d-dimensional Brownian motion, and let Q have terminal density f(G_1)/F. Because 0<=f<=1,

$$
D:=D(Q\|P)=D(Q_1\|\gamma)
 =E_Q\log(f/F)\le\log(1/F)<\infty.
\tag{P2.1}
$$

The convention 0log0=0 is used under P. Set H_t(z)=P_{1-t}f(z), L_t(z)=P_{1-t}B(z), where P_s convolves with N(0,sI), and let v_t=grad log H_t(G_t). Since f is nonzero on a positive-measure set, H_t is strictly positive and smooth for t<1. The density on the Brownian filtration at time t is H_t(G_t)/F. Both H and L solve the backward heat equation. Ito and the positive density process, first localized away from zero, show that

$$
dG_t=dW_t+v_t\,dt
$$

under Q for t<1, with W a Q-Brownian motion. Applying Ito to log(H_t/F), after localization, gives the finite-time entropy identity. Let t increase to 1. The bounded density H_t/F converges almost surely and in L1 to f/F; xlogx is bounded and continuous on [0,1/F]. Hence its entropies converge, and monotone convergence on the energy gives

$$
E_Q\int_0^1\|v_t\|^2dt=2D.
\tag{P2.2}
$$

These statements do not require a finite terminal Fisher information or a positive terminal f. To remove localization at a fixed t, one can first stop the strictly positive smooth density between 1/n and n; its bounded entropy and the stopped entropy identity bound the drift energy, and then use uniform integrability of the density. The density is globally bounded by 1/F. The resulting finite energy extends W continuously to t=1. Coupling G_1 with W_1, both on this Q-space, also gives W2(Q_1,gamma)^2<=E_Q||int_0^1v_t dt||^2<=2D, but no BH claim follows from that diagnostic.

Bayes' formula gives the bounded vector martingale

$$
a_t={L_t(G_t)\over H_t(G_t)}=E_Q[b(G_1)\mid\mathcal F_t],
\qquad \|a_t\|\le1/H.
$$

The quotient rule with the backward heat equations and Q's drift yields da_t=K_t dW_t, with matrix convention (K_t)_{ij}=partial_j(a_t)_i. Differentiating the Gaussian convolution gives, at s=1-t>0,

$$
K_t={\nabla L_t\over H_t}-{L_t\otimes\nabla H_t\over H_t^2}
 ={\operatorname{Cov}_Q(b(G_1),G_1\mid G_t)\over1-t}.
\tag{P2.3}
$$

In particular the covariance numerator is one half the conditional expectation of (b(Y)-b(Y'))(Y-Y')^T for independent replicas Y,Y' from the SAME posterior Q( G_1 in dot | G_t); their FDP tilt and actual BH sets are retained. This is a conditional replica construction, not independence of posterior coordinates.

The bounded martingale converges in L2 to b(G_1), since the terminal Brownian filtration determines G_1 and f(G_1)>0 Q-almost surely. Ito isometry implies E_Q int_0^1||K_t||_HS^2dt=E_Q||b||^2-||a_0||^2<=1/H^2. Thus for each finite d the signed trace is absolutely integrable in expectation, by |tr K|<=sqrt(d)||K||_HS and Cauchy--Schwarz. This finite-d integrability justification introduces no constant into the later certificate. The drift product is integrable by (P2.2) and bounded a. Applying Ito to G_t dot a_t, localizing and passing to 1, therefore gives

$$
J=F E_Q\int_0^1(a_t\cdot v_t+\operatorname{tr}K_t)dt.
\tag{P2.4}
$$

For completeness, the stopped stochastic integral has zero expectation; the endpoint products are uniformly integrable since |a_t dot G_t|<=||G_t||/H and E_Q sup_t||G_t||^2<infinity. The latter follows directly from the bounded terminal density relative to P. The two finite-variation integrals converge absolutely in L1 by the preceding estimates. This justifies the endpoint passage without a formal improper local-time convention. Define M=F E_Q int tr K_t dt, A=E_Q int||a_t||^2dt and x=H^2 A in [0,1].

### P3. Total deficit and the conditional implication of TC (Step 3)

For the same L2 martingale, E_Q||b||^2-E_Q||a_t||^2=E_Q int_t^1||K_s||_HS^2ds. Integrating t from 0 to 1 and using Tonelli gives

$$
E_Q\|b\|^2-A=E_Q\int_0^1t\|K_t\|_{HS}^2dt.
$$

On f>0, b=vbar_0/h(u_R), with vbar_0=V^{-1}sum_selected-null v_i. Since ||vbar_0||^2=1-V^{-2}sum_selected-null(i,j)(1-Sigma_ij), substitution proves exactly

$$
1-x=E_Q\left[1-(H/h(u_R))^2
 +(H/h(u_R))^2V^{-2}\sum_{i,j\in\mathcal R\cap I_0}(1-\Sigma_{ij})\right]
 +H^2E_Q\int_0^1t\|K_t\|_{HS}^2dt.
\tag{P3.1}
$$

All displayed summands are nonnegative. They are rank slack, the actual selected-null Gram dispersion, and the posterior Jacobian energy; no separate maximization of the Gram matrix was taken.

The certificate TC, M_+<=Cq sqrt(1-x), is NOT established here. If it were true, (P1.1), (P2.2), (P2.4) and Cauchy--Schwarz would give

$$
U\le\sqrt{2Dx}+{CqH\over F}\sqrt{1-x}
 \le\sqrt{2\log(1/F)+C^2q^2H^2/F^2}.
$$

Set z=F/(qH). The exact identity exp(-U^2/2)=sqrt(2pi)qH turns this into 2log[z/sqrt(2pi)]<=C^2/z^2. If z>max(sqrt(2pi e),C), the left side exceeds 1 and the right side is below 1, a contradiction. Finally S(U)<=exp(-U^2/2) for U>=1 (by S(U)<=phi(U)/U), so U<=sqrt(2log(1/q)), while H<=U+1/U<=2U. Thus this UNPROVED certificate would imply the stated universal order with constant 2sqrt(2)max(sqrt(2pi e),C). The rest of this execution tests TC; no target proof or approval is asserted.

### P4a. Reconstructing the small-loading population crossings (first test in Step 4)

This section was reconstructed from the immutable source `bh_fdr_research/reference_arxiv/FDR_BH_v4.tex`, equations one-br through one-nu and the three following regime proofs (planning-time lines 3876--5095). The source theorem and the approved lower-bound node are not used as black boxes. Fix q in (0,S(1)] for this construction, and write y=sqrt(2log(1/q)). The parameter r tends to zero at this FIXED q. Define

$$
b_r=rS^{-1}(r^2),\quad
W_r(a)={\{1-qe^{a^2/2}\}S(a/r)\over q},\quad
\tau_r=W_r(b_r),\quad
\mu_r([a,y])=W_r(a)/\tau_r\quad(b_r\le a\le y),
$$

and pi_r=1-r-tau_r, with c_r determined by S(c_r)=q(r+tau_r)/(1-q pi_r). For sufficiently small r, b_r<y, pi_r>0 and c_r>0. Both nonnegative factors defining W_r decrease, with W_r(y)=0 and W_r(b_r)>0; thus this is a probability survival law with continuous cdf. The type law has mass pi_r at (theta,loading)=(0,r), mass r at (c_r+b_r,-1), and mass tau_r mu_r(da) at (a/r+a,-1). All alternative means are positive.

From the elementary Mills bounds proved in P1, log S(t)=-t^2/2-log t-(log(2pi))/2+O(t^{-2}) as t tends to infinity. In particular S^{-1}(s)/sqrt(2log(1/s)) tends to 1 as s tends to zero. Consequently

$$
b_r\to0,\quad b_r/r\sim2\sqrt{\log(1/r)},\quad
\tau_r\sim[(1-q)/q]r^2,\quad
c_r\sim\sqrt{2\log(1/r)},\quad rc_r\to0,\quad
b_r/r-c_r\to\infty.
\tag{P4.1}
$$

Given a common Z=z, the null score is rz+sqrt(1-r^2) epsilon, while an alternative of mean theta is theta-z. For a score cutoff c>=U set the full normalized population curve Rbar_r,z(c)=q P(T>=c|Z=z)/S(c), with the separate true-null, primary, and secondary contributions denoted A_0,A_1,A_2. Directly from the preceding law,

$$
A_0=q\pi_r{S((c-rz)/\sqrt{1-r^2})\over S(c)},\qquad
A_1={qr\over S(c)}\mathbf1_{c\le c_r+b_r-z},
$$

$$
A_2={q\tau_r\over S(c)}
 \mu_r([r(c+z)/(1+r),y]).
\tag{P4.2}
$$

The survival law is understood to be 1 below b_r and 0 above y. On its interior, with beta=r(c+z)/(1+r),

$$
A_2=[1-qe^{\beta^2/2}]\,{S(\beta/r)\over S(c)};
\qquad 0\le A_2\le {S((c+z)/(1+r))\over S(c)}
\tag{P4.3}
$$

in all cases. For the lower endpoint case, q tau_r<=[S(b_r/r)]<=S((c+z)/(1+r)); for the upper endpoint case A_2=0. This proves the stated global upper bound, including outside the interior.

We need two uniform elementary tail facts. If z and rc stay in compact sets and c tends to infinity, put Delta=(c-rz)/sqrt(1-r^2)-c. Then Delta=O(r), cDelta=(rc)^2/2-z(rc)+o(1). Integrating h(t)=t+O(1/t) over [c,c+Delta] therefore proves

$$
A_0=q\exp\{(rc)z-(rc)^2/2\}+o(1).
\tag{P4.4}
$$

All errors here are uniform on those compact sets. Also, for z in any compact subset K of (0,infinity), the largest possible primary term tends to zero:

$$
A_1\le {qr\over S(c_r+b_r-z)}
 ={r(1-q\pi_r)\over r+\tau_r}
   {S(c_r)\over S(c_r+b_r-z)}=o(1).
\tag{P4.5}
$$

Indeed z-b_r is bounded below by a positive constant, c_r tends to infinity, and the tail ratio is exp(-int_{c_r+b_r-z}^{c_r}h), which tends uniformly to zero. These facts keep every earlier potential crossing under control.

Define the population first crossing C_r(z)=inf{c>=U:Rbar_r,z(c)>=1}, with infinity if empty. Here first crossing in score cutoff is the SAME extremum as largest ordinary BH rank in a finite model, as proved in P4b below. We now give compact brackets excluding every earlier crossing, rather than merely showing that a candidate cutoff qualifies.

For a compact K contained in z<0, all alternatives are selected throughout c=c_r+h/c_r for bounded h, by (P4.1). Equation (P4.4) gives A_0 tends uniformly to q there, and the exact calibration of c_r and the integrated hazard give

$$
\bar R_{r,z}(c_r+h/c_r)\to q+(1-q)e^h.
\tag{P4.6}
$$

For every eta>0 and U<=c<=c_r-eta/c_r, the shifted null cutoff is larger than c (because z<0), so

$$
\bar R_{r,z}(c)
 \le q\pi_r+{q(r+\tau_r)\over S(c_r-\eta/c_r)}
 \to q+(1-q)e^{-\eta}<1.
\tag{P4.7}
$$

The same inequality bounds the alternative term even if some alternatives are absent. Thus A_r(z)=c_r-eta/c_r and B_r(z)=c_r+eta/c_r are strict brackets with a uniform positive gap, and A_0 throughout this bracket tends uniformly to q.

For compact K contained in (0,y), put d(z)=q exp(z^2/2)<1. At c=z/r+h for bounded h, the primary term is absent because z/r dominates c_r+b_r-z. The secondary-law cutoff beta=z+rh/(1+r) is interior. The logarithm of its tail ratio is

$$
\log{S(z/r+h/(1+r))\over S(z/r+h)}=zh+o(1),
$$

uniformly on K and bounded h, by integrating h(t)=t+O(1/t) on the interval of length rh/(1+r). Hence (P4.3)--(P4.4) give

$$
\bar R_{r,z}(z/r+h)\to d(z)+(1-d(z))e^{zh},
\qquad A_0(z/r+h)\to d(z).
\tag{P4.8}
$$

To exclude earlier crossings fix eta>0. If there were r_n decreasing to zero, z_n in K and U<=c_n<=z_n/r_n-eta with Rbar_{r_n,z_n}(c_n)>=1-o(1), pass to a subsequence with z_n tending to z_0 and r_n c_n tending to x in [0,z_0]. If c_n stays bounded, the null term tends to q and the alternatives are at most q(r_n+tau_{r_n})/S(c_n)=o(1), a contradiction. If c_n tends to infinity and x<z_0, put d_n=(c_n+z_n)/(1+r_n). Then d_n-c_n tends to z_0-x>0, and (P4.3) plus h(t)>=t give A_2<=exp[-c_n(d_n-c_n)]=o(1). The primary term is o(1) by (P4.5), and (P4.4) bounds the limit by q exp(xz_0-x^2/2)<=d(z_0)<1. Finally if x=z_0, write h_n=c_n-z_n/r_n<=-eta. A bounded h_n gives a strict gap by (P4.8). If h_n tends to minus infinity, then c_n(d_n-c_n) is asymptotic to -z_0 h_n and tends to infinity, so again A_2=o(1), A_1=o(1), and A_0 tends to d(z_0)<1. This exhausts all subsequences and proves the uniform earlier gap. Therefore A_r=z/r-eta and B_r=z/r+eta are strict brackets, with A_0 uniformly tending to d(z) throughout.

For compact K contained in (y,infinity), let alpha(z)=z-sqrt(z^2-y^2), so 0<alpha(z)<min(z,y). Choose eta>0 so that 0<alpha(z)-eta<alpha(z)+eta<min(z,y) uniformly. For x in a compact set with 0<x<z, at c=x/r the primary term is absent and (P4.3) implies A_2<=exp[-(x/r)(z-x)/(1+r)] tends to zero. Thus

$$
\bar R_{r,z}(x/r)\to q\exp(xz-x^2/2),\qquad
A_0(x/r)\to q\exp(xz-x^2/2).
\tag{P4.9}
$$

This limit crosses 1 at its smaller root x=alpha(z). There is a uniform earlier gap for U<=c<=(alpha(z)-eta)/r: a hypothetical near-crossing subsequence has either bounded c and total limit q, or unbounded c with rc tending to x<=alpha(z_0)-eta<z_0. In the latter case (P4.5) makes A_1=o(1), (P4.3) makes A_2=o(1), and (P4.4) bounds the limit by q exp[(alpha(z_0)-eta)z_0-(alpha(z_0)-eta)^2/2]<1. At B_r=(alpha(z)+eta)/r the null term alone exceeds 1 with a uniform positive gap. Taking A_r=(alpha(z)-eta)/r gives the required bracket. As eta decreases to zero and then r decreases to zero, A_0 throughout that bracket tends uniformly to 1. No derivative or local regularity theorem is needed for these brackets.

We have proved directly, on every compact set avoiding 0 and y, strict lower/upper crossing brackets with A_0 throughout them arbitrarily close to

$$
D^*(z)=
\begin{cases}
q,&z\le0,\\
qe^{z^2/2},&0<z<y,\\
1,&z\ge y.
\end{cases}
\tag{P4.10}
$$

For the population itself these brackets imply A_0(C_r(z)) tends to D^*(z) uniformly on each such compact set. At the two endpoints the assigned values do not affect integrals. Its Gaussian expectation is exactly

$$
\ell(q)=E D^*(Z)=q/2+{qy\over\sqrt{2\pi}}+S(y)
 ={q\sqrt{\log(1/q)}\over\sqrt\pi}+q/2+S(y).
\tag{P4.11}
$$

This is so far only population crossing information. The finite deterministic Gaussian realization, with the actual ordinary largest-rank rule, is supplied next; no population limit has been substituted for a finite counterfamily.

### P4b. Finite deterministic realization and simultaneous small-rank control

Fix q and a compact E contained in the complement of {0,y}. It can be chosen so that int_E D^*(z)phi(z) dz>=7ell(q)/8: D^* is bounded and the Gaussian law gives arbitrarily small mass to the two excluded points and far tails. By P4a choose r>0 sufficiently small, with r^2<=1/8, and compact brackets A_r(z)<B_r(z), z in E, such that for some gamma>0

$$
\sup_{z\in E}\sup_{U\le c\le A_r(z)}\bar R_{r,z}(c)\le1-\gamma,
\qquad \inf_{z\in E}\bar R_{r,z}(B_r(z))\ge1+\gamma,
$$

$$
\sup_{z\in E}\sup_{A_r(z)\le c\le B_r(z)}
 |A_0(c)-D^*(z)|\le\ell(q)/16.
\tag{P4.12}
$$

For the positive regime, choose its bracket width eta first to give the latter error, and then r small; all compact component brackets have bounded supremum C_*:=sup_E B_r(z)<infinity. These choices are at fixed q and r; C_* is allowed to be very large.

Temporarily sample N independent types from the three-component law in P4a, independently of Z and independent standard normal residuals epsilon_i. Conditional on the types omega=((theta_i,loading_i))_{i<=N}, define

$$
T_i=\theta_i+B_iZ+\sqrt{1-B_i^2}\,\varepsilon_i.
\tag{P4.13}
$$

For every deterministic type realization this is a finite jointly Gaussian model with unit marginal variances and a PSD correlation matrix. A null has theta_i=0,B_i=r; every alternative has theta_i>0,B_i=-1. Its means and null labels do not depend on Z. Let F_omega denote its ordinary BH FDR. Conditional on Z=z BEFORE fixing omega, the pairs (type_i,epsilon_i) are iid. Define the empirical p-value cdf Fhat_N(s) and the null sub-cdf Ghat_N(s)=N^{-1}sum_i 1{theta_i=0,p_i<=s}; their population means are F_z(s),G_z(s). Then Rbar_{r,z}(c)=qF_z(S(c))/S(c) and A_0(c)=qG_z(S(c))/S(c).

Here is a self-contained uniform empirical bound adequate for all atoms and marks. For iid uniforms U_i, at each grid point j/m the centered Bernoulli sum obeys

$$
P\left(\left|N^{-1}\sum_i\mathbf1_{U_i\le j/m}-j/m\right|>a\right)
 \le2e^{-2Na^2}.
$$

To derive this, the log moment generating function of a centered Bernoulli has value and first derivative zero at 0 and second derivative at most 1/4 everywhere; integrating twice gives E exp(lambda(X-EX))<=exp(lambda^2/8). Markov's inequality, independence and minimization at lambda=4a yield each one-sided exp(-2Na^2) bound. Monotonicity of the empirical cdf between grid points then gives its uniform error at most a+1/m whenever all grid errors are at most a. Quantile-transform any distribution, with independent randomized uniforms at atoms, to obtain exactly the same bound for its empirical cdf, since the inverse-cdf representation satisfies 1{X_i<=s}=1{U_i<=F_X(s)} almost surely simultaneously in s. For the null sub-cdf, use X_i=p_i if theta_i=0 and X_i=2 otherwise; its ordinary cdf restricted to s in [0,1] is exactly the sub-cdf. Applying the argument to the two cdfs separately and union bounding is valid even though they share observations.

For any e>0 choose m>=2/e, take a=e/2, and conclude, uniformly in the arbitrary conditional z,

$$
P\left(\max\{\|\widehat F_N-F_z\|_\infty,
 \|\widehat G_N-G_z\|_\infty\}>e\mid Z=z\right)
 \le4(m+1)e^{-Ne^2/2}.
\tag{P4.14}
$$

Now take e>0 so that q e/S(C_*)<=min(gamma/2,ell(q)/16). On the complementary event in (P4.14), both normalized empirical curves differ from their population counterparts by at most min(gamma/2,ell(q)/16) throughout [U,C_*]. This is a fixed positive tolerance at fixed q,r and E.

The empirical first crossing is EXACTLY the ordinary BH cutoff. Indeed let R be the largest qualifying rank and C_N=u_R if R>0, infinity otherwise. At u_R exactly R p-values are <=qR/N: more would give a larger qualifying rank. Thus q Fhat_N(S(u_R))/S(u_R)=1. Conversely if q Fhat_N(S(c))/S(c)>=1 at any c>=U, put k=N Fhat_N(S(c)). Then k>=1, S(c)<=qk/N and the kth largest score is at least c>=u_k. Rank k qualifies, so R>=k and u_R<=u_k<=c. Therefore C_N is the smallest empirical crossing, with the original non-strict comparisons and all multiplicities. This proof makes no continuity assumption about conditional alternatives or their possible ties.

The earlier gap and upper bracket in (P4.12) now imply A_r(z)<C_N<=B_r(z). At C_N the normalized empirical null curve is precisely the FDP, because R/N=S(C_N)/q. Hence on the good empirical event and z in E,

$$
f\ge D^*(z)-\ell(q)/8.
$$

On the bad event f>=0, so integrating gives

$$
E_\omega F_\omega
 \ge\int_E D^*(z)\phi(z)dz-\ell(q)/8-4(m+1)e^{-Ne^2/2}
 \ge3\ell(q)/4-4(m+1)e^{-Ne^2/2}.
\tag{P4.15}
$$

For EVERY sufficiently large integer N this is at least 5ell(q)/8. In particular some deterministic omega at that N has F_omega>=ell(q)/2. Since y>=U, ell(q)>=qU/sqrt(2pi). With the fixed universal c_0=1/(2sqrt(2pi)), we have proved the following finite existence statement, not an asymptotic-model substitute:

For each chosen q, one can choose a fixed sufficiently small r>0 with r^2<=1/8 such that for every sufficiently large finite N there is a deterministic original type realization with

$$
F_\omega\ge c_0 qU.
\tag{P4.16}
$$

The deterministic realization may depend on N, as the main model allows. Its alternatives have singular loading -1, which is admissible. No positive-definite perturbation is needed or used in this counterfamily; hence the selected-null normal geometry remains exact.

It remains to ensure a LARGE number of selected nulls under the FDP tilt, without assuming it from a population limit. In every finite deterministic realization (P4.13), the selected true-null normals are r e_0+sqrt(1-r^2)e_i for distinct i. Thus pointwise on V>0,

$$
\|b\|^2={r^2+(1-r^2)/V\over h(u_R)^2},\qquad
x=H^2A\le H^2E_Q\|b\|^2
 \le r^2+(1-r^2)E_Q(1/V).
\tag{P4.17}
$$

For any integer L>=1,

$$
E_Q(1/V)={E_\gamma[\mathbf1_{V>0}/R]\over F}
 \le{P_\gamma(V>0,R<L)+1/L\over F}.
\tag{P4.18}
$$

If V>0 and R<L, some null score is at least u_R>=u_L:=S^{-1}(qL/N). For N>=L, conditional on Z=z a union bound over at most N true nulls gives, UNIFORMLY over all deterministic type realizations,

$$
P(V>0,R<L\mid Z=z)
 \le\min\left\{1,N S\left({u_L-rz\over\sqrt{1-r^2}}\right)\right\}.
\tag{P4.19}
$$

At fixed q,r,L,z with 0<r<1, the Mills expansion above implies u_L^2=2log N+O(loglog N). Consequently the logarithm of the untruncated right-hand factor is

$$
\log N-{(u_L-rz)^2\over2(1-r^2)}+O(\log u_L)
 =-{r^2\over1-r^2}\log N+O_{q,r,L,z}(\sqrt{\log N}+\log\log N),
$$

which tends to minus infinity. Dominated convergence in z proves that the integral epsilon_N(q,r,L) of the right side in (P4.19) tends to zero. Crucially epsilon_N does not depend on the alternative layout or the number of nulls.

Choose parameters in this order. Fix q small. Choose a single r>0 as in (P4.16), with r^2<=1/8. Then choose a finite integer L with 1/L<=c_0 qU/16. Finally choose a sufficiently large finite N>=L so that BOTH the finite existence threshold (P4.16) holds and epsilon_N<=c_0 qU/16. At that SAME N choose its deterministic realization with F>=c_0 qU. The uniform bound (P4.19) still applies to it, so (P4.18) gives E_Q(1/V)<=1/8 and (P4.17) gives

$$
x\le1/8+1/8=1/4.
\tag{P4.20}
$$

There is no exchange of a q-limit with the dimension limit: r,L,N have all been selected finitely at each q, in the stated order, and the original model is retained.

### P4c. A finite counterfamily to TC, with all entropy identities retained

For the deterministic finite models just constructed, P1.1, P2.2 and P2.4 imply

$$
M=J-F E_Q\int a_t\cdot v_tdt
 \ge{F\over H}\{U-\sqrt{2D x}\}
 \ge{F\over H}\left\{U-\tfrac12\sqrt{2\log(1/F)}\right\}.
\tag{P4.21}
$$

Because F>=c_0 qU and U/sqrt(2log(1/q)) tends to 1, for all sufficiently small q we have sqrt(2log(1/F))<=3U/2. To check this last asymptotic without another black box, apply the two Mills bounds to q=S(U): log(1/q)=U^2/2+log U+(log(2pi))/2+O(U^{-2}); also log(1/F)<=log(1/q)-log(c_0 U). Their ratio to U^2/2 tends to at most 1. Thus (P4.21), H<=2U and (P4.16) give

$$
M\ge {FU\over4H}\ge F/8\ge(c_0/8)qU>0.
\tag{P4.22}
$$

Given ANY proposed universal constant C<infinity and ANY proposed small-q interval (0,q_0], choose q in that interval small enough for all preceding estimates and U>8C/c_0. Then choose r,L,N and a deterministic Gaussian realization exactly as in P4b. In this ONE finite legal original model,

$$
M_+=M>Cq\ge Cq\sqrt{1-x}.
\tag{P4.23}
$$

This rigorously refutes TC as quantified in Step 3. It does not refute the target: its FDR is of the allowed lower order q sqrt(log(1/q)), and neither a violation of the desired upper bound nor any negative-null-mean simplification was asserted. The trace resource must be allowed to be of that same order in a low-coherence family. Since TC has already failed the mandatory first test, the later calibration examples and replica allocation are not executed or treated as established here.

## Failure

Step 3's stronger certificate TC is false. The first mandatory test of Step 4 supplies a counterfamily of finite admissible original Gaussian models: P4a reconstructs all three source population regimes and excludes every earlier crossing; P4b reconstructs the finite empirical transfer and selects a deterministic type realization at the same sufficiently large N used in the uniform small-rank bound. For every sufficiently small q its parameters are selected in the order q, fixed small r>0, integer L, finite N. It has F>=c_0 qU, selected-null coherence resource x<=1/4, and signed trace M>=(c_0/8)qU. Thus no finite universal C on any small-q interval can satisfy M_+<=Cq sqrt(1-x).

The exact obstruction is low selected-null coherence with a nonnegligible trace of order qU: the proposed O(q) trace payment is too small even for a known lower-order Gaussian construction. No face allocation to the same total-deficit resource can prove this false certificate. A replacement would have to allow this trace scale while still converting its interaction with entropy and coherence into the unchanged universal FDR upper bound; that further estimate has not been proved here.

Steps 1--3 are established in P1--P3, and the decisive first test of Step 4 is established in P4a--P4c. The other Step 4 calibrations, Step 5 and Step 6 were deliberately not executed after the certificate failed. All completed derivations remain under Progress. The main target's statement and file are untouched; this is an auxiliary-certificate counterfamily, not a counterexample to the main theorem, and no result approval is asserted.
