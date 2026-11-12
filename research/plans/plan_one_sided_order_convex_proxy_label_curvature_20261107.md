---
id: plan_one_sided_order_convex_proxy_label_curvature_20261107
type: plan
title: Universal one-sided order through convex isotonic energy and labelled curvature
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by:
  - idea_4ce93cc06b33
---

# Universal one-sided order through convex isotonic energy and labelled curvature

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged finite-model statement: finite universal C and q0>0 such that ordinary one-sided Gaussian BH has FDR at most C q sqrt(log(1/q)) for every 0<q<=q0, every finite N, every mean vector theta and every unit-diagonal PSD Sigma, including singular matrices. Preserve the original labels I0={i:theta_i<=0}, every alternative mean, multiplicities, non-strict threshold comparisons and the largest qualifying BH rank. All parameters may vary with q. No dimension, covariance rank, factor count, entropy, null-proportion or eigenvalue restriction is permitted; no sharp constant is sought.

The [rank-adaptive convex-energy proposal](../ideas/idea_4ce93cc06b33.md) is draft guidance. All finite formulas below must be reconstructed in execution, not cited as approved results. Native library searches for convex proximal Gaussian supermodular sorted energies and labelled increment/common-shift Laplace rank estimates returned no analogue. No library theorem is a black box or adapted source. The workspace root is not Git. Source idea SHA256 before exclusive creation: 224aa56577450b7517076c03a2f9f595d9cbe2615014f7f2c192eb73c9028838; unchanged target SHA256: 7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305.

Primary-source inspiration only: Malgorzata Bogdan, Ewout van den Berg, Chiara Sabatti, Weijie Su and Emmanuel J. Candes, *SLOPE—Adaptive Variable Selection via Convex Optimization*, Annals of Applied Statistics 9(3), 1103–1140 (2015), DOI 10.1214/15-AOAS842, original full text https://pmc.ncbi.nlm.nih.gov/articles/PMC4689150/ . Proposition 2.2 and section 2.3 give the sorted isotonic proximal mechanism. Their Theorem 1.1 assumes orthogonal design and iid Gaussian noise, with two-sided zero-coefficient nulls; it is not a result for the present model. Reprove the one-sided geometry, Gaussian interpolation and estimates inline. No bibliography change or unapproved reference black box is authorized.

Save the first completed derivation into Progress immediately. Save each later checkpoint only after re-reading the insertion region and checking source/target/plan hashes, in patches of at most 6000 tokens. Parent owns native reports, transitions and approvals. Stop at the first essential unpaid remainder after attempting the stated finite-cell/Laplace allocation. A negative cell, failed stronger budget or unproved comparison does not refute the target or every convex-proxy route.

## Plan

1. [x] **Reconstruct the exact rank-adaptive proxy and deterministic margins.** Put S=barPhi, phi=-S', U=S^{-1}(q)>=3, u_j=S^{-1}(qj/N) and lambda_j=u_j-4/u_j>0. Work on the universal interval q<=min(S(3),1/198). For b>=0 let b_(j) be its decreasing coordinates and define

   $$
   F_N(T)=\sup_{b\ge0}\left\{T^\top b-\sum_{j=1}^N\lambda_j b_{(j)}-\frac12\|b\|^2\right\},\qquad x(T)=\mathop{\rm argmax}_{b\ge0}\{\cdots\}.
   $$

   Prove convexity of the sorted penalty by its finite permutation-max formula, existence/uniqueness, sorting alignment, and the decreasing nonnegative isotonic projection of d_j=T_(j)-lambda_j. Derive the min-max average characterization directly by the PAVA block optimality inequalities, including ties. Prove F_N=||x||^2/2, grad F_N=x, and the positive-block Hessian H=sum_B 1_B1_B^top/|B|, with inactive rows zero, as a weak a.e. derivative with no omitted singular Hessian mass (x is globally Lipschitz).

   If ordinary BH has rank k>0, all top k scores are >=u_k. For every suffix a:k, bound its average quantile by the first-k average and the right-Riemann integral <=phi(u_k)/S(u_k)<=u_k+1/u_k. For w=avg_(a:k)u_j and v=u_k+1/u_k, Jensen and monotonicity of w-4/w give avg lambda_j<=w-4/w<=v-4/v<=u_k-1/u_k. Conclude x_(k)>=1/u_k, retaining all non-strict BH comparisons. If the proxy support has size m>0, use its final positive block to prove d_m>=x_(m)>0, so T_(m)>lambda_m. Reprove by integrating phi/S<=t+1/t that S(u-4/u)/S(u)<99 for u>=3. Thus the actual rejection sets satisfy BH(q) subset supp(x) subset BH(99q). Do not infer any FDP inequality from this sandwich alone. Record independent null, common-factor and independent perfect-clone-block calibrations; reconstruct the weighted leave-one-block argument if used.

2. [x] **Prove the genuine unlocalized Gaussian comparison and its quantitative limitation.** For fixed means and original Sigma put Gamma_t=(1-t)Sigma+tJ, 0<=t<=1, J=11^top. Reconstruct Gaussian differentiation by parts for smooth functions; mollify F_N and, if necessary, add independent Gaussian regularization. Since every mixed entry of H is nonnegative and 1-Sigma_ij>=0, prove

   $$
   \mathbb E F_N(\theta+Z_\Sigma)\le\mathbb E F_N(\theta+Z\mathbf1)
   $$

   for every fixed theta, including singular endpoints after fixed-model dominated passage. Check polynomial growth explicitly. At theta=0 the common-factor proxy equals (Z-barlambda)_+*1, so E||x||^2<=N E(Z-barlambda)_+^2. Combine this with Step 1 to display exactly the remaining N/R loss; do not claim it proves an FDR bound. No independent Gram maximization or unverified covariance comparison may replace the actual Gamma_t contraction.

3. [x] **Compute labelled increments and a concrete finite shift/Laplace localization, including all sign defects.** Let I1=[N]\I0. Define F_alt on T_I1 with the FIRST |I1| original-N penalties lambda_1,...,lambda_|I1|; for I1 empty it is zero. Embedding b_I0=0 gives Delta F=F_N-F_alt>=0. On every common refinement of the two PAVA cell partitions, write

   $$
   \partial_{ij}\Delta F=(H_N)_{ij}-\mathbf1_{\{i,j\in I_1\}}(H_{\rm alt})_{ij}.
   $$

   Construct the explicit N=3 open cell with I0={1}, T1 large and unpooled, all proxy levels positive, and g=T2-T3 strictly between lambda2-lambda3 and lambda1-lambda2. Verify this interval exists: for p=S(u), lambda''(p)=(u+4/u-8/u^3)/phi(u)^2>0 at u>=3. Then H_N=I3 while H_alt has the {2,3} block of entries 1/2; hence partial_23 Delta F=-1/2, all null-alt mixed entries vanish, and tr[(J-I3) Hess Delta F]=-1 on this cell. This is a local actual-path sign defect, not a negative expected derivative theorem or a target counterexample.

   Set y=T-a*1_I0-c*1, keeping the ORIGINAL labels as a,c vary. Establish partial_c^2 F_N(y)=M(y) and partial_a partial_c F_N(y)=W(y) a.e., where M=|supp x| and W=|I0 intersect supp x|. Prove x(T-c1)=(x(T)-c)_+ for c>=0. For a Laplace parameter s>0, calculate the specific class

   $$
   G_s(T)=\int_0^\infty e^{-sc}F_N(T-c\mathbf1)\,dc=\sum_i f_s(x_i(T)),
   $$
   $$
   f_s(z)=\frac{z^2}{2s}-\frac z{s^2}+\frac{1-e^{-sz}}{s^3},\quad z\ge0.
   $$

   Verify the integral and growth bounds before differentiating. On a positive block of level b, Hess G_s has entries f_s''(b)/|B|=(1-e^{-sb})/(s|B|)>=0. But the labelled derivative L_s=-partial_a G_s(T-a1_I0)|_(a=0)=sum_(i in I0) f_s'(x_i) has positive cell-interior entries |B intersect I0| e^{-sb}/|B|^2 AND signed interface measures. Compute the full merge/split and activation table rather than dropping those measures. As a calibration, for N=2, fixed ordering and top coordinate null, at d1=d2=b>0 the singular mixed derivative is -f_s''(b)delta(d1-d2)/2. Along Gamma_t its Price contribution is -(1-Sigma12)f_s''(b)E[delta(d1-d2)]/2, with the local face mask and density included. Check orientation, coarea normalization and the factor 1/2. Reversing the null label reverses this interface sign. Activation at b=0 must be checked separately; no sign preservation is assumed for finite label differences, derivatives, or rank weighting.

   Make the general merge coefficient explicit. For adjacent positive blocks B,C with p=|B|, h=|C|, null fractions r_B,r_C, common merger level b, and zero-sum normal n=1_B/p-1_C/h, put zeta=b_B-b_C. Orient zeta>0 toward the unmerged cell. Verify that the gradient jump of L_s from the merged to unmerged side is kappa*n, where kappa=ph(r_B-r_C)f_s''(b)/(p+h). Thus its singular Hessian is kappa*n*n^top*delta(zeta), with the actual neighboring-cell mask. Since n^top J n=0, its Price contribution on the actual path is exactly -kappa*n^top Sigma n*E[delta(zeta)*mask]/2 (keep b and kappa inside the expectation when random). Harmful merges have r_B>r_C. Derive all coarea constants and the positive cell-interior contribution before integrating. This identifies an actual block-variance-weighted signed face functional, not an independently maximized PSD charge.

   Perform a concrete favorable pairing check at N=2 before attempting arbitrary blocks. With one null coordinate 1 and one alternative coordinate 2, theta1<=0<theta2, put D=T1-T2, A=T1+T2 and g=lambda1-lambda2>0. Equal marginal variances imply A and D are independent Gaussian variables for every nonsingular correlation. The null-top and null-bottom merger faces are respectively D=g and D=-g, have the same positive block level b=(A-lambda1-lambda2)/2, and opposite mixed-Hessian coefficients. Since E D=theta1-theta2<0, the density of D at -g is at least its density at g. Reconstruct the paired expected coefficient f_s''(b)*(f_D(-g)-f_D(g))/2>=0 after integrating b>0 against the independent A law, with the Price factor kept separate. Check the all-null/all-alternative label cases and singular endpoints. This is a scoped actual-mean N=2 cancellation, not a general pairing theorem. For N>=3 derive the conditional Gaussian density ratio at the paired faces with all other scores and relevant block sums retained; the conditional difference mean need not retain its original sign. The first residual from that loss of independence must appear explicitly in the later budget.

