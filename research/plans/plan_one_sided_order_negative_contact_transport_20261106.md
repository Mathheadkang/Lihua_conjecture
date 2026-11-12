---
type: plan
title: Universal one-sided order through actual negative-covariance contact transport
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by: [idea_a86ab0021015, idea_61f383a494e4, idea_7e2b1eaa2f33, idea_bdb4492a7046]
---

# Universal one-sided order through actual negative-covariance contact transport

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the exact current statement with finite universal constants, without seeking sharp constants: every finite N, every mean vector, every unit-diagonal PSD covariance including singular matrices, actual true nulls I_0={i:theta_i<=0}, and ordinary largest-qualifying-rank BH with non-strict inequalities. All these parameters, including the null proportion, may vary arbitrarily with q. A restricted covariance class or a dimension-dependent bound is not sufficient.

The new proposed mechanism is the exact active one-contact formula with the original negative covariance coefficients. It is a new attack on the unresolved actual-mean flux estimate, not a claim that that estimate was proved earlier. The [contact proposal](../ideas/idea_a86ab0021015.md), earlier partial BV calculations, and fixed-gap calculation in the third failed plan are sources of proof obligations only. The [audited auxiliary obstruction](../ideas/idea_61f383a494e4.md) rules out the unweighted integrated SDP budget, not this contact budget or the target. Planning-time library searches for Gaussian BH negative-covariance contact transport and fixed-gap density packing returned no applicable result. No supporting theorem outside the target's existing dependencies is assumed.

Execution must write its first completed derivation into this plan's Progress immediately, and save each subsequent checkpoint in edits of at most 6000 tokens. Do not accumulate a whole attempted proof in chat. Re-read the current file and exact insertion region before each write; preserve concurrent changes. Stop at the first essential unproved gate, retaining all successful derivations and the precise obstruction.

## Plan

1. [x] **Reconstruct the actual-mean BV reduction inline.** Fix an arbitrary positive-definite unit-diagonal covariance, N>=2, and 0<q<=S(1), where S=barPhi, phi=-S', U=S^{-1}(q)>=1, t_k=qk/N and u_k=S^{-1}(t_k). Treat N=1 and I_0 empty directly. For each actual true null put X_i=T_i-theta_i and regress
   $$
   T_j=\theta_j+\Sigma_{ij}X_i+W_j^{(i)},\qquad j\ne i,
   $$
   where the jointly Gaussian residual vector W^(i) is independent of X_i; its coordinates are not asserted independent. Force only p_i to zero, and let R_i(x)>=1 be the resulting ordinary BH rank, tau_i(x)=q R_i(x)/N. Prove the force-zero identity for the actual rejection of i, including ties, and hence
   $$
   \operatorname{FDR}=\frac qN\sum_{i\in I_0}\mathbb E I_i,
   \qquad
   I_i=\int_{\mathbb R}\frac{\phi(x)}{\tau_i(x)}
   \mathbf1\{S(x+\theta_i)\le\tau_i(x)\}\,dx.
   $$
   Define g_i(x)=S(x)/S(x+theta_i) and h_i(x)=min{S(x)/tau_i(x),g_i(x)}. Prove finite piecewise constancy of R_i, Gaussian hazard monotonicity, g_i'<=0 for theta_i<=0, h_i(-infinity)=1, h_i(+infinity)=0, and all integrability assertions. Include theta_i=0 separately where needed. On rejection cells h_i'=-phi/tau_i; on the other cells h_i'=g_i'. Sum the interval identities, including endpoints, to prove
   $$
   I_i=1+J_i-D_i\le1+P_i,
   \quad J_i=\sum_x\Delta h_i(x),\quad
   P_i=\sum_x(\Delta h_i(x))_+,\quad
   D_i=-\int_{\{S(x+\theta_i)>\tau_i(x)\}}g_i'(x)\,dx\ge0.
   $$
   Thus FDR<=q|I_0|/N+(q/N)sum_i E P_i. These identities must be proved here rather than cited as approved from a failed plan. Check finite-model integrability before rearranging expectations.

2. [x] **Prove the exact active-contact Rice identity with the original covariance factor.** Fix i,j and the actual background y=T_{-ij}; define r(y)=R(p_i=p_j=0) and s(y)=R(p_i=0,p_j=1). Prove r>=s+1>=2 and that with i forced zero the rank equals r precisely for p_j<=t_r and equals s otherwise. This follows from maximal BH and replacement of selected/unselected coordinates; it cannot assume a monotone arbitrary conditional rank map. The only active j-contact is therefore T_j=u_r(y). Define
   $$
   \Psi_i(x;r,s)=S(x)\left[
   \min\left\{\frac1{t_s},\frac1{S(x+\theta_i)}\right\}
   -\min\left\{\frac1{t_r},\frac1{S(x+\theta_i)}\right\}\right]\ge0.
   $$
   A downward rank transition, giving a positive h_i jump, can only come from Sigma_ij<0. Prove that its full jump is Psi_i, including an r-to-s cascade, rather than one unit of rank loss. Positive covariance produces the opposite orientation; zero covariance produces no crossing.

   Derive, for the positive-definite law and its ordinary conditional two-dimensional density, the exact formula
   $$
   \boxed{\displaystyle
   \mathbb E P_i=
   \sum_{j:\Sigma_{ij}<0}(-\Sigma_{ij})
   \mathbb E_{T_{-ij}}\int_{\mathbb R}
   f_{X_i,T_j\mid T_{-ij}}(x,u_{r};T_{-ij})
   \frac{\Psi_i(x;r,s)}{\phi(x)}\,dx.}
   \tag{AC}
   $$
   First partition background space into fixed BH grid cells, then apply the change of variables for the crossing equation theta_j+Sigma_ij x+W_j^(i)=u_r. The speed is the unconditional regression slope |Sigma_ij|. The residual expectation has no phi(x) sampling weight, so converting it to the joint Gaussian density introduces exactly 1/phi(x). Prove these two facts explicitly; a conditional correlation or conditional standard deviation cannot replace Sigma_ij. Under positive definiteness, intersections of distinct contact hypersurfaces have zero residual measure: prove this by the relevant nonsingular Gaussian linear constraints and finite grid enumeration. Background rank-cell boundaries are not extra jumps when no grid threshold is crossed. Account for all multiple-contact and grid-boundary exceptions rather than assuming them away. Establish finiteness, measurability, and conditional-density normalization; a finite sum of possible grid crossings bounds P_i for each fixed N,q. Verify that Psi vanishes unless x>=u_r-theta_i>=U. In particular, entrywise nonnegative covariance gives P_i=0 as a consistency check.

