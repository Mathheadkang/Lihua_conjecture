---
type: plan
title: Universal one-sided order through null-tagged convex-cell replicas and a mixed trace budget
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by:
  - idea_7b7e6c517ab6
  - idea_f732727f85b3
  - idea_a7ecc31ede74
  - idea_9e69d45b53bb
adapts: []
tags:
  - universal-order
  - fdp-tilt
  - convex-gaussian-cells
  - null-tagged-replicas
  - mixed-trace-budget
---

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged universal finite-model statement, with finite constants independent of every model parameter, for every finite N, all original means, all unit-diagonal PSD covariance matrices including singular ones, negative true-null means, actual multiplicities, non-strict comparisons and the largest qualifying BH rank. All model parameters may vary with q. A complexity-dependent or restricted-model result does not complete the target.

This is a new attempt using [the two-scale repair](../ideas/idea_7b7e6c517ab6.md), [actual convex BH mesh components](../ideas/idea_f732727f85b3.md), [the bounded-reweight bridge calculation](../ideas/idea_a7ecc31ede74.md), and [null-marked rotations](../ideas/idea_9e69d45b53bb.md). These ideas are guidance, not approved lemmas. In particular, the pure O(q) square-root certificate and the pure entropy-amplified linear-deficit certificate are not assumed. Their original claims, failures and independently checked counterexample remain unchanged.

The new sufficient estimate to ATTEMPT is
$$
M_+\le C_*q\{\sqrt{\delta}+\sqrt{1+D}\,\delta\},\qquad
\delta=1-x. \tag{MT}
$$
Its two terms allow different mechanisms. This plan does not call (MT) a theorem: Steps 4--5 require an explicit null-tagged replica/coarea calculation, including all denominator terms, and stop at the first unpaid paired remainder. No new auxiliary required goal or dependency is created.

Native library searches for Gaussian BH entropy/convex covariance, Gaussian convex truncation/Poincare, and Gaussian replica Stein boundary martingales found no analogue. The statement of [the deterministic-level scalar replica bound](../assets/gaussian_conditional_tail_density_replica_bound.md) was checked. It does not control the inverse heat-FDP denominator or a correlated joint mark in one future replica; it cannot be applied after substituting an uncontrolled selected rank. Accordingly it is not a black box or an adaptation in this plan. Every needed Gaussian estimate below is proved inline.

The workspace root is not Git. At exclusive creation, the target SHA256 was 7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305. The source-idea hashes were 16958c6257deed3d49bae8aeae08d22fabfdaefec6713b0d47a17928cee70495, 15c34d8359035734ba04a1fe663b325ade89f9636d0bfa660573134fb1f37270 and 0ea77230db694c4dc36cd9ede7727932a7ac9634ebcddd4c828735c96f4f9904, respectively, in the first three links above.

Save the first completed derivation under Progress immediately; save later checkpoints after a fresh raw-byte hash and insertion-region read, in patches of at most 6000 tokens. The parent alone reports and changes native state. A partial execution saves all finished arguments before returning partial. A failure leaves the target untouched.

## Plan

1. [x] **Reconstruct the exact finite heat experiment and its closure resources.** Use a latent representation T_i=theta_i+v_i dot G, with every v_i a unit vector and the actual original covariance v_i dot v_j. Restate all notation from [FDP-tilted Gaussian Mills heat fields](../definitions/gaussian_bh_fdp_mills_heat_fields.md) inside the proof. Deal with F=0 immediately. For F>0, reconstruct terminal Q, path measure, heat Hcal=P_(1-t)f, Lcal=P_(1-t)B, a=Lcal/Hcal, spatial K, Brownian innovation W^Q, D, x and M. Prove all endpoint integrability rather than assuming smooth FDP. In particular rederive
   $$
   \|b\|\le H^{-1},\quad D\le\log(1/F),\quad
   \mathbb E_Q\int_0^1\|\beta_t\|^2dt=2D,\quad
   J:=\mathbb E_\gamma[G\cdot B]\ge UF/H,
   $$
   $$
   M=F\mathbb E_Q[b(W_1)\cdot W^Q_1],\qquad
   J=F\mathbb E_Q\int_0^1a_t\cdot\beta_t\,dt+M,
   $$
   $$
   \delta=\mathbb E_Q[1-H^2\|b\|^2]
      +H^2\mathbb E_Q\int_0^1t\|K_t\|_{\rm HS}^2dt. \tag{R}
   $$
   Keep the actual negative null means in the score inequality. Separate the rank/Mills and selected-null Gram parts of the first term in (R), using the ordered-pair sum of 1-Sigma_ij. These exact identities are not the required estimate.

2. [x] **Establish local convex-cell facts, including their limits.** Partition latent space by the finite hyperplanes theta_i+v_i dot g=u_r. Use all threshold comparisons to recover the actual largest BH rank; group coincident hyperplanes and simultaneous changes. Each positive-mass open cell C is convex and has fixed R_C, V_C, f_C and b_C. Write the terminal Q mixture and the exact heat posterior
   $$
   \pi_C(t,y)=\frac{f_CP_s1_C(y)}{\mathcal H(t,y)},\quad
   \beta_C=\nabla\log P_s1_C,\quad
   a=\sum_C\pi_Cb_C,\quad
   K=\sum_C\pi_C(b_C-a)\otimes(\beta_C-\beta),\quad s=1-t.
   $$
   Reprove Cov(N(y,sI) conditioned on C)<=sI, and hence
   $$
   -I/s\preceq\nabla^2\log P_s1_C(y)\preceq0.
   $$
   A fully elementary route is a smooth convex penalty k dist_C^2 added to the Gaussian potential: prove contraction of the synchronous Langevin derivative flow, derive the variance identity by differentiating its stationary semigroup, and integrate the resulting exp(-2t/s) gradient bound for linear tests. Then pass through smooth convex penalties and k to infinity using Gaussian domination of second moments. This avoids a new external black box. Prove stationarity, convergence and the variance identity used in that argument. Do not assert these properties for the full, generally disconnected Q mixture.

3. [x] **Calibrate the mixed certificate on actual stress families before general allocation.** First take N identical null coordinates with a common nonpositive mean and common unit direction. Prove b=v/H on the positive-FDP support, so a=v/H, K=0, x=1 and M=0. The symmetrized replica numerator in Step 4 must vanish pointwise whenever its endpoint FDP factors are nonzero. A proposed absolute packet allocation that destroys this cancellation is invalid.

   Reconstruct the unbalanced signed-null duplication family directly: N-1 copies of G and one of -G, all original means zero. For q<=S(3), let p=1/N, a=u(q(1-p)), A=u(qp), c_a=1/h(a), c_A=1/h(A), d_0=c_a+c_A. Verify actual BH ranks N-1 and 1 on the two tails and F=q. Under Q, b=c_a-d_0 1_minus and W^Q_1 is standard one-dimensional Gaussian, so
   $$
   |M|\le qd_0\sqrt{p(1-p)},\qquad
   \delta\ge p\{1-H^2/h(A)^2\}.
   $$
   Derive a universal bound |M|<=Cq sqrt(delta) by splitting h(A)<=2H and h(A)>2H. In the first case use h'(u)>=9/10 for u>=3, A>=u(q/2), and log 2<=h(A)(A-U); in the second use 1-H^2/h(A)^2>=3/4. This is an upper calibration, not reuse of the false linear certificate. Also reprove the full N=2 single-null bounded-reweight bridge bound: above u(q/2)-theta_0, f lies in [1/2,1], so truncated Gaussian variance bounds the mean perturbation, and the conditional Brownian bridge bounds its complete innovation bias. Finally compute one actual three-test mixed-sign model with all three positive-probability ranks 3,2,1; use the same original means throughout. No free rank selector is permitted. If (MT) is already falsified by a checked legal family, stop, preserve it in Failure and do not claim the main target is false.