4. [ ] **Derive the exact combined proxy-FDR and BH dilution transfer, then attempt the labelled curvature allocation.** Write R,V for the ORIGINAL BH counts and M,W for the unshifted proxy support counts. The Step 1 inclusion gives M>=R. With all R=0 terms defined as zero, prove the nonnegative transfer identity and bound

   $$
   E_D=\mathbb E\left[V\left(\frac1{R\vee1}-\frac1{M\vee1}\right)\right]\ge0,
   $$
   $$
   \operatorname{FDR}_{\rm BH}\le\mathbb E\Psi(T),\qquad
   \Psi(T)=\frac W{M\vee1}+V\left(\frac1{R\vee1}-\frac1{M\vee1}\right).
   $$

   Do not assume either proxy FDR or E_D has the desired order. Use the exact integer-rank Laplace identity W/M=int_0^infinity W exp(-rM)dr on M>0, distinguishing its parameter r from the common-shift Laplace parameter s. Attempt to express its finite differences by the a,c derivatives and G_s/L_s from Step 3. For every proposed integration or summation, retain merger/split, score-permutation, proxy activation, BH threshold/cascade, endpoint and rank-normalization terms in a signed table with actual Gaussian density and covariance coefficients. Verify the finite table first for N=2 and N=3, all label assignments; keep alternative-alternative terms. The N=3 cell above forbids silently applying the unlocalized comparison to Delta F.

   There is a concrete endpoint budget to prove independently: KKT gives x_i>0 =>T_i-x_i>=lambda_N. At the common-factor endpoint T_i=theta_i+Z, a selected original null therefore implies Z>lambda_N. Since 0<=Psi<=2 and Psi>0 implies W>0,

   $$
   \mathbb E_J\Psi\le2S(\lambda_N)\le198q
   $$

   uniformly in every original mean vector. Check this endpoint with negative null means and arbitrary alternative magnitudes; no all-null reduction of the original model is being made.

   For nonsingular regularization, form the finite polyhedral refinement of the BH grid, score order and proxy PAVA cells. On each cell Psi is constant. If an oriented face separates values Psi_- and Psi_+, with unit normal n from minus to plus, derive the exact signed interpolation formula using the original Gaussian density f_t:

   $$
   K(t)=-\frac12\sum_{\mathcal F}(\Psi_+-\Psi_-)\int_{\mathcal F}n^\top(J-\Sigma)\nabla f_t\,d\mathcal H^{N-1},\qquad
   \frac d{dt}\mathbb E_{\Gamma_t}\Psi=K(t).
   $$

   Specify all face masks and refine where adjacent cells or labels change; no unrestricted free-threshold envelope is allowed. To use nonunit-diagonal regularization, first normalize the covariance and use its corresponding actual path difference, then pass to the original path only after obtaining a uniform estimate. Alternatively work on t<1 with a positive-definite original covariance and approximate the original Sigma by (1-epsilon)Sigma+epsilon I. Never omit a t=1 terminal limit.

   The concrete allocation attempt is to combine the full-energy nonnegative bulk of Step 2, the explicit signed kappa*n^top Sigma n merge terms of L_s and the exact BH-to-proxy transfer face coefficients BEFORE taking absolute values. Start with the actual-mean N=2 face pairing, then attempt an original-label Gaussian pairing or null-marked tail allocation for adjacent blocks using their actual variance n^top Sigma n. For higher-dimensional conditional pairs, write their full conditional means, variances, density ratio and unchanged cell masks; neither PSD nor unconditional null/alternative mean ordering implies conditional mean ordering. If the pairing leaves background-dependent likelihood-ratio or interface mass, retain that signed residual with its exact coefficient. Seek a finite table identity K=K_paid+K_rem and prove the external budget

   $$
   \int_0^1[-K_{\rm rem}(t)]_+dt\le A q(1+U)
   $$

   with finite universal A, while K_paid has a separately proved lower integrated bound of the same order. If a stronger budget on int[-K]_+ is proved directly, it also suffices. Every proposed allocation must specify its weights, their measurability, all endpoint terms, and the resulting numerical bound. The elementary identity int K=E_J Psi-E_Sigma Psi is NOT an external estimate. If the finite shift/Laplace collation leaves exactly an unknown FDR/normalized proxy term or a signed interface integral without a new q(1+U) budget, record that FIRST unpaid expression explicitly and stop this route as failed. A negative cell alone does not falsify this integrated gate; likewise a bare declaration of a gate is not successful execution.

5. [ ] **Finish only after the allocation budget is proved.** Combine the independent common-factor endpoint with the signed integrated lower bound to obtain E_Sigma Psi<=C q(1+U), then FDR_BH<=E Psi. Justify each regularization and singular endpoint at fixed finite N, using continuous univariate marginals at all BH thresholds and a separate check of proxy activation boundaries or a direct monotone/semicontinuity argument. Preserve ties and original labels. Establish universal constants and a universal q interval; relate 1+U to sqrt(log(1/q)) by an explicit Gaussian tail bound. Only then take the full supremum over N,theta,Sigma, allowing arbitrary q-dependent models. Without Step 4's new external estimate, do not write a main-asset proof or claim any PSD transfer of a uniform bound.

## Progress

### 1. Exact proxy geometry and deterministic inclusions (execution checkpoint)

Execution began from plan SHA256 16ab2a0899d376818e70f85c402c1684017019ef26e3ad4e4c6ad6ee471db594 and target SHA256 7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305. The workspace root has no Git HEAD. No target text has been changed.

Write P(b)=sum_j lambda_j b_(j) on b>=0. Since lambda is decreasing and positive, rearrangement by swapping inverted pairs gives
$$
P(b)=\max_{\pi}\sum_j\lambda_j b_{\pi(j)}.
$$
Thus P is convex, continuous and positively homogeneous. Adding the nonnegative-orthant indicator gives a proper closed convex function Q. The maximizer defining F exists by quadratic coercivity and is unique by strict concavity. Swapping an inverted pair of b coordinates increases T^T b without changing its other terms; hence a maximizer can be aligned with decreasing T. If two scores coincide, uniqueness and symmetry force their fitted coordinates to coincide. In sorted coordinates the maximizer is the Euclidean projection of d_j=T_(j)-lambda_j onto z_1>=...>=z_N>=0.

For completeness, the decreasing unconstrained projection is obtained by starting from singleton blocks and merging neighboring blocks whose means violate decreasing order. At termination its block means decrease. Within a resulting block [a,b] with mean beta, every prefix [a,h] has mean <=beta and every suffix [h,b] has mean >=beta. These facts hold for a singleton and are preserved by a merge of left mean <=right mean: a prefix crossing the merger is bounded by the mean of the entire merged block, using the prefix inequality inside its right part; the suffix statement follows by subtraction. Equivalently the residual prefix sums within each block are nonpositive, and the full block sum is zero. Summation by parts then gives <d-z,v-z><=0 for every decreasing v: the within-block term is a sum of nonpositive residual prefixes times v_j-v_(j+1)>=0, and the block sum terms vanish. This is the projection optimality condition. Truncating all nonpositive final levels to zero satisfies the analogous condition on the nonnegative decreasing cone (the negative part has nonpositive pairing against every nonnegative decreasing v by the same prefix inequalities). This also proves optimality and uniqueness of PAVA.

The block inequalities give, including equality and repeated scores,
$$
x_{(i)}=\left[\max_{b\ge i}\min_{a\le i}\frac1{b-a+1}\sum_{j=a}^{b}d_j\right]_+.
$$
Indeed, taking b at the right endpoint of i's block makes every a<=i average at least its block level (whole earlier blocks have larger levels; the initial partial block is a suffix). Taking a at the left endpoint makes every b>=i average at most its level (later full blocks are smaller and the terminal partial block is a prefix). These two choices prove the two inequalities.

