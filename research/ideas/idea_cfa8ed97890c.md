---
type: idea
title: >-
  Tagged-direction screening: occupation bound and non-transfer of old
  refutations
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - tagged-direction-smoothing
  - occupation-bound
  - screening
---

Screening of [Background-preserving tagged-direction smoothing of transported BH cells](idea_9504c21390e4.md). The source is preserved. These are new agent derivations in a draft observation, not independently verified or approved results. No helper goal, pending main plan, project/state change or original-gate repair is made.

## Exact mass identity and physical replication

Write S for the standard Gaussian survival function, phi for its density, u_r=S^{-1}(qr/N), U=S^{-1}(q), v=1-exp(-2), and h(t)=phi(t)/S(t). All calculations below use 0<q<=S(1), so U>=1. Use precisely H_i, R_i and B_q from the source, with the original true-null labels.

Deterministic BH stability: if the forced-zero rank is r and the original p_i<=qr/N, replacing the zero by p_i leaves at least r values below qr/N, so the original rank is at least r. Forcing a p-value down cannot decrease rank, hence the original rank equals r. Conversely, if original BH rejects i with rank r, then at every later threshold qk/N, k>r, p_i is already below the threshold; forcing it to zero changes no later count, and the forced rank remains r. This proves the cell identity with ties and largest nonstrict rank. Translation by c_ir a_i has Gaussian density ratio exp(-c_ir a_i.y-c_ir^2/2), proving sum_i int H_i d gamma=FDR. One-dimensional Mehler invariance, with the ORIGINAL perpendicular law, implies FDR<=B_q by Tonelli.

Replicate every physical score J times in the same latent embedding. Original BH has R'=JR and identical FDP: a replicated qualifying rank k implies the original rank ceil(k/J) qualifies, while every original qualifying r gives the replicated qualifying Jr. On every nonzero transported clone term the clone's own original p-value meets the forced-rank threshold, so stability gives the actual rank R'=JR. Consequently only ranks Jr occur on that term's support, the translation threshold is exactly c_ir, and each clone's full H is H_i/J. Taking its directional Mehler supremum and summing J clones proves exact B_q replication invariance, including ties and negative null means.

## N=1 and independent scores

For independent original scores, conditional on the perpendicular background, the forced rank is one fixed r independent of the tagged coordinate. Hence H_i is one exponential half-line with c=u_r-theta_i>=u_r>=1. The smoothing density is at most 1/sqrt(2*pi*v), so
$$
sup_z M_i H_i(z,xi) <= exp(-c^2/2)/(r c sqrt(2*pi*v))
=phi(c)/(r c sqrt(v)) <=2S(c)/(r sqrt(v)) <=2q/(N sqrt(v)).
$$
The Mills estimate used here follows from S(c)>=phi(c)c/(c^2+1). Summation gives B_q<=2q/sqrt(v); N=1 with any theta<=0 is included. There is no assumption on alternative means.

## New occupation bound for K identical-loading groups

Suppose the ORIGINAL true-null directions take only K distinct unit-vector values. No restriction is placed on alternative directions, their means, the ambient rank or the number of distinct true-null means. Within each identical-direction null group order null means nonincreasingly, breaking ties arbitrarily, and assign label k=1,...,n_g to each null. On a genuine rejected contribution of the k-th null, the k earlier same-direction null scores are at least its score, hence r>=k. Put b_k=u(qk/N)>=U.

For a fixed perpendicular background xi, first integrate H_i with ordinary Lebesgue measure in its marked coordinate. In the r-th term substitute physical source coordinate x=w+c_ir and then the tag's physical score t=x+theta_i. The forced-rank sets in x partition the real line, so at any t there is at most one active r. Its support has t>=u_r and r>=k, hence U<=u_r<=b_k. Moreover the exact kernel identity is
$$
exp[-c_ir x+c_ir^2/2]/r
= sqrt(2*pi)q/N * h(u_r) exp[-u_r(t-u_r)] exp[theta_i t-theta_i^2/2].
$$
The last factor is <=1 because theta_i<=0 and t>=U>0. This is an occupation integral, with no count of the path's switches.

On U<=t<=b_k, monotonicity of h gives h(u_r)exp[-u_r(t-u_r)]<=h(t). For t>=b_k, use h(u)<=2u for u>=1. The function u exp[-u(t-u)] has convex logarithm on [U,b_k], since the second derivative is 2-1/u^2>=1. Its maximum is at an endpoint. Thus the tail integral is at most
$$
2 int_{b_k}^infty [U exp(-U(t-U))+b_k exp(-b_k(t-b_k))]dt <=4.
$$
Also int_U^{b_k}h(t)dt=log[S(U)/S(b_k)]=log(N/k). Combining with the supremum bound on the one-dimensional smoothing density gives, for EVERY background xi,
$$
sup_z M_iH_i(z,xi) <= q/(N sqrt(v))*[4+log(N/k)].
$$
Therefore, using log(n!)>=n log(n)-n,
$$
B_q <= q/sqrt(v) * [5+log K].
$$
For completeness, with p_g=n_g/N and pi=sum_g p_g<=1, the sum is at most pi[5+log(K/pi)]<=5+log K; this function increases on 0<pi<=1. Empty true-null sets give B_q=0. This proves a useful complexity-dependent screening bound, not the unrestricted gate.