3. [ ] **First mandatory new analytic gate: prove full-law active negative-contact transport.** Let B(N,theta,Sigma,q) denote the sum over i in I_0 of the right side of (AC). Prove a finite universal A, on the universal interval 0<q<=S(1), such that
   $$
   \boxed{B(N,\theta,\Sigma,q)\le A N(1+U).}
   \tag{NT}
   $$
   Uniformity includes the least eigenvalue, all means (negative true-null means included), all N, and all negative edges of the same original PSD covariance. The following is an explicit finite global transport inequality and derivation strategy for (NT); none of its required estimates is a premise.

   (a) For each pair, partition the N-2 background p-values into their fixed bands (t_{k-1},t_k], k=1,...,N, and (q,1], with t_0=0. Write C_b for a band-assignment cell and L_k(b) for its cumulative count. Derive
   $$
   s_b=\max\{k:1+L_k(b)\ge k\},\qquad
   r_b=\max\{k:2+L_k(b)\ge k\}.
   $$
   Preserve L_s=s-1, L_r=r-2; for k>s, L_k<=k-2; for k>r, L_k<=k-3. In particular the adjacent background bands after s and r are empty when they exist. Preserve the longer deficits as well, and distinguish r=N. Prove the layer-cake identity
   $$
   \Psi_i(x;r,s)=S(x)\int_{t_s}^{t_r}
   \mathbf1\{x\ge S^{-1}(v)-\theta_i\}\,\frac{dv}{v^2}.
   \tag{LC}
   $$
   It retains the exact cascade interval; split the integral into its deterministic bands only after writing this equality. No logarithmic number of rank layers may be charged separately at full cost.

   (b) Let f_{-ij}(y) be the original background density and set
   $$
   A_{ij,b}(v)=\int_{C_b} f_{-ij}(y)
   \int_{S^{-1}(v)-\theta_i}^{\infty}
   \frac{S(x)}{\phi(x)}
   f_{X_i,T_j\mid T_{-ij}}(x,u_{r_b};y)\,dx\,dy.
   $$
   The checkable finite global inequality to establish is exactly
   $$
   \sum_{i\in I_0}\sum_{j:\Sigma_{ij}<0}(-\Sigma_{ij})
   \sum_b\int_{t_{s_b}}^{t_{r_b}}A_{ij,b}(v)\,\frac{dv}{v^2}
   \le A N(1+U).
   \tag{FT}
   $$
   Establish equality of its left side with B by Tonelli and (LC), with the background event and original covariance law intact. This prevents an unspecified decoupling assertion from replacing the obligation. Null-null and null-alternative edges may be handled separately, but their total must satisfy (FT); conditional means do not redefine I_0. The positive equicorrelation family obstructing IG3 has no terms here, so it cannot serve as an obstruction to (FT).

   (c) Attempt a finite summation by parts over the consecutive bands in (LC), using the exact occupancy/deficit constraints of (a). Work with each fixed cell and fixed rank before summing cells. The intended allocation charges an endpoint density to its empty adjacent gap and, when a cascade spans several ranks, transports that charge across the successive deficit constraints. Keep the full reciprocal-threshold difference 1/t_s-1/t_r until the allocation is written; neither a unit rank cost nor the number of crossings replaces it. Display the coefficients of the resulting endpoint, interior and terminal contributions, and bound their full Gaussian averages. A successful certificate must show cancellation/telescoping of rank layers or a summable allocation with total A N(1+U), rather than a harmonic series in N.

   Use the following elementary fixed-gap calculation as a concrete diagonal-packing attempt, rederiving it inline. If Y~N(mu,a^2), d(z)=phi((z-mu)/a)/a, h>0 and C=e/sqrt(2pi), then
   $$
   d(z)^2\le\frac{C}{a\min(h,a)}\Pr\{z-h\le Y\le z\}.
   \tag{DG1}
   $$
   Prove it by setting w=(z-mu)/a, b=h/a: for b<=1 use unimodality and phi(w)^2/phi(w-b)<=e/sqrt(2pi), and for b>1 use the final length-a subinterval. Reflection gives the right gap. For independent Gaussian coordinates at a common fixed gap, with occupancy probabilities g_j, it follows that
   $$
   \sum_j d_j(z)^2\prod_{\ell\ne j}(1-g_\ell)
   \le\frac{C}{a\min(h,a)}
   \Pr\{\text{exactly one gap occupant}\}\le\frac{C}{a\min(h,a)}.
   \tag{DG2}
   $$
   A positive-definite model admits T=theta+Z+a epsilon with independent residual coordinates for a^2<lambda_min(Sigma). Conditional on Z, expand the exact fixed-band cell probabilities as products and apply (DG1)--(DG2) only to fixed gaps. Retain all remaining cell/deficit restrictions through the finite sum; selecting a rank from epsilon destroys the required independence. Try weighted Cauchy--Schwarz to move contact cross terms to these diagonal charges, retaining the actual factors (-Sigma_ij) throughout, and use the PSD law linking Z, its covariance, and those factors in the finite allocation. Explicitly account for every diagonal, positive-edge or boundary remainder introduced by Cauchy--Schwarz or PSD completion. The required output is a bound for (FT), uniform as a tends to zero, not merely (DG2), a pointwise graph inequality, or a lambda_min-dependent estimate. If this decomposition cannot remove inverse noise factors, keep the direct conditional density expression in (FT) and attempt Gaussian integration by parts on each fixed cell; write all its cell-boundary and mean terms before summing. No assertion of their cancellation is available in advance.

   This is the critical unresolved part: the scalar density-square bound alone neither controls cross-rank transport nor aggregates the actual negative edges. Do not maximize against an independent Gram matrix, take beta of a coefficient matrix, replace (-Sigma_ij) by 1, discard active-rank events, or use the old inactive N-grid crossing envelope. No fixed-level expectation bound may be evaluated at a data-selected level by exchanging expectation and supremum. The approved scalar helper is not used as a black box here; if later adapted, first read its proof and reproduce the required deterministic-level argument without changing the target's dependencies.

   If (FT) cannot be proved by the explicit cell, cascade and diagonal-charge attempts, stop at (NT)/(FT), state which transport/PSD or noise-uniform estimate fails, and preserve any valid partial identities. An auxiliary candidate must receive a fresh audit before reuse as an established obstruction. It is a counterexample to the main target only if the actual ordinary-BH FDR normalized by q sqrt(log(1/q)) is shown unbounded along admissible models with q tending to zero.