4. [x] **Derive the null-tagged two-future replica ledger, then its finite rotation/coarea form.** At a fixed heat state y, let X=y+sqrt(s)Z and X'=y+sqrt(s)Z' with independent standard Gaussian future vectors. Establish exactly
   $$
   \operatorname{tr}K(t,y)=
   \frac{\mathbb E[f(X)f(X')(b(X)-b(X'))\cdot(X-X')\mid y]}
        {2s\mathcal H(t,y)^2},
   $$
   $$
   M=\int_0^1\mathbb E_{\gamma_t}
      \left[\frac{\mathbb E[B(X)\cdot(X-X')f(X')\mid y]}
      {s\mathcal H(t,y)}\right]dt. \tag{RP}
   $$
   Here gamma_t is the original Brownian marginal, not Q. Refine the cell mixture by actual selected true-null tags:
   $$
   \pi_{C,i}=\frac{P_s1_C(y)}{R_C\mathcal H(t,y)}
   \quad(i\in I_0\cap\mathcal R_C),\qquad
   a=\sum_{C,i}\pi_{C,i}\frac{v_i}{h(u_{R_C})}.
   $$
   Their sum is one. Do not add or drop their index entropy. Use these exact 1/R weights, not arbitrary unit-ball cell labels.

   To calculate the differences in (RP), use a variance-preserving path between its endpoints. With independent S_0,D_0,E_0 standard Gaussian, set
   $$
   X=y+\sqrt{s/2}(S_0+D_0),\quad
   X'=y+\sqrt{s/2}(S_0-D_0),\quad
   X_\alpha=y+\sqrt{s/2}\{S_0+\cos\alpha D_0+\sin\alpha E_0\},
   \quad0\le\alpha\le\pi.
   $$
   Then X_0=X and X_pi=X'. Every unconditional X_alpha is standard Gaussian, with the original means/covariance for its test statistics, and its standardized velocity is independent of its current position. Keep both endpoint FDP masks f(X)f(X') and the fixed Hcal(t,y) denominator throughout. Expand all finite crossed facets with their full neighboring BH rejection sets, false-discovery counts and simultaneous cascades; include passages through f=0 cells in the zero extension of b.

   Reprove the marked rotation estimate for centered unit Gaussian position Y and velocity V with Y independent of V, and any centered unit null mark Z:
   $$
   \phi(z)\mathbb E[|V|1_{\{\theta_i+Z\ge u_r\}}\mid Y=z]
   \le\sqrt{2/\pi}\phi(u_r-\theta_i).
   $$
   At a fixed genuine null threshold the deterministic calibration is
   $$
   \frac{\phi(u_r-\theta_i)}{r h(u_r)}\le\frac qN. \tag{NC}
   $$
   Write exactly which conditional factors and endpoint masks remain after (NC); it is not permission to bound a random selected threshold by a deterministic one. If integration by parts in y is used, retain every derivative of Hcal^{-1}. Record the full signed ledger before any absolute values, and retain original covariance dot products rather than maximizing against an independent Gram matrix.

5. [ ] **Attempt the actual two-scale payment, with an explicit first failure gate.** Start with the finite ledger of Step 4, not with (MT). Pair the reverse rotations and the replica exchange, so that null entry, null exit and false-null-triggered dilution packets retain their exact coefficients. Expand each selected-null prototype difference and its squared norm using the actual rank/Mills coefficients and the original Gram matrix. Use the normalized tags pi_(C,i) to sum multiplicities before dropping any mask. Apply the local covariance contraction from Step 2 and Gaussian conditional regression only after fixing the corresponding cell, threshold and tag. In particular, do not apply the marked scalar estimate to a naked sum of rotating rows.

   Calculate all numerator and denominator derivative terms explicitly. The proposed payment mechanism is to use Gaussian Cauchy--Schwarz/Young on the completed paired ledger: its linear boundary remainder should be controlled by q times the square root of the two nonnegative resources in (R), while its drift-coupled quadratic remainder should use the same resources and the exact entropy energy 2D. Any weights or kernels used for that allocation must be displayed as measurable formulas from the finite tagged cells and Gaussian bridges; defining them by the unknown M, FDR, or a post-hoc ratio to delta is forbidden. A successful calculation must prove
   $$
   \mathcal L_{\rm paired}\le Cq\sqrt{\delta},\qquad
   \mathcal E_{\rm paired}\le Cq\sqrt{1+D}\,\delta,\qquad
   M\le\mathcal L_{\rm paired}+\mathcal E_{\rm paired},
   $$
   with the two paired quantities derived from that ledger, not assumed names for M. Check the ledger first in the actual three-rank mixed model from Step 3, and in the unbalanced duplication model, before summing arbitrary cells.

   **First essential failure condition:** if the denominator derivatives, a signed multi-rank dilution packet, or a cross-cell term cannot be paid by explicit allocations to (R) after this calculation, stop there. Save the exact remaining conditional integral, masks, signs, covariance coefficients and the allocation that failed. Merely obtaining the unknown M again, a global mixture covariance assertion, log(number of cells), log N, a naked inverse conditional variance or a pointwise absolute row count is a failed execution, not a proof of (MT). Do not attempt to rescue a failed first allocation by silently assuming (MT) or a high-FDR-only version.

6. [ ] **Close the unchanged theorem only after the mixed payment is proved.** Put z=F/(qH), c=C/z, delta=1-x and use Step 1 to obtain
   $$
   U\le\sqrt{2D}\sqrt{1-\delta}
      +c\sqrt{\delta}+c\sqrt{1+D}\,\delta.
   $$
   For z>=4C and D>=1, let a_0=sqrt(2D). Prove the right side is at most
   $$
   a_0-a_0\delta/4+c\sqrt{\delta}\le a_0+c^2/a_0.
   $$
   Hence U^2<=2D+3c^2. Since D<=log(1/F) and F=z phi(U), conclude log(z/sqrt(2pi))<=3/32. For D<1 the displayed right side is at most sqrt(2)+1/4+sqrt(2)/4<3, contradicting U>=3. Thus z<=max(4C,e sqrt(2pi)). Use Mills inequalities to give explicit finite universal C_1 and q_(0,1), without optimizing them. The latent proof already allows singular original covariance; if any intermediate smooth regularization was imposed, remove it for each fixed finite original model using the continuous univariate threshold marginals, with constants uniform before the limit and no supremum/limit interchange.

## Verification

A successful execution supplies complete proofs of every identity, every local covariance/bridge estimate, the actual paired null-tagged payment and its uniform constants. Rechecking only the final algebra or only fixed-size families does not verify the theorem. A fresh verifier must independently check actual largest-rank masks, negative means, simultaneous rank changes, the inverse heat-FDP denominator, the distinction between scalar deterministic-level calibration and masked adaptive levels, every limit and the two-scale allocation.

The full target statement remains frozen. All known auxiliary counterexamples must remain legal calibrations and must not be relabelled as counterexamples to the main theorem. Failure at Step 5 leaves all completed derivations in this plan and the target untouched; success puts the complete self-contained proof in the target and requires native independent verification before approval.

## Assumed definitions

No draft definition or unproved result is assumed. The five approved model/BH/FDR definitions in the target context and the approved FDP-tilted Mills heat-field definition provide notation only; all analytic identities are reconstructed here. The statement of the deterministic-level scalar replica lemma was inspected but is not invoked as a black box. Old plan Progress, draft ideas, candidate-family calculations and the pending counterexample confirmation are not approved proof dependencies.

## Difference from failed plans

- [Signed-label half-line occupation](plan_252211621cea.md): replaces the terminal half-line switch potential by a conditional two-future Gaussian replica and its inverse heat-FDP denominator; returning to the unknown FDR is explicitly a failure.
- [Global-shift entrant allocation](plan_503f8fddcbb5.md): uses variance-preserving future rotations and true-null prototype tags rather than a fixed-order global shift or an unsigned entrant allocation.
- [Compatible rank-chain transport](plan_ee2f7b97740a.md): does not assume a rejection-set potential or a Hall-cut cancellation; actual mixed cell packets and denominator derivatives are calculated.
- [Actual-mean global flux](plan_one_sided_order_actual_mean_global_flux_20261106.md): retains both endpoint actual-BH masks in the replica ledger and cannot replace active cascades by all marginal critical levels.
- [Common-anchor rotation](plan_one_sided_order_common_anchor_rotation_20261107.md): uses no raw FDR positive-variation certificate; the rotation is inside the exact Mills heat posterior and aims at the explicit two-scale coherence resource.
- [Convex isotonic proxy](plan_one_sided_order_convex_proxy_label_curvature_20261107.md): convexity is only a local property of exact BH mesh cells; there is no proxy support, labelled convex gradient, or global mixture-convexity assertion.
- [Single-scale Mills entropy certificate](plan_one_sided_order_fdp_entropy_mills_coherence_20261107.md): keeps its exact identities but replaces the disproved O(q) square-root-only payment by two distinct resources; the second pure linear certificate is also excluded by the unbalanced-clone calibration.
- [Signed interpolation SDP](plan_one_sided_order_gaussian_interpolation_sdp_20261106.md): introduces no diagonal completion, independent Gram maximization or scalar-to-matrix leap; the fixed-rank q/N calibration is kept attached to its conditional masks.
- [Negative-contact transport](plan_one_sided_order_negative_contact_transport_20261106.md): preserves the original covariance and full endpoint masks without assuming an inverse residual variance is summable; all heat-denominator terms remain visible.
- [Stopped peeling history](plan_one_sided_order_peeling_history_kernel_20261107.md): does not use a stopping compensator that saturates to terminal FDR; the new possible resource is the actual time-weighted quadratic variation in (R).
- [Three-face noise packing](plan_one_sided_order_three_face_noise_packing_20261106.md): never maximizes covariance independently of its own face law; a pointwise packet bound is not used to discard actual cancellations or multiplicity.

## Progress

### 1. Finite heat experiment (Step 1 established)

Fix any finite original model and 0<q<=S(3), where S is the standard normal survival function, phi its density, and u=S^{-1}. Take a square root of the original PSD covariance and write T_i=theta_i+v_i dot G in R^d, with G standard Gaussian, ||v_i||=1 and v_i dot v_j=Sigma_ij. No inverse covariance is used. Let R and the rejection set be the actual largest-rank BH outputs, V the actual selected true-null count, f=V/(R vee 1), and F=E_gamma f. The case F=0 already satisfies the target. For F>0 put
$$
u_r=u(qr/N),\quad U=u_N,\quad h(z)=\phi(z)/S(z),\quad H=h(U),
$$
$$
B(g)=\frac{1}{R(g)h(u_{R(g)})}
       \sum_{i\in I_0\cap\mathcal R(g)}v_i,
\qquad b(g)=B(g)/f(g)\quad(f(g)>0).
$$
Set both B and b to zero when f=0. On f>0,
$$
b=\frac{1}{Vh(u_R)}\sum_{i\in I_0\cap\mathcal R}v_i,
\qquad \|b\|\le H^{-1}.
$$
Indeed h is increasing: h'=h(h-z)>0 for z>0, because S(z)<phi(z)/z by integration of t phi(t)/z. Integration by parts also gives h(z)<z+1/z: S=phi/z-int_z^infty phi(t)/t^2 dt, and the last integral is <S/z^2. Consequently (z/h(z))'=[1-z(h(z)-z)]/h(z)>0. For a selected true null the original negative mean gives v_i dot g=T_i-theta_i>=u_R-theta_i>=u_R. Thus, with absolutely integrable G dot B,
$$
J:=\mathbb E_\gamma[G\cdot B]\ge
\mathbb E_\gamma[f\,u_R/h(u_R)]\ge UF/H. \tag{P1}
$$
Let P be Brownian motion W on [0,1] starting at zero and tilt its complete path by f(W_1)/F. Call this path law Q; its terminal law has density f/F with respect to gamma_d. Define P_s g(y)=E[g(y+sqrt(s)Z)], s=1-t,
$$
\mathcal H(t,y)=P_sf(y),\quad \mathcal L(t,y)=P_sB(y),\quad
\beta=\nabla\log\mathcal H,\quad a=\mathcal L/\mathcal H,
\quad K_{ij}=\partial_j a_i.
$$
For every t<1 the denominator is strictly positive and the functions are smooth. The likelihood process L_t=Hcal(t,W_t)/F is bounded above by 1/F. The entropy D=E_Q log(f(W_1)/F) is finite and <=log(1/F), since 1/N<=f<=1 wherever f>0. Ito's formula for z log z, stopped where L_t and its inverse and gradients are bounded, gives
$$
\mathbb E_Q\log L_t=\frac12\mathbb E_Q
    \int_0^t\|\beta_r\|^2dr. \tag{P2}
$$
Here removing stops is justified by the bounded upper range of L_t, the lower bound z log z>=-1/e, and monotone convergence of its nonnegative quadratic-variation term. As t increases to 1, bounded martingale convergence gives L_t to f(W_1)/F. The continuous function z log z on [0,1/F], with 0 log 0=0, permits dominated convergence. Therefore E_Q int_0^1||beta||^2=2D. On each compact subinterval of [0,1), Ito and the likelihood change of measure show that
$$
W_t^Q=W_t-\int_0^t\beta_rdr
$$
is a Q Brownian motion. The finite energy just proved extends the integral in L2(Q) to t=1. Brownian finite-dimensional distributions and path continuity therefore extend W^Q to a standard Brownian motion on the closed interval. This does not require finite terminal Fisher information or a derivative of the discontinuous f.

The conditional-expectation identity a_t=E_Q[b(W_1)|F_t] follows by Bayes, including the zero extension on f=0. Hence a is a bounded Q martingale with terminal b(W_1). Ito's quotient formula gives da_t=K_t dW_t^Q for t<1. The martingale isometry, first to time T<1 and then by bounded martingale convergence, gives
$$
\mathbb E_Q\int_0^1\|K_t\|_{\rm HS}^2dt
 =\mathbb E_Q\|b\|^2-\|a_0\|^2\le H^{-2}.
$$
In particular int E_Q|tr K| is finite for each finite d, by |tr K|<=sqrt(d)||K||_HS. Define M=F E_Q int_0^1 tr K_t dt; the proof will need a dimension-free upper bound, but existence does not. The product martingale identity for a and W^Q gives
$$
M=F\mathbb E_Q[b(W_1)\cdot W_1^Q]. \tag{P3}
$$
Also G=W_1=W_1^Q+int beta. Conditional expectation and Cauchy--Schwarz, using bounded b and the energy (P2), justify Fubini and give
$$
J=F\mathbb E_Q\int_0^1a_t\cdot\beta_tdt+M. \tag{P4}
$$
Put x=H^2 E_Q int_0^1||a_t||^2dt and delta=1-x. Since a is a conditional mean, x is in [0,1]. The isometry gives E_Q||b||^2-E_Q||a_t||^2=E_Q int_t^1||K_r||_HS^2dr. Integrating this nonnegative identity and using Tonelli proves exactly
$$
\delta=\mathbb E_Q[1-H^2\|b\|^2]
 +H^2\mathbb E_Q\int_0^1t\|K_t\|_{\rm HS}^2dt. \tag{P5}
$$
The terminal resource separates without discarding covariance signs:
$$
1-H^2\|b\|^2=
1-\frac{H^2}{h(u_R)^2}
 +\frac{H^2}{h(u_R)^2 V^2}
  \sum_{i,j\in I_0\cap\mathcal R}(1-\Sigma_{ij}). \tag{P6}
$$
The last sum is over ordered pairs, including the zero diagonal terms. Each term is nonnegative since the original rows have unit norm. These are identities and resources, not the mixed trace estimate (MT).

### 2. Convex cells and an elementary covariance proof (Step 2 established)

Use all distinct hyperplanes theta_i+v_i dot g=u_r for 1<=i,r<=N, merging coincident geometric hyperplanes. A connected open component C of their complement is an intersection of open halfspaces and is convex. Every comparison 1{T_i>=u_r} is constant there. Its comparison table fixes each qualifying rank, then its largest qualifying rank, its complete rejection set, V_C, f_C and b_C. Crossings of a merged hyperplane may change several comparisons at once; no sequential ordering is imposed on them. The finite union of hyperplanes has gamma_d measure zero because each v_i is a unit vector, even when the original covariance is singular.

Retain only positive-f_C cells. With g_C=gamma_d(C) the terminal Q mixture has weights f_C g_C/F and component gamma_d(.|C). At a heat state set p_C=P_s1_C, beta_C=grad log p_C and pi_C=f_C p_C/Hcal. Then, exactly,
$$
\beta=\sum_C\pi_C\beta_C,\qquad a=\sum_C\pi_Cb_C,
$$
$$
\nabla\pi_C=\pi_C(\beta_C-\beta),\qquad
K=\sum_C\pi_C(b_C-a)\otimes(\beta_C-\beta). \tag{P7}
$$
All sums are finite. This is a mixture formula, not a contraction claim for Q.

Here is a self-contained covariance contraction for each individual cell, including unbounded cells. Let A be its closure, let m be its nonempty interior, and fix y and s>0. The squared distance psi=dist_A^2 is convex, nonnegative, C1, and has 2-Lipschitz gradient. To see the last properties, write Pi_A x for the unique nearest point, whose existence follows by minimizing on a closed bounded ball. The optimality inequalities (x-Pi_A x) dot(z-Pi_A x)<=0 imply that Pi_A and I-Pi_A are nonexpansive, and differentiation of the minimizing value gives grad psi=2(I-Pi_A). Convexity also follows directly by interpolating two candidate nearest points in the convex set.

Convolve psi with a centered smooth compactly supported probability kernel at scale epsilon, obtaining psi_epsilon. It is smooth and convex, has Hessian between 0 and 2I, converges locally uniformly to psi, and is nonnegative. For k>0 let
$$
U_{k,\epsilon}(z)=\frac{\|z-y\|^2}{2s}+k\psi_\epsilon(z),
\qquad d\mu_{k,\epsilon}=Z_{k,\epsilon}^{-1}e^{-U_{k,\epsilon}}dz.
$$
Its Hessian lies between I/s and (1/s+2k)I. Consider the diffusion dX_t=-grad U(X_t)dt+sqrt(2)dA_t and semigroup T_t. Existence and uniqueness follow by Picard iteration for its globally Lipschitz drift on each finite time interval; Ito's formula for ||X_t-y||^2 bounds second moments. The density mu is stationary: integration by parts gives int Lg dmu=0 for compactly supported smooth g, L=Delta-grad U dot grad. For general T_tg, insert smooth cutoffs of radius R into that integration and let R increase; the quadratic Gaussian tail of e^{-U}, at-most-linear drift and the finite-time derivative bounds make all cutoff terms tend to zero. Differentiation of int T_tg dmu then gives zero for compactly supported smooth g. Bounded-function approximation extends stationarity.

Two solutions driven by the same A satisfy d||X_t-X'_t||^2/dt<=-(2/s)||X_t-X'_t||^2 by strong convexity. Hence their separation is at most e^{-t/s} times the initial separation. Differentiating the smooth flow gives J'_t=-Hess U(X_t)J_t, so ||J_t||<=e^{-t/s} and
$$
\|\nabla T_tg\|\le e^{-t/s}\|g\|_{\rm Lip}. \tag{P8}
$$
For bounded Lipschitz g, couple an initial x with an independent initial Y~mu using that same noise. Stationarity and the contraction show |T_tg(x)-mu g|<=Lip(g)e^{-t/s}E||x-Y||. Thus T_tg converges to mu g in L2(mu), since mu has a finite second moment. Integration by parts also gives
$$
\frac d{dt}\int(T_tg)^2d\mu=-2\int\|\nabla T_tg\|^2d\mu.
$$
The formula follows first with smooth bounded g and cutoffs as above. Integrating to infinity and using the just-proved convergence gives Var_mu(g)=2 int_0^infty int||grad T_tg||^2 dmu dt. In conjunction with (P8), this implies Var_mu(g)<=s Lip(g)^2. Smooth clipped approximations to g(z)=ell dot z have Lipschitz norm at most ||ell|| and converge in L2(mu), so
$$
\operatorname{Var}_{\mu_{k,\epsilon}}(\ell\cdot z)\le s\|\ell\|^2. \tag{P9}
$$
For fixed k let epsilon tend to zero, and then let k tend to infinity. Nonnegativity of each penalty supplies Gaussian domination for normalizers and all first and second moments. In the second limit e^{-k dist_A^2} decreases to 1_A, and the limiting normalizer is positive because A has nonempty interior. The boundary of this polyhedron is contained in finitely many hyperplanes, so conditioning on A and C agrees. Thus Cov(N(y,sI)|C)<=sI follows from (P9) in every direction ell. Direct differentiation under the Gaussian integral gives
$$
\nabla^2\log p_C(t,y)=-I/s+
 \operatorname{Cov}(N(y,sI)\mid C)/s^2,
$$
and hence -I/s<=Hess log p_C<=0. The lower inequality uses only the nonnegativity of covariance. No covariance or Poincare assertion for the mixture Q has been made.

### 3. Actual stress-family calibration (Step 3 established)

First take N copies of theta+v dot G with the same theta<=0. BH rejects all N exactly when v dot G>=U-theta, and otherwise rejects none. On Q support f=1 and b=v/H, regardless of theta. Conditional expectation gives a=v/H, K=0, x=1, delta=0 and M=0. The two-future numerator f(X)f(X')(b(X)-b(X')) therefore vanishes pointwise, not just in expectation. Any absolute boundary allocation that assigns a nonzero cost to this example loses a necessary cancellation.