Positive homogeneity and optimality along the feasible ray t x show T^T x-P(x)=||x||^2; thus F=||x||^2/2. For two inputs T,T', adding their variational inequalities gives ||x(T)-x(T')||^2<=<x(T)-x(T'),T-T'>. Hence x is globally 1-Lipschitz. The two maximizing-value inequalities also show grad F=x. On every open score-order/PAVA cell, each positive block B has level avg_(i in B) T_i minus its fixed average rank penalty. Consequently
$$
H= D x=\sum_{B\ {\rm positive}}\frac{1_B1_B^T}{|B|}.
$$
The finitely many order/PAVA inequalities define a finite polyhedral partition. Lipschitz continuity means the distributional derivative of x is its bounded a.e. derivative, without singular face mass. All mixed entries of the weak Hessian of F are nonnegative.

Let BH(q) have largest rank k>0. Its rejection set has exactly k elements: if more passed qk/N, the larger count itself would qualify. In sorted scores T_(j)>=u_k for j<=k. For a<=k, monotonicity of u_j bounds the suffix average w=avg_(a:k)u_j by the first-k average. The right-endpoint Riemann bound and a change of variables give
$$
w\le\frac Nk\int_0^{k/N}S^{-1}(qt)dt
=\frac{\phi(u_k)}{S(u_k)}\le u_k+1/u_k=:v.
$$
The last inequality follows from integration by parts: S(u)=phi(u)/u-int_u^infinity phi(t)/t^2 dt>=phi(u)/u-S(u)/u^2. Jensen applied to 1/u gives avg lambda<=w-4/w<=v-4/v<=u_k-1/u_k, where the last inequality is equivalent to 2u_k^2>=2 and u_k>=3. Thus every suffix average of d through k is >=1/u_k; the min-max formula proves x_(k)>=1/u_k. All ordinary BH rejections belong to supp x.

If m=|supp x|>0, the final positive block ends at m. Its suffix inequality at m gives d_m>=x_(m)>0, whence T_(m)>lambda_m. For u>=3, integrating the preceding hazard bound between u-4/u and u yields
$$
\log\frac{S(u-4/u)}{S(u)}
\le4-8/u^2+\log\frac{u}{u-4/u}
<4+\log(9/5)<\log99.
$$
Here e^4<55, for instance directly from its convergent power series. Therefore S(T_(m))<99qm/N. Rank m qualifies for BH(99q), whose largest qualifying rank is >=m, so every member of supp x belongs to its rejection set. We have proved the set sandwich, with no FDP comparison inferred from it.

Calibration only: under mutually independent test p-values, replacing null p_i by zero fixes a leave-one-out rejection count R_i independently of p_i; whenever i is rejected R=R_i. Hence E[1_{i rejected}/(R vee1)]<=E[(qR_i/N)/R_i]=q/N. Summing gives FDR<=q|I0|/N; the proof permits nonpositive null means. At the rank-one common-factor model, any rejected original null requires Z>=u_R-theta_i>=U, so FDR<=q, for arbitrary original alternative means. Finally suppose independent blocks are perfect clones with a common mean within each block and positive integer sizes w_g. For a null block replace its entire common p-value by zero, obtaining R_g>=w_g depending only on other blocks. On block rejection R=R_g. Conditional independence and null superuniformity give E[w_g 1_{g rejected}/R_g | other blocks]<=qw_g/N. Summing gives q times the total null-block size divided by N. These restricted calibrations do not establish the unrestricted target.

### 2. The actual Gaussian comparison, without localization

Set A=J-Sigma. A has zero diagonal and nonnegative entries, since PSD and unit diagonal imply |Sigma_ij|<=1. First use Gamma_t+epsilon I. For its Gaussian density f, differentiating det(C)^(-1/2)exp(-(T-theta)^T C^(-1)(T-theta)/2) gives
$$
\partial_t f=\tfrac12 A:\nabla^2 f.
$$
For a smooth polynomially bounded function, integrating by parts twice (with compact cutoffs sent to infinity against the Gaussian tails) gives d_t E F=E[A:Hess F]/2. Convolve F with a compact smooth nonnegative kernel. Its Hessian is the convolution of the weak H above, so all entries remain nonnegative and the derivative is nonnegative. There are no hidden face distributions because grad F is Lipschitz. Since 0<=F(T)<=||T||^2/2 and ||x(T)||<=||T||, dominated convergence first removes mollification and then epsilon, at each fixed finite model. It follows that
$$
E_\Sigma F(\theta+Z_\Sigma)\le E_J F(\theta+Z1)
$$
for all means and singular endpoints. This statement concerns F only.

At theta=0, d_j=Z-lambda_j increases with j, so PAVA pools every coordinate. Thus x=(Z-barlambda)_+1 and E_Sigma||x||^2<=N E(Z-barlambda)_+^2. The exact pointwise margin implication for R>0 is
$$
\frac VR\le\frac{u_R^2}{R}\sum_{i\in I0}x_i^2\le\frac{u_R^2}{R}||x||^2.
$$
In particular, at theta=0 and r>=1,
$$
P(R\ge r)\le\frac{N u_r^2}{r}E(Z-barlambda)_+^2.
$$
The uncontrolled factor N/r is present even in this restricted calibration. With arbitrary alternative means the common-factor energy can additionally grow without bound. No uniform FDR estimate follows by the unlocalized comparison.

### 3. Labelled increment, shift derivatives, and all codimension-one Laplace interfaces

Embedding an alternative-only candidate with zeros at the original nulls proves Delta F>=0: its nonzero coordinates use exactly the first |I1| penalties. On a common open PAVA cell, Hess Delta F=H_N-embedded H_alt. For p=S(u), differentiating lambda(p)=u-4/u twice gives
$$
\lambda''(p)=\frac{u+4/u-8/u^3}{\phi(u)^2}>0\quad(u\ge3).
$$
At N=3 this implies lambda1-lambda2>lambda2-lambda3. Choose g=T2-T3 strictly between these gaps, choose their common height sufficiently large, and choose T1 still larger so its singleton is separated and positive. Then H_N=I, while the alternative-only {2,3} fit is one positive pooled block. With I0={1}, partial23 Delta F=-1/2, every null-alternative entry is zero, and (J-I):Hess Delta F=-1. This is an open actual-cell defect; its Gaussian expectation has not been assigned a sign.

For y=T-a1_I0-c1, the labels remain the original ones. The weak Hessian formula gives partial_cc F(y)=1^T H1=M(y) and partial_ac F(y)=1_I0^T H1=W(y) a.e. PAVA block averages shift by exactly c, and truncation commutes with this shift, so
$$
x(T-c1)=(x(T)-c)_+\quad(c\ge0).
$$
For s>0, integrating each (z-c)_+^2/2 over c>=0 with weight exp(-sc) gives
$$
G_s=\sum_i f_s(x_i),\qquad
f_s(z)=\frac{z^2}{2s}-\frac z{s^2}+\frac{1-e^{-sz}}{s^3},
$$
$$
f_s'(z)=\frac zs-\frac{1-e^{-sz}}{s^2},\quad
f_s''(z)=\frac{1-e^{-sz}}s,\quad f_s'''(z)=e^{-sz}.
$$
Here 0<=G_s<=||T||^2/(2s), 0<=f_s'(z)<=z/s and 0<=f_s''<=1/s. These bounds justify the fixed-model differentiations and Gaussian integrals by domination. On a positive block B with size p, level b, null count w and fraction r=w/p, Hess G_s has entries f_s''(b)/p. Its gradient is continuous across all faces, so G_s has no singular Hessian. The labelled derivative is
$$
L_s=-\left.\partial_aG_s(T-a1_{I0})\right|_{a=0}
=\sum_{i\in I0}f_s'(x_i).
$$
On B, grad_i L_s=r f_s''(b), and its cell-interior Hessian has entries r exp(-sb)/p=w exp(-sb)/p^2 for i,j in B; other block-crossing entries are zero.

The complete generic codimension-one interface table for L_s is as follows. Higher-codimension intersections carry no Hessian face measure, because L_s is continuous and piecewise C1 with locally bounded gradients.

| Interface | Gradient jump, with the normal convention below | Singular Hessian |
|---|---|---|
| Adjacent positive blocks B,C merge/split | kappa n | kappa n n^T delta(zeta), on the actual neighboring-cell mask |
| A final positive block activates at b=0 | zero, since f_s''(0)=0 | zero |
| Two inactive blocks repartition | zero | zero |
| Score order exchanges at equal scores | zero | zero |

For the order row, strict rank penalties force equal neighboring scores into a common PAVA block in a neighborhood; exchanging their ranks leaves its average penalty and level unchanged. Thus the displayed zero is valid also with different labels. A positive/inactive collision necessarily has b=0 and belongs to the activation row. The cells with repeated rank or block equalities are covered by the lower-dimensional-intersection assertion.

In the first row put p=|B|, h=|C|, r_B=|B intersect I0|/p and r_C=|C intersect I0|/h. Let b be the common level on the face. Define
$$
n=1_B/p-1_C/h,\quad\zeta=b_B-b_C,\quad
\kappa=\frac{ph}{p+h}(r_B-r_C)f_s''(b).
$$
The side zeta>0 is unmerged; grad zeta=n and ||n||^2=1/p+1/h. The merged fraction is r_*=(pr_B+hr_C)/(p+h). On B the unmerged-minus-merged gradient is (r_B-r_*)f_s''=h(r_B-r_C)f_s''/(p+h)=kappa/p; on C it is -kappa/h. Thus the gradient jump is exactly kappa n. Distributionally, with delta(zeta) dT=dH^(N-1)/||n||, its Hessian face term is kappa n n^T delta(zeta) times the cell mask. This convention incorporates the coarea factor; writing unit normals instead gives gradient jump tensor unit-normal measure kappa n n^T dH/||n||.

Since 1^T n=0, its Price contraction on the ACTUAL path is
$$
-\tfrac12 E_t[\kappa\,n^T\Sigma n\,\delta(\zeta)\,1_{\rm mask}].
$$
No independently chosen PSD matrix replaces Sigma. Harmful signs require r_B>r_C. The positive interior contribution is separately
$$
\tfrac12 E_t\sum_{B>0}\frac{r_B e^{-s b_B}}{|B|}
\left(|B|^2-1_B^T\Sigma1_B\right)\ge0.
$$
This is nonnegative because each Sigma_ij<=1. It does not remove the signed face terms.

At N=2 with the upper score null and both levels positive, p=h=1, r_B-r_C=1, zeta=d1-d2 and kappa=f_s''(b)/2. The singular mixed derivative is -f_s''(b)delta(d1-d2)/2. Contracting both mixed entries with A_12=1-rho and the Price factor 1/2 yields -(1-rho)E[f_s''(b)delta(d1-d2)mask]/2. Reversing the labels reverses this sign. With both labels null or both alternative the jump is zero. In particular the all-null labelled derivative has nonnegative interior curvature and no merge mass, while the all-alternative derivative is zero.

For the actual-mean two-test pairing, suppose theta1<=0<theta2, put D=T1-T2, A0=T1+T2 and g=lambda1-lambda2>0. Their covariance is zero because the marginal variances agree. For |rho|<1 they are independent normals, with means mu_D=theta1-theta2<0, mu_A=theta1+theta2, variances 2(1-rho), 2(1+rho). The null-top and null-bottom merge faces are D=g and D=-g, respectively, with the identical positivity mask A0>lambda1+lambda2 and b=(A0-lambda1-lambda2)/2. If tau^2=Var(D),
$$
\frac{f_D(-g)}{f_D(g)}=\exp(-2g\mu_D/\tau^2)\ge1.
$$
Their total Price term is therefore
$$
\frac{1-\rho}{2}\left(f_D(-g)-f_D(g)\right)
\int_{\lambda1+\lambda2}^{\infty}
 f_s''((a-\lambda1-\lambda2)/2)f_{A0}(a)da\ge0.
$$
The separate 1/2 is the merge coefficient and includes the mixed-derivative contraction just computed. The density on D already incorporates the delta/coarea normalization; introducing coordinates (A0,D) gives Jacobian 1/2, which cancels their original joint density's factor 2. Singular rho endpoints follow by covariance approximation for E L_s, since L_s is continuous with linear growth. This proves a scoped N=2 comparison after integrating the nonnegative derivative on nonsingular paths; it does not supply a general-dimensional pairing.

For a higher-dimensional scalar difference D and retained background Y (other scores and the relevant block sum), a nonsingular jointly Gaussian law has
$$
\mu(Y)=\mu_D+\operatorname{Cov}(D,Y)\operatorname{Var}(Y)^{-1}(Y-EY),
$$
$$
\tau^2=\operatorname{Var}(D)-\operatorname{Cov}(D,Y)\operatorname{Var}(Y)^{-1}\operatorname{Cov}(Y,D),\quad
\frac{f_{D\mid Y}(-g\mid Y)}{f_{D\mid Y}(g\mid Y)}
=e^{-2g\mu(Y)/\tau^2}.
$$
These formulas follow by completing the joint quadratic density; conditioning leaves the displayed constant Schur-complement variance. The conditional mean can have either sign despite mu_D<0. Moreover the actual PAVA masks at the two faces can differ. Their exact residual must therefore keep both densities and masks. A finite N=3 calculation and the combined rank/transfer table are developed next rather than assuming those defects are harmless.

### 3a. An actual finite three-test conditional pair, with identical masks

Take theta=(0,eta,eta), eta>0, and
$$
\Sigma=\begin{pmatrix}1&0&1/2\\0&1&-1/2\\1/2&-1/2&1\end{pmatrix}.
$$
Its eigenvalues are 1, 1+1/sqrt(2), 1-1/sqrt(2), so it is admissible and positive definite. Write A0=T1+T2, D=T1-T2, Y=T3 and g=lambda1-lambda2, L=lambda1+lambda2. At t=0, A0 is independent of (D,Y), A0~N(eta,2), Y~N(eta,1), and
$$
D\mid Y=y\sim N(y-2eta,1).
$$
On the region 2eta<y<lambda3 and a>L, the faces D=+g and D=-g both describe a positive merged top pair and inactive third coordinate. Indeed the smaller pair score is (a-g)/2>lambda2>lambda3>y. The two masks are literally the same. The paired contribution to d_t E L_s at t=0 on this region is exactly
$$
\frac12\left[\int_L^\infty f_s''((a-L)/2)\frac{\phi((a-eta)/\sqrt2)}{\sqrt2}da\right]
\left[\int_{2eta}^{\lambda3}
\{\phi(-g-y+2eta)-\phi(g-y+2eta)\}\phi(y-eta)dy\right]<0.
$$
The strict sign follows pointwise from y-2eta>0, provided 2eta<lambda3. This is a finite actual-Gaussian calculation, not an independently optimized charge. For q=.001, eta=.1, s=1, direct composite-Simpson diagnostics using Python's standard-library NormalDist give u=(3.4029328354,3.2087069104,3.0902323062), lambda=(2.2274761945,1.9620988182,1.7958312373), the two bracket integrals .0003298304374 and -.03484202713, and contribution approximately -5.745980523e-6. The exact integral and its sign are proved above; these decimal quadratures are diagnostic only and make no error-certified or FDR claim.

Along the actual path Gamma_t=(1-t)Sigma+tJ, retain BOTH A0 and Y. Completing the conditional square gives
$$
\mu_t(a,y)=-eta+\frac{1+t}{1+2t}
\left[y-eta-\frac{t}{1+t}(a-eta)\right],\qquad
\tau_t^2=\frac{(1-t)(1+3t)}{1+2t}.
$$
Thus the full paired density coefficient is
$$
\frac12 f_s''((a-L)/2)f_{A0,Y;t}(a,y)
\left[\frac1{\tau_t}\phi\!\left(\frac{-g-\mu_t(a,y)}{\tau_t}\right)
-\frac1{\tau_t}\phi\!\left(\frac{g-\mu_t(a,y)}{\tau_t}\right)\right]
$$
on the identical top-pair/inactive-third mask a>L,y<lambda3. Here n^T Sigma n=2 and the 1/2 coefficient is retained. On other backgrounds the correct masks at +/-g must be retained separately. No sign for the full expected derivative, and no contradiction to a possible integrated order budget, follows from this negative region.

### 4. Exact combined observable and its finite face table

Use the original BH counts R,V and proxy counts M,W. On R>0, M>=R and V<=W. Therefore E_D=E[V(1/(R vee1)-1/(M vee1))]>=0, and, with all zero-count fractions defined as zero,
$$
\Psi=\frac W{M\vee1}+V\left(\frac1{R\vee1}-\frac1{M\vee1}\right)
=\frac V{R\vee1}+\frac{W-V}{M\vee1}\ge\operatorname{FDP}_{BH}.
$$
Since W-V<=M-R on R>0, 0<=Psi<=2; if R=0 it is W/(M vee1)<=1. Also Psi>0 implies W>0.

For selected i, coordinate optimality gives T_i-x_i>=lambda_N: along either sufficiently small coordinate perturbation at x_i>0 the sorted-penalty slopes lie between lambda_N and lambda_1, so stationarity forces this bound. At T=theta+Z1 a selected original null hence implies Z>=lambda_N+x_i-theta_i>lambda_N. Consequently, independently of all alternative means,
$$
E_J\Psi\le2S(\lambda_N)<198q.
$$
This endpoint does not use an all-null reduction.

Here is the finite face table for Psi. Write m=M,w=W,r=R,v=V on the minus side. Orient each activation or BH face toward the side with more selections. All rows include the original null labels. Faces are restricted to the actual adjacent cells of the common score-order, PAVA and BH-grid refinement; inactive crossings of a hyperplane have coefficient zero. The reverse face has the opposite jump.

| Face | Counts changed | Exact jump Delta Psi |
|---|---|---|
| Positive PAVA merge/split | none | 0 |
| Score-order exchange away from other faces | none | 0 |
| Proxy activation of h coordinates, ell null, m>0 | M+=h,W+=ell; R,V fixed | [ell m-h(w-v)]/[m(m+h)] |
| First proxy activation, m=0 | M=h,W=ell; R=V=0 | ell/h |
| BH cascade r->r+h, ell newly rejected nulls, r>0 | R+=h,V+=ell; M,W fixed | [r ell-hv]/[r(r+h)]-ell/m |
| First BH crossing r=0 | R=h,V=ell; M,W fixed | ell/h-ell/m |

The BH margin ensures proxy support cannot change on a generic BH face, because every coordinate rejected at that face has x_i>=1/u_(r+h)>0. Conversely an activating zero proxy coordinate cannot be BH rejected. Coinciding distinct face types have codimension >=2 after removing redundant hyperplanes; their intersections create no extra term for a piecewise-constant function's first distributional derivative. The BH face mask at sorted score j=k is T_j=u_k, all sorted scores/order inequalities valid, rank k qualifies on the face, no rank >k qualifies, and the minus-side largest qualifying rank is the specific r<k; its newly selected ranks r+1,...,k determine h and ell. A proxy activation face consists of a final PAVA block B with average d equal to zero, all its internal prefix/suffix inequalities, all other positive block inequalities strict, and all BH-grid inequalities fixing r,v. These masks include alternative-alternative faces: their ell can be zero but their denominator effect need not vanish.

The table exhausts all null assignments at N=2 and N=3 by allowing each newly selected set to contain ell=0,...,h nulls, with 0<=v<=r and 0<=w-v<=m-r. For an explicit small-N audit, the BH rows specialize as follows (only m>=new rank is allowed):

| BH transition | Delta Psi |
|---|---|
| 0->1, N=2 or 3 | ell(1-1/m) |
| 0->2, N=2 or 3 | ell(1/2-1/m) |
| 1->2, N=2 or 3 | ell(1/2-1/m)-v/2 |
| 0->3, N=3 (m=3) | 0 |
| 1->3, N=3 (m=3) | -2v/3 |
| 2->3, N=3 (m=3) | -v/6 |

For proxy rows: at m=0 the jump is ell/h for every h<=N; at m=1 the jump is [ell-h(w-v)]/(1+h), h=1 or 2 if N permits; at m=2,h=1 it is ell/3-(w-v)/6. Thus the two-test 1->2 BH row with m=2 is -v/2 even when the entering coordinate is alternative. At N=3 the same transition at m=3 is ell/6-v/2. These concrete negative dilution terms cannot be omitted as alternative-alternative effects. All-null and all-alternative configurations are included by setting (v,w,ell)=(r,m,h) or (0,0,0). Pure positive merge faces, despite their signed L_s curvature, have ZERO Psi jump.

For positive-definite original Sigma, Gamma_t is positive definite for t<1. On every finite face F let nu be its UNIT normal from minus to plus. Twice integrating the Gaussian heat equation over the constant cells gives
$$
\frac d{dt}E_t\Psi=K(t)
=-\frac12\sum_F\Delta_F\Psi\int_F\nu^T(J-\Sigma)\nabla f_t\,dH^{N-1}.
$$
The sign is from the distributional gradient grad Psi=sum_F Delta Psi nu dH, followed by one integration by parts. Each term uses the exact masks just described, the original mean Gaussian density f_t, and the ACTUAL covariance difference. There is no bulk term for Psi. For a fixed finite model these integrals exist on every t<=1-delta; the endpoint limit is addressed below rather than suppressed.

At an activation of a block B of size h one may take zeta=avg_B(T_i-lambda_rank(i)); then nu=1_B/sqrt(h), surface coarea is delta(zeta)dT=dH sqrt(h), and the exact coefficient in K is -Delta Psi times the displayed normal-density flux divided by 2. At a BH cascade the generic face is a single score threshold, nu=e_j in original coordinates; its coefficient is the BH jump above divided by -2, multiplying int_mask sum_i(1-Sigma_ji) partial_i f_t dH. In particular there is no diagonal density-derivative term. Replacing the masked hyperplane by the full hyperplane would integrate this tangential derivative to zero, discarding precisely the needed background boundary flux.

### 4a. Concrete shift/rank-Laplace collation attempt and its remaining terms

For the INTEGER support count, W/M=int_0^infinity W exp(-rho M) d rho on M>0; rho is unrelated to s. The immediate common-shift representation gives counts as right derivatives at c=0, not integrals in rho. To collate them concretely, define
$$
h_s(z)=1-e^{-sz},\quad M_s=\sum_i h_s(x_i),\quad W_s=\sum_{i\in I0}h_s(x_i).
$$
These satisfy W_s=-s partial_c L_s(T-c1)|_(c=0+) and M_s=-s partial_c L_s^{all}(T-c1)|_(c=0+), directly from f_s''. Also M_s->M, W_s->W pointwise, 0<=W_s/M_s<=1, and
$$
\frac{W_s}{M_s}=\int_0^\infty W_s e^{-\rho M_s}d\rho
$$
when M_s>0, with zero otherwise. On an open positive-block cell the exact Hessian of the integrand is
$$
e^{-\rho M_s}\left[H_{W_s}-\rho W_sH_{M_s}
-\rho(\nabla W_s\nabla M_s^T+\nabla M_s\nabla W_s^T)
+\rho^2W_s\nabla M_s\nabla M_s^T\right].
$$
The two cross terms have indefinite actual-path contraction. Neither H_(W_s) nor H_(M_s) inherits the nonnegative curvature of F: their cell second derivatives contain h_s''=-s^2 e^{-sb}. At a positive B,C merge, grad M_s has no jump but grad W_s has jump kappa_h n, where kappa_h=ph(r_B-r_C)s e^{-sb}/(p+h). Hence the singular Hessian of W_s/M_s has coefficient kappa_h/M_s. Its exact Price term is
$$
-\frac12 E_t\left[\frac{ph(r_B-r_C)s e^{-sb}}{(p+h)M_s}\,
n^T\Sigma n\,\delta(\zeta)1_{\rm mask}\right].
$$
The rank integral produces 1/M_s here because int exp(-rho M_s)d rho=1/M_s; M_s's own merge gradient is continuous. This term tends to zero at each fixed b>0 as s->infinity. Its possible surviving endpoint is near b=0, exactly where the activation and denominator terms in the finite Psi table live. At a first activation M_s vanishes, so differentiating the ratio requires this endpoint term; dropping it would erase its nonzero ell/h jump. At all later activations the limiting jumps are [ell m-h(w-v)]/[m(m+h)] after the BH dilution correction is included. Positive-level merges therefore cannot be identified with a missing positive Psi bulk; that bulk is identically zero.

One can keep all terms without formal limit interchange by integrating this bounded ratio over the finite cells first and using dominated convergence, obtaining the Psi face table after adding the exact transfer. But then the cross-gradient, activation and BH-cascade terms remain with the coefficients already written; the favorable unlocalized energy derivative provides no inequality controlling them. The explicit N=3 conditional integral above additionally shows that a pointwise conditional-density pairing cannot sign the merge allocation, even on an unchanged mask. We have not discarded that signed term or its actual variance.

### 4b. New actual-measure transport domination and a finite three-test joint allocation

The independent read-only pair-reflection calculation suggested a further useful allocation; it is reconstructed here. This is NEW partial progress beyond the conditional-sign obstruction, so the route is not declared failed merely from that obstruction.

Fix a null i, alternative j and remaining index k at N=3. Let gamma=1-Sigma_ij>0, c=Sigma_ki-Sigma_kj and C_t=(1-t)Sigma+tJ, t<1. Put kappa_t=sqrt(2(1-t)gamma). The centered pair sum and difference can be represented by independent standard normals S,D:
$$
T_i+T_j=\theta_i+\theta_j+2\alpha_t S,\quad
T_i-T_j=\mu+\kappa_tD,\quad
T_k=\theta_k+a_tS+\beta_tD+\epsilon,
$$
$$
\mu=\theta_i-\theta_j<0,\quad
\alpha_t=\sqrt{(1+C_{t,ij})/2},\quad
a_t=\frac{C_{t,ki}+C_{t,kj}}{\sqrt{2(1+C_{t,ij})}},\quad
\beta_t=\frac{(1-t)c}{\kappa_t}.
$$
Gaussian regression makes epsilon independent of (S,D); its nonnegative variance is the Schur complement. With a positive-definite original model it is positive. These formulas follow by taking covariances with S,D and subtracting their projections, without a change of mean or labels.

For adjacent pair ranks r,r+1, r=1 or 2, set g_r=lambda_r-lambda_(r+1), L_r=(lambda_r+lambda_(r+1))/2, m=(theta_i+theta_j)/2+alpha_t S, b=m-L_r, and d_+=(g_r-mu)/kappa_t,d_-=(-g_r-mu)/kappa_t. The positive-level mask is b>0. The other PAVA mask is exactly
$$
M_1(z)=1\{z<b+\lambda_3\},\qquad
M_2(z)=1\{z>b+\lambda_1\}.
$$
These inequalities force the correct score order as well: at the pair face its smaller score is b+lambda_(r+1) and larger score is b+lambda_r. Thus no order mask has been dropped. The paired Price contribution from these two singleton-merger faces is
$$
Q_{ij,r}(t)=\frac{\gamma}{2\kappa_t}\int\phi(S)f_s''(b)1_{b>0}
 E_\epsilon[\phi(d_-)M_r(z(d_-))-\phi(d_+)M_r(z(d_+))]dS,
$$
where z(d)=theta_k+a_t S+beta_t d. The factor gamma is the ORIGINAL path multiplier, not 1-C_(t,ij).

Since mu<0, d_+>=|d_-|. Therefore phi(d_-)>=phi(d_+), and phi(d)>=phi(d_+) throughout [d_-,d_+]. The bracket splits EXACTLY into the nonnegative term
$$
[\phi(d_-)-\phi(d_+)]M_r(z(d_-))
$$
and the signed transport term
$$
-\phi(d_+)\beta_t\int_{d_-}^{d_+}M_r'(z(d))\,dd.
$$
Here M_1'=-delta(z-b-lambda3), M_2'=+delta(z-b-lambda1). Crucially
$$
\frac{\gamma\beta_t}{2\kappa_t}=\frac c4
$$
on the ACTUAL path, including the (1-t) cancellation. Thus the exact residual R_(ij,r) keeps coefficient -c/4, phi(d_+), the same S,epsilon, b>0 mask and the displayed signed threshold delta. Replacing phi(d_+) by its dominating ACTUAL phi(d) only after taking the magnitude proves
$$
|R_{ij,r}(t)|\le\frac{|c|}{4}I_k^r(t).
$$
This is an actual finite Gaussian measure domination, not a conditional-mean-sign assertion.

Here I_k^r is the genuine adjacent triple-block facet integral. To verify every normalization directly, use coordinates
$$
M=(T_i+T_j+T_k)/3,\quad h=(T_i+T_j)/2-T_k,\quad\delta=T_i-T_j.
$$
Their inverse is T_i=M+h/3+delta/2, T_j=M+h/3-delta/2, T_k=M-2h/3, with absolute Jacobian 1. Write barlambda=(lambda1+lambda2+lambda3)/3, h1=L1-lambda3 and h2=lambda1-L2. Then
$$
I_k^1(t)=\int_{M>\bar\lambda}\int_{|\delta|<g_1}
 f_s''(M-\bar\lambda)
 f_t(M+h1/3+\delta/2,M+h1/3-\delta/2,M-2h1/3)
 \,d\delta\,dM,
$$
$$
I_k^2(t)=\int_{M>\bar\lambda}\int_{|\delta|<g_2}
 f_s''(M-\bar\lambda)
 f_t(M-h2/3+\delta/2,M-h2/3-\delta/2,M+2h2/3)
 \,d\delta\,dM.
$$
Arguments of f_t in these formulas are in coordinate order (i,j,k), with original means and covariance. The transported d interval is precisely |delta|<g_r. The mask threshold delta in z is the same as delta(h-h1) or delta(h+h2), with absolute derivative 1 in h; hence no further surface-normalization factor occurs. The new lemma has not freely moved a face or maximized a Gram charge.

The first concrete joint allocation table can now be written with all triple faces and the positive bulk. Set eta_k=1_{k in I0}, m0=sum eta_k, and
$$
v_k=\operatorname{Var}_\Sigma((Z_i+Z_j)/2-Z_k)
=3/2+\Sigma_{ij}/2-\Sigma_{ki}-\Sigma_{kj}.
$$
On the top-pair triple face, kappa=(m0-3eta_k)f_s''/3, while on the bottom-pair face it is its negative. Their total ACTUAL Price contribution is therefore
$$
T_3(t)=\sum_k\frac{(3\eta_k-m0)v_k}{6}
[I_k^1(t)-I_k^2(t)].
$$
The full-pool interior bulk is
$$
B_3(t)=\frac{m0\sum_{i<j}(1-\Sigma_{ij})}{9}
\int_{M>\bar\lambda}e^{-s(M-\bar\lambda)}
\int_{\mathcal H}3 f_t(M+z_1,M+z_2,M-z_1-z_2)dz_1dz_2dM,
$$
where z3=-z1-z2 and the exact contrast hexagon is max z_k<=lambda1-barlambda, min z_k>=-(barlambda-lambda3). These inequalities are equivalent to the full-block PAVA prefix/suffix conditions at N=3. Its coordinate Jacobian is 3. Every positive pair block {i,j} with m_ij nulls contributes the additional nonnegative bulk
$$
B_{2,ij}(t)=\frac{m_{ij}(1-\Sigma_{ij})}{4}
\int_{\text{actual pair-positive PAVA cells}}e^{-s b_{ij}}f_t(T)dT.
$$
Singleton blocks contribute zero, and activation/order faces contribute zero to L_s. Consequently the EXACT three-test derivative is
$$
\frac d{dt}E_t L_s=B_3+\sum B_{2,ij}+T_3+
\sum_{i\in I0,j\in I1,r=1,2}(G_{ij,r}+R_{ij,r}),
$$
where G is the explicitly nonnegative density-gap integral above and R is the signed transport integral with coefficient -c/4. All original label assignments are covered by m0,eta_k,m_ij; no pair of equal labels has a singleton-merge jump. A proved but weaker lower bound replaces the last sum by -sum |Sigma_ki-Sigma_kj| I_k^r/4. This is a finite multi-facet-plus-bulk allocation attempt; its remaining signed integrals are explicit.

Paying each transported face solely by its own v_k charge cannot yield a universal coefficient. For unit Gram vectors w_i=(cos e,sin e), w_j=(cos e,-sin e), w_k=(cos(e^2),sin(e^2)),
$$
\Sigma_{ki}-\Sigma_{kj}=2\sin(e)\sin(e^2)\sim2e^3,\qquad
v_k=\|(w_i+w_j)/2-w_k\|^2\sim5e^4/4.
$$
Their ratio diverges as e->0. A small independent regularization makes this example positive definite while preserving arbitrarily large ratios. This disproves that SINGLE-FACET coefficient payment only; joint allocations involving the other triple faces and B_2,B_3 remain open. No failure of the universal target or of every joint allocation is claimed.

### 4c. A fully paid dimension-dependent estimate, endpoint limits, and continuation gate

There is a separate explicit tail budget, but it keeps harmonic dimension. For alpha in (0,1/N), let h_alpha(p)=1/k on ((k-1)alpha,k alpha], k=1,...,N, and zero above Nalpha. Null superuniformity and summation by parts give
$$
E h_\alpha(p_i)
=\sum_{k=1}^{N-1}(1/k-1/(k+1))P(p_i\le k\alpha)
+P(p_i\le N\alpha)/N\le\alpha H_N.
$$
BH self-consistency implies 1_{i rejected}/(R vee1)<=h_(q/N)(p_i); proxy self-consistency implies 1_{x_i>0}/(M vee1)<=h_(99q/N)(p_i). Summing over original nulls proves the independent finite estimate
$$
E_\Sigma\Psi\le\operatorname{FDR}_{BH}+E_\Sigma(W/(M\vee1))
\le100q\frac{|I0|}{N}H_N\le100qH_N.
$$
This is a concrete paid estimate for the combined observable, but H_N is unbounded in the original supremum and cannot be absorbed into 1+U. Keeping the signed multi-facet allocation instead of this marginal tail envelope is essential if this route is to reach the target.

For any fixed positive-definite original Sigma, the terminal Psi limit t->1 is justified: BH boundaries have continuous univariate marginals, and every possible proxy activation hyperplane at J is Z plus a fixed block-average mean minus its fixed penalty, hence has nonzero variance 1. There are finitely many such hyperplanes. Score ties at J away from activation do not change support. Thus bounded convergence under a coupled Gaussian path gives E_t Psi->E_J Psi, and integration over [0,1-delta] followed by delta->0 retains the terminal value. For singular original Sigma, approximate by (1-epsilon)Sigma+epsilon I, which is unit diagonal, and prove any required estimate uniformly before passing to the limit. The BH FDP itself is locally constant away from the finite union of individual threshold hyperplanes T_i=u_k, each of probability zero even at singular Sigma. Hence BH FDR passes to the singular limit. Direct convergence of Psi at a singular original proxy-activation hyperplane is NOT assumed; zero-variance block averages may sit on such a hyperplane.

Current continuation gate: the exact N=3 sum B_3+sum B_2+T_3+sum(G+R) above needs a JOINT signed allocation, beyond the disproved single-facet payment. Even if that L_s allocation succeeds, it must still survive the explicit s/rho quotient cross terms, first/later activation endpoints and BH-cascade dilution coefficients in sections 4 and 4a. The final needed estimate is an external lower integrated budget for the masked activation-plus-BH flux K(t), of order q(1+U), uniformly in arbitrary finite N. Its coefficients and masks are fully recorded above; its integral being E_J Psi-E_Sigma Psi is only an identity. No such uniform estimate has yet been proved. Step 4 remains unchecked, the plan stays pending with this disk-backed Progress, and the main target is unchanged. Resume from section 4b rather than redoing Steps 1-3. Parent reports and native state transitions remain parent-owned.

### 4d. Parent-proposed common-anchor label chain: deterministic lemma and exact shared-noise formula

A final new direction is preserved for fresh continuation rather than discarded. Couple the actual path as T_i=theta_i+a X_i+b Z0, with X~N(0,Sigma), Z0 independent standard normal, a=sqrt(1-t) decreasing, b=sqrt(1-a^2). Fix the entire original Gaussian vector X. For an original null i and alternative j,
$$
T_i-T_j=(\theta_i-\theta_j)+a(X_i-X_j).
$$
The intercept is strictly negative. If X_i-X_j<=0 the null is always below the alternative. If X_i-X_j>0, as a decreases the difference decreases and can cross zero only from null above to null below. Thus, for EVERY fixed raw-score prefix size k, its original-null count V_k(a) is nonincreasing as a decreases. Within-label swaps have no effect, and simultaneous ties can be resolved by their two neighboring open orders; the one-sided count change is still nonpositive. This is one common chain with original means, not different per-null residual couplings.

Let s_(k)(a) be the decreasing order of theta_i+a X_i, including the original labels in that same order. For 0<a<1 define
$$
h_k(a)=\frac{u_k-s_{(k)}(a)}b,\quad
h_k^*(a)=\min_{l\ge k}h_l(a),\quad h_{N+1}^*=+\infty.
$$
Since BH uses the largest qualifying rank,
$$
P(R\ge k\mid X)=S(h_k^*),\qquad
P(R=k\mid X)=S(h_k^*)-S(h_{k+1}^*).
$$
Consequently shared-noise integration BEFORE any absolute values gives the exact conditional formula
$$
E[\operatorname{FDP}_{BH}\mid X]
=\sum_{k=1}^N\frac{V_k(a)}k[S(h_k^*)-S(h_{k+1}^*)]
=\sum_{k=1}^N\Delta(V_k/k)S(h_k^*),
$$
where V_0/0 is defined as zero in this finite Abel sum. On an interval with fixed raw order and suffix-minimizing index l_k, h_k^*=h_(l_k) and
$$
\frac d{da}h_{l_k}
=\frac{a(u_{l_k}-\theta_{i(l_k)})-X_{i(l_k)}}{b^3}.
$$
Thus the conditional derivative on that interval is the explicitly masked sum -sum_k Delta(V_k/k) phi(h_k^*) (h_k^*)'. The coefficients Delta(V_k/k) have both signs, including when the entering score is alternative. This is a concrete threshold-motion term that a monotone label-chain potential would still need to pay.

At an adjacent null-alternative score tie across prefix k, h_k>h_(k+1) because u_k>u_(k+1), while their raw scores agree. Hence h_k^*=h_(k+1)^* and P(R=k|X)=0. The atomic decrease of V_k at that tie therefore has ZERO instantaneous coefficient in the direct conditional FDP formula. This exact largest-rank mask prevents assigning a positive immediate payment to each removed raw inversion without a further integration or potential identity. No such identity has been established here.

The same shared-Z integration is available for the full Psi: the UNTRUNCATED decreasing PAVA partition of theta+aX-lambda is independent of Z0, with levels beta_B(a). Proxy activations occur at Z0=-beta_B(a)/b. Refine these finitely many thresholds together with the BH h_k^*(a); on each resulting interval of Z0 the four counts R,V,M,W and Psi are constant. Its exact conditional expectation is the finite sum of each Psi value times that interval's standard-Gaussian probability. Original labels and largest-rank masks are retained. A useful next step is to derive a monotone-label-chain potential whose derivative pays the threshold-motion sum, proxy activation and BH dilution on this ONE shared refinement. The deterministic monotonicity lemma alone is not an external order bound.

Continuation status: partial, not failed. Steps 1-3 are written in full; Step 4 has the exact combined table, explicit finite Gaussian conditional defect, a new actual-measure transport domination, and a joint N=3 face-plus-bulk formula. Its universal integrated allocation is unfinished. Resume with section 4b's joint allocation or section 4d's common-chain potential; do not repeat the completed PAVA/curvature derivations and do not replace the frozen target. The source idea's changed hash b1fd6fcc04f5150748387a6036865e722697bf7e32dd03035ec9ba63c4c7a79b was confirmed by the parent to result solely from its native resolve metadata/conversion note; no worker source-idea edits or mathematical use occurred.

### 4e. Executed rank-localized allocation: exact block coefficients and an integrated activation benchmark

This continuation takes the concrete rank-localized-null-energy option, keeping the same h_s,M_s,W_s as section 4a. It does not reprove Steps 1-3. The pre-insertion raw-byte plan hash was a0497ad00e713af5e84f39582b907ff8c0bc0ec8063827682367b323d68779bc; the frozen target still had hash 7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305. The older partial-continuation paragraphs above are retained as history; the conclusion below supersedes their continuation recommendation.

Put m_s=M_s>0, w_s=W_s and Q_s=w_s/m_s on a positive-support cell. On block B of size p, null fraction r_B and level b_B, write h_B=1-exp(-s b_B), h'_B=s exp(-s b_B), h''_B=-s^2 exp(-s b_B). Then m_s=sum_B p h_B and w_s=sum_B p r_B h_B. Direct quotient differentiation gives, for i,j in B,
$$
\partial_{ij}Q_s=(r_B-Q_s)\left[\frac{h''_B}{p m_s}-\frac{2(h'_B)^2}{m_s^2}\right],
$$
and, for i in B,j in C with B different from C,
$$
\partial_{ij}Q_s=(2Q_s-r_B-r_C)\frac{h'_B h'_C}{m_s^2}.
$$
Thus, with A=J-Sigma and A_{BC}=1_B^T A1_C, the EXACT cell-interior Price contraction is
$$
\frac12 A:D^2Q_s=
\frac12\sum_B A_{BB}(r_B-Q_s)
\left[\frac{h''_B}{|B|m_s}-\frac{2(h'_B)^2}{m_s^2}\right]
+\sum_{B<C}A_{BC}(2Q_s-r_B-r_C)\frac{h'_B h'_C}{m_s^2}.
$$
These are measurable functions of the actual fitted blocks. Every A_{BC} is nonnegative, but the displayed numerical coefficients have both signs. The positive-merge face coefficient is still kappa_h/m_s from section 4a; activation and BH faces remain separate. This is the finite block calculation of the proposed rank allocation, rather than assigning the unlocalized energy's sign to its quotient.

For a concrete actual N=3 check let I0={1}, theta=(0,eta,eta), eta>0, and Sigma have Sigma23=1, Sigma12=Sigma13=0. This is the admissible model T1=X,T2=T3=eta+Y with independent standard X,Y. Consider the open relative-support cell with null singleton level b0>0 and alternative pair level bA>0, b0>bA. Its scores are T1=b0+lambda1 and T2=T3=bA+(lambda2+lambda3)/2. Equal alternative scores force that pair to pool, while b0>bA separates the null singleton. All original means and labels are retained. On this cell A_{11}=A_{23,23}=0 and A_{1,23}=2. Consequently the entire interior Price contraction is
$$
2(2Q_s-1)\frac{h'_0h'_A}{(h_0+2h_A)^2}.
$$
At s=1, b0=log(4/3), bA=log(5/4), we have h0=1/4,hA=1/5,Q_s=5/13, and the contraction is exactly -1440/2197. It stays strictly negative in a neighborhood of positive actual Gaussian measure. Both F and L_s have ZERO interior Price contraction there: their only nonsingleton block is the perfectly cloned alternative pair. A sufficiently small unit-diagonal independent regularization preserves the strict negative quotient coefficient on a nearby open full-dimensional cell. This rules out a cellwise payment of this quotient term solely by the favorable F/L_s bulk on the same cell. It does not determine the sign of its globally integrated expectation or disprove an order budget.

There is a more decisive coefficient test of the entire rank integral on the legitimate all-null submodel. Here W_s=M_s, so Q_s=1_{M>0} for EVERY s>0. The integrand is M_s exp(-rho M_s). On M_s>0 its Hessian is
$$
e^{-\rho M_s}\left[(1-\rho M_s)D^2M_s+
(-2\rho+\rho^2M_s)\nabla M_s\nabla M_s^T\right].
$$
Integrating the TWO coefficients separately at fixed M_s>0 gives exactly
$$
\int_0^\infty(1-\rho M_s)e^{-\rho M_s}d\rho
=1/M_s-1/M_s=0,
$$
$$
\int_0^\infty(-2\rho+\rho^2M_s)e^{-\rho M_s}d\rho
=-2/M_s^2+2/M_s^2=0.
$$
Positive-level merge coefficients also vanish, because every block has r_B=1. Thus the direct rho allocation has ZERO remaining bulk and ZERO positive-level merge payment even in this all-null subproblem. It leaves the first-activation jump 1, where M_s=0. This endpoint cannot be recovered by setting M_s=0 in the preceding coefficient integrals: the terms 1/M_s and 1/M_s^2 diverge individually. In particular no unproved interchange of the rank integral with an absolute Hessian integral is made. The count quotient has a genuine distributional boundary term, although F and L_s themselves are continuous with zero first-activation gradient jump in their recorded interface tables.

The endpoint loss can be integrated exactly at N=2; it is not merely a negative cell. Take theta=(0,0), Sigma=I2, l1=lambda1,l2=lambda2,L=l1+l2. For ordered scores a>=b the PAVA optimality inequalities give
$$
\{M>0\}=\{a>l1\}\cup\{a+b>L\},\qquad
\{M=1\}=\{a>l1,b\le l2\}.
$$
To check the first identity, if d1>=d2 the largest fitted level is [a-l1]_+; otherwise both coordinates have level [(a+b-L)/2]_+. The union formula covers both cases. For M=1, its second fitted level is nonpositive while its first is positive, forcing the unpooled inequalities exactly as shown. With two nulls, Psi=1_{M>0}+1/2 on the event R=1,M=2 and equals 1_{M>0} elsewhere. The exceptional event is exactly
$$
\{a\ge u1,\ l2<b<u2\}.
$$
Indeed R=1 means a>=u1,b<u2; since a>l1, the two-coordinate support condition is then b>l2. Under independence this yields the explicit finite expectation
$$
P_I(M>0)=1-\Phi(l2)\Phi(l1)
-\int_{l2}^{l1}\phi(z)\Phi(L-z)dz,
$$
$$
E_I\Psi=P_I(M>0)+\frac q2[S(l2)-q].
$$
At the common-factor endpoint x=(Z-L/2)_+1, and ordinary BH selects either both tests or neither. Consequently
$$
E_J\Psi=S(L/2).
$$
Composite Simpson quadrature of the displayed ONE-dimensional integral, with 200,400,800 subintervals at q=.001, gives E_I Psi=.03777354689492692,.03777354689492499,.03777354689492488, respectively. The common-factor analytic benchmark is .026472235781286043; the integrated negative difference is approximately -.01130131111363884. Independent all-null BH itself has FDR=q in this example; the larger numbers concern the particular combined majorant Psi. The decimals are refined diagnostics, not an error-certified proof of a sign.

The strict sign for all sufficiently small q follows analytically without quadrature. Put U=S^{-1}(q). The hazard bounds U<=phi(U)/S(U)<=U+1/U imply
$$
u1=U+\frac{\log2}{U}+o(1/U),\quad
l1=U+\frac{\log2-4}{U}+o(1/U),\quad
l2=U-\frac4U.
$$
For fixed c, integration of the same hazard bounds shows S(U+c/U)/q->exp(-c). Hence S(l1)/q->e^4/2, S(l2)/q->e^4 and S(L/2)/q->e^4/sqrt(2). The part of {M>0} outside {max T>l1} has BOTH coordinates in (l2,l1], so its probability is at most [S(l2)-S(l1)]^2=O(q^2). Also P(max T>l1)=2S(l1)-S(l1)^2 and the BH correction above is O(q^2). Therefore
$$
\frac{E_I\Psi-E_J\Psi}{q}\longrightarrow
 e^4(1-1/\sqrt2)>0.
$$
The approximate limiting constant is 15.9914279045. This is an actual globally integrated obstruction to ZERO-defect covariance comparison for the normalized combined observable, even with no alternative labels. It does NOT refute the required O(q(1+U)) interpolation budget: this finite-model loss is only O(q), and can in principle be paid by such a budget.

For clarity the first unpaid flux after this executed rank allocation can now be written without any missing coefficient, already on the all-null submodel. For each oriented face F put
$$
\mathcal F_t(F)=\int_F\nu_F^T(J-\Sigma)\nabla f_t\,dH^{N-1},
$$
with the actual masks and unit normals from section 4. Write A0 for first proxy activations (m=0), A+ for later proxy activations adding h coordinates when M=m>0 and R=r, B0 for first BH crossings adding h coordinates, and B+ for later BH cascades adding h coordinates when R=r>0. Since w=m,v=r,ell=h, the complete remaining contraction is
$$
K_{\rm rank,rem}(t)=-\frac12\left[
\sum_{F\in A0}\mathcal F_t(F)
+\sum_{F\in A+}\frac{rh}{m(m+h)}\mathcal F_t(F)
+\sum_{F\in B0}(1-h/m)\mathcal F_t(F)
-\sum_{F\in B+}\frac h m\mathcal F_t(F)\right].
$$
There is no bulk, score-order, or positive-merge term in this all-null rank allocation. The A0 coefficient 1 is its FIRST unpaid expression; its normal for an activating h-block is 1_B/sqrt(h), with the full PAVA neighboring-cell mask. The remaining coefficients come from the exact dilution transfer, not independent per-rank optima. N=2 evaluates the joint integral above and proves it need not be nonnegative. For arbitrary N the allocation has supplied no external estimate of its negative integral of order q(1+U); the separately paid marginal estimate still contains H_N as in section 4c. Keeping original labels in the general case additionally retains the signed block and merge coefficients derived here and earlier, rather than removing this all-null activation difficulty.

This finishes a concrete rank-localized null-energy allocation through its finite coefficients and a globally integrated benchmark. It leaves the explicitly masked activation-plus-dilution flux, whose general-dimensional budget is still unknown. Failure below is the plan's stipulated stop on that essential unpaid remainder; neither the negative local coefficient nor the nonzero O(q) benchmark is presented as a failure of the proposed order bound or of every possible future joint allocation.


## Failure

Step 4 is not established. After the concrete rank-localized allocation in section 4e, its first unpaid term is the actual first-proxy-activation flux
$$
K_{A0}(t)=-\frac12\sum_{F\in A0}
\int_F\nu_F^T(J-\Sigma)\nabla f_t\,dH^{N-1},
$$
with coefficient 1 already in the all-null submodel and with the complete neighboring PAVA masks. The exact rank-Laplace coefficients cancel both interior Hessian contributions there; positive-level merges also contribute zero. The remaining later-activation and BH-dilution coefficients are the explicitly displayed K_rank,rem in section 4e. No external estimate of their joint negative integral by A q(1+U), with universal A and interval, has been obtained. The proved marginal fallback retains H_N. For general original labels the additional signed bulk/merge terms and section 4b's transport/triple-facet sum likewise have no jointly paid universal estimate.

This is the exact stopping condition prescribed in Step 4: the finite shift/rank collation has left a signed, masked activation-plus-BH flux without the required external bound. Its integral equaling an unknown expectation difference is not a bound. The new N=3 cell calculation specifically defeats cellwise payment by the available F/L_s bulk on that same cell. The new N=2 globally integrated benchmark specifically defeats zero-defect comparison for Psi. Neither countercalibration defeats an O(q(1+U)) budget: the two-test expectation difference is O(q), not an obstruction to its permitted rate. Thus this plan fails at an unpaid essential allocation, not because the frozen theorem has been disproved, and not as a claim that all possible nonlocal reallocations fail.

A successful replacement would need an independent dimension-free bound for the displayed activation-plus-dilution flux, coupled to the general labelled residuals, or a different BH majorant with a proved transfer that avoids this endpoint. Steps 1-3 and all Progress remain preserved. Step 5 cannot be executed, the target asset and its statement/Proof are untouched, and no main-asset proof or approval is claimed. Native reporting and subsequent state transitions remain parent-owned.

Narrow notation repair during finalization: the unique literal carriage-return byte followed by `m positive` in section 1's Hessian display was replaced by the intended literal LaTeX `\rm positive`, retaining every other preexisting byte. Raw-byte hashing, rather than newline-normalizing text hashing, was used for this and both insertions. The source idea was not edited.


## Verification

A successful proof must reconstruct the one-sided PAVA map, both deterministic inclusions and the BH margin; prove the actual supermodular Gaussian energy comparison with means fixed; calculate the loss of its sign after label/rank operations; retain every resulting interface and transfer coefficient; and give a genuinely independent universal budget for the combined remainder. The common-factor bound is quantitative, includes all means, and is insufficient without that remainder budget. Fresh independent verification is required before any proof approval. The parent owns native reports and approval requests.

The finite checks must distinguish: (i) a true local negative labelled curvature, (ii) failure of a proposed stronger allocation, (iii) an unpaid integrated gate, and (iv) a counterexample to the original target. Only an actual admissible finite Gaussian FDR violation could establish (iv). Fixed-dimension tests, restricted covariance calibrations and absence of counterexamples do not prove the theorem.

## Assumed definitions

Use only the target's existing approved definitions: Gaussian multiple-testing model, Gaussian test p-values and true nulls, ordinary Benjamini-Hochberg step-up procedure, false discovery rate, and uniform worst-case Gaussian BH false discovery rate. No unproved asset or draft library statement is assumed. The source idea and all failed plans are guidance and diagnostics only; every fact used here is reproved inline.

## Difference from failed plans

- plan_252211621cea: its signed-label occupation ended at the fully masked unknown FDR switch sum. This trial begins with a different, explicit C1 convex energy having nonnegative weak mixed derivatives, then computes the exact new label-localization defects instead of assuming an occupation budget.
- plan_503f8fddcbb5: its global-shift entrant allocation left signed facet flux and allocation decreases. Here common shifts act on PAVA block levels with an explicit Laplace primitive and label-fraction merger table; these new coefficients must be integrated together with the transfer, not replaced by entrant monotonicity.
- plan_ee2f7b97740a: compatible rank-chain transport had non-potential cut circulation and inverse-noise score losses. This plan has a genuine proxy potential but does not assert that BH weights or labelled derivatives are its gradient; actual merge faces replace any assumed path-independence.
- plan_one_sided_order_actual_mean_global_flux_20261106: marginal critical-level envelopes counted inactive transitions and whole cascades. This plan keeps actual BH and PAVA cells and the exact transfer, with no free crossing-level count.
- plan_one_sided_order_common_anchor_rotation_20261107: actual-mask Abel collation returned the unknown signed FDR derivative. The new feature is a proved external comparison for unlocalized proxy energy and explicit PAVA localization operations; if their combined collation again saturates at an unknown FDR, stop and record that precise failure rather than rename it a bound.
- plan_one_sided_order_gaussian_interpolation_sdp_20261106: no arbitrary covariance-free diagonal completion is sought. The actual covariance path contracts an explicitly nonnegative energy Hessian before any label localization; all newly negative terms retain their actual coefficients.
- plan_one_sided_order_negative_contact_transport_20261106: inverse-noise negative-contact allocations and unmatched background endpoints were unpaid. Here the proposed finite PAVA/Laplace table must keep both signs and prove integrability instead of paying row degrees or inverse conditional variances.
- plan_one_sided_order_peeling_history_kernel_20261107: stopped-history compensation and sibling pairing cancelled exactly to the terminal FDR. This trial uses no peeling histories; it has a different convex energy, a genuine covariance comparison, explicit labelled defects and a separately proved common-factor endpoint for Psi. The same terminal-saturation failure rule still applies.
- plan_one_sided_order_three_face_noise_packing_20261106: the obstructed Gram-maximized charge discarded the original small covariance multiplier. This plan never maximizes against an independent Gram matrix and retains J-Sigma in every localized interface contraction.
- The draft observation idea_57b374aee6d8 excludes exact scalar-potential gradients for BH selection weights. This plan respects that obstruction: x is a DIFFERENT proxy gradient; BH FDP enters only through the explicit, unpaid dilution-transfer term, whose curvature is not asserted nonnegative.