4. [ ] **Close the finite bound and only then pass to all PSD models.** If and only if (NT) is proved, Steps 1--3 give FDR<=q*pi_0+Aq(1+U), uniformly for positive-definite models. For an arbitrary fixed finite PSD model couple
   $$
   T^{(\epsilon)}=\theta+\frac{X+\sqrt\epsilon Z}{\sqrt{1+\epsilon}},
   \qquad X\sim N(0,\Sigma),\quad Z\sim N(0,I_N)\text{ independent}.
   $$
   This has the same means, unit diagonal and positive-definite covariance (Sigma+epsilon I)/(1+epsilon). Let epsilon decrease to zero after proving the uniform bound. Each marginal Gaussian is continuous even for singular Sigma, so the finite collection T_i=u_k has probability zero. Outside it BH's finite band assignment, FDP and fixed true-null labels are eventually unchanged. Bounded convergence yields the same bound for the original singular model, including any ties induced by singular dependence. No uniform dimension rate, noise modulus or exchange of a supremum and a limit is needed. Prove U<=sqrt(2log(1/q)), take a universal q_0<=min{S(1),e^{-1}}, and obtain a finite universal C_1, for example C_1=1+A(1+sqrt(2)), for the exact target. Do not optimize it.

## Verification

Check every original quantifier, theta_i<0 as well as theta_i=0, ordinary largest rank and non-strict thresholds, all forced-rank endpoints, the full cascade cost, the actual unconditional covariance multiplier and 1/phi normalization, measure-zero exceptional contacts, finite integrability, and the unchanged PSD law in (FT). Verify any fixed-gap independence at its conditioning stage; arbitrary conditional means need not be true-null means. The plan succeeds only with a finite universal proof of (FT) and Step 4, followed by fresh whole-proof native verification. Scoped earlier audits, numerical checks, finite-N examples and researcher approval of another lemma do not verify this target. No target Proof is to be written on partial success.

As a finite coefficient sanity check, use Sigma with rows (1,-0.1,0.6), (-0.1,1,-0.6), (0.6,-0.6,1). Verify its positive definiteness (determinant 0.342); Sigma_12=-0.1 while Cov(T_1,T_2 given T_3)=0.26. The conditional density kernel can therefore have correlation of the opposite sign to the crossing slope. (AC) must still select this edge by Sigma_12 and multiply by 0.1. This checks only the identity's coefficient, not (NT) or the main target.

## Assumed definitions

Only the target's approved definitions of the Gaussian model, p-values/true nulls, ordinary BH, FDR and worst-case envelope are used. No draft definition or unproved dependency is assumed. BV, contact/coarea, occupancy and fixed-gap arguments are rederived in this plan; the new global transport inequality is an obligation, not a premise. No statement, approval record, loop state, settings or prior failed record is changed.

## Difference from failed plans

- `plan_one_sided_order_actual_mean_global_flux_20261106`: retains its correct actual-mean BV objective but replaces the refuted inactive marginal-crossing envelope by one active leave-two-out contact per pair, exact r-to-s cascade mass, and a finite full-law transport sum with actual negative covariance coefficients.
- `plan_one_sided_order_gaussian_interpolation_sdp_20261106`: uses the original covariance-weighted active contacts directly rather than an independent PSD completion; the fixed-cell cascade/gap allocation must remove dimension and inverse-noise factors before any singular limit.
- `plan_one_sided_order_three_face_noise_packing_20261106`: the audited IG3/IE obstruction forces retention of the actual covariance multipliers. Here only actual negative edges contribute; neither beta(H) nor an arbitrary Gram path can erase their size, and the old weak-positive-correlation obstruction contributes zero to (FT). The fixed-gap calculation is rederived only as scalar support for the new transport obligation.

## Progress

### Checkpoint 1: actual-mean BV identity (Step 1 established)

Write S=barPhi, phi=-S', t_k=qk/N, u_k=S^{-1}(t_k), and U=u_N>=1. Fix a finite positive-definite model. If I_0 is empty the FDR is zero. For N=1, a true null has FDR=P(T_1>=U)=S(U-theta_1)<=q, and otherwise the FDR is zero. Hence assume N>=2. For each i in I_0 put X_i=T_i-theta_i. The Gaussian vector W_j=T_j-theta_j-Sigma_ij X_i, j!=i, has covariance Sigma_{-i,-i}-Sigma_{-i,i}Sigma_{i,-i}, which is positive definite by completing the square in the quadratic form of Sigma. It has zero covariance with X_i. Their joint Gaussian density therefore factors (by the block diagonal covariance), proving independence. No independence between W coordinates is used.