For the unbalanced family assume N>=2, put p=1/N, and use N-1 rows +1 and one row -1, all theta_i=0, in dimension one. Set
$$
a=u(q(1-p)),\quad A=u(qp),\quad
c_a=1/h(a),\quad c_A=1/h(A),\quad d_0=c_a+c_A.
$$
Since U>=3>0, positive and negative rejection tails are disjoint. On G>=a exactly the positive rows pass the largest qualifying rank N-1; on G<=-A exactly the negative row passes rank 1. In between no positive rank qualifies. Thus f=1 on these two tails and zero elsewhere, F=q, and their conditional Q probabilities are 1-p and p. If I_minus marks the negative tail, b=c_a-d_0 I_minus. In (P3), W_1^Q is a standard normal under Q and has mean zero. Cauchy--Schwarz for the centered Bernoulli variable gives
$$
|M|\le qd_0\sqrt{p(1-p)},\qquad
\delta\ge p\{1-H^2/h(A)^2\}. \tag{P10}
$$
For the calibration a uniform lower bound h'>=1/2 suffices in place of the checklist's proposed stronger 9/10 estimate. We prove the weaker sufficient bound directly, so no stronger derivative claim is assumed. Write r=integral_0^infty e^{-zt-t^2/2}dt and m=integral_0^infty t e^{-zt-t^2/2}dt=1-zr. Then h'=m/r^2. Splitting a double integral by the sum variable,
$$
r^2=\int_0^\infty e^{-zu}
        \int_0^u e^{-[t^2+(u-t)^2]/2}\,dt\,du
 \le\int_0^\infty u e^{-zu-u^2/4}\,du
 \le 2\int_0^\infty u e^{-zu-u^2/2}\,du=2m.
