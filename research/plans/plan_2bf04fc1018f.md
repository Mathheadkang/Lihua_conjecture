---
id: plan_2bf04fc1018f
type: plan
title: >-
  Conditional empirical crossing limit and global rank-cell comparison for
  compensated private clones
status: succeeded
target_asset: gaussian_bh_growing_clone_compensated_variation
inspired_by:
  - idea_320da635a4ce
  - idea_58aef0c223be
  - idea_c90946845a39
  - idea_30958c18ad42
  - idea_3734fd4524a6
adapts: []
tags:
  - gaussian-bh
  - private-clones
  - compensated-variation
  - largest-crossing
proof_digest: e761771cf8890aaf87a64816590973de482ea4649aed1945dd0e3313db7f16f8
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
dependency_digests:
  gaussian_bh_correlated_clone_first_variation: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
  gaussian_bh_compensated_private_clone_model: 4b7e14860e1ebfe41c3883571099a5b59674d01d89e9062632949673d4b6ac65
verified_proof_digest: e761771cf8890aaf87a64816590973de482ea4649aed1945dd0e3313db7f16f8
---

## Goal

Target: [Growing-private-clone compensated variation of finite Gaussian BH](../assets/gaussian_bh_growing_clone_compensated_variation.md).

Prove both assertions in their stated order for the exact construction: first the finite-copy limit at each fixed positive private noise, then the compensated variation as that noise decreases. Keep fixed finite N, q in (0,1/2), positive-definite original unit-diagonal covariance, chosen nonzero mean with its sign preserved locally, original labels, and actual common largest BH crossings. No estimate uniform over models or interchange of the two limits is sought.

## Existing-proof check

The current context pack lists no pending or failed plan for this asset and no library analogue. Native library searches for Gaussian BH largest crossing/private clone, empirical CDF/root stability/conditional binomial, saddle/clipping/rank threshold, contact upper branch/Gaussian Mills, and signed coordinate threshold variation returned no matches. The source-gap idea explicitly imports no external crossing theorem. This plan derives its crossing and error estimates directly; it does not adapt the incomplete external atomic-background arguments. The approved correlated-clone identity supplies the target's original signed-face notation, but its fixed-K exceptional-event estimate is not used for growing K.

## Plan

1. [x] **Fix the exact empirical crossing and the scope.** Write c_s=sqrt(1-s^2), m=theta_i+d_epsilon+c_s(T_i-theta_i), ell_i=1{i in I_0}, and n(x)=sum_{j!=i}1{T_j>=u(x)}. Let B_K(x)=K^{-1}sum_b 1{m+s xi_b>=u(x)}, H_K=n+B_K, and J_K be the same expression with the actual null labels. Prove directly from the non-strict largest-rank BH definition that R_{K,epsilon}/K is the largest point x=l/K, l=0,...,NK, with H_K(x)>=x, that H_K(R/K)=R/K when R>0, and that its FDP is J_K(R/K)/(R/K). Preserve exact ties of the unchanged copies. Check variance one, joint Gaussianity, and I_0 times [K] for the stated local sign-preserving epsilon range. Do not identify an empirical root with a population root yet.

2. [x] **Prove the conditional empirical CDF bound and the microscopic-rank exclusion separately.** Condition on the full original score vector, with fixed finite m and fixed s in (0,1). For each finite probability grid prove the binomial Chernoff deviation bound; bracket arbitrary thresholds between adjacent population-quantile grid points. A grid mesh smaller than a/4 gives, for each fixed a>0, P(sup_x|B_K(x)-b(x)|>a | T)<=C_a exp(-c_a K). Sum over K, then over rational a decreasing to zero, to obtain uniform conditional almost-sure convergence. This is a self-contained finite-grid proof, not an unlisted empirical-process black box.

   Also derive from the elementary Gaussian tail bounds, for any fixed 1<a<1/s^2, constants C and delta>0 depending on the conditioned vector and s such that b(x)<=C x^a for 0<x<=delta. All unchanged atoms are absent in this strip after decreasing delta. Make e C delta^{a-1}=z<1. For l<=delta K, show

   $$
   P\{K B_K(l/K)\ge l\mid T\}
   \le [eK b(l/K)/l]^l\le z^l.
   $$

   For each fixed l the first bound tends to zero as K tends to infinity. Dominated convergence of the sum over l>=1, dominated by z^l, proves that the probability of any empirical crossing in (0,delta] tends to zero. State the ceiling/floor conventions explicitly. Population b(x)/x tending to zero alone is insufficient for this conclusion about the FDP. **Failure gate:** stop if the bound is not uniform in l and K on this strip, or if a vanishing normalized rank is treated as zero FDP without this argument.