For any deterministic p vector the BH rejection count equals its largest qualifying rank K: if more than K coordinates satisfied p_j<=t_K, that larger count would itself qualify. Force coordinate i to zero and denote the resulting rank by K_i>=1. The exact identity, with non-strict inequalities, is
$$
\frac{\mathbf1\{i\in\mathcal R_q(p)\}}{R_q(p)\vee1}
=\frac{\mathbf1\{p_i\le t_{K_i}\}}{K_i}.
$$
Indeed if i was rejected at rank K, its original p_i<=t_K is also <=t_l for every l>K. Forcing it to zero changes none of the counts at these higher thresholds, so K_i=K. Conversely if p_i<=t_{K_i}, restoring p_i preserves qualification at K_i; monotonicity under lowering one p-value then forces the restored rank to equal K_i. This argument also covers ties and a restored rank zero.

For fixed W define R_i(x)=K_i for p_j=S(theta_j+Sigma_ij x+W_j), j!=i, and tau_i(x)=t_{R_i(x)}. Conditional integration over the independent standard normal X_i gives exactly
$$
\operatorname{FDR}=\frac qN\sum_{i\in I_0}\mathbb E_W I_i(W),\qquad
I_i(W)=\int_{\mathbb R}\frac{\phi(x)}{\tau_i(x)}
\mathbf1\{S(x+\theta_i)\le\tau_i(x)\}\,dx.
$$
Every moving background coordinate crosses each fixed u_k at most once. Coordinates with Sigma_ij=0 are constant. Thus R_i has at most N(N-1) possible breakpoints; it is constant between them. Define g_i=S(x)/S(x+theta_i) and h_i=min(S(x)/tau_i,g_i). Both are measurable, with 0<=h_i<=g_i<=1. To check monotonicity rather than assume it, put lambda=phi/S. Differentiation gives lambda'=lambda(lambda-x)>0: for x<=0 this is immediate, while for x>0 the strict inequality x S(x)<integral_x^infinity t phi(t)dt=phi(x) proves lambda>x. Consequently g_i'/g_i=-lambda(x)+lambda(x+theta_i)<=0. For theta_i=0, g_i=1 and g_i'=0. For theta_i<0 it is decreasing, so -integral g_i'<=1; no asymptotic formula for its derivative is needed.

As x tends to minus infinity, g_i tends to 1 and S(x)/tau_i>=S(x)/q tends to 1/q>1, so h_i tends to 1. As x tends to plus infinity, h_i<=NS(x)/q tends to zero. Subdivide the finitely many rank intervals also at their possible switching points x=u_k-theta_i. On an open rejection subinterval h_i=S(x)/tau_i and h_i'=-phi(x)/tau_i; on its complement h_i=g_i and h_i'=g_i'. Switches within one rank cell are continuous. At rank contacts use the right-minus-left jump Delta h_i; the value assigned at the contact itself has no effect on the integral. Summing the fundamental theorem of calculus on these finitely many intervals, then taking their infinite endpoints, gives
$$
-1=-I_i-D_i+J_i,\quad
D_i=-\int_{\{S(x+\theta_i)>\tau_i(x)\}}g_i'(x)\,dx\ge0,\quad
J_i=\sum_x\Delta h_i(x).
$$
Hence I_i=1+J_i-D_i<=1+P_i, where P_i=sum_x(Delta h_i(x))_+. All operations are integrable for this finite model: I_i<=N/q, 0<=D_i<=1, and P_i, |J_i|<=N(N-1) since each jump has absolute size at most one. In particular expectations can be taken without an unproved uniform bound, yielding
$$
\operatorname{FDR}\le q|I_0|/N+(q/N)\sum_{i\in I_0}\mathbb E P_i.
$$
No draft lemma or earlier failed-plan calculation was invoked. These are finite-model statements; no bound uniform in N has yet been obtained.

### Checkpoint 2: active-contact identity (Step 2 established)

Fix i!=j. Partition the background y=T_{-ij} by its finite band assignments to (t_{k-1},t_k], k=1,...,N, and (q,1]. Denote such a cell C_b and its cumulative count by L_k. Values on cell boundaries are temporarily omitted. For the two forced-zero and zero/one configurations the largest ranks are
$$
r_b=\max\{k:2+L_k\ge k\},\qquad
s_b=\max\{k:1+L_k\ge k\}.
$$
Here s_b<=N-1. Maximality and monotonicity of L_k imply L_{s_b}=s_b-1: a strict excess would qualify s_b+1. Similarly L_{r_b}=r_b-2 when r_b<N, and also when r_b=N since only N-2 background coordinates exist. Thus r_b>=s_b+1>=2. For any actual value of p_j, with i forced zero, the rank is r_b if p_j<=t_{r_b}: that threshold qualifies and the both-zero rank bounds all ranks above it. If p_j>t_{r_b}, every k with s_b<k<=r_b fails because j is absent from its threshold count and 1+L_k<k; all k>r_b fail even with j forced zero. The rank is consequently s_b. This proves the claimed two-valued rank law for an arbitrary background, including ties assigned to their non-strict bands.