$$
The last inequality follows by the substitution u=sqrt(2)v in its left-hand integral and z>=0. Thus h'>=1/2 for z>=0. If h(A)<=2H, then A>=u(q/2), and
$$
\log2=\int_U^{u(q/2)}h(t)dt\le h(A)(A-U).
$$
Consequently h(A)-H>=(A-U)/2>=log(2)/(4H), and
$$
1-H^2/h(A)^2\ge[h(A)-H]/h(A)\ge\log(2)/(8H^2).
$$
Using d_0<=2/H in (P10) gives |M|<=2sqrt(8/log2) q sqrt(delta)<7q sqrt(delta). If h(A)>2H, (P10) gives delta>=3p/4 and |M|<=4q sqrt(delta)/(sqrt(3)H)<q sqrt(delta), since H>3. Thus the new square-root term uniformly controls this actual finite family, including the rare-branch regime that invalidated the pure linear certificate. This changes only a local sufficient derivative estimate, not the target or its quantifiers.

Next consider N=2 with exactly one true null, its mean theta_0<=0 and unit direction v, and one alternative of arbitrary fixed mean mu>0 and arbitrary unit direction w. This includes v dot w=+/-1. Put a_*=u(q/2), A_*=a_*-theta_0, B_*=U-theta_0, c_2=1/H, c_1=1/h(a_*), d=c_2-c_1>0. Write Z=v dot G. On Z>=A_* the actual FDP is in [1/2,1]: it is 1/2 if the other statistic is at least U and 1 otherwise. On Z<B_* it is zero; on B_*<=Z<A_* it is either zero or 1/2. Hence
$$
F\le S(A_*)+\tfrac12[S(B_*)-S(A_*)]\le 3q/4<q.
$$
On Q support the actual terminal prototype is b=v(c_2-d I_1), where I_1 indicates the actual rank-one state. That state always has Z>=A_*.