3. [x] **Prove the population maximum and its almost-sure regularity, including the random atoms.** At fixed original vector, b(x) is continuous and increasing, and n has finitely many upward jumps with their non-strict values. Use b(x)/x tending to zero at zero, right continuity, and finite jumps to show the positive supremum is attained. If H(rho)>rho, right continuity gives a larger crossing unless rho=N; at N, H(N)<=N with strict inequality because b(N)<1. Conclude H(rho)=rho. In fact a positive maximum cannot lie at an integer, because n+b is then a noninteger.

   For root stability condition instead on W=(T_j)_{j!=i}. Positive definiteness gives T_i|W a Gaussian law of strictly positive variance; m|W therefore has a continuous density. On each interval between the finitely many atom locations x_j=N S(T_j)/q in (0,N], let k be the unchanged count. Every equality H(x)=x has x=k+nu with 0<nu<1 and

   $$
   m=g_{k,s}(\nu):=u(k+\nu)-s S^{-1}(\nu).
   $$

   The analytic function g_{k,s} is nonconstant (in particular its value tends to infinity at nu=1). Its derivative has a discrete, hence countable, zero set, so its critical values form a conditional null set for m. At every atom, list the finitely many equality values obtained from its left and right unchanged counts and b(x)=x-k when 0<x-k<1; these also have conditional probability zero. This explicitly disposes of tangencies and atom-endpoint equalities without assuming strict crossings. Away from these exceptional levels every positive largest root is a simple downward crossing on an atom-free interval. On compact sets above that root, H(x)-x has a strictly negative maximum; when rho=0 the same holds away from zero. Prove the compactness statement using the right-value upper semicontinuity of the finitely many upward jumps. Treat N=1 by conditioning on the empty vector. **Failure gate:** do not assume an a.s. strict crossing or invoke an atomic-background stability theorem in place of proving these claims.

4. [x] **Complete the inner limit before starting the outer expansion.** At a regular vector with rho>0, bracket the simple downward root by strict inequalities at atom-free points and use the uniform empirical bound plus the lattice mesh 1/K to show R/K tends to rho in conditional probability (indeed almost surely on a fixed positive-root compact interval). No later empirical root can survive the compact negative gap. The unchanged selected set is eventually stable there, B_K(R/K) tends to b(rho), and the full fractional FDP tends to J(rho)/rho. At rho=0 combine the compact negative gap with step 2 to show P(R>0|T) tends to zero. Since all FDPs are in [0,1], conditional then unconditional bounded convergence yields lim_K F_{K,epsilon}=E D_epsilon. Establish this for every fixed epsilon in a sufficiently small sign-preserving interval; the regular null set may depend on epsilon.

