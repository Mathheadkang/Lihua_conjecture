---
type: plan
title: Reflection-paired Stein capacities on the complete two-sided BH grid
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
inspired_by:
  - idea_6e91300d2bf7
---

## Goal

Target: [Sharp uniform upper-bound target for two-sided Gaussian BH](../assets/gaussian_bh_two_sided_sharp_upper.md).

Prove the unchanged unrestricted target using a fixed, explicitly falsifiable
finite linear-programming certificate. The proposed certificate couples the
complete BH grid to its global reflection, shares null capacity between each
cell and its reflection, and permits a signed flux on an individual face when
the complete reflected face pair has nonnegative integrated flux. Neither
uniform feasibility nor a construction of its coefficients is known. Feasibility
is a sufficient condition, not an equivalent reformulation of the target.

Fix the range and constants BEFORE execution:

$$
u=Q^{-1}(q/2)\geq10,\qquad D_u=64\log(2+u),\qquad
z_k=Q^{-1}(qk/(2N)),\quad t_k=qk/N.
$$

Here Q is the standard normal survival function. The first substantive gate is
the FULL two-coordinate certificate for all labels, actual alternative means,
and correlations, using every cell and every face. Checking only N=1, two
selected faces, a sampled Gaussian moment, or a scalar-ray surrogate does not
pass it. A counterexample to this fixed certificate ends the plan; its constant,
range, coefficient basis and constraints may not be enlarged after failure.

Native library searches for `Gaussian BH two-sided`, `Stein capacity reflection
Gaussian face`, `Farkas Gaussian polyhedral divergence`, `Gaussian Stein
equation`, `reflection paired flux capacity`, and `finite linear programming
Farkas polyhedron` returned no results. The context pack contains no Library
analogues section. No library statement is cited or proof adapted. The
additional native read of [A reflection-paired Stein capacity certificate for
two-sided Gaussian BH](../ideas/idea_6e91300d2bf7.md) was needed because this
new proposal was absent from the pack; its assertions are rederived below.

## Plan