We prove the required complete bridge bound. At a heat state y with s=1-t, average the terminal FDP over the orthogonal coordinates conditional on the scalar null coordinate z. This gives a weight w_y(z) which is in [1/2,1] on z>=A_*, zero below B_*, and in [0,1/2] between. The posterior mean of z is no greater than its mean restricted to z>=A_*: any added mass lies below all points in that restriction. Inside the restriction its difference from the unweighted truncated normal mean is Cov(z,w_y)/Ew_y. The weight has variance at most 1/16 (its range has length 1/2) and Ew_y>=1/2. The one-dimensional convex-cell contraction from Step 2 gives Var(z)<=s. Therefore, by Cauchy--Schwarz,
$$
v\cdot\beta(t,y)\le
 s^{-1/2}h((A_*-v\cdot y)/\sqrt{s})+(2\sqrt{s})^{-1}. \tag{P11}
$$
The regression and the weight are taken at the original means and original directions; no conditional variance is inverted except the fixed scalar s.

For any real x, h(x)<=x_++1. Indeed h is increasing, h(0)<1, and h'(x)=1-Var(Z|Z>=x)<1 implies h(x)-x decreases on x>=0. Conditional on any full terminal vector g with z=v dot g>=A_*, the Brownian bridge under Q equals the original bridge, so v dot W_t is N(tz,t(1-t)). Since h is increasing, its expected value in (P11) is maximized over such z at z=A_*. At that value, its argument is sqrt(s)A_*-sqrt(t)Z_0, with Z_0 standard normal. Therefore
$$
\mathbb E[h(\sqrt{s}A_*-\sqrt{t}Z_0)]
 \le\sqrt{s}A_*+1+1/\sqrt{2\pi}.
$$
Integration of (P11) in t gives conditional expected integrated drift at most A_*+3+1=A_*+4, since 2(1+1/sqrt(2pi))<3 and int_0^1(2sqrt(1-t))^{-1}dt=1. Thus
$$
\mathbb E_Q[v\cdot W_1^Q\mid G=g]\ge z-A_*-4\ge-4
\quad\text{on the actual rank-one state}. \tag{P12}
$$
All expectations can first be made on [0,T] and then extended using (P2) and the displayed positive integrable bridge majorant. Let p_1=Q(I_1=1) and e=Hd in (0,1). Formula (P3), the zero mean of W_1^Q and (P12) give M<=4Fdp_1. Formula (P5) gives delta>=p_1 e(2-e)>=p_1 Hd. Consequently
$$
M_+\le 4q\delta/H. \tag{P13}
$$
This checks a full family, including all correlations and negative true-null means, and does not prove the arbitrary-N budget.

