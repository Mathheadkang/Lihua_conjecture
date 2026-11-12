---
type: idea
title: >-
  Exact signed centering allocation across old and enlarged BH ranks with
  trigger normalization
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - centering
  - signed-rank-allocation
  - plan-stage-partial
---

Draft new exact coupling identities and a concrete failed pointwise payment attempt from the current PLAN stage. They refine idea_6a6dd5cbb6e1 without treating it as an approved lemma. No proof of a uniform expected centering comparison, no main theorem proof, and no native state transition is claimed.

COUPLING AND SIGNED IDENTITY. Couple two full Gaussian testing models by the same centered Gaussian score vector and same covariance. Increase only the means of a set J of original true nulls, leaving all original labels and all alternatives fixed; the increase can be complete centering of shallow negative nulls. Keep the full ordinary largest-crossing BH procedure in both. Coordinatewise monotonicity gives nested rejection sets. On the event R=r>=1 and R_plus=s>r, put V=v, A=r-v, DeltaV=V_plus-V, DeltaA=A_plus-A. Then the exact signed difference is
FDP-FDP_plus = [v DeltaA-A DeltaV]/(r s).
This isolates dilution by newly admitted alternatives and its paired new-null payment. On R=0 the original FDP is zero, and on R_plus=R the rejection sets coincide.

ACTUAL-SELECTED-RANK TRIGGER ALLOCATION. Let t_k=qk/N and C_original(t)=#{i:p_i<=t}. At the enlarged actual selected rank s, C_plus(t_s)=s. The original largest-crossing rule gives C_original(t_s)<s. Thus
m=s-C_original(t_s)=#{j in J:p_j_plus<=t_s<p_j}>=1.
Each such trigger is a newly admitted null, so DeltaV>=m. Because alternatives are unchanged, DeltaA=#{k in I1:t_r<p_k<=t_s}, where I1 is the fixed original alternative set. Consequently the positive term has the exact finite allocation
(v/r)(DeltaA/s)
= sum_{i in I0,j in J,k in I1} 1{i originally rejected}1{p_j_plus<=t_s<p_j}1{t_r<p_k<=t_s}/(r s m).
The i and j indices are automatically distinct. Every indicator refers to the original pair of full procedures and the same two selected ranks. No data-chosen free threshold is introduced. The negative term -A DeltaV/(r s) remains part of the exact signed expectation and must not be discarded before averaging.

CONCRETE POINTWISE PAYMENT ATTEMPT AND FAILURE. A candidate rule charging every positive dilution cell by a small universal multiple of the mean increment cannot work. Take N=s>=3; one null has p<q/s, one trigger null has original p>q but centered p<q, and all s-2 alternatives have p in (q(s-1)/s,q). Originally no rank 2,...,s qualifies: the alternatives exceed each threshold up to s-1 and at rank s the trigger is absent. Thus R=V=1. After the trigger crosses q, rank s qualifies and is largest, with R_plus=s and V_plus=2. The exact signed FDP loss is 1-2/s, while the trigger score increment can be arbitrarily small. This is an open cell of positive probability in a legal independent Gaussian model: give the trigger a shallow negative mean, the other null mean zero, the alternatives any strictly positive means, and choose its centered score in (U,U+a) when its original mean is -a. Every displayed strict p interval then has positive probability. This does not refute an expectation bound; negative contributions on other cells must cancel this local loss, as independent Gaussian BH calibration already requires.

WHY ELEMENTARY GAUSSIAN PAYMENT DOES NOT CLOSE. For centering means -a_j with a_j<=a_q, a fixed deterministic enlarged rank s has trigger condition X_j in [u_s,u_s+a_j), u_s=barPhi^{-1}(qs/N). Its marginal probability is at most a_j phi(u_s). Summing these fixed-s marginal bounds over all j and all possible selected s removes the exact reciprocal trigger normalization and the joint largest-crossing masks, leaving uncontrolled rank/direction multiplicity. Conversely, the exact triple allocation above retains the required weights but currently has no uniform signed Gaussian sum estimate. The remaining task is an averaged estimate of this explicit allocation paired with -A DeltaV/(rs), not a newly named assumed comparison theorem.

DIFFERENCE FROM THE PREVIOUS SIGNED PATH MECHANISM. Native show of plan_252211621cea, Progress sections 4-5, was used because its summary omits the exact endpoint calculation: full scalar record/Abel pairing leaves M=sum_i E[(2Phi(X_i)-1)1{i rejected}/(R vee1)], between (1-2q)FDR and FDR. Hence repeating the same integration by parts would recover the unknown FDR rather than pay the new triple allocation. Native show of plan_one_sided_order_negative_contact_transport_20261106, Plan steps 2-3, confirms that its active negative-contact density retains actual covariance weights but needs a global signed transport estimate after empty-gap packing. The present two-model rank allocation is genuinely different algebraically, yet neither old result supplies its averaged payment. No filler main proof plan is created. Original assets, approvals, failed plans and loop state remain unchanged.