1. [x] **Audit the scalar kernels and signs before assembling a certificate.**
   Define the one-tail Stein solution explicitly by
   
   $$
   h_z(x)=
   \begin{cases}
   -Q(z)\Phi(x)/\phi(x),&x\leq z,\\
   -\Phi(z)Q(x)/\phi(x),&x>z.
   \end{cases}
   $$
   
   Verify its continuity and
   \(h_z'-xh_z=\mathbf1\{x>z\}-Q(z)\) off its single kink. Set
   
   $$
   H_k(x)=\frac{h_{z_k}(x)-h_{-z_k}(x)}{t_k},\qquad
   H_k'(x)-xH_k(x)=\frac{\mathbf1\{|x|>z_k\}}{t_k}-1.
   $$
   
   Prove that H_k is odd. Set
   
   $$
   K_u(x)=\tfrac12\sup_{0\leq a\leq u}e^{a|x|-a^2/2},\qquad
   c_u=\mathbb EK_u(G)=\tfrac12+u\phi(0),
   $$
   
   where G is standard normal. Check the piecewise maximizing a, and integrate
   directly to establish the displayed value of c_u. Define
   
   $$
   \psi_u(x)=\phi(x)^{-1}\int_0^x(K_u(s)-c_u)\phi(s)\,ds.
   $$
   
   Establish that psi is odd, solves \(\psi_u'-x\psi_u=K_u-c_u\), and is
   strictly NEGATIVE for x>0. Its Gaussian boundary product tends to zero at
   both infinities; prove the needed integrability and flux limits from the
   explicit tail integrals, without asserting that psi itself is bounded.
   No two-sided noisy-clone transfer is used.

2. [x] **Build the exact reflection-closed grid and freeze the finite LP.**
   First assume Sigma is positive definite. Realize
   \(g_i=v_i\mathbin{\cdot}Z\), where Z is standard N-dimensional Gaussian,
   \(\|v_i\|=1\) and \(v_i\mathbin{\cdot}v_j=\Sigma_{ij}\).
   Keep every actual alternative mean. In each g-coordinate cut at ALL
   
   $$
   \{-\theta_i\pm z_k,\ \theta_i\pm z_k:1\leq k\leq N\}.
   $$
   
   Remove duplicate cut locations as a set, retaining all coincident rank
   events. The products of adjacent intervals, including both unbounded
   intervals, are the cells C. Record exactly BOTH largest qualifying ranks
   R_C=R(g) and R_{-C}=R(-g) on every cell, with \(\kappa_C=R_C\vee1\).
   Null indicators at every rank are retained. Equality walls have zero
   Gaussian measure but must use the ordinary non-strict BH rule when checked.
   
   On each cell use only the following field basis:
   
   $$
   A_C(Z)=\frac1N\sum_{i\in J}v_i
   \{H_{\kappa_C}(g_i)-\beta_{Ci}\psi_u(g_i)\}
   +\sum_{j=1}^N\alpha_{Cj}v_j,
   $$
   
   where J is the actual set of zero-mean nulls, \(\pi_0=|J|/N\), alpha is
   unrestricted, and the ONLY capacity and pointwise cell-budget conditions are
   
   $$
   0\leq\beta_{Ci}\leq1,\quad
   \beta_{Ci}+\beta_{-C,i}\leq1,
   $$
   
   $$
   \pi_0-\frac{c_u}{N}\sum_{i\in J}\beta_{Ci}
       +\sup_{g\in C}\sum_j\alpha_{Cj}g_j\leq D_u.
   \tag{S1}
   $$
   
   For a bounded rectangle the support term is the maximum of finitely many
   endpoint linear forms. On an interval unbounded above require the associated
   alpha coefficient nonpositive, and on one unbounded below require it
   nonnegative, then use the finite endpoint. A coefficient unbounded in both
   directions is zero. Introduce epigraph variables if desired. This gives
   FINITELY many linear inequalities without truncating a cell.
   
   Orient each ordinary adjacent face F from C^- to C^+ by its latent-space
   unit normal n_F. Define its jump flux, with Gaussian surface density, by
   
   $$
   I_F(A)=\int_F(A_{C^+}-A_{C^-})\mathbin{\cdot}n_F\,\phi_N\,dS.
   $$
   
   Reflection sends this orientation to that from -C^- to -C^+ with normal
   -n_F. For each UNORDERED distinct reflected face pair impose
   
   $$
   I_F(A)+I_{-F}(A)\geq0.\tag{S2}
   $$
   
   A geometrically self-reflected face is included ONCE with I_F>=0. Include
   rank-inactive faces as well: changing coefficients can give them flux.
   All face integrals are affine in the unknowns and use the actual Sigma,
   never a separately optimized correlation matrix. Provide their exact
   Gaussian-integral expressions. In g-coordinates a face g_j=a has coefficients
   \(\phi(a)\mathbb E[\sum_i\Sigma_{ij}\Delta b_i(g)\,
   \mathbf1\{g_{-j}\text{ in its face intervals}\}\mid g_j=a]\), where
   \(b_i=\mathbf1_{i\in J}(H_{\kappa_C}-\beta_{Ci}\psi_u)/N+\alpha_{Ci}\).
   This formula fixes the surface normalization and uses the conditional
   Gaussian mean and Schur-complement covariance. Exact integrals or rigorous
   enclosures are allowed; Gaussian sampling is not.

3. [ ] **Mandatory full N=2 gate, before any universal feasibility claim.**
   Assemble EVERY rectangle and EVERY face from step 2 for N=2. Treat both
   nulls, no nulls, and each mixed labeling. For mixed labels retain
   \(\theta=(0,\mu)\), every \(\mu>0\), and all \(-1<\rho<1\); coordinate
   permutation and sign conjugation cover the other position and arbitrary
   alternative signs. The all-null case has both means zero. The no-null
   case is checked explicitly, not used as a proxy for a mixed case.
   A reduction to mu>0 and rho>=0 is allowed ONLY after proving full LP
   equivariance: flipping an alternative row together with its mean preserves
   its folded p-value, and flipping a zero-mean null row preserves its folded
   p-value while changing the sign of rho. Reflect the corresponding grid
   coordinate, replace its alpha coefficient by its negative, and use the
   oddness of H and psi to preserve the field, budget and geometric jump flux.
   Both the normal and adjacent-cell ordering must be transported. This gauge
   must cover the original rho(q)->-1 cases as well as rho(q)->1; it does not
   remove any mean or correlation rate regime.
   Include coincident cuts, all unbounded cells, rank holes, and simultaneous
   changes of the TWO ranks. Use the exact BH count formula independently of
   the LP. Face coefficients reduce to one-dimensional conditional Gaussian
   integrals with mean rho*a and variance 1-rho^2.
   
   Derive a complete primal/dual pair and either prove feasibility for this
   whole parameter family at every u>=10, or produce a rigorously checked
   infeasibility witness. Particular attention goes to q-dependent means
   approaching zero, threshold coincidences, means diverging with u, and
   \(\rho(q)\to1\) AND \(\rho(q)\to-1\) at arbitrary rates. A grid of numerical
   parameter values is diagnostic only. A gate pass needs analytic coverage
   or rigorous interval/subdivision arguments including all parameter tails;
   a failure needs an explicit finite Farkas witness with all coefficient
   enclosures and a strict separating margin. Include the singular endpoints
   via a fixed-model limit where applicable, without inferring uniformity
   from a fixed-rho calculation. If this gate fails or remains unresolved,
   STOP the plan here. Do not alter S1/S2, the basis, 10, or 64.

4. [ ] **Prove the conditional implication with all normalization factors.**
   This step checks sufficiency, not feasibility. For the Gaussian divergence
   \(\delta A=\operatorname{div}A-Z\mathbin{\cdot}A\), show on every open cell
   
   $$
   \delta A_C=
   \frac{\operatorname{FDP}(g)}q-\pi_0
   -\frac1N\sum_{i\in J}\beta_{Ci}K_u(g_i)
   +\frac{c_u}{N}\sum_{i\in J}\beta_{Ci}
   -\sum_j\alpha_{Cj}g_j.\tag{S3}
   $$
   
   When R_C=0, maximal-rank BH implies there are no p-values below t_1, so
   the first term remains exactly zero with kappa=1. Sum cellwise Gaussian
   integration by parts, verifying
   \(\mathbb E\delta A=-\sum_F I_F(A)\leq0\). Account for each geometric face
   once, all mirror orientations, and every infinity boundary using step 1.
   
   Since K_u is even and g has central symmetry, prove exactly
   
   $$
   \mathbb E[\beta_{C(g),i}K_u(g_i)]
   =\frac12\mathbb E[(\beta_{C(g),i}+\beta_{-C(g),i})K_u(g_i)]
   \leq\frac12c_u.\tag{S4}
   $$
   
   Combine S1--S4 to obtain, whenever the finite LP is feasible,
   
   $$
   \operatorname{FDR}_{\rm BH}^{(2)}
   \leq q\left[D_u+\pi_0\left\{\frac14+
                    \frac{u}{2\sqrt{2\pi}}\right\}\right].\tag{S5}
   $$
   
   The cell correction D_u is GLOBAL: it is not multiplied by pi_0. S4
   creates the proposed half coefficient only AFTER feasibility is proved.
   Never replace R_C by a chosen root, forced-zero rank, or an independent
   copy of the opposite rank.
   
   Optionally reduce variables by the following EXACT odd symmetrization:
   
   $$
   \widetilde A_C(g)=\tfrac12\{A_C(g)-A_{-C}(-g)\},\quad
   \bar\beta_{Ci}=\tfrac12(\beta_{Ci}+\beta_{-C,i})\leq\tfrac12,
   \quad\bar\alpha_C=\tfrac12(\alpha_C-\alpha_{-C}).
   $$
   
   Its baseline is \((H_{\kappa_C}(g_i)+H_{\kappa_{-C}}(g_i))/2\), not a
   single-rank kernel. The beta coefficients are reflection-even and alpha
   coefficients reflection-odd. For a distinct pair, its single-face flux is
   \((I_F(A)+I_{-F}(A))/2\); on a self-reflected face it is I_F(A). Average
   the two pointwise budgets at g and -g to prove S1 for this field.
   Conversely lift a feasible reduced solution by using its beta and alpha
   in the original single-rank fields and recheck their paired flux. This
   establishes equivalence of the two finite feasibility problems, rather
   than assuming individual original faces have nonnegative flux.

5. [ ] **Construct or refute the universal finite certificate.**
   After passing the complete N=2 gate, use the reduced formulation to write
   its full Farkas dual for general finite N: include every endpoint support
   inequality, the unbounded-interval sign restrictions, every reflected
   capacity, and every face-pair integral. Eliminate only genuinely redundant
   alpha directions, retaining the actual Gram entries and both ranks.
   Produce either explicit feasible coefficients for all admissible data or
   a proved dual obstruction bound showing that no separating vector exists
   with the fixed D_u. The proof must exploit exact largest-rank cell
   incidences and Gaussian face moments, and keep capacities summed globally;
   a per-null proportional estimate is not permitted.
   
   Make this a finite algebraic construction or a finite dual inequality,
   with its induction/flow rule and invariant displayed. Check the rule on
   the single-null staircase, all-null independent arrays, opposed and
   identical loading fixtures, mixed-sign Gram matrices, and all unbounded
   cells. Require the construction to be unchanged under harmless insertion
   of a reflection-paired rank-inactive cut. No estimate may contain the
   original unknown FDR, an independently maximized covariance completion,
   a dimension-dependent harmonic remainder, or an assumed general
   one-sided upper bound. Merely citing finite LP duality does not prove
   this step: an unproved universal feasibility or dual inequality ends
   execution as a failed proof attempt, preserving any checked subresults.

6. [ ] **Remove positive-definiteness and finish the exact uniform target.**
   Once S5 holds with the fixed constants for every positive-definite finite
   model, fix an arbitrary finite singular model and use
   \(\Sigma_\epsilon=(1-\epsilon)\Sigma+\epsilon I\). Couple its centered
   observation with \(g_\epsilon=\sqrt{1-\epsilon}g+\sqrt\epsilon W\), where W
   is independent standard Gaussian. Every coordinate still has a continuous
   unit-variance marginal, so the finite collection of BH threshold walls has
   zero probability in the limiting model. Prove a.s. convergence of the
   actual ranks and FDP, including tied coordinates and R=0. Bounded FDP
   transfers S5 by dominated convergence. This takes the regularization limit
   only after fixing the finite model; the coefficients themselves need not
   converge. Finally use
   \(u\sim\sqrt{2\log(1/q)}\), \(D_u=o(u)\), and \(\pi_0\leq1\) to derive
   the stated limsup constant and its epsilon-uniform formulation, allowing
   N, theta and Sigma to depend arbitrarily on q.

## Verification

Steps 1--2 define a finite, fixed certificate. Step 3 is a genuine early
refutation gate. Step 4 proves only the implication certificate => S5. Step 5
is the principal NEW proof obligation and cannot be assumed from that
implication, the target, marginal Gaussianity, or a numerical gate pass.
Only a completed step 5 plus step 6 establishes the target. The asymptotic
coefficient in S5 is
\(\sqrt2/(2\sqrt{2\pi})=1/(2\sqrt\pi)\), and the fixed global remainder
\(64q\log(2+u)+q\pi_0/4\) is smaller order. Failure of the stronger certificate
does not falsify the target. Record the exact failing inequality and retain
the original constants and model if a countercertificate is found.

## Assumed definitions

Only the target's approved definitions are used as definitions:
[Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md),
[Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md),
[ordinary Benjamini--Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md),
[false discovery rate](../definitions/false_discovery_rate.md), and
[uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md).
No draft result, draft definition, general one-sided upper bound, unproved
two-sided clone transfer, or library conclusion is assumed. Gaussian
integration by parts, the scalar Stein identities, finite LP duality and
the fixed-model continuity argument are to be supplied within execution.

## Difference from failed plans

- `plan_two_sided_signed_face_budget_20261104`: its remaining signed-face sum
  had no proved global constraint and its proposed pointwise opposite-face
  ordering failed. Here S1/S2 specify a different, finite coefficient LP;
  individual original faces may be negative, and actual reflected Gaussian
  integrals, rather than pointwise kernel ordering, are paired. The complete
  paired-rank N=2 certificate is tested before any general bound is sought.
- `plan_two_sided_null_noise_folded_completion_20261104`: its diagonal SDP
  completion permitted correlation matrices unrelated to the generating
  alternative block and had an explicit divergent dual. This LP uses only
  the actual Gaussian face law of the unchanged covariance, and has no
  covariance-completion maximization or null-noise interpolation.
- `plan_two_sided_fixed_label_blocks_20261104`: fixing covariance blocks
  left an unproved signed derivative negative-part bound, an uncontrolled
  residual-variance derivative, and an all-null trace budget. Here no
  covariance path or derivative is introduced. The new obligations are
  finite reflected capacities and paired transmission on the actual grid;
  those obligations must be proved, not inferred from the failed ones.
- `plan_two_sided_signed_forest_rank_cells_20261104`: its C9/C10 imposed a
  false sharp budget proportional to pi_0, refuted by the single-null
  staircase. S5 retains the explicit GLOBAL D_u, with no pi_0 factor on
  that correction; there is no anchored per-null cluster allocation. The
  staircase remains a compulsory check of the actual new LP.
- `plan_two_sided_rotation_pooled_arc_transport_20261104`: its available
  rank-only transport paid an unmatched term by the unknown FDR, yielding a
  circular estimate. This plan uses a fixed Stein-field basis, a displayed
  cell support budget, reflection-shared capacities and actual face-pair
  constraints. The exact Stein implication does not contain an unknown FDR
  on its right side. Universal feasibility is still unproved, and step 5
  explicitly forbids charging its dual obstruction to the original FDR.

## Progress

Execution checkpoint, 2026-11-04. Steps 1 and 2 are established below. The
complete N=2 coefficient system and its Farkas alternative have been specified,
but step 3 has NOT passed for all mixed means and correlations. No negative
dual witness has been proved either. Stop at this gate; steps 4--6 are not
claimed, the asset is untouched, and this plan remains pending. All constants,
the field basis, and S1/S2 are the ones fixed above. In particular the
calculations below do not prove the unrestricted upper-bound target.

### 1. Scalar identities, sign, and tail control

Write phi for the standard normal density and Phi=1-Q. Direct differentiation
of the two branches of h_z gives h_z'-x h_z=-Q(z) below z and 1-Q(z) above z.
At z both branches equal -Q(z)Phi(z)/phi(z), so h_z is continuous. Moreover
h_{-z}(-x)=h_z(x), as follows by applying the branch definitions and
Phi(-x)=Q(x). Consequently H_k is odd, continuous, and satisfies the displayed
Stein equation in step 1 off its two kinks, because 2Q(z_k)=t_k. Its one-sided
derivatives are locally integrable, so there is no Dirac mass at a kink.
For x>=0 its particularly useful exact form is

$$
H_k(x)=
\begin{cases}
-\{\Phi(x)-1/2\}/\phi(x),&0\leq x\leq z_k,\\
-(1/t_k-1)Q(x)/\phi(x),&x>z_k.
\end{cases}
\tag{P1}
$$

The two branches agree at z_k. For every fixed finite model and q>0 these
kernels are bounded, since Q(x)/phi(x)<=1/x for x>0, with their behavior on
compact intervals supplied by continuity. Thus phi(x)H_k(x) tends to zero at
both infinities, and H_k(G) and G H_k(G) are absolutely integrable. Boundedness
here is for a fixed kernel; no bound uniform in k,N,q is being asserted.

The maximizing a in K_u is min(|x|,u), so

$$
K_u(x)\phi(x)=
\begin{cases}
\phi(0)/2,&|x|\leq u,\\
\phi(|x|-u)/2,&|x|>u.
\end{cases}
$$

Integrating both half-lines gives c_u=u phi(0)+1/2. The integrand
(K_u-c_u)phi is even and has integral zero. It follows that psi_u is odd and
psi_u'-x psi_u=K_u-c_u. Here are explicit tail formulas, including the sign
of the normalization:

$$
\phi(x)\psi_u(x)=
\begin{cases}
c_uQ(x)-\tfrac12\phi(0)(u-x)-\tfrac14,&0\leq x\leq u,\\
c_uQ(x)-\tfrac12Q(x-u),&x\geq u.
\end{cases}
\tag{P2}
$$

Indeed these are minus the integral from x to infinity of (K_u-c_u)phi.
The increasing continuous function K_u(x), x>=0, starts at 1/2<c_u, tends to
infinity, and crosses c_u exactly once. The integral from 0 to x of
(K_u-c_u)phi is therefore strictly negative for every finite x>0: before the
crossing it decreases strictly, and afterwards it increases strictly to zero.
This proves psi_u(x)<0 for x>0. Formula P2 proves phi psi tends to zero at
both infinities without claiming psi is bounded. It also proves

$$
\int_{\mathbb R}(1+|x|)|\psi_u(x)|\phi(x)\,dx<\infty,
\qquad
\mathbb E|\psi_u'(G)|<\infty,
$$

because the tails are bounded by c_u Q(x)+Q(x-u)/2 and both this expression
and x times it are integrable on (u,infinity). The derivative conclusion
uses the Stein equation and E K_u(G)=c_u.

For completeness the same formulas give a fixed-u bound
|psi_u(x)|<=M_u exp(u|x|) for some finite M_u. For x>=u+1, use
Q(x-u)<=phi(x-u)/(x-u) in P2, and absorb the compact remainder in M_u;
oddness handles negative x. Hence every conditional face integral below is
absolutely convergent. On an infinity boundary g_j=+/-M the absolute
Gaussian flux is at most a fixed finite model-dependent constant times
phi(M){1+exp(uM)}. To see this, condition on g_j=+/-M and use, for each i,

$$
\mathbb E[e^{u|g_i|}\mid g_j=a]
\leq 2\exp\{u|\Sigma_{ij}a|+u^2(1-\Sigma_{ij}^2)/2\}.
$$

The constant coefficients and bounded H_k terms cause no problem. This
bound tends to zero for M tending to infinity, and restrictions to portions
of a cell only decrease the absolute bound. It justifies Gaussian flux
limits for the finite union of cells and all its unbounded sides.

### 2. Exact finite system and Gaussian normalization

For a positive-definite Sigma choose an invertible square root V with rows
v_i and set g=VZ. Each row has norm one. In coordinate i form precisely the
finite cut set in step 2, sort its DISTINCT values, and include all intervening
open intervals and the two unbounded intervals. Cartesian products give all
cells. The cuts include the actual thresholds of both theta+g and theta-g,
so both largest BH ranks and every null threshold indicator are constant on
each open cell. Coincident events are evaluated together, rather than being
replaced by an ordering of events. Reflection permutes the full cell set.
On a wall use the non-strict BH rule; finitely many walls have zero Gaussian
probability, so they do not affect any integral.

Here is the exact finite implementation of the support constraint. For
I_j=(l_j,r_j), require alpha_Cj<=0 when r_j=+infinity and alpha_Cj>=0 when
l_j=-infinity. If both ends are infinite require alpha_Cj=0. Form E_C by
taking all choices of l_j or r_j on bounded coordinates and the finite
endpoint on a half-infinite coordinate (zero on a full line). Then

$$
\pi_0-\frac{c_u}{N}\sum_{i\in J}\beta_{Ci}
       +\sum_j e_j\alpha_{Cj}\leq D_u
\quad(e\in E_C)
\tag{P3}
$$

together with those sign restrictions is exactly S1. This follows by taking
the supremum of a linear form separately over every interval. Endpoints need
not belong to the open cell because its supremum equals the supremum on its
closure. No cell has been truncated.

Orient a face F on g_j=a from the interval below a to the one above it.
The latent unit normal is v_j. Write B_F for the Cartesian product of all
other face intervals, and

$$
b_{Ci}(g)=\frac{\mathbf1_{i\in J}}N
   \{H_{\kappa_C}(g_i)-\beta_{Ci}\psi_u(g_i)\}+\alpha_{Ci}.
$$

The EXACT jump, with no determinant or extra surface factor, is

$$
I_F=\phi(a)\,
\mathbb E\!\left[
 \sum_i\Sigma_{ij}\{b_{C^+,i}(g)-b_{C^-,i}(g)\}
 \mathbf1_{B_F}\mid g_j=a\right].
\tag{P4}
$$

This is Gaussian disintegration along the unit linear functional v_j dot Z;
(v_i dot v_j)=Sigma_ij accounts for the vector-field contraction. Under this
conditional law g_{-j} has mean Sigma_{-j,j}a and covariance
Sigma_{-j,-j}-Sigma_{-j,j}Sigma_{j,-j}. Its covariance is positive definite.
In particular, P4 is an affine expression in all alpha and beta variables
with finite, exactly specified Gaussian-integral coefficients. The bound
following P2 justifies these moments even when B_F is unbounded.

Choose each geometric face once. Reversing its orientation reverses BOTH
the jump and the normal, leaving I_F unchanged. Reflection sends its two
cells and its normal to their reflected versions as prescribed in step 2.
For distinct reflection pairs add the two expressions P4; for a self-paired
face retain one expression. Denote the resulting affine forms by

$$
f_p+a_p\mathbin{\cdot}\alpha+b_p\mathbin{\cdot}\beta\geq0.
\tag{P5}
$$

Every face is included, including rank-inactive faces. Equations P3--P5,
the sign constraints, beta>=0, beta<=1, and beta_Ci+beta_{-C,i}<=1 freeze
the original finite LP for each actual model. On a self-reflected cell the
last condition is 2 beta_Ci<=1. No covariance is optimized separately.

One local identity useful for checking this assembly is obtained by
differentiating the field on an open cell. The norm-one rows give
delta(v_i H_k(g_i))=H_k'(g_i)-g_iH_k(g_i), with no cross-covariance factor.
For R_C>0, the number of p-values at or below qR_C/N equals R_C: if it were
a larger integer m, p_(m)<=qR_C/N<=qm/N would contradict maximality. Thus

$$
\frac1N\sum_{i\in J}
 \frac{\mathbf1\{|g_i|>z_{R_C}\}}{t_{R_C}}
=\frac{\operatorname{FDP}(g)}q.
$$

For R_C=0, no p-value is at or below t_1, and both sides are zero with
kappa_C=1. Applying the scalar identities and delta(v_j alpha_Cj)
=-alpha_Cj g_j proves S3, including its 1/N and c_u/N factors. This is a
local identity only; it supplies no feasibility conclusion.

### 3. Full finite Farkas alternative

The following describes the entire primal/dual pair, rather than a subset
of selected faces. Let S alpha<=0 be all unbounded-interval sign rows,
T beta<=1 all unordered reflected-cell capacities (coefficient 2 for a
self-reflected cell), and retain beta<=1 and beta>=0 separately. Let
lambda_Ce>=0 multiply each P3, eta>=0 each sign row, tau>=0 each capacity,
zeta>=0 each beta upper bound, and gamma_p>=0 each row -P5<=0. Put
L_C=sum_{e in E_C}lambda_Ce, and regard L as repeated for every null i in C.
The exact separating dual conditions are

$$
\sum_{C,e}\lambda_{Ce}E_{Ce}+S^{\mathsf T}\eta
       -\sum_p\gamma_p a_p=0,
\tag{P6}
$$

$$
r:=T^{\mathsf T}\tau+\zeta
       -\sum_p\gamma_p b_p-\frac{c_u}{N}L\ \geq0.
\tag{P7}
$$

Here E_Ce is the vector supported in alpha_C with entries e. The scalar
dual value is

$$
W=(D_u-\pi_0)\sum_{C,e}\lambda_{Ce}
       +\sum\tau+\sum\zeta+\sum_p\gamma_pf_p.
\tag{P8}
$$

A feasible primal implies W>=0 for every such nonnegative dual vector:
multiply all rows by their multipliers, use P6 to cancel alpha, and obtain
r dot beta<=W, whose left side is nonnegative. Conversely infeasibility
gives a vector satisfying P6--P7 with W<0. This is the finite Farkas
alternative applied after splitting each free alpha into its positive and
negative parts, and including -beta<=0; its multiplier on -beta is exactly
r. Thus no constraint has been omitted. Equivalently minimize W under
P6--P7 and the normalization that the sum of all multipliers equals one;
its minimum is negative exactly when the original LP is infeasible. The
normalized feasible set is compact and nonempty. If J is nonempty, one
zeta alone suffices. If J is empty, choose a cell whose closure contains
the origin and endpoint multipliers with total mass one and barycenter
zero; its intervals are bounded because every coordinate's cut set is
symmetric and nonempty. This satisfies P6, and P7 has no beta coordinates.
A negative computed value would still need rigorous coefficient enclosures
and a strict verified margin before it could be called a countercertificate.

### 4. Reflection reduction, retaining both ranks

An exact reduction used only to analyze the N=2 gate is as follows. Given
an original feasible field set

$$
\bar\beta_{Ci}=(\beta_{Ci}+\beta_{-C,i})/2,\qquad
\bar\alpha_C=(\alpha_C-\alpha_{-C})/2.
$$

These obey bar beta_Ci=bar beta_{-C,i} in [0,1/2] and
bar alpha_{-C}=-bar alpha_C. Oddness of both scalar kernels gives

$$
\widetilde A_C(g)=\frac1N\sum_{i\in J}v_i
 \left\{\frac{H_{\kappa_C}(g_i)+H_{\kappa_{-C}}(g_i)}2
           -\bar\beta_{Ci}\psi_u(g_i)\right\}
       +\sum_j\bar\alpha_{Cj}v_j.
\tag{P9}
$$

For each g in C average the two original pointwise budgets at g and -g;
the result is the P3 budget for the barred coefficients. Reflecting both
the normal and the adjacent-cell ordering shows that its single-face jump
is (I_F+I_{-F})/2 for a distinct pair, and I_F on a self-paired face. Hence
all its single-face fluxes are nonnegative. Conversely take barred
coefficients with these symmetries, their budgets, and nonnegative fluxes
for P9, and put them in the original SINGLE-rank fields. Odd averaging
recovers P9, so the paired flux of the original fields is twice that
single-face flux for a distinct pair and equal to it for a self-pair.
The original capacities and budgets already hold. This proves equivalence
of the finite systems; it does not assert that each original face has
nonnegative flux. The two H ranks in P9 cannot be collapsed to one rank.

### 5. Complete N=2 assembly and checked special cases

Set v=z_1=Q^{-1}(q/4)>u=z_2. For epsilon in {+1,-1} define

$$
A_i^\epsilon=\mathbf1\{|\theta_i+\epsilon g_i|\geq v\},
\qquad B_i^\epsilon=\mathbf1\{|\theta_i+\epsilon g_i|\geq u\}.
$$

The exact BH count is, separately for EACH epsilon,

$$
R^\epsilon=
\begin{cases}
2,&B_1^\epsilon B_2^\epsilon=1,\\
1,&B_1^\epsilon B_2^\epsilon=0\text{ and }
            \max(A_1^\epsilon,A_2^\epsilon)=1,\\
0,&\text{otherwise}.
\end{cases}
\tag{P10}
$$

This follows directly from testing the two largest-rank inequalities and
remains valid at simultaneous events and ties. In particular kappa^epsilon
is 2 exactly in the first case, and is 1 in both other cases. Rank holes
and the distinction between R=0 and R=1 are retained by P10 even though
they use the same H_1 baseline.

For mixed labels take theta=(0,mu), mu>0. The x coordinate cuts are exactly
{-v,-u,u,v}; the y cuts are the distinct members of
{+/-mu+/-u,+/-mu+/-v}. Thus there are at most 5 by 9 rectangles, and every
ordinary face belongs to either an x cut with one y interval, or a y cut
with one x interval. At the maximum number of distinct cuts this gives
4*9+8*5=76 faces. All-null means give 25 cells and 40 faces. With no nulls
there are at most 81 cells and 144 faces. Coincidences simply reduce these
counts by merging duplicate cuts; they do not remove any event in P10.
Unbounded intervals are present in every enumeration.

For every one of these faces P4 reduces to the following explicit
one-dimensional coefficients. On a face g_j=a let I be its other-coordinate
interval, sigma=sqrt(1-rho^2), and

$$
M_f(a,I)=\int_I f(s)\frac1\sigma
                \phi\!\left(\frac{s-\rho a}\sigma\right)\,ds,
\qquad M_1(a,I)=\mathbb P(g_\ell\in I\mid g_j=a).
\tag{P11}
$$

An own-coordinate H or psi term equals its value at a times M_1; an
other-coordinate term is M_H or M_psi times rho. Explicitly the baseline
part is

$$
f_F=\frac{\phi(a)}2\left[
 \mathbf1_{j\in J}(H_{\kappa_+}(a)-H_{\kappa_-}(a))M_1
 +\rho\mathbf1_{\ell\in J}
       M_{H_{\kappa_+}-H_{\kappa_-}}\right],
$$

and the variable part is

$$
\phi(a)\left[
 M_1(\Delta\alpha_j+\rho\Delta\alpha_\ell)
 -\frac12\{\mathbf1_{j\in J}\psi_u(a)M_1\Delta\beta_j
       +\rho\mathbf1_{\ell\in J}M_{\psi_u}\Delta\beta_\ell\}\right].
\tag{P12}
$$

Use P10 for kappa_+ and kappa_-, and include P12 for EVERY interval I,
including rank-inactive and unbounded ones. Pair by reflection as in P5,
or use P9. These formulas plus P3 and P6--P8 specify the complete N=2
primal and dual for every mu>0 and -1<rho<1, without taking a tail or
small-mean approximation. They are a specification, not a feasibility proof.

Here is a useful exact simplification for further work. Put d=H_2-H_1.
It is odd and, for x>=0,

$$
d(x)=
\begin{cases}
0,&0\leq x\leq u,\\
\{\Phi(x)-1/2-(1/q-1)Q(x)\}/\phi(x),&u<x\leq v,\\
Q(x)/(q\phi(x)),&x>v.
\end{cases}
\tag{P13}
$$

In the mixed case the null component of P9 before its beta and alpha
corrections is

$$
\frac12\{H_1(x)+\lambda_\mu(y)d(x)\},\qquad
\lambda_\mu(y)=\frac12\left(
 \mathbf1\{|\mu+y|\geq u\}+\mathbf1\{|\mu-y|\geq u\}\right).
\tag{P14}
$$

Indeed both ranks in P10 are 2 only when the null is beyond u, and d=0
inside that interval. For 0<mu<u, lambda_mu is respectively 0,1/2,1 on
|y|<u-mu, u-mu<|y|<u+mu, |y|>u+mu. For mu>u it is respectively 1,1/2,1
on |y|<mu-u, mu-u<|y|<mu+u, |y|>mu+u. At mu=u use the indicator formula
P14, including its non-strict endpoints; this also handles the coincident
cut y=0. For all-null labels the two components have baselines
{H_1(x)+1{|y|>=u}d(x)}/2 and
{H_1(y)+1{|x|>=u}d(y)}/2. Cuts at v can still separate R=0 from R=1,
and MUST remain in the LP even though these reduced baselines have no jump
there. Correcting coefficients can create a jump on such a face.

The exact sign/permutation equivariance covers the originally negative
correlations; it is not an assumption about nonnegative dependence. Apply
a signed coordinate permutation P to g, theta, and the rows v_i, and send
each cell to its corresponding signed-coordinate cell. Send each alpha
coefficient with its coordinate sign and keep beta with its permuted null.
Since H_k and psi are odd, each vector summand and thus the latent field
is unchanged, alpha dot g and the capacities are unchanged, and normals
and the order of adjacent cells are transported together. Folded p-values
and both ranks agree exactly. Hence every budget and geometric flux agrees.
For a mixed model make its alternative mean positive by flipping that row
if needed, then make rho nonnegative by flipping the zero-mean null row
if needed. These operations prove equivalence for EACH model and apply
unchanged to rho(q) tending to either endpoint at any rate. They do not
remove any mean or correlation regime from the unsolved feasibility task.

Two complete subfamilies pass. With no nulls choose all alpha=0; the field
and every jump are zero, and S1 is 0<=D_u. For rho=0, with ANY N=2 labels
and means, choose alpha=beta=0. On a face only the own component contributes
to the normal contraction. Its reduced baseline is continuous across its
own cuts: P13 has d(u)=0, its branches agree at v, and P14 has no x
dependence in lambda. The all-null formulas have the same continuity.
Thus every reduced face jump is zero; the exact lifting above proves
original paired flux zero, including dummy faces. S1 is pi_0<=1<D_u.
This checks all cells and faces for these subfamilies, not just selected
faces. It leaves every correlated mixed model and the correlated all-null
family unresolved.

As a separate check on the actual rank bookkeeping, the singular mixed
model g_1=g_2=Z and mu=u+v has the exact FDR

$$
\operatorname{FDR}=\frac{5q}{8}-\frac12 Q(2u+v).
\tag{P15}
$$

For Z>=u its FDP is 1/2. For Z=-x with u<=x<=v it is 1/2, for
v<x<2u+v it is 1, and for x>=2u+v it is 1/2; elsewhere it is zero.
Integrating uses Q(u)=q/2 and Q(v)=q/4 and gives P15. Equality walls
have probability zero. Positive-definite correlations tending to one
converge to this FDR by coupling and dominated convergence, since the
finite threshold walls still have zero marginal probability. This verifies
a mean of order 2u that a small fixed-mu test misses; it says nothing about
LP feasibility and is consistent with the large D_u remainder.

### 6. Precise continuation obligation

Step 3 still needs either (i) a feasible coefficient construction for every
u>=10, every mu>0 and every |rho|<1 in the complete P3/P5/P10--P12 system,
including all-null correlated labels, or (ii) a finite dual vector P6--P8
with rigorous coefficient bounds and W<0 for one fixed admissible model.
No numerical parameter grid, local negative face, or unnormalized local
path settles this alternative. The arbitrary alpha directions on unbounded
cells are essential. For example in the mu=1 grid the cell
(v,infinity) times (-U,U), U=u-1, permits
alpha_1=-M, alpha_2=-v M/U for any M>0; its support is exactly
-vM+U(vM/U)=0. Thus an assumed alpha_2>=0 on that cell, or an old
one-sided proof using it, is invalid in this reflected grid. Its reflected
cell can receive the negative alpha vector consistently with P9.

No feasibility result has been proved for means approaching zero, crossing
all threshold coincidences, diverging with u, or correlations approaching
either singular endpoint at arbitrary rates. The exact formulas remain
valid in those regimes; their validity alone is not analytic coverage of
the gate. The fixed-model limit in P15 does not imply such uniformity.
Accordingly no later universal-capacity step or final target is asserted.

### 7. Deterministic full-grid diagnostic, with the small-q scale retained

A continuation on 2026-11-04 executed the complete mixed-label N=2 reduced
system, rather than selected faces. The reproducible, short deterministic
script is `research-local/mixed_n2_full_lp_exec_20261104_c.py`. It constructs
every cut, cell, endpoint budget, unbounded-interval sign row and ordinary
face of P9--P14, parametrizes reflection-even beta and reflection-odd alpha,
and uses beta in [0,1/2]. It does not sample Gaussian observations. At 45
cells there are 23 reflection orbits, 69 declared scalar columns (the two
central self-reflected alpha columns have no effect), and all 76 faces. At
mu=u the coincident y=0 cuts merge, leaving 40 cells and 67 faces.

The face row is divided by its strictly positive factor
phi(a) P(g_other in I | g_j=a). Thus its kernel coefficients are conditional
means on the actual face interval, including unbounded intervals, not
unnormalized tiny probabilities. The probability is computed from log-normal
tails. The conditional integrals are split at -v,-u,0,u,v and integrated
in standardized conditional coordinates; the kernel and density exponents
are combined before exponentiation. Put S=phi(u), alpha_hat=S alpha, and
multiply every kernel by S. The exact scaled mixed-cell budget is

$$
\sum_j e_j\widehat\alpha_{Cj}
       -\frac{c_uS}{2}\beta_C
\leq S(D_u-1/2).
\tag{P16}
$$

In addition to the floating version of P16 the script solves the more
restrictive homogeneous support problem

$$
\sum_j e_j\widehat\alpha_{Cj}\leq0
\quad\hbox{for every endpoint row},
\tag{P17}
$$

with the same complete face system, sign restrictions and beta bounds.
An EXACT feasible solution of this homogeneous problem would satisfy S1:
its support is nonpositive and 1/2-c_u beta_C/2<=1/2<D_u. A floating solution
of P17 is not such an exact solution. In particular a support residual of
size 1e-17 after this scaling can become enormous after division by S.

The six short runs gave the following diagnostic outcomes. Here `feasible`
means only SciPy/HiGHS status 0, `infeasible` only status 2, and the residual
is the largest normalized inequality residual of the floating P17 solution.

| u | mu | rho | cells/faces | full floating system | P17 floating system | alpha=0 floating system | P17 residual |
|---|---|---|---|---|---|---|---|
| 10 | 1 | .5 | 45/76 | feasible | feasible | infeasible | 6.94e-18 |
| 10 | .001 | .9999 | 45/76 | feasible | feasible | infeasible | 4.02e-8 |
| 10 | 10 | .99 | 40/67 | feasible | feasible | infeasible | 6.94e-18 |
| 10 | u+v=20.06841183608143 | .99 | 45/76 | feasible | feasible | infeasible | 3.01e-8 |
| 10 | 1 | .99 | 45/76 | feasible | feasible | infeasible | 4.17e-17 |
| 12 | 50 | .9 | 45/76 | feasible | feasible | infeasible | 2.78e-17 |

These are six diagnostic instances, with non-rigorous quadrature and LP
tolerances. They give neither a verified primal vector nor a Farkas witness;
the tiny right side of P16 is below ordinary LP feasibility tolerances.
They do reveal a concrete issue worth resolving analytically: nonzero alpha
coefficients in support-nonpositive directions can repair faces which a
capacity-only ansatz cannot repair. The latter issue is proved for one
actual admissible model next. No row, fixed constant or coefficient basis
has been altered in the plan.

### 8. A rigorous obstruction to the capacity-only simplification

For the admissible mixed model

$$
u=10,\qquad \mu=1,\qquad \rho=99/100,
\tag{P18}
$$

the COMPLETE system with alpha identically zero is infeasible. This is a
restriction of the proposed LP, not a countercertificate for the full LP.
It rules out a simplification and does not settle step 3.

Here is a proof using only exact conditional face formulas. Let
v=Q^{-1}(Q(10)/2), q=2Q(10), c=1/2+10phi(0), and let X=g_1,Y=g_2.
The standard Mills inequalities

$$
\frac{x}{1+x^2}\phi(x)\leq Q(x)\leq\frac{\phi(x)}x
\quad(x>0)
\tag{P19}
$$

follow by integration by parts: Q(x)=phi(x)/x-
integral_x^infinity phi(t)/t^2 dt, whose remainder is between zero and
Q(x)/x^2. In particular
Q(10.1)/Q(10)<=exp(-1.005)<1/2, since the rational prefactor
101/(10*10.1) is exactly one. Therefore

$$
10<v<10.1.
\tag{P20}
$$

Follow all y-faces with the fixed other-coordinate interval X in
(v,infinity), from the bottom unbounded cell to the central y interval
(-9,9). On the negative y-axis lambda_1(y) drops by 1/2 at a=-11 and by
1/2 at a=-9. Every intervening cut at +/-1+/-v remains in this path; at
those cuts lambda has zero jump. Because d(X)>0 and psi_10(X)<0 on this
interval, P12 or P14 gives, when alpha=0,

$$
\Delta\beta\ \geq\ -r_a\Delta\lambda,
\qquad
r_a=\frac{\mathbb E[d(X)\mid X>v,Y=a]}
              {\mathbb E[-\psi_{10}(X)\mid X>v,Y=a]}.
\tag{P21}
$$

Indeed the normalized face flux is
rho{Delta lambda E d-Delta beta E psi}/2. Thus inactive cuts require
Delta beta>=0, and the two active cuts require increments at least
r_{-11}/2 and r_{-9}/2. It suffices to show each r_a>1/2.

For x>v put P(x)=phi(x){-psi_10(x)}=Q(x-10)/2-cQ(x)>0 by P2. Define
sigma^2=1-rho^2 and

$$
W_a(x)=\frac{\sigma^{-1}\phi((x-\rho a)/\sigma)}{\phi(x)}.
$$

The positive normalizing probability cancels from the ratio, so P13 gives

$$
r_a=\frac{q^{-1}\int_v^\infty Q(x)W_a(x)\,dx}
           {\int_v^\infty P(x)W_a(x)\,dx}.
\tag{P22}
$$

Write A=rho^2/sigma^2 and L_a=(rho^2 v-rho a)/sigma^2. For a=-11 or -9,
P20 and rho=99/100 imply A<50 and L_a>900. Direct expansion gives

$$
\frac{W_a(v+t)}{W_a(v)}
   =\exp(-L_at-At^2/2)\quad(t\geq0).
\tag{P23}
$$

Take delta=1/100 and K_a=L_a+A delta. Integrating the exponential upper
bound on the whole ray and its lower bound on 0<=t<=delta yields

$$
\frac{\int_v^{v+\delta}W_a(x)\,dx}
     {\int_v^\infty W_a(x)\,dx}
\geq\frac{L_a}{K_a}(1-e^{-K_a\delta})
>\frac{900}{900.5}(1-e^{-9})>.99.
\tag{P24}
$$

For the last elementary inequality one may use e^9>1000 and
900/900.5>999/1000; their product exceeds .998. The lower bound on the
segment follows from At^2/2<=A delta t, so the use of K_a is conservative.

P19, applied once at v+delta and once at v, also gives

$$
\frac{Q(v+\delta)}{Q(v)}
\geq e^{-v\delta-\delta^2/2}
\frac{v(v+\delta)}{(v+\delta)^2+1}>.88.
\tag{P25}
$$

For a direct rational check of the last strict inequality, P20 gives the
exponential factor greater than 1-.102=.898. The rational factor is
1-(1+v delta+delta^2)/{(v+delta)^2+1}>.98, and .898*.98=.88004>.88.
Finally P(x)<=Q(x-10)/2<=1/4 on x>v. By restricting the numerator of
P22 to the segment, using Q(v)=q/4, and applying P24--P25, obtain

$$
r_a\geq\frac{4Q(v+\delta)}q
\frac{\int_v^{v+\delta}W_a}{\int_v^\infty W_a}
>.88\cdot.99>.87>\frac12.
\tag{P26}
$$

Summing P21 over ALL faces on this negative-y path, including the inactive
cuts, now forces beta_central-beta_bottom>(.87+.87)/2=.87. Both values
must lie in [0,1/2] in the reduced system, whose difference is at most 1/2.
This is a strict contradiction. If the original paired system had a
solution with alpha=0, the exact symmetrization P9 would produce such a
reduced solution, so the same restriction fails there as well.

This argument deliberately retains the two allowed alpha components as
the unresolved mechanism in the FULL problem: their differences would
appear in P21 and invalidate the telescoping capacity contradiction.
Consequently it supplies no dual vector for P6--P8, does not fail the
fixed certificate, and does not justify ticking step 3. The continuation
obligation in section 6, including every mean regime, correlated all-null
labels and arbitrary rates to both singular correlation endpoints, remains
in force. The target asset has not been edited.

### 9. An explicit complete mixed fixed-case primal certificate

A further continuation on 2026-11-04 constructs a feasible certificate for
the FULL 45-cell, 76-face mixed system at

$$
u=10,\qquad \mu=1,\qquad \rho=1/2.
\tag{P27}
$$

This is a single admissible model, not the universal step-3 gate. The
construction below specifies its coefficients by exact conditional integrals;
active equalities are algebraic, and remaining strict inequalities have
directed interval enclosures with explicit integration and tail errors.
The new reproducible script is
`research-local/mixed_n2_exact_basis_exec_20261104_d.py`; run its
`--rigorous` mode with `/opt/anaconda3/bin/python`. Its first, separately
labelled high-precision reconstruction is diagnostic only; the subsequent
interval branch does not use that reconstruction's quadrature values.
The previous `mixed_n2_full_lp_exec_20261104_c.py` is unchanged.

Write S=phi(u), v=Q^{-1}(Q(u)/2), U=u-mu=9, T=u+mu=11, V=v-mu.
Use the ordered y endpoints

$$
(-\infty,-v-\mu,-T,-V,-U,U,V,T,v+\mu,\infty).
$$

Index the nine intervening intervals by j=0,...,8. Index the x intervals
by i=0,...,4, with I_0=(-infinity,-v), I_1=(-v,-u), I_2=(-u,u);
the remaining two are their reflections. Retain every interval even when
lambda_mu is constant across its boundary. For i=0,1 define EXACT moments

$$
d_i(a)=\mathbb E[Sd(X)\mid X\in I_i,Y=a]<0,\qquad
P_i(a)=\mathbb E[S\psi_u(X)\mid X\in I_i,Y=a]>0,
\tag{P28}
$$

where d=H_2-H_1 is P13. Let P_u=S psi_u(-u), P_v=S psi_u(-v), both
positive. The conditional law is N(rho a,1-rho^2), with exactly the
interval normalizer in P11; no face probability is dropped. Introduce

$$
p=\widehat\alpha_1+\rho\widehat\alpha_2,\quad
r=\rho\widehat\alpha_1+\widehat\alpha_2,\qquad
\widehat\alpha=\frac{(p-\rho r,r-\rho p)}{1-\rho^2},
\quad \widehat\alpha=S\alpha.
$$

Thus, after division by the positive face density and multiplication by S,
an x-face has flux Delta p-P_a Delta beta/2, where P_a=S psi_u(a).
A y-face on the negative-x interval I_i has flux

$$
\Delta r+\frac\rho2\Delta\lambda_\mu\,d_i(a)
              -\frac\rho2P_i(a)\Delta\beta.
\tag{P29}
$$

Set

$$
K_s=\frac{s/U-\rho}{1-\rho s/U}\ (s=u,v),\qquad
K_T=\frac{u/T-\rho}{1-\rho u/T},\qquad R_i=\rho d_i(T)/4.
$$

All three K constants are positive and their denominators are positive
at P27. Define the following scalars, in the displayed dependency order:

$$
B_{14}=-\frac{R_1+\rho d_1(U)/4}{(K_uP_u+\rho P_1(U))/2},\quad
p_{14}=P_uB_{14}/2,\quad r_{14}=-K_up_{14},
$$

$$
B_{13}=B_{14}+\frac{\rho d_1(-U)/4-r_{14}}{\rho P_1(-U)/2},\qquad
B_{12}=\frac{\rho P_1(-V)B_{13}}{\rho P_1(-V)+K_TP_u},
\quad p_{12}=P_uB_{12}/2,\quad r_{12}=-K_Tp_{12},
$$

$$
B_{04}=\frac{K_v(P_v-P_u)B_{14}/2-R_0-\rho d_0(U)/4}
                  {(K_vP_v+\rho P_0(U))/2},\qquad
p_{04}=p_{14}-P_v(B_{14}-B_{04})/2,\quad r_{04}=-K_vp_{04},
$$

$$
B_{03}=B_{04}+\frac{\rho d_0(-U)/4-r_{04}}{\rho P_0(-U)/2},\qquad
B_{02}=B_{03},\qquad B_{01}=B_{03}+\frac{d_0(-T)}{2P_0(-T)}.
\tag{P30}
$$

Every coefficient (p,r,beta) is now specified by this complete table:

| i | j=0 | j=1 | j=2 | j=3 | j=4 | j=5,6 | j=7,8 |
|---|---|---|---|---|---|---|---|
| 0 | (0,0,1/2) | (0,0,B01) | (0,0,B03) | (0,0,B03) | (p04,r04,B04) | (0,R0,0) | (0,0,0) |
| 1 | (0,0,0) | (0,0,0) | (p12,r12,B12) | (0,0,B13) | (p14,r14,B14) | (0,R1,0) | (0,0,0) |
| 2 | (0,0,0) | (0,0,0) | (0,0,0) | (0,0,0) | (0,0,0) | (0,0,0) | (0,0,0) |

Fill i=3,4 by beta_{-C}=beta_C and alpha_{-C}=-alpha_C.
The table's two j=5,6 entries use p=0; one floating basic solution had an
unnecessary negative p at i=0,j=5. Choosing zero there preserves every
y-face flux and makes the x=-v,j=5 face exactly tight.

Here is a complete face check. Across x=-v, the j=4 face is zero by the
definition of p04, and j=5,...,8 are zero. The j=0,1 faces are nonnegative
by P_v>0 and beta>=0. The j=2 face has flux
p12+P_v(B03-B12)/2>0, and j=3 has P_v(B03-B13)/2>0.
Across x=-u, j=2,4 are zero by p1j=P_u B1j/2; j=0,1,5,...,8
are zero, and j=3 has P_u B13/2>0. Reflection gives both positive-x cuts.
These are all 36 x-faces.

For i=0 the y-faces at cuts 2,3,4,5,6,7,8 are zero respectively by
B01, B02=B03, B03, B04, the repeated (0,R0,0), R0, and zero entries.
Cut 1 has flux rho P_0(-v-mu)(1/2-B01)/2>=0. For i=1, cuts
1,3,4,5,6,7,8 are zero respectively by zero entries, B12, B13, B14,
the repeated (0,R1,0), R1, and zero entries. Its sole remaining cut 2
has flux

$$
E=-\rho d_1(-T)/4-(K_TP_u+\rho P_1(-T))B_{12}/2>0.
$$

Every y-face in i=2 has zero flux since d=0 and all corrections are zero.
Reflection supplies i=3,4. These are all 40 y-faces, including every
rank-inactive face. Thus all 76 ordinary reduced fluxes are nonnegative.

The cell budgets are exact, without subtracting nearly equal floating
numbers at the S scale. Positivity of p12,p14,p04 and K_T,K_u,K_v makes
alpha_hat1>0 and alpha_hat2<0 in each of the three corresponding cells.
The relations r12=-K_Tp12, r14=-K_up14, r04=-K_vp04 say respectively
alpha_hat2=-(u/T)alpha_hat1, -(u/U)alpha_hat1, -(v/U)alpha_hat1.
The support maxima are therefore exactly zero at corners (-u,-T),
(-u,-U), (-v,-U). In the j=5,6 cells R_i<0, so p=0 gives
alpha_hat1>0, alpha_hat2<0 on x<0<y; their supports are strictly negative.
All other alpha are zero. Every unbounded-interval sign is respected.
Reflection preserves these support bounds. Consequently sup_C alpha dot g<=0
on every cell, and S1 follows directly from
1/2-c_u beta_C/2<=1/2<D_u. Since every beta in the table lies in [0,1/2],
all reflected capacities hold. P9 then lifts this reduced field to the
original single-rank field with the required paired fluxes. The two ranks
have not been identified or discarded.

For clarity, the remaining scalar signs above were certified as follows.
The interval branch uses `mpmath.iv` at 65 decimal digits for directed
arithmetic, pi, square root and exponentials. Gaussian Q is not taken from
an unverified floating erfc call. For x>=3 it encloses Q(x)/phi(x) between
the depth-80 and depth-81 convergents of

$$
\frac1{x+\frac1{x+\frac2{x+\frac3{x+\cdots}}}}.
$$

Indeed J_n=integral_0^infinity t^n exp(-xt-t^2/2)dt is positive,
J_1=1-xJ_0 and J_{n+1}=nJ_{n-1}-xJ_n; its positive ratio remainder
lies between truncation at zero and infinity, giving adjacent bounds.
For 0<=x<3, the code integrates the first 61 terms of exp(-t^2/2)
from 0 to x and bounds the absolute integral remainder by the next term
times phi(0). Taylor's integral remainder makes this valid without an
asymptotic-tail assumption. It proves the root bracket

$$
10.06841183608142940450<v<10.06841183608142940451.
$$

For each moment put z=-X>=u, m=rho a, sigma^2=1-rho^2 and
B(z)=(z^2-u^2)/2-(z+m)^2/(2sigma^2). Apart from the exact normalizer,
its integrand is n(z)exp B(z), where n is Q(z)/q on I0 for d,
(1-Q(z)/Q(u))/2 on I1 for d, and Q(z-u)/2-c_u Q(z) for psi.
The sign of the d moment is negative. Differentiate Q explicitly through
order four; its derivatives after order zero are
-phi(z), z phi(z), (1-z^2)phi(z), (z^3-3z)phi(z).
If A=rho^2/sigma^2, the derivatives of exp B divided by exp B through
order four are 1, B', B'^2-A, B'^3-3AB', B'^4-6AB'^2+3A^2.
Their binomial product gives an interval enclosure of the fourth derivative
on each subinterval. Simpson's rule then has absolute error at most
length^5 sup|f''''|/2880, computed with outward interval rounding.
The total allocated error is at most 1e-6 per moment; all arithmetic
enclosures are retained rather than replacing values by decimal centers.

The I0 integrals are cut at z=L=40 solely for this rigorous integration,
not to truncate any LP cell. If M_i is the conditional interval mass,
the omitted positive-magnitude tails are bounded, respectively, by

$$
\frac{S}{qL M_0}Q((L+m)/\sigma),\qquad
\frac{S e^{-u^2/2-um+u^2\sigma^2/2}}{2(L-u)M_0}
 Q((L+m-u\sigma^2)/\sigma).
$$

These follow from Q(z)<=phi(z)/z and a Gaussian exponential tilt.
Every invoked tail bound is interval-verified below 1e-100 and added back.
The complete run used 1487 adaptive Simpson panels, no sampling and no
parameter sweep. Outward-widened excerpts of its final enclosures are:

| scalar | verified enclosing interval |
|---|---|
| B01 | [0.26955032, 0.26955052] |
| B02=B03 | [0.27000405, 0.27000425] |
| B04 | [0.26974572, 0.26974590] |
| B12 | [0.09637280, 0.09637350] |
| B13 | [0.20290162, 0.20290299] |
| B14 | [0.16420825, 0.16420863] |
| p04 | [0.04530495, 0.04530513] |
| B03-B13 | [0.06710106, 0.06710263] |
| B03-B12 | [0.17363055, 0.17363144] |
| E | [0.00815396, 0.00815412] |

The code also encloses P_v-P_u strictly above 0.21957749 and p12
strictly above 0.01204660. Thus each stated strict scalar inequality
has a separating interval, and active fluxes/budgets are exact identities,
not residuals rounded to zero. This supplies one full fixed-case primal
certificate, subject to the explicitly recorded interval-arithmetic
implementation; independent cold checking remains appropriate.

### 10. What this construction does and does not parameterize

The table and formulas P28--P30 define a conditional construction whenever
the same cut order holds, 0<rho<1, the K denominators are positive, and
the listed scalar sign inequalities hold. The strict enclosures at P27
and continuity of the finite conditional integrals give an open parameter
neighborhood of that model, with u restricted to its allowed domain u>=10.
No explicit size of that neighborhood has been certified, and it does not
cover all u,mu,rho. In particular 1-rho v/U changes sign at rho=U/v<1;
the positive-p outer corner used here cannot retain this basis near rho=1.
It requires a different construction or a rigorous obstruction there.
Small means where the cut order changes, coincident cuts, diverging means,
the correlated all-null case and arbitrary singular-correlation rates
remain unsolved. Step 3 stays unchecked; steps 4--6 are not advanced.

Finally, P17 with its nonzero baseline face source is a support-nonpositive
primal problem, not the homogeneous alpha recession cone. For a truly
homogeneous alpha direction with no beta direction, S1 gives
alpha_C dot g<=0 throughout every cell and S2 gives nonnegative paired
flux. For its piecewise constant field B_C=sum_j alpha_Cj v_j,

$$
\mathbb E[-\alpha_C\mathbin{\cdot}g]
 =\mathbb E\delta B=-\sum_F I_F(B)\leq0.
\tag{P31}
$$

The integrand on the left is nonnegative. Hence it vanishes almost
everywhere; positive definiteness gives strictly positive Gaussian density
on each full-dimensional cell, so its linear form vanishes on that cell
and alpha_C=0. Thus the genuine alpha-only recession cone is trivial.
This fact is compatible with the nonzero P30 coefficients because their
face inequalities contain the original baseline source and beta corrections.
The fixed constants, coefficient basis, S1/S2 and target asset are unchanged.

### 11. Fixed-case proof-version boundary

The bounded Strict re-audit of section 9 is archived in
`research-local/proof_audits/two_sided_fixed_case_20261104T220632Z/proof_only_repair_v2/SYNTHESIS_v2.md`.
Its artifact is
`6461261b13f0f2cbd5d2c95fc8ed3e2e55362e98a0b1afe31fe06a048b52aaea`,
claim version 1, proof version 2. All nine binding file digests were
rechecked unchanged. Its result is `no-blocking-defect-found` within the
disclosed computational trust boundary. The original interval-exponential
issue IVEXP-1 is closed for this repaired proof version; its historical
baseline ledger remains preserved. The new proof-version closure does not
make the original uncorrected arithmetic implementation valid.

This audit concerns only u=10, mu=1, rho=1/2 and the complete 45-cell,
76-face system. It supplies no all-parameter feasibility result, researcher
approval, arbitrary-N proof or proof of the target asset. The additional
cold reconstruction in that archive is another certificate for the same
fixed model and has the same scope.

### 12. Central-strip corrections are essential near singular correlation

There is a further rigorous obstruction to extending a restricted basis,
even when the FULL positive S1 allowance is retained. Fix u=10, mu=1,
q=2Q(10), v=Q^{-1}(Q(10)/2), U=9, T=11, V=v-1 and W=v+1.
For all rho sufficiently close to 1, the reduced complete mixed N=2 LP
has no solution satisfying the additional restriction

$$
\widehat\alpha_C=0\quad\hbox{on every cell with }-u<g_1<u,
\qquad \widehat\alpha=S\alpha,\quad S=\phi(u).
\tag{P32}
$$

All beta variables, all other alpha variables, all original face rows and
all original budgets remain free as prescribed by the frozen certificate.
Thus P32 is an additional restriction, not an obstruction to the full LP.
In particular, this result does not supply its Farkas countercertificate.

Here is a proof without assuming that any coefficient has a finite limit
as rho tends to 1. Write, on each cell,

$$
p=\widehat\alpha_1+\rho\widehat\alpha_2,\qquad
r=\rho\widehat\alpha_1+\widehat\alpha_2,\qquad
\eta=S(D_u-1/2+c_u/4).
\tag{P33}
$$

The exact scaled S1 budget gives sup_C alpha_hat dot g<=eta since
0<=beta_C<=1/2. Follow the fixed negative-x interval I_0=(-infinity,-v).
Start in the y interval (-T,-V), and end in (W,infinity). Denote the
corresponding coefficients by (r_s,beta_s) and (r_e,beta_e).
The unbounded x interval imposes alpha_hat1>=0. If alpha_hat2<0 in the
start cell, its corner (-v,-T) gives
alpha_hat2>=-(v/T)alpha_hat1-eta/T. If alpha_hat2>=0, r_s>=0 directly.
Consequently, for rho>=v/T,

$$
r_s\geq-\eta/T.
\tag{P34}
$$

The end cell also has alpha_hat2<=0 by its unbounded positive y interval,
so r_e<=rho p_e. Let beta_0,beta_1,beta_2 be the beta values in that final
y interval on x in (-infinity,-v), (-v,-u), (-u,u), respectively.
Set P_u=S psi_u(-u)>0 and P_v=S psi_u(-v)>P_u. The strict last
inequality also has an elementary check independent of interval software.
P19 gives Q(10.06)/Q(10)>.54*.98>1/2: its exponential factor is
exp(-.6018)>.54 by the cubic Taylor lower bound, and its rational
factor is greater than .98. Together with P20 this gives
.06<v-u<.1. Thus P_u=1/4-c_uQ(u)<1/4, whereas P2 gives
P_v=exp((v^2-u^2)/2){Q(v-u)/2-c_uQ(v)}>.36. Here
Q(v-u)>.46, exp((v^2-u^2)/2)>1.6,
c_u<5, Q(v)<S/20<5*10^{-23}, and exp((v^2-u^2)/2)<3 suffice.
The x=-u and x=-v fluxes, with p_2=0 from P32, give respectively

$$
p_1\leq\tfrac12P_u(\beta_1-\beta_2),\qquad
p_e\leq p_1+\tfrac12P_v(\beta_0-\beta_1)
\leq\tfrac12P_v\beta_e.
\tag{P35}
$$

Thus r_e<=rho P_v beta_e/2. These are necessary consequences of actual
LP rows. In particular no sign or size has been imposed on the remaining
bounded-cell alpha directions.

The six y faces on this path are

$$
(a_1,\ldots,a_6)=(-V,-U,U,V,T,W),\qquad
(\Delta\lambda_1,\ldots,\Delta\lambda_6)
=(0,-1/2,1/2,0,1/2,0).
\tag{P36}
$$

The three dummy cuts are retained. For their exact normalized conditional
moments define

$$
D_a=-\mathbb E[Sd(X)\mid X<-v,Y=a]>0,\qquad
P_a=\mathbb E[S\psi_u(X)\mid X<-v,Y=a]>0,
\qquad d_*=Sd(v)=\frac{S}{4\phi(v)}.
$$

The y-face inequality P29 is exactly
Delta r>=(rho/2){Delta lambda D_a+P_a Delta beta}.
Introduce the nonnegative coefficient error

$$
\mathcal E_\rho=
\sum_{k=1}^6|\Delta\lambda_k|\,|D_{a_k}-d_*|
 +\frac12\sum_{k=1}^6|P_{a_k}-P_v|.
\tag{P37}
$$

Every beta increment lies in [-1/2,1/2]. Summing all six inequalities,
using sum Delta lambda=1/2 and P34--P35, therefore forces

$$
\frac{\rho P_v}2\beta_e
\geq-\frac\eta T+
\frac\rho2\left\{\frac{d_*}2+
 P_v(\beta_e-\beta_s)-\mathcal E_\rho\right\},
\qquad
d_*-P_v\leq\frac{4\eta}{\rho T}+2\mathcal E_\rho.
\tag{P38}
$$

The second inequality uses beta_s<=1/2. It is an exact necessary
finite-rho inequality, with no numerical quadrature or coefficient limit.

For completeness the conditional moments in P37 converge analytically,
including these extremely rare opposite-sign faces. Every a in P36 is
strictly greater than -v. Conditional on X<-v,Y=a, the variable
Z=-X=v+t, t>=0, has density proportional to

$$
\exp\{-L_a t-t^2/(2\sigma^2)\},\qquad
\sigma^2=1-\rho^2,\quad L_a=\frac{v+\rho a}{1-\rho^2}
\longrightarrow+\infty.
\tag{P39}
$$

Its tail satisfies P(t>b)<=exp(-L_a b): after shifting t by b, the
remaining integral has the extra factor exp(-bs/sigma^2)<=1. In
particular, when L_a>u,
E exp(ut)<=L_a/(L_a-u). Mills' upper bound gives
0<=Sd(z)<=S/(qv) on z>=v, and

$$
0<-S\psi_u(z)
\leq\frac{S e^{uz-u^2/2}}{2(z-u)}\leq C_u e^{u(z-v)}
\quad(z\geq v)
$$

for a fixed finite C_u. Continuity at v, the displayed exponential tail
bound, and its exponentially weighted version therefore prove
D_a->d_* and P_a->P_v. For example the contribution of t>b to
E exp(ut) is at most
exp(-(L_a-u)b){1+u/(L_a-u)}, which tends to zero for each b>0.
There are only six faces, so mathcal E_rho->0. This argument keeps
the conditional normalizer exact and does not evaluate a huge exponential
and a tiny normal probability separately.

Finally P2 and P13 give the strict gap

$$
d_*-P_v=\frac S{\phi(v)}
 \{1/4-Q(v-u)/2+c_uQ(v)\}>.009.
\tag{P40}
$$

Indeed the elementary bounds just proved give
.06<v-u<.1, phi(.1)>.3 and S/phi(v)>1; hence the first two terms
in braces equal one half of integral_0^{v-u}phi and exceed .009.
Meanwhile S<10^{-21}, D_10<192 and c_10<5 give eta<2*10^{-19}.
For rho>=v/T, 4eta/(rho T)<8*10^{-20}. Since mathcal E_rho->0,
P38 contradicts P40 for every rho sufficiently close to 1. This proves
the claimed restricted infeasibility at actual positive-definite models.
No explicit endpoint of that correlation interval is asserted.

P32 holds for the complete fixed-case table in section 9, so a change of
its scalar formulas alone, while keeping its central-strip alpha entries
zero, cannot extend that table to all correlations. A full construction
near rho=1 would have to use central-strip alpha corrections or leave that
restriction in another way. It remains possible in the frozen basis;
nothing above permits deleting these allowed directions from the full LP.

## Failure

Execution terminated on 2026-11-04 at the mandatory step-3 gate. The exact
obstruction to completing this proof plan is an unproved prerequisite:
feasibility of the frozen complete N=2 LP has not been established for all
u>=10, mu>0, -1<rho<1 and all labels. Neither has a full-LP negative
Farkas witness with rigorously bounded coefficients been obtained. Step 3
explicitly requires stopping when that gate fails or remains unresolved;
steps 4--6 have not been advanced. The earlier pending checkpoint notes
record historical partial executions; this terminal status supersedes them.

The completed scalar identities, exact finite primal/dual system, special
subfamilies, fixed-case proof-version-2 certificate, and the two proved
restrictions in sections 8 and 12 are preserved in Progress. In particular,
section 12 identifies why a family that keeps the central-strip alpha
entries zero cannot supply the missing singular-correlation coverage. It
does not prove infeasibility when those allowed entries are restored.

Reopening a related route would require a genuinely established all-parameter
N=2 construction, including correlated all-null models and all mixed-mean
and correlation regimes, or a rigorous full-system countercertificate.
No frozen constant, coefficient basis, S1/S2 constraint or target statement
was changed. The target asset is untouched. This failed proof plan is not
a falsification of the proposed certificate or of the Gaussian BH conjecture.