For an actual three-rank stress model take one true null G and two alternatives 4u_1-G and 2u_1-G, with u_1=u(q/3), u_2=u(2q/3), U=u(q). These are one fixed vector of original means (0,4u_1,2u_1) and one rank-one PSD covariance, not separate means selected by the rank. Let b_3=2u_1-U and b_2=4u_1-u_2. They satisfy U<b_3<b_2. On the entire positive-FDP support [U,infty) the actual BH rank is
$$
R(G)=3\quad(U\le G\le b_3),\qquad
R(G)=2\quad(b_3<G\le b_2),\qquad
R(G)=1\quad(G>b_2).
$$
For the first interval all three statistics are at least U. In the second interval rank 3 fails, the null and first alternative both exceed u_2, and the second alternative is below U. In the last interval both rank 3 and rank 2 fail whereas the null exceeds u_1. For G<U the null is not rejected, so f=0. Every displayed interval has positive Gaussian mass. Here f=1/R and b=1/h(u_R) is decreasing on the Q support. At every heat state its scalar Jacobian is
$$
K=s^{-1}\operatorname{Cov}_{Q(\cdot\mid W_t=y)}(b(G),G)\le0,
$$
because twice that covariance equals E[(b(G)-b(G'))(G-G')]<=0 for independent posterior replicas. Thus M<=0 in this actual mixed-sign three-rank model. The zero extension below U causes no error in this covariance, since the posterior is supported where f>0.

### 4. Exact replicas, rotations and signed finite-face ledger (Step 4 established)

At any fixed t<1 and y, take independent X,X'~N(y,sI), s=1-t. Gaussian differentiation gives grad Hcal=s^{-1}E[f(X)(X-y)] and grad Lcal=s^{-1}E[B(X) tensor (X-y)]. Quotient differentiation and exchange of X,X' give
$$
\operatorname{tr}K(t,y)=
 \frac{\mathbb E[B(X)\cdot(X-X')f(X')]}{s\mathcal H^2}
 =\frac{\mathbb E[f(X)f(X')(b(X)-b(X'))\cdot(X-X')]}
        {2s\mathcal H^2}. \tag{P14}
$$
All expectations in this paragraph are conditional on y. Since the Q marginal at time t has density Hcal/F relative to the original Brownian marginal gamma_t,
$$
M=\int_0^1\mathbb E_{\gamma_t}
 \frac{\mathbb E[B(X)\cdot(X-X')f(X')]}{s\mathcal H}\,dt. \tag{P15}
$$
The signed integrand is integrable by the finite-energy bound for K in Step 1. For every positive-f cell and selected true null define
$$
\pi_{C,i}(t,y)=\frac{p_C(t,y)}{R_C\mathcal H(t,y)},
\quad i\in I_0\cap\mathcal R_C.
$$
Then sum_{C,i}pi_{C,i}=1 and a=sum_{C,i}pi_{C,i}v_i/h(u_{R_C}). These are the exact selected-null tags with their 1/R_C weights. There is no independent rank selector or entropy estimate in this identity.

For the rotation let S_0,D_0,E_0 be independent standard d-dimensional Gaussians, independent of y, and set
$$
X=y+\sqrt{s/2}(S_0+D_0),\qquad
X'=y+\sqrt{s/2}(S_0-D_0),
$$
$$
X_\alpha=y+\sqrt{s/2}(S_0+\cos\alpha D_0+\sin\alpha E_0),
\quad \nu_\alpha=-\sin\alpha D_0+\cos\alpha E_0.
$$
The endpoints are the independent futures just used. Also dot X_alpha=sqrt(s/2)nu_alpha; nu_alpha is standard Gaussian and independent of (X_alpha,y). Averaging y~gamma_t gives X_alpha~gamma_d for every alpha, so all original means and covariance rows are preserved. Endpoints and the velocity are generally dependent, a fact used below rather than dropped.

Let F_j enumerate all open codimension-one faces of the merged hyperplane arrangement. Choose an orientation n_j, ||n_j||=1, and c_j with its containing hyperplane n_j dot x=c_j. Let C_j^- and C_j^+ be its two neighboring cells, and write Delta_j b=b_{C_j^+}-b_{C_j^-}, and similarly Delta_j f and Delta_j B. Cells with f=0 retain b=B=0. Thus every coefficient uses the actual complete neighboring BH rejection sets, with all simultaneous changes on a coincident hyperplane already merged. Almost surely the rotating path has finitely many transverse crossings of these faces and avoids their lower-dimensional boundaries. Indeed each containing hyperplane gives an equation A+B cos(alpha)+C sin(alpha)=0 with finitely many roots unless identically zero, an event of probability zero; noncoincident codimension-two intersections also have zero crossing probability. Therefore the piecewise constant field has the exact signed coarea identity
$$
b(X)-b(X')=-\sum_j\Delta_j b\int_0^\pi
 1_{\{X_\alpha\in F_j\}}\,
 \delta(n_j\cdot X_\alpha-c_j)\,
 (n_j\cdot\dot X_\alpha)\,d\alpha. \tag{P16}
$$
Here the face indicator means restriction of hyperplane surface measure; the delta is equivalently the one-dimensional signed crossing formula. This notation does not discard paths through f=0 cells. Inserting (P16) in the symmetrized (P14)--(P15) yields the exact ledger
$$
-\sum_j\int_0^1\!dt\int_0^\pi\!d\alpha\;
\mathbb E\left[
 \frac{f(X)f(X')}{2s\mathcal H(t,y)}
 [(X-X')\cdot\Delta_j b]\,
 (n_j\cdot\dot X_\alpha)
 1_{F_j}(X_\alpha)\delta(n_j\cdot X_\alpha-c_j)
\right]=M. \tag{P17}
$$
To avoid assuming absolute integrability of a newly expanded signed expression, (P17) is first read with epsilon<=t<=1-epsilon and ||y||<=L. The denominator then has a positive lower bound, and every finite Gaussian surface integral is integrable. Remove L and then epsilon by equality with (P14), using the already proved integrability of tr K. The grouped signed limit is the asserted ledger; absolute convergence after arbitrary further splitting is not being asserted.

Each Delta_j b is the difference between the two explicit vectors
$$
b_C=\sum_{i\in I_0\cap\mathcal R_C}
       \frac{v_i}{V_C h(u_{R_C})}\quad(V_C>0),
$$
with zero used otherwise. Thus its squared norm is precisely the double sum of these coefficients times the original Sigma_ik. For example, with e_{C,i}=1{i selected true in C}/[V_C h(u_{R_C})] and e=0 on f=0,
$$
\|\Delta_j b\|^2=
 \sum_{i,k\in I_0}(e_{C_j^+,i}-e_{C_j^-,i})
 (e_{C_j^+,k}-e_{C_j^-,k})\Sigma_{ik}. \tag{P18}
$$
There is no independent Gram optimization in this expansion. Full identical clones give Delta_j b=0 when both neighbors have positive FDP, and any crossing to a zero-FDP cell is still canceled by the complete endpoint expression (P14). In the exact clones example both endpoints with f(X)f(X')>0 have equal b, so the sum in (P16), with its signs, is zero even if individual intermediate crossings do not vanish.

We now prove the marked scalar rotation estimate. Let Y,V be independent standard real Gaussians, and let the centered unit Gaussian mark Z be jointly Gaussian with them. Write Z=aY+bV+cE, where E is an independent standard Gaussian, a^2+b^2+c^2=1; zero residual variance is permitted. For k>=0 and every z,
$$
\phi(z)\mathbb E[|V|1_{\{Z\ge k\}}\mid Y=z]
 \le 2\phi(0)\phi(k)=\sqrt{2/\pi}\,\phi(k). \tag{P19}
$$
Here is a proof including the case when the mark depends on velocity. Tilt V by |V|/(2phi(0)), calling the resulting symmetric variable V_tilde. Its absolute value has the Rayleigh tail exp(-x^2/2). If sigma^2=b^2+c^2>0, the symmetric variable W=b V_tilde+cE satisfies P(|W|>=x)<=exp(-x^2/(2sigma^2)). To prove this, normalize sigma=1. Under the original untilted law W=bV+cE is standard normal; the new density at w is phi(w) E[|N(bw,c^2)|]/(2phi(0)). Thus the density of |W| on w>0 divided by the Rayleigh density w exp(-w^2/2) equals
$$
r(w)=\mathbb E|b+(c/w)E|.
$$
This function decreases in w: increasing the Gaussian variance increases the expectation of the convex absolute-value function, by conditional Jensen. Its limit is |b|<=1. Consequently the two probability densities cross at most once, from the new density being larger to being smaller, and their cumulative distribution functions show the asserted tail domination. If c=0 it is equality after normalization; if b=0 the same decreasing-ratio argument applies. Symmetry then gives P(W>=x)<=one-half exp(-x^2/(2sigma^2)) for x>=0.

The left side in (P19) is 2phi(0)phi(z) P(W>=k-az). If k-az>=0, use the preceding bound and z^2+(k-az)^2/sigma^2>=k^2, yielding even the stronger upper bound phi(0)phi(k). If k-az<0, then |z|>k and the trivial probability bound 1 gives (P19). When sigma=0, Z=+/-Y and the indicator itself forces |z|>=k, which proves the same inequality. Applied to the original true-null mark with k=u_r-theta_i>=U, this gives the planned marked rotation estimate, including all degeneracies.

At a deterministic genuine null threshold,
$$
\frac{\phi(u_r-\theta_i)}{r h(u_r)}
 \le\frac{\phi(u_r)}{r h(u_r)}=q/N,\quad\theta_i\le0. \tag{P20}
$$
Crucially, (P19) controls a single conditional scalar expectation with no additional weight. The (P17) integrand still contains both endpoint FDP masks, 1/Hcal(t,y), the face-restriction indicator, the remaining factor (X-X') dot Delta_j b, and the actual neighboring ranks and null prototypes. These factors are jointly dependent on Y,V,Z and on the conditioning y. None may be erased or pulled outside that scalar expectation. Fixing an endpoint cell makes its rank deterministic but also adds its correlated cell mask. Thus (P20) has not yet paid any unrestricted sum of adaptive faces.

For an equivalent signed ledger with the denominator derivative fully visible, define
$$
\Lambda_j(t,y)=\int_{F_j}\phi_s^d(x-y)\,d\mathcal H^{d-1}(x).
$$
Distributional derivatives of the finite piecewise constant fields give
$$
\nabla\mathcal H=\sum_j\Delta_j f\,n_j\Lambda_j,
\qquad\operatorname{div}\mathcal L=
 \sum_j(\Delta_j B\cdot n_j)\Lambda_j.
$$
They follow by integrating by parts in each cell and canceling paired boundaries; cutoffs tending to infinity have zero Gaussian boundary contribution. Differentiating a=Lcal/Hcal, with no integration by parts in y, gives
$$
M=\int_0^1\mathbb E_{\gamma_t}
 \sum_j\Lambda_j(t,y)
 [\Delta_j B-a(t,y)\Delta_j f]\cdot n_j\,dt. \tag{P21}
$$
The second term is exactly the derivative of the inverse denominator: grad(Hcal^{-1})=-Hcal^{-2}grad Hcal. Each face term is integrable separately in (P21), since ||a||<=1/H and E_{gamma_t}Lambda_j=int_{F_j}phi_1^d(x)dS<=phi(c_j), uniformly in t. No rank-dependent approximation has been used in (P21).

For a noncoincident single row-j threshold r which genuinely changes the largest rank, let S^- and S^+ be its neighboring rejection sets, with ranks k<r and r. Increasing that statistic makes S^- a subset of S^+. With V_-=|S^- intersect I_0| and A_0=(S^+ minus S^-) intersect I_0, its exact coefficients are
$$
\Delta f=(V_-+|A_0|)/r-V_-/k,
$$
$$
\Delta B=\frac{\sum_{i\in A_0}v_i}{r h(u_r)}
 +\left[\frac1{r h(u_r)}-\frac1{k h(u_k)}\right]
       \sum_{i\in S^-\cap I_0}v_i. \tag{P22}
$$
If k=0 the old-set terms are zero. If the trigger is a false null, Delta f may be negative; if the trigger is a true null, the other retained and added terms remain. For coincident hyperplanes use the complete two neighboring sets in (P21), not an invented ordered list of single-row transitions. Formula (P22) displays the actual dilution and the original covariance entries Sigma_ij upon taking its dot product with n_j=v_j.

The stress ledgers can be checked without a new bound. In the three-rank example of Step 3 let c_r=1/h(u_r), and write Acal(t,y)=a(t,y) for the scalar heat field to avoid confusion with tail thresholds. The only positive-FDP boundary points are U,b_3,b_2, with respective signed coefficients in (P21)
$$
(c_3-\mathcal A)/3,\qquad
c_2/2-c_3/3-\mathcal A/6,\qquad
c_1-c_2/2-\mathcal A/2. \tag{P23}
$$
The first is positive, although their heat-weighted total is nonpositive by monotonicity of b. For the unbalanced family let pi=Q(G<=-A|W_t=y), so Acal=c_a-(c_a+c_A)pi. The two faces -A and a, oriented towards increasing G, have coefficients
$$
c_A+\mathcal A=(c_a+c_A)(1-\pi),\qquad
c_a-\mathcal A=(c_a+c_A)\pi. \tag{P24}
$$
Their kernels are phi_s(-A-y) and phi_s(a-y). Thus the full denominator-dependent ledger is positive in that example and agrees with Step 3; it was not discarded by a sign convention.

### 5. Current precise boundary before the mixed payment

The new established estimates here are the individual convex-cell covariance contraction, the full single-null bridge estimate (P13), the uniform square-root calibration (P10), and the marked rotation inequality (P19), including velocity-dependent null marks. The general finite-face identity (P21) itself is only a repackaging of the earlier trace identity. It does not supply a new bound.

The exact remaining expression to pay is (P17), or equivalently (P21) with coefficients (P22), endpoint masks retained as specified after (P20). Local contraction controls Cov(X|C), whereas this expression contains the between-cell conditional means: with m_C=E[X|X in C],
$$
K=s^{-1}\sum_C\pi_C(b_C-a)\otimes(m_C-\overline m),
\quad\overline m=\sum_C\pi_Cm_C. \tag{P25}
$$
Within-cell covariance does not bound these between-cell terms. For example direct weighted Hilbert--Schmidt Cauchy--Schwarz on epsilon<=t<=1 gives only
$$
\left|F\mathbb E_Q\int_\epsilon^1\operatorname{tr}K_tdt\right|
\le \frac{F\sqrt d}{H}\sqrt{\delta\log(1/\epsilon)}. \tag{P26}
$$
This follows from |tr K|<=sqrt(d)||K||_HS and (P5). It loses dimension, the starting-time limit and the required q factor, so is not an allocation proving (MT). Similarly applying (P20) separately after deleting the masks in (P17) would still count unrestricted threshold/face incidences. No such deletion is justified here. The next execution must construct an explicit paired allocation for (P17)/(P22), with the correlated masks and denominator intact, or apply the plan's failure gate if it only returns (P25) or an uncontrolled face count. Step 5 is still open, not claimed established; the original asset is untouched.

### 6. Continuation: exact narrow-cell obstruction to the first boundary allocation

This continuation starts at Step 5; Steps 1--4 above are retained. For each face j write its coefficient from (P21) as
$$
c_j(t,y)=f_{C_j^+}(b_{C_j^+}-a(t,y))
          -f_{C_j^-}(b_{C_j^-}-a(t,y)). \tag{P27}
$$
In particular this formula retains the complete inverse-denominator derivative. Define two measurable nonnegative finite-face quantities
$$
\mathcal P(t,y)=\sum_j\Lambda_j(t,y)
       (f_{C_j^+}+f_{C_j^-}),
$$
$$
\mathcal Q(t,y)=\sum_j\Lambda_j(t,y)
 \{f_{C_j^+}\|b_{C_j^+}-a\|^2
    +f_{C_j^-}\|b_{C_j^-}-a\|^2\}.
$$
Weighted Cauchy--Schwarz over the two sides of all faces gives
$$
\sum_j\Lambda_j|c_j\cdot n_j|
 \le\sqrt{\mathcal P\mathcal Q}. \tag{P28}
$$
These are explicit cell quantities, with no quotient defined using the desired conclusion. However, paying the left side, or even just its positive-face part, by the right side of (MT) is false. The following actual Gaussian BH family identifies the lost cancellation, with no uncontrolled number of cells, directions or ranks.

Fix any q<=S(3), put A=u(q/2)>U, c_1=1/h(A), c_2=1/H and d=c_2-c_1>0. For each epsilon>0 take N=2 and the original model
$$
T_1=G,\qquad T_2=G+U-A-\epsilon,\qquad G\sim N(0,1).
$$
Both means are nonpositive, so both tests are true nulls. The original covariance is the valid rank-one matrix with all entries one. The largest qualifying ranks are exactly
$$
R=0\ (G<A),\qquad
R=1\ (A\le G<A+\epsilon),\qquad
R=2\ (G\ge A+\epsilon). \tag{P29}
$$
Indeed rank two qualifies exactly when the smaller statistic T_2 reaches U, at A+epsilon; below this point rank one qualifies exactly when T_1 reaches A. The non-strict endpoint convention agrees with (P29). Consequently f=1_{G>=A}, F=S(A)=q/2 and D=log(2/q), independent of epsilon. On Q support, with J_epsilon=1_{A<=G<A+epsilon},
$$
b=c_2-dJ_\epsilon,\qquad
a(t,y)=c_2-d\pi_\epsilon(t,y),\qquad
\pi_\epsilon(t,y)=
 \frac{P_s1_{[A,A+\epsilon)}(y)}{P_s1_{[A,\infty)}(y)}. \tag{P30}
$$
Thus all heat denominators and actual cell masks have been evaluated, rather than bounded away. Let alpha_epsilon=Q(J_epsilon=1)=[S(A)-S(A+epsilon)]/S(A). Since E_Q pi_epsilon(t,W_t)=alpha_epsilon at every time, direct expansion of the definition of delta gives
$$
\delta=2Hd\alpha_\epsilon
      -H^2d^2\int_0^1 E_Q\pi_\epsilon(t,W_t)^2dt,
$$
$$
Hd(2-Hd)\alpha_\epsilon\le\delta
       \le2Hd\alpha_\epsilon\longrightarrow0. \tag{P31}
$$
Here 0<Hd<1 and pi_epsilon^2<=pi_epsilon. This uses the complete resource (P5) through its equal definition 1-x; no terminal or time component is silently discarded.

There are exactly two active faces in (P21). In the increasing-G orientation their coefficients are
$$
c_A=-d(1-\pi_\epsilon),\qquad c_{A+\epsilon}=d. \tag{P32}
$$
The first contains Delta f=1 and therefore includes the term -a; the second has Delta f=0. Their Gaussian kernels are Lambda_A=phi_s(A-y) and Lambda_{A+epsilon}=phi_s(A+epsilon-y). The positive-face allocation is consequently
$$
\mathcal B_\epsilon^+
 :=\int_0^1 E_{\gamma_t}
       \sum_j\Lambda_j(c_j\cdot n_j)_+dt
 =d\phi(A+\epsilon)\longrightarrow d\phi(A)>0. \tag{P33}
$$
Likewise its unsigned version converges to 2d phi(A). To see the latter limit, E_gamma_t Lambda_z=phi(z) for all t<1. Moreover pi_epsilon tends to zero pointwise for every fixed t<1,y and is bounded by one. Dominated convergence on dt gamma_t(dy), with the integrable majorant Lambda_A, gives integral E_gamma_t pi_epsilon Lambda_A to zero. Therefore neither positive-face nor unsigned face payment can be bounded by Cq{sqrt(delta)+sqrt(1+D)delta}, for any finite universal C, even with N=2 and D fixed.

This obstruction also survives merely pairing a path with its reversed orientation or exchanging its two future endpoints: in (P16)--(P17) both relevant signs reverse together, so each complete oriented-face contribution is unchanged. Cancellation in this model is between the two distinct faces A and A+epsilon. It is not a cancellation between two orientations of one face. Their nearly coincident geometric hyperplanes are kept distinct for every epsilon>0; no coincident-face ordering has been invented. The original covariance coefficients are all exactly one.

The model itself satisfies the proposed budget, which further distinguishes this obstruction from a counterexample to (MT). Keeping its two faces together gives the exact signed expression
$$
M=d\int_0^1 E_{\gamma_t}
 \{\Lambda_{A+\epsilon}-\Lambda_A
                  +\pi_\epsilon\Lambda_A\}dt. \tag{P34}
$$
Here the first difference has expectation phi(A+epsilon)-phi(A)<0. A direct bridge proof pays the whole expression. The scalar Q drift is beta(t,y)=h((A-y)/sqrt(s))/sqrt(s). Conditional on a terminal g>=A, its original Brownian bridge has W_t distributed as N(tg,t(1-t)). Monotonicity of h and h(z)<=z_++1, already proved above, imply
$$
E_Q[\beta_t\mid G=g]
 \le A+(1+1/\sqrt{2\pi})/\sqrt{1-t}.
$$
Hence E_Q[W_1^Q|G=g]>=g-A-2(1+1/sqrt(2pi))>=-3. Integrability and the t=1 limit follow from this bound and (P2). Since E_Q W_1^Q=0, (P3) gives M=-dF E_Q[J_epsilon W_1^Q]<=3dF alpha_epsilon. Also b is nondecreasing on Q support, so the independent-posterior covariance identity gives K>=0 and M>=0. Combining with (P31),
$$
0\le M\le3F\delta/H\le3q\delta/H\longrightarrow0. \tag{P35}
$$
Thus the actual signed budget is small precisely when the separate positive face cost in (P33) is not. This is a rigorous failure of the first local boundary allocation, and an additional successful scoped bridge estimate, not a falsification of the main result or of (MT).

## Failure

Step 5 fails at the first attempted allocation (P27)--(P28). Its full numerator and inverse-denominator coefficients are explicit, but passing to their separate positive or unsigned face costs cannot be paid from (P5): the actual finite family (P29)--(P33) has fixed q and D, delta tending to zero, and strictly positive limiting cost. Reverse rotations and replica exchange do not remove this distinct-face obstruction. The required additional ingredient is a measurable pairing or bridge comparison between different actual rank faces, with the negative denominator term kept until after that pairing. The special halfline bridge in (P34)--(P35) supplies such a pairing only for that actual family; applying it to an arbitrary selected cell is not justified by its covariance contraction.

The general signed conditional integral still unpaid is exactly (P17), equivalently (P21) with c_j from (P27) and the full actual-rank/Gram coefficients (P18),(P22). Every endpoint FDP mask, the inverse Hcal(t,y), and the original covariance remain part of this remainder. Summing the cell contraction inequalities yields (P25), not the missing cross-face comparison. No general paired quantities meeting Step 5 have been constructed, so the failure gate is used rather than assuming this comparison or (MT). Steps 1--4 and the complete new continuation remain above. Step 6 is not reached. The target statement and Proof are unchanged. This failed plan does not assert that (MT) or the main conjecture is false.