Along the regression path of Checkpoint 1, a background grid threshold can be crossed only at theta_j+Sigma_ij x+W_j=u_k. Except on a residual null set, two different coordinates cannot cross grid thresholds at the same x. In fact, if their slopes are a_j,a_l and at least one is nonzero, simultaneous crossing imposes the nontrivial affine equation
$$
a_l W_j-a_j W_l=a_l(u_k-theta_j)-a_j(u_m-theta_l).
$$
The relevant W covariance is positive definite, so this nonzero linear form has a continuous normal distribution. If one slope is zero this is still a nontrivial constraint on that constant coordinate. A coordinate of zero slope lying constantly at a grid threshold has probability zero by its positive residual variance. Finite enumeration over indices and grid levels proves that all these exceptions have probability zero. Two distinct thresholds of the same moving coordinate cannot coincide. Thus near a crossing the other coordinates remain in fixed bands, and the two-valued law above shows that only k=r_b is active. Moving within a background cell without a grid crossing cannot change a BH count; boundaries of a more refined rank description create no additional jumps.

For Sigma_ij<0, increasing x decreases T_j across u_{r_b}, changing the forced rank from r_b to s_b. The resulting h_i jump is exactly
$$
\Psi_i(x;r_b,s_b)=S(x)\left[\min\{1/t_{s_b},1/S(x+\theta_i)\}
-\min\{1/t_{r_b},1/S(x+\theta_i)\}\right].
$$
It is nonnegative and includes the complete cascade. If Sigma_ij>0 the orientation is reversed and the jump is nonpositive. A zero slope has no crossing. The displayed difference vanishes unless S(x+theta_i)<=t_{r_b}, hence unless x>=u_{r_b}-theta_i>=U. Equality at the first endpoint gives zero as well. Since 0<=h_i<=1, each such cost is at most one.

Here is an elementary density change of variables proving (AC), without a Rice theorem as a black box. Write h_W for the nondegenerate residual density for this i and a_j=Sigma_ij. Fix a cell b and j with a_j<0. At its active contact, parametrize residuals by x and y in C_b through
$$
W_j=u_{r_b}-theta_j-a_jx,\qquad
W_l=y_l-theta_l-Sigma_{il}x\quad(l\ne i,j).
$$
The absolute determinant is |a_j|: order the row for j first and the columns as (x,y); the lower-right block is identity and the first row has only -a_j. Within this fixed cell, the map is one-to-one. Conversely every active crossing assigned to this b has precisely this preimage. A residual path can contribute several different crossings, and integration over the finite disjoint labels (j,b) correctly sums them. Exceptional cell boundaries were just shown null. By the usual finite-dimensional density substitution, the expected cost over this contact is
$$
|a_j|\int_{C_b}\int_{\mathbb R}
h_W(u_{r_b}-theta_j-a_jx,\ y-theta_{-ij}-Sigma_{-ij,i}x)
\Psi_i(x;r_b,s_b)\,dx\,dy.
$$
The transformation (X_i,W)->(X_i,T_{-i}) has determinant one, so the full joint density in (x,z,y) equals phi(x) times the residual density at (z-theta_j-a_jx,y-theta_{-ij}-Sigma_{-ij,i}x). Dividing by phi(x)>0, then factoring this full density into the positive background Gaussian density f_{-ij}(y) and its normalized conditional two-dimensional Gaussian density gives precisely
$$
\mathbb E P_i=\sum_{j:\Sigma_{ij}<0}(-\Sigma_{ij})\mathbb E_{T_{-ij}}
\int_{\mathbb R} f_{X_i,T_j\mid T_{-ij}}(x,u_{r};T_{-ij})
\frac{\Psi_i(x;r,s)}{\phi(x)}\,dx.
$$
For N=2 the background space is the singleton of mass one and the same determinant calculation applies. Conditional Gaussian densities exist and normalize because every Schur complement of this positive-definite covariance is positive definite; their means are unrestricted. The factor |a_j| is the unconditional regression slope, unaffected by the sign of a conditional covariance. The reciprocal phi(x) is required because a crossing is sampled over W, without an additional X_i sampling weight. All integrands are measurable and nonnegative; their finite sum is integrable by P_i<=N(N-1), already proved before this substitution. Consequently no singularity in this density expression is an unverified finite-model integrability assumption.

As checks, entrywise nonnegative Sigma gives P_i=0, and the three-by-three matrix in Verification has leading principal minors 1, 0.99, 0.342 and is positive definite. Its unconditional covariance -0.1 on edge (1,2) is selected with coefficient 0.1, whereas the conditional covariance given coordinate 3 equals -0.1-(0.6)(-0.6)=0.26. Replacing the coefficient or its sign by that conditional covariance would contradict the determinant calculation.

### Checkpoint 3: exact cascade transport and the fixed-gap diagonal lemma (Steps 3(a),(b) established)

In the notation of Checkpoint 2, maximality gives L_k<=k-2 for k>s and L_k<=k-3 for k>r. Since L_s=s-1, when s+1<=N we have L_{s+1}=L_s, so band s+1 is empty. If r<N, then L_{r+1}=L_r=r-2 and band r+1 is empty as well. If r=N no band N+1 is introduced. All longer cumulative deficits remain part of C_b; only these two particular consequences were singled out. These are constraints on the actual joint background law, not independent occupancy assumptions.

For any a=S(x+theta_i)>0 the elementary identity
$$
\min(1/t_s,1/a)-\min(1/t_r,1/a)
=\int_{t_s}^{t_r}\mathbf1\{a\le v\}\,\frac{dv}{v^2}
$$
follows by splitting the integral at a (also covering a<=t_s and a>=t_r). Multiplication by S(x) proves (LC). Substitute it into (AC) and use Tonelli on the nonnegative measurable integrands. This proves that B=sum_{i in I_0} E P_i equals exactly the left side of (FT), with A_{ij,b} as defined in the plan. In particular, the full background cell and the unconditional coefficient c_{ij}=(-Sigma_ij)_+ survive. There is no maximization over covariance matrices or decoupled rank here.