5. [x] **Derive the high-root saddles and a quantitative low-root dichotomy in every rank cell.** For the outer limit put alpha_s=s/t_s and A(x)=-u'(x)=q/[N phi(u(x))]=1/[x h(u(x))]. Then A'(x)=-u(x)A(x)^2<0 for 0<x<=N. For r=1,...,N put k=r-1 and

   $$
   g_{k,s}(\Phi(t))=u(k+\Phi(t))+s t,
   \qquad B_k(t)=A(k+\Phi(t))\phi(t).
   $$

   On t>=0, (log B_k)'=-t-u(k+Phi(t))B_k(t)<0, so for all sufficiently small s there is one t_{c,r}>0 with B_k(t_{c,r})=s. The upper branch t>=t_{c,r} is strictly increasing in m and has minimum M_r(s)=g_{k,s}(Phi(t_{c,r})). Let nu_r(m)=Phi(t_+(m)) there and delta_r(m)=1-nu_r(m), defined only for m>=M_r. Prove delta_r<=C alpha_s and t_{c,r}=t_s+O(1/t_s), uniformly over the finitely many ranks of this fixed model.

   Supply a concrete common eta_s<=C exp(-c/s^2) for k>=1, with c>0 depending only on the finite threshold gaps. Choose D>0 smaller than one half of every gap u(k+1/2)-u(k+1), and take eta_s=S(D/s); on eta_s<=nu<=1/2, g_{k,s}(nu)>=u(k+1/2)-D>M_{k+1}(s) for small s. On nu>=1/2 the unique minimum is M_{k+1}. Thus below birth every root in cell k+nu is microscopic, nu<=eta_s. Above birth the high root exists; any feasible root below it makes the high root feasible because n(x) is nondecreasing. For k=0 prove no below-birth root at all: for nu<=1/2, S^{-1}(nu)>=0 and u(nu)>=S^{-1}(nu), hence g_{0,s}(nu)>=(1-s)u(nu)>=(1-s)u(1/2)>M_1(s) for small s. These inequalities plus the upper-half unique minimum cover the entire first cell. **Failure gate:** root births and lower roots must satisfy this dichotomy with a checked eta_s; a local saddle calculation by itself does not complete this step.

6. [x] **Derive the exact compensated threshold expansion and the integrated fractional deficit.** Starting from the exact equation A(k+Phi(t_c))phi(t_c)=s, not the heuristic equation with A_r, prove

   $$
   M_r(s)=u_r+s(t_s+t_s^{-1})+\alpha_s\log A_r
       +O(s/t_s^3+s^2),\qquad A_r=A(r).
   $$

   Derive the needed Mills remainders directly by integration by parts with an explicit bounded remainder. Convert m>=M_r into the original chosen-score threshold

   $$
   T_i\ge\beta_r(s):=\theta_i+
       \frac{M_r(s)-\theta_i-d_\varepsilon}{c_s},
   \qquad
   \beta_r(s)=u_r+\alpha_s\log A_r+O(s/t_s^3+s^2).
   $$

   The beta_r remain strictly decreasing in r. The marginal density of m is bounded uniformly for small s. On the upper branch dm/dt=s-B_k(t)>=0; therefore

   $$
   E[\delta_r(m)1\{m\ge M_r\}]
   \le C\int_{t_{c,r}}^\infty S(t)(s-B_k(t))dt
   \le Cs[\phi(t_{c,r})-t_{c,r}S(t_{c,r})]
   =O(\alpha_s^2).
   $$

   No deficit estimate is claimed on the unstable branch. Verify every bound for r=1 as well as r>=2; denominator issues for r=1 will be removed by the exact label identity in the next step.