Consequences: all scalar Gaussian arrays have K<=2, with arbitrary mixed labels and means, so B_q<=q[5+log2]/sqrt(v). This is stronger screening than finitely many scalar numerical evaluations. The approved [tangent-reserve positive-path counterexample](../assets/cx_gaussian_bh_positive_p_path_jump_budget_r4_s3_tangent_reserve_reset.md) has at most THREE true-null directions: selected X and the two driver loadings; reserve mean 2 is alternative. Its B_q is therefore uniformly O(q), even though its positive jump budget diverges. The jump-budget refutation does not transfer: repeated occupation switches do not multiply this integral. Its fixed level q=S(1) is covered by this calculation.

## What happens to the approved vanishing-loading calculation

Read the exact approved [vanishing-loading refutation](../assets/cx_gaussian_bh_one_sided_translated_cell_mehler_congestion_r2_s3_vanishing_loading.md), including all later-rank checks. For its eta=1/L, m=ceil(exp(L^3/10)), N=2m and selected ranks k in its K interval, retain its notation Delta_k and J_k=((1+eta/4)Delta_k,(1+eta/2)Delta_k). Put s=sqrt(1-eta^2). For tagged null i write the marked coordinate as w and its ORIGINAL perpendicular Gaussian coordinates as W=s Z_0-eta Z_i and Z_j, j!=i. These are independent standard normals. At the transported source, the common coordinate is eta(w+u_k)+sW. Set Y_0=eta w+sW. On Y_0 in J_k, the old alternative-count calculation is unchanged: at threshold u_{k+1}, exactly k-1 alternatives qualify. Indeed alternative j=k is below the threshold because Y_0>Delta_k, while j=k-1 is above it because Y_0<(1+eta/2)Delta_k<=(1+eta)Delta_{k-1}.

But the other-null count at the same threshold, conditional on w,W, is now Binomial(m-1,p), with
$$
p=S((u_{k+1}-eta Y_0-eta^2 u_k)/s) >= S(u_k)=qk/N.
$$
The inequality uses Y_0>0, u_{k+1}<u_k and s^2=1-eta^2. Its mean is at least qk/3 for large m. In the approved selected-rank range, min_k qk tends to infinity, since log a=(2/45)L^3+L-O(log L). Consequently the probability of no other-null exceedance is at most exp(-qk/3), uniformly tending to zero. Whenever there is at least one other-null exceedance, the forced zero plus k-1 alternatives plus that null make rank k+1 qualify. Therefore the essential old exact mask R_i=k fails on these same J_k slices with probability tending to one under the new background law.

This is a precise NON-TRANSFER result for the approved lower-bound argument, not an upper bound for B_q on that family. Later ranks could still contribute under other slices; no cancellation or uniform estimate for them is asserted. The old full-dimensional refutation, and the unverified constant-width full-dimensional risk, provide no refutation of the new functional. The ladder has m distinct null directions, so the proved K-bound still gives only a dimension-dependent estimate there.

## Decision and first unpaid step

The tagged functional is a distinct stronger sufficient gate, not algebraically equal to unknown FDR: its conditional supremum has discarded the original marked-coordinate averaging, while retaining the original perpendicular law. The occupation calculation supplies a genuinely new partial mechanism and explains why positive variation is unnecessarily costly. It does NOT yet give an executable unrestricted main proof. There is no uniform control replacing log K when all true-null directions are distinct, including the full original-variance ladder. A successful continuation must prove an original-background averaged bound on the occupation envelope using correlations between DIFFERENT directions, preserving actual ranks. Simply assuming that bound would be a filler main plan. No pending main plan is written.

Native library search for marked directional Gaussian occupation BH original background supplied no applicable lemma. The closest Simes node requires positive dependence and has no reproduced proof; the OU reverse-isoperimetry node supplies no BH occupation or conditional-supremum budget. Neither is used as a black box.

Source hashes checked immediately before creation: proposal 7e4907e284e220c4aaee0d282824bae305c9b6da905aab0614af55ee9679187d; tangent-reserve example 33ef7680918563e5276c7589229ef61a758c43111671d1d737c062d1c4e6fca7; vanishing-loading example f64c1f761b603cdc8bdaca81c70c9f1c47315341b4614b5e086d35505f4d5819. The cwd is not a Git repository. Native idea add creates a new node; no existing source node is rewritten.