One finite summation by parts can be made fully explicit. For fixed i,j,b put F_b(v)=A_{ij,b}(v). On [t_s,t_r] it is continuously differentiable; positive-definite Gaussian decay and the positive lower bound on v justify differentiation of its moving lower limit. Explicitly,
$$
F_b'(v)=\frac1{\phi(S^{-1}(v))}\int_{C_b} f_{-ij}(y)
\frac{S(S^{-1}(v)-theta_i)}{\phi(S^{-1}(v)-theta_i)}
f_{X_i,T_j\mid T_{-ij}}(S^{-1}(v)-theta_i,u_r;y)\,dy\ge0.
$$
Cells with unbounded sides cause no difficulty: on the compact interval of v the joint Gaussian density and its derivatives have integrable Gaussian bounds in y. For every deterministic band k=s+1,...,r, integration by parts gives
$$
\int_{t_{k-1}}^{t_k}F_b(v)\frac{dv}{v^2}
=\frac{F_b(t_{k-1})}{t_{k-1}}-\frac{F_b(t_k)}{t_k}
+\int_{t_{k-1}}^{t_k}\frac{F_b'(v)}v\,dv.
$$
Thus interior endpoint coefficients +1/t_k and -1/t_k cancel within this same cell. The remaining lower endpoint has coefficient +1/t_s, the upper (including terminal r=N) has coefficient -1/t_r, and the interior density has positive coefficient 1/v. This telescoping alone does not bound either the surviving endpoints or the interior average. In particular discarding the negative terminal term before an allocation is not a proved transport bound. The original reciprocal difference remains exactly
$$
1/t_s-1/t_r=\sum_{k=s+1}^{r}\alpha_k,\qquad
\alpha_k=1/t_{k-1}-1/t_k=\frac{N}{qk(k-1)}.
$$
It is not replaced by a number of contacts or by a unit rank decrement.

For completeness, the proposed scalar diagonal lemma is proved here without importing a failed-plan result. Write w=(z-mu)/a, b=h/a. For 0<b<=1, unimodality gives
$$
\int_{w-b}^{w}\phi(t)dt\ge b\min\{\phi(w-b),\phi(w)\}.
$$
Also phi(w)<=1/sqrt(2pi) and
$$
\frac{\phi(w)^2}{\phi(w-b)}
=\frac1{\sqrt{2\pi}}\exp\{-\tfrac12(w+b)^2+b^2\}
\le e/\sqrt{2\pi}=C.
$$
Consequently phi(w)^2<=C b^{-1} P(w-b<=G<=w). Rescaling proves (DG1) when h<=a. For h>a apply that case to the last length-a subinterval [z-a,z] contained in [z-h,z], obtaining the same formula with min(h,a)=a. Reflection gives the right-gap version. This proof handles arbitrary means and every positive a,h.

For independent Gaussian Y_j of common variance a^2 and any fixed common gap, let g_j be their gap probabilities. Multiplying (DG1) by product_{l!=j}(1-g_l) and summing gives (DG2), because sum_j g_j product_{l!=j}(1-g_l) is exactly the probability of one gap occupant. More restricted fixed band events can be retained: condition on the band allocations outside the gap and sum the corresponding disjoint product probabilities. This does not permit a randomly selected gap or rank inside the conditional expectation. The conclusions so far prove the exact FT representation and a scalar packing tool, not the inequality FT.

### Checkpoint 4: explicit conditional diagonal allocation and its unclosed costs

Choose a>0 with a^2<lambda_min(Sigma), and write T=theta+Z+a epsilon, where Cov(Z)=Sigma-a^2 I and the epsilon coordinates are independent standard normals independent of Z. Conditional on Z, let d_i(x)=phi((x-Z_i)/a)/a be the density of X_i, d_j(z)=phi((z-theta_j-Z_j)/a)/a for j!=i, and p_{l,b_l}=P(T_l belongs to the fixed T-band b_l | Z). Put H_{ij,b}=product_{l!=i,j}p_{l,b_l}. The exact full-law kernel in FT is therefore
$$
A_{ij,b}(v)=\mathbb E_Z\left[H_{ij,b}\int_{a_i(v)}^\infty
w(x)d_i(x)d_j(u_{r_b})\,dx\right],\qquad
a_i(v)=S^{-1}(v)-theta_i,\quad w(x)=S(x)/phi(x).
$$
This follows directly by conditioning all N independent residual coordinates, not by choosing a rank after sampling them. In particular Z has the covariance linked to the very same original coefficients c_{ij}=(-Sigma_ij)_+.

Fix deterministic r<N and v<=t_r. The adjacent empty band is G_r=[u_{r+1},u_r), of width h_r=u_r-u_{r+1}>0. Every cell with r_b=r forbids all its background coordinates from this gap. For fixed i,r,v, write chi_b(v)=1{t_{s_b}<=v<=t_{r_b}}. If g_{j,r}=P(T_j in G_r | Z), the disjoint product expansion yields
$$
\sum_{j:c_{ij}>0}\sum_{b:r_b=r}
c_{ij}\chi_b(v)g_{j,r}H_{ij,b}
\le (\max_j c_{ij})P(\text{exactly one of }T_{-i}\text{ lies in }G_r\mid Z)
\le\max_j c_{ij}.
$$
To see disjointness, the sole gap occupant determines j uniquely, and all other realized residual coordinates determine their band assignment b uniquely; the rank/deficit conditions only remove configurations. Thus none of the longer deficit restrictions was replaced by independence of a selected rank. DG1 now proves the valid endpoint diagonal allocation
$$
\sum_{j,b:r_b=r} c_{ij}\chi_b(v)d_j(u_r)^2H_{ij,b}
\le K_r\max_j c_{ij},\qquad
K_r=\frac C{a\min(h_r,a)}.
$$
The coefficient c_{ij} was retained up to the displayed, explicit maximum in this upper bound; it was not set to one in FT.

For an actual attempt at cross-term allocation, use eta(x)=1+x^2 and the elementary weighted square inequality
$$
c_{ij}d_i(x)d_j(u_r)\le\tfrac12 c_{ij}
\{\eta(x)d_i(x)^2+\eta(x)^{-1}d_j(u_r)^2\}.
$$
It introduces two diagonal charges and no signed covariance cancellation. A constant eta would make the j-diagonal x integral of w(x) diverge, so the weight is essential. Since w(x)<=1/x for x>0, the valid j-diagonal allocation just obtained has, for each fixed i,r,v, total integrated cost at most
$$
\frac12 K_r\max_j c_{ij}\int_{a_i(v)}^\infty\frac{w(x)}{1+x^2}dx
\le\frac{K_r\max_j c_{ij}}{4U^2}.
$$
The remaining cascade integration has its exact weight chi_b(v)dv/v^2. Even replacing it by the upper interval [t_1,t_r] leaves the explicit factor 1/t_1-1/t_r=N(1-1/r)/q, and K_r has an inverse-a^2 dependence when a<h_r. Hence this packing certificate is not noise-uniform or dimension-uniform. It is an attempted upper bound, not a claim that the actual FT cost diverges.

For the i-diagonal charge put D_i^-=sum_j c_{ij}. At fixed r and v, sum_b chi_b H_{ij,b}<=1 for each j, so a valid but insufficient bound is
$$
\frac12\mathbb E_Z\int_{a_i(v)}^\infty w(x)\eta(x)d_i(x)^2
\sum_{j,b:r_b=r}c_{ij}\chi_b(v)H_{ij,b}\,dx
\le\frac{D_i^-}{2\sqrt{2\pi}a}\int_U^\infty(1+x^2)S(x)dx
\le\frac{D_i^- q(U+2)}{2\sqrt{2\pi}a}.
$$
Here d_i(x)^2<=(sqrt(2pi)a)^{-1}d_i(x) and E_Z d_i(x)=phi(x) were used only after the fixed-cell expansion. For the last bound, S(x)<=phi(x)/x gives the integral <=phi(U)+q/U, and integration by parts in S(U)=phi(U)/U-integral_U^infinity phi(t)/t^2 dt gives phi(U)<=q(U+1/U). This identifies explicitly the remaining i-diagonal row-degree cost and inverse-noise factor. The original cell restrictions have not been claimed to bound this cost more sharply.

At r=N there is no G_{N+1}. Using d_j(u_N)^2<=1/(2pi a^2) and the same finite cell partition instead gives a j-diagonal cost at most D_i^-/(8pi a^2 U^2) for fixed v; no empty terminal gap is invented. Band s+1 is empty but its endpoint is u_s rather than u_N, so DG1 there cannot replace this density without an additional cascade-transport argument.

No PSD completion cancels these explicit remainders automatically. For example, the admissible actual matrix Sigma=(1-delta)vv^T+delta I with v having entries +1 and -1 has c_{ij}=1-delta across the two sign groups, and D_i^-=(1-delta) times the size of the opposite group. Positive within-group entries are equally large. Thus a use of PSD that discards the positive edges cannot justify a universal diagonal row bound in this allocation. This elementary coefficient check is not an auxiliary FT counterexample and makes no claim about this family's actual FDR or its active cell probabilities. A needed improvement would have to use those probabilities or retain and control the signed positive-edge remainder. The direct full-law Gaussian integration-by-parts calculation below is attempted for that reason.

### Checkpoint 5: direct full-law integration by parts and the first unproved global charge

Keep i,j,b fixed, with Sigma_ij<0, and let f(x,z,y) be the original full Gaussian density of (X_i,T_j,T_{-ij}). Define
$$
Q_b(x,y)=\int_{u_{r_b}}^\infty f(x,z,y)\,dz,\qquad
H_b(x)=\int_{C_b}Q_b(x,y)\,dy.
$$
The notation H_b here denotes a full-law tail density, distinct from the conditional product H_{ij,b} of Checkpoint 4. Every derivative and boundary integral below is absolutely integrable: x>=a_i(v)>=1, w(x)<=1/x, derivatives of a fixed positive-definite Gaussian density are linear polynomials times that density, and all finite cell faces have Gaussian integrable restrictions. Infinite cell faces give zero limits. The estimates here may depend on this fixed finite covariance; no uniform eigenvalue conclusion is inferred.

For clarity about mean terms, put K=Sigma^{-1} with indices ordered as (i,j,-ij). The density derivative is
$$
\partial_x f=-[K_{ii}x+K_{ij}(z-theta_j)+\sum_{l\ne i,j}K_{il}(y_l-theta_l)]f,
$$
and analogous formulas hold for the other coordinates. Multiplying the full gradient by the actual i-th covariance row gives the exact identity
$$
x f=-\partial_x f-Sigma_{ij}\partial_z f
-\sum_{l\ne i,j}Sigma_{il}\partial_{y_l}f.
$$
Thus all means are their original means. Their subtractions cancel by Sigma K=I; no conditional mean is asserted null or nonpositive. Integrating z from u_{r_b} to infinity gives
$$
c_{ij} f(x,u_{r_b},y)=-xQ_b-\partial_x Q_b
-\sum_{l\ne i,j}Sigma_{il}\partial_{y_l}Q_b,
\qquad c_{ij}=-Sigma_{ij}>0.
$$
Since w'=xw-1, integration over x>=a=a_i(v) and y in C_b gives the particularly explicit formula
$$
c_{ij}A_{ij,b}(v)=w(a)H_b(a)-\int_a^\infty H_b(x)dx
-\sum_{l\ne i,j}Sigma_{il}\int_a^\infty w(x)
\int_{\partial C_b}n_l(y)Q_b(x,y)\,dS(y)\,dx.
\tag{IBP-cell}
$$
For N=2 the boundary sum is empty. The coefficient c_{ij} has been used exactly through the original covariance row, not discarded or replaced by a conditional correlation. In particular its smallness can be encoded by cancellations between the three terms on the right; bounding them separately does not preserve that smallness automatically.

Multiply (IBP-cell) by chi_b(v)/v^2 and sum over b, then integrate v in [t_1,q]. This is the full finite-cell IBP expansion of the FT left side. It has: (i) the lower-x endpoint w(a)H_b(a), (ii) the negative bulk -integral_a^infinity H_b, and (iii) every background-face flux, with its signed actual Sigma_il. There is no unlisted diagonal remainder: Sigma_ii=1 produced w'-xw=-1 and hence the bulk term; the j coordinate produced precisely the contact being bounded. All l!=i,j, including positive covariance edges, remain in (iii).

More explicitly, a finite common face y_l=u_k has adjacent cells C^- below and C^+ above it. After summing these two cells, its coefficient in (iii) is
$$
Sigma_{il}\int_{t_1}^{q}\frac{dv}{v^2}\int_{a_i(v)}^\infty w(x)
\int_{y_l=u_k}\{\chi_{b^+}(v)Q_{b^+}(x,y)-\chi_{b^-}(v)Q_{b^-}(x,y)\}\,dS(y)\,dx.
\tag{Face}
$$
The other background band coordinates on this face are fixed and are summed afterwards. This lists the signs of both orientations and covers the q face and all internal grid faces; at infinity the flux is zero. On a common face with unchanged r,s, both Q and chi coincide and the two terms cancel. In general increasing y_l can raise r and s, and the indicators chi=1{t_s<=v<=t_r} can either enter or leave a fixed v. Therefore the displayed difference does not have a proved sign. Dropping positive Sigma_il terms, dropping one orientation, or simply calling all internal faces telescoping would leave an unproved inequality. These are precisely the cell-boundary terms that a new signed allocation must control.

A concrete insufficient estimate illustrates the missing cancellation. For each fixed pair i,j and v, the background cells are disjoint, and Q_b(a,y) is at most the corresponding full background density with X_i=a. Thus
$$
\sum_b\chi_b(v)w(a_i(v))H_b(a_i(v))
\le S(a_i(v))\le v.
$$
Its v integral is log(q/t_1)=log N. Summing such endpoint costs over negative edges loses the desired N scale, while the Face terms still have no absolute-sum control uniform in covariance or dimension. The negative bulk was kept exactly in (IBP-cell), but no inequality has been proved that uses it to cancel both this endpoint cost and the signed face flux at the required total scale. This is the first global mathematical charge left unresolved by this attempt, rather than a hidden assertion of cancellation.

### Scoped independent audit received

The parent coordinator reported a fresh strict partial audit confirming Checkpoints 1–2 (then lines 144–216) at snapshot SHA-256 3aa1f25df6d0597aada2e958418c7a63f0b76e60e6b9d8a0fa3ae5e259883bf8, with no concrete gap for a fixed finite positive-definite covariance. This is a coordinator-reported scoped audit, not an approval or whole-target verification; it does not cover NT, the singular limit, or the new Checkpoints 3–5. The content of Checkpoints 1–2 has not been revised since their derivation. The present file hash changes because later checkpoints and this failure record were appended.

### Second scoped independent audit received

A different fresh strict reviewer independently checked Checkpoints 3–5, then lines 218–360, at block SHA-256 ba8c2c13b3b4cb92fa5efd2060a81dcd4b35ae00f56b74e24d4ff9456630868c (whole-file snapshot 94fd4e2fde96d008004361644950376e7845f210a66987fa7486ba78327fa261). The reviewer found no concrete algebra error in LC/FT, the fixed-cell summation by parts, DG1/DG2 and their finite-noise allocation, or IBP-cell/Face. In particular the original covariance multiplier, reciprocal marginal density, and shared-face signs were confirmed. The inverse-noise costs and the combined endpoint/bulk/signed-face estimate remain unresolved. This scoped confirmation neither proves NT/FT nor verifies or approves the target.

## Failure

Step 3(c), and specifically (NT)/(FT), is not proved. Steps 1 and 2 and the exact cell, layer-cake and summation-by-parts identities in Steps 3(a),(b) have been written out in Checkpoints 1–3. The fixed-gap lemma was reproved inline. Checkpoint 4 attempts the requested finite independent-residual diagonal allocation, retaining the actual negative coefficients and the full fixed-cell restrictions up to explicit upper bounds. Its j-diagonal charge still contains C/[a min(h_r,a)], its i-diagonal contains D_i^-/a, and the r=N terminal charge contains D_i^-/a^2. No uniform control of these terms as a decreases to zero was derived. The elementary actual-covariance coefficient example only explains why PSD alone cannot bound the row degree in that allocation; it is not an FT obstruction.

Checkpoint 5 then attempts direct Gaussian integration by parts with the original joint density. Formula (IBP-cell) and (Face) identify all endpoint, bulk, diagonal, mean and background-boundary contributions. The exact remaining obligation is to bound their combined sum, over i in I_0 and j with Sigma_ij<0 and all cells, by A N(1+U) with a universal A. Neither an allocation cancelling the positive and negative covariance face fluxes nor a summable rank/deficit charge for this combined expression was established. Separately bounding the endpoints gives a log N cost per negative edge and loses the coefficient cancellations; separately bounding the diagonal terms gives inverse-noise factors. Those are insufficient estimates, not false versions of FT asserted as facts.

Execution stops at this first essential global gate. No Step 4 limit is taken and no uniform bound for singular models is claimed. There is no counterexample to the main asset, and no auxiliary candidate is being used as an established obstruction. A continuation would require a genuinely new proof of the combined signed boundary allocation or another proof of FT, not a fresh declaration that the scalar packing lemma implies it. The target Statement, status and Proof, all approval/loop records, and all previous failed plans remain untouched.