7. [x] **Prove the global largest-crossing comparison through an explicit event partition.** Define n_r=n(r), B_r=1{T_i>=beta_r}, and the finite surrogate R^*=max({0} union {r:n_r+B_r>=r}). If R^*>0 select every unchanged j with T_j>=u_{R^*}, and select i exactly when B_{R^*}=1; call the resulting fixed-label FDP f_s^*. Prove from largest-rank maximality and monotonicity of n_r and B_r that the surrogate selects exactly R^* labels: n_{R^*}=R^*-B_{R^*}. This surrogate is an auxiliary comparison functional, not a new Gaussian testing model.

   Define the high clipping event as the union, over all r and j!=i, of

   $$
   \{m\ge M_r,\quad u_r\le T_j\le u(r-1+\nu_r(m))\}.
   $$

   Its probability is O(alpha_s^2): the interval has width <=C delta_r (the roots are near r>=1), the conditional density of T_j given T_i is bounded by original positive definiteness, and step 6 integrates delta_r. Define the low clipping event as the union over 1<=k<=N-1 and j!=i of T_j in [u(k+eta_s),u(k)]. Its probability is O(eta_s), by bounded one-dimensional Gaussian densities and a bounded u' near these positive integers. Endpoints have probability zero and can be included in the events. No independence of labels or coordinates is used.

   Off these events prove the following exhaustive routing statements from the cell decomposition x=k+nu, step 5, and largest-root maximality:

   - If R^*=0, no actual positive crossing exists. A high crossing in cell r would qualify surrogate rank r; a microscopic crossing in cell k+1 with k>=1 would, off the low strips, force n_k>=k and hence surrogate rank at least k. The first cell has no microscopic below-birth crossing.
   - If R^*=r and B_r=1, its high root x_r=r-1+nu_r(m) is feasible because all r-1 surrogate unchanged scores survive at its raised threshold off the high strips. Every later high root would qualify a later surrogate rank. Every later microscopic root would force a later background-only surrogate rank, except a possible microscopic root just above r; that last possibility is excluded by n_r=r-1 and the low strips. Hence the actual largest crossing is exactly x_r and has the same unchanged selected labels as the surrogate.
   - If R^*=r and B_r=0, n_r=r, so x=r is an actual crossing. Later high roots would qualify later surrogate ranks. All later microscopic roots are excluded by maximality except those with x in (r,r+eta_s]; off the low strips these retain exactly the same r unchanged selected labels and have chosen mass <=eta_s. Thus the actual largest crossing is in this interval (with the N endpoint handled directly).

   For the chosen high case r>=2, the two FDPs are (v+ell_i nu_r)/(r-1+nu_r) and (v+ell_i)/r, whose difference is <=C delta_r; for r=1 both are exactly ell_i regardless of the positive fraction. In the background case their difference is <=C eta_s. Combining all cases and the clipping probabilities proves the explicit global estimate

   $$
   E|D_\varepsilon-f_s^*|
      \le C\{\alpha_s^2+\eta_s\}.
   $$

   This estimate is the output of the routing proof and density bounds, not an assumed global comparison. It simultaneously treats atom clipping, lower roots, fractional-null FDP, root births/switches, all ranks, and cascades. **Failure gate:** if any routing case admits an uncharged extra crossing or changed label set, stop and mark the plan failed; do not replace the case analysis by a comparison conjecture or discard the signed term it would affect.

8. [x] **Compute the surrogate expectation from the original signed face jumps and assemble the iterated limit.** Set d_r=beta_r-u_r. For small s the bands between beta_r and u_r are disjoint in the single variable T_i. In the rth band only that chosen-coordinate rank qualification changes; all other ranks use their original qualifications. Using the same largest-rank rule prove that the FDP change across this band is exactly minus the oriented original coordinate-face jump, with the unchanged coordinates frozen at their realized values. This identity must allow arbitrary jumps of the final selected rank; no immediate-rank or positive-part substitute is permitted.

   Given T_i=t, the unchanged vector is Gaussian with a nondegenerate fixed conditional covariance and mean affine in t. Show directly from its density (including its integrable derivative near each fixed u_r) that the conditional expectation of this bounded signed jump is Lipschitz in t. Equivalently one may use the original PD pair-density intersection estimate plus smooth one-coordinate density. Integrate over each oriented band to obtain

   $$
   E f_s^*-F=-\sum_{r=1}^N d_r\,\mu_{i,r}(\mathbb R^{d-1})
                    +O\!\left(\sum_r d_r^2\right).
   $$

   Check that conditioning at T_i=u_r gives exactly phi(a_r) times the target's U_i-pulled-back Gaussian face integral; the other coordinates are frozen there, not displaced with Z. Combine with steps 4, 6, and 7 to prove the stronger fixed-model error statement

   $$
   F_{\infty,\varepsilon}-F
    =-\alpha_s\sum_{r=1}^N\log A_r\,\mu_{i,r}(\mathbb R^{d-1})
      +O\!\left(\alpha_s^2+s/t_s^3+s^2+\eta_s\right).
   $$

   Every displayed remainder divided by alpha_s tends to zero. Since -log A_r=log(r h(u_r)), this is the requested finite coefficient with its sign and original ranks. Check empty-null labels, N=1 with either permitted sign, and a chosen negative null with sign preserved; the proof must not add a chosen-positive-only condition. **Final failure gate:** any unavailable estimate, unlisted black box, uncharged exception of order alpha_s, or required change to the target statement means this plan fails rather than the target being declared proved.

## Verification

Execute the checklist in order. Steps 1--4 must produce the finite-copy expectation limit at each fixed positive noise before any population asymptotics are used. Steps 5--7 must establish the stated global L1 comparison through all routing cases and the two explicit clipping events, not merely exhibit the saddle displacement. Step 8 must derive the signed original-face coefficient from that same largest-rank surrogate and verify every remainder is o(s/t_s). Constants may depend on the fixed original model, N, q, means and covariance. No constant uniform over K is inferred from the prerequisite's fixed-K perturbative estimate. Neither research-goal bounds nor later rare-mean/Pareto constructions are part of this proof.

## Assumed definitions

The current pack marks all five used definitions approved: gaussian_multiple_testing_model, gaussian_test_pvalues, benjamini_hochberg_step_up, false_discovery_rate, and gaussian_bh_compensated_private_clone_model. There are no draft definitions and no unproved dependency statements assumed. The sole listed dependency gaussian_bh_correlated_clone_first_variation is approved; only its existing signed original-face identification is retained. All new empirical, regularity, saddle, Mills, clipping, and global comparison claims above are proof obligations to establish within execution. The inspired ideas remain draft motivation and are not black-box lemmas.

## Outcome

The complete proof is in the target asset's `## Proof`. Proof part 1 establishes checklist steps 1--2; part 2 establishes steps 3--4 and the full fixed-positive-noise finite-copy expectation limit before any outer expansion. Parts 3--4 establish steps 5--6 using the exact saddle equation, explicit Mills remainder, and integrated upper-root deficit. Part 5 establishes step 7 through both clipping events and all actual-largest-crossing routing cases. Part 6 establishes step 8 from the signed original-face jumps and gives the stated iterated coefficient with an explicit remainder that is o(s/t_s).

The target statement, status, scientific scope, original ranks and labels are unchanged. All five used definitions are marked approved in the execution context pack, including gaussian_bh_compensated_private_clone_model; no draft definitions or unproved external results are assumed. The asset remains draft for independent proof verification. No fixed-K tail estimate was made uniform in K and no order of limits was exchanged.

Checks: research-maintenance validate reported zero problems (with a pre-existing older-schema migration advisory); target-scoped links preview and apply reported zero review items and no file changes. The notation review used all five approved definitions from the context pack and the configured macros.tex and notations.tex, both of which contain only placeholder comments. All added symbols are defined locally, the signed jump and fractional deficit have distinct notation, and no missing relationship or notation conflict was found. The pre-proof asset content was checked against its starting SHA256 and preserved exactly. No approval record, loop state, digest, setting, or other research node was changed.

## Verdict

confirmed

Independently checked the statement against the proof and the supplied approved definitions, without consulting the producing plan's reasoning. For each fixed positive sign-preserving noise, the conditional empirical bound, microscopic-rank binomial estimate, conditional critical-value and atom exclusions, and bounded conditional FDP convergence establish the finite-copy expectation limit at the actual common largest crossing. The exceptional sets may depend on the fixed noise, as the quantifiers permit.

The saddle equation is exact before expansion. Its threshold remainder is $O(s/t_s^3+s^2)$, while the integrated upper-root deficit is $O((s/t_s)^2)$. The below-birth first-cell exclusion and the exponentially short higher-cell roots complete the classification. The routing in part 5 compares a single global maximum: outside the clipping events it identifies either its actual upper root or its background-only microscopic continuation. The conditional Gaussian density bound makes the clipping probability $O((s/t_s)^2)$, and the displayed fractional FDP estimates include the chosen null-copy mass and the rank-one endpoint.

The signed-band identity retains all original largest-rank cascades. Conditional Gaussian density differentiation supplies the required Lipschitz face integral, and its value at the face is precisely the stated signed measure, with the other coordinates frozen. All four final remainder ratios tend to zero. The argument covers $N=1$, empty null sets, negative chosen means with preserved sign, and arbitrary finite representations under the stated positive-definite original covariance. No substantive gap was found; no uniform-in-model or exchanged-limit conclusion is used.
