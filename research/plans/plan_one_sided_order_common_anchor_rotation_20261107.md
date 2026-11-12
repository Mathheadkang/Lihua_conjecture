---
type: plan
schema_version: 2
title: Universal one-sided order through common-anchor rotation and integrated signed facet flux
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by:
  - idea_37ca6f19c953
adapts: []
tags:
  - current_phase
  - universal_order
  - one_sided
  - common_anchor_rotation
---

# Universal one-sided order through common-anchor rotation and integrated signed facet flux

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged finite-model statement with universal constants: for every sufficiently small q, every finite N, every mean vector and every unit-diagonal PSD covariance, including singular covariance, the original one-sided Gaussian BH FDR is at most C q sqrt(log(1/q)). Keep the original labels I0={i:theta_i<=0}, largest qualifying rank, multiplicities and non-strict comparisons. Every model parameter may depend on q. No rank, eigenvalue, dimension, null-proportion, direction or factor restriction and no sharp-constant claim is allowed.

The [common-anchor proposal](../ideas/idea_37ca6f19c953.md) is an unproved trial. It supplies a different endpoint and the actual squared-distance coefficients for a new integrated allocation attempt. Identities and N=2 calibration do not complete the theorem. Planning-time native library searches for Gaussian common-anchor/PRDS BH and marked rotation/signed boundary flux found no applicable result. No unapproved theorem is used as a black box. There is no Git repository at this cwd. Planning-time source hashes were 97888f5e92afc075751446bb4f07f37ffa0e5ac9b51c0574ac403b0233e49538 for the source idea and 7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305 for the unchanged target.

The online technique inspiration is Xianyang Zhang, Exact Simes inequalities for two-sided Gaussian tests, arXiv:2611.02513v1, Appendix F, Lemmas F.9--F.10 and the marked-crossing calculation F.30, https://arxiv.org/html/2611.02513v1 . Its all-null two-sided and bounded-degree/cluster hypotheses do not transfer here. Reconstruct Gaussian rotations, conditional marked moments and crossing calculus inline; this is source inspiration, not an adapted library node or an imported conclusion.

Save the first completed derivation into this plan immediately. Save each later checkpoint after a fresh source/target read and hash check, in patches of at most 6000 tokens. Preserve all other files and histories. Stop at the first essential unproved proposition, recording the exact integrated remainder and which allocation failed. Failure of an auxiliary gate is not a target counterexample.

## Plan

1. [x] **Prove the endpoint and establish the actual finite Gaussian path.** Write S=barPhi, u_k=S^{-1}(qk/N), U=u_N, and f(T)=V(T)/(R(T) vee 1) with original labels. Initially take a positive-definite correlation matrix C. For X~N(0,C) and independent Z0~N(0,1), set

   $$
   T_i(s)=\theta_i+\cos(s)X_i+\sin(s)Z_0,
   \qquad 0\le s\le\pi/4.
   $$

   Its covariance is C_s=cos^2(s) C+sin^2(s) J. Prove positive definiteness and unit diagonal along this path, the endpoint correlations (1+C_ij)/2>=0, and the actual coefficient

   $$
   d_{ij}=1-C_{ij}=\tfrac12\|v_i-v_j\|^2\ge0,
   \qquad \dot C_{s,ij}=2\sin(s)\cos(s)d_{ij}
   \quad(i\ne j).
   $$

   Reprove FDR(pi/4)<=q|I0|/N<=q for the actual endpoint law, with arbitrary positive alternative means and negative true-null means. A concrete route is the deterministic forced-zero identity with R_i^0, nonnegative Gaussian conditional shifts, the monotonicity of conditional forced-rank events, and the finite PRDS summation-by-parts proof. Show all conditional monotonicities and the superuniform marginal step explicitly; do not invoke PRDS as a slogan or replace negative null means by zero while preserving a supposedly unchanged FDP. Handle N=1 directly. Do not alter true labels at any point along the path.

2. [x] **Complete a new two-test calibration before any general allocation.** For N=2, theta=(0,mu), mu>0, put a=S^{-1}(q/2), b=S^{-1}(q), c=b-mu and rho_s=cos^2(s)rho+sin^2(s). Enumerate all ordinary BH rejection outcomes and prove

   $$
   F(s)=q/2-P_{\rho_s}(X\ge a,Y\ge c)
          +\tfrac12P_{\rho_s}(X\ge b,Y\ge c).
   $$

   Prove by differentiating the bivariate Gaussian density and integrating its mixed spatial derivative that the derivative of either joint upper tail with respect to correlation is phi_2 at its two thresholds. Thus, with t=sin^2(s),

   $$
   \frac{dF}{dt}=(1-\rho)
     \{-\phi_2(a,c;\rho_t)+\tfrac12\phi_2(b,c;\rho_t)\},
   \qquad \rho_t=(1-t)\rho+t.
   $$

   Prove the finite negative-variation budget rather than only checking the formula:

   $$
   \int_0^{1/2}\!\left(-\frac{dF}{dt}\right)_+dt
   \le\int_\rho^{(1+\rho)/2}\phi_2(a,c;r)\,dr
   \le P_{r=1}(X\ge a,Y\ge c)\le q/2.
   $$

   Justify the last comparison by the already proved nonnegative derivative and finite-model continuity, including singular rho=+-1 by limits. Extend the same calibration to theta_1<=0 by shifting a and b by -theta_1, obtaining the same q/2 bound. Record the all-null and all-alternative two-test cases separately if needed to check sign and normalization. These are calibration facts only.

3. [x] **Derive the full labelled finite facet table and exact signed path identity.** For i<j and thresholds u_k,u_l, hold all other coordinates fixed away from their grid hyperplanes. Define the exact mixed jump

   $$
   \Delta_{ij}^{kl}f=f_{++}-f_{+-}-f_{-+}+f_{--}
   $$

   at (T_i,T_j)=(u_k,u_l), where signs denote the two sides of those thresholds. Determine all four largest BH ranks, null counts and zero/nonzero masks from the actual background counts. Prove the resulting coefficient table, including both true/alternative labels, zero predecessor rank, every cascade, and alternative--alternative terms. Do not import a three-face identity without reconstructing its hypotheses and endpoint conventions. A valid computational check may enumerate small finite threshold cells, but the table needs a deterministic proof for all N.

   With p_{ij,s} the centered two-coordinate density under C_s, establish

   $$
   H_{ij}(s)=\sum_{k,l=1}^N
       p_{ij,s}(u_k-\theta_i,u_l-\theta_j)
       E_s[\Delta_{ij}^{kl}f\mid T_i=u_k,T_j=u_l],
   $$

   $$
   F'(s)=2\sin(s)\cos(s)\sum_{i<j}d_{ij}H_{ij}(s).
   \tag{CA-exact}
   $$

   Prove differentiation and integrability for this finite positive-definite model by the finite grid representation and Gaussian integration by parts, including trace double-counting factors. Preserve the sum with its signs and its actual d_ij. Cross-check it against Step 2.

4. [ ] **Attempt a specified rank-weighted marked allocation for the integrated flux.** Reconstruct the equivalent signed single-facet Rice expression along the same angular path, whose standardized coordinate velocity is -sin(s)X_i+cos(s)Z0 and is independent of its current standardized coordinate. At an active increasing-score crossing let the predecessor rank be b, predecessor FDP f_b=V_b/(b vee 1), and let a new original nulls and c new original alternatives enter, so r=b+a+c. Prove the exact cascade jump

   $$
   A=\frac{(1-f_b)a-f_b c}{r}.
   \tag{CA-cascade}
   $$

   For b=0 use f_b=0. Retain both terms before any bound. Verify that the difference of these single-facet jumps across an outside coordinate's threshold reproduces each mixed coefficient in Step 3. Thus every packet is marked by an actual newly rejected coordinate and carries exactly (1-f_b)/r for a null entry or -f_b/r for alternative dilution, with its actual predecessor and largest-rank mask.

   Apply the following concrete summation attempt. Expand each packet's selected-rank weight by the exact Abel identity

   $$
   \frac1r=\frac1N+\sum_{h=r}^{N-1}\frac1{h(h+1)}.
   $$

   First collect all packets with their actual masks R<=h under the same original path law, cancel entry and dilution boundaries between adjacent ranks and between adjacent threshold cells, and only then integrate in s and condition on the crossing coordinate. Do not replace a marked event by all marginal critical levels, change the outside law, or assume conditional residual independence. Keep the exact d_ij contraction when switching back to the double-facet expression. The purpose of this operation is to test whether the rank denominators and signed dilution provide a summable charge, rather than requiring a bound on unweighted marked neighbors.

   Reprove the conditional marked Gaussian moment used for the surviving packets. If a standardized outsider Y has correlation r_s with the crossing coordinate x and actual mean theta_l, set h=(v-theta_l-r_s x)/sqrt(1-r_s^2). Regression bounds the conditional absolute unit velocity on its upper-tail mark by B(h), where B(h)=phi(h)+sqrt(2/pi)S(h) for h>=0 and B(h)=sqrt(2/pi) for h<0. Treat zero conditional variance and singular regression directly. Prove the finite crossing/change-of-variable identity rather than assuming velocity independent of the mark. Explain why arbitrary positive means can force h=0 for arbitrarily many lawful outside coordinates, so an unweighted alternative-mark count cannot close the argument. The signed rank-weighted masks above, not the naked mark estimate, must pay that multiplicity.

   The **first mandatory unresolved aggregate gate** is a proof, using this actual finite signed allocation or a fully written improvement of it, of

   $$
   \mathcal V(C,\theta,q):=
   \int_0^{\pi/4}\!
    \left[-2\sin(s)\cos(s)\sum_{i<j}d_{ij}H_{ij}(s)\right]_+ds
   \le A q(1+U)
   \tag{CA-integrated}
   $$

   with one finite universal A on a universal small-q interval. Integrate the actual signed contraction before estimating; the positive part here is taken after the complete finite i,j,k,l sum. Do not demand a dimension-free pointwise derivative bound, and do not replace d_ij by an independent Gram supremum or by row-absolute sums. A narrow dimension-dependent transition layer need not violate this integrated gate.

   Save the explicit terminal/Abel/interface remainder produced by the attempted allocation. If it retains uncontrolled N, means, rank, graph degree, regularization or inverse-variance factors, or the allocation merely restates the unknown FDR, mark this plan failed at that first unproved inequality and record exactly why. If a stronger convenient local inequality is false, record its counterexample and continue only if the actual integrated allocation still has a concrete remaining step; otherwise record the corresponding gate failure. A counterexample to (CA-integrated) rejects this certificate, not the main theorem. Identities, the Rice bound and the N=2 result alone cannot be reported as a successful general estimate.

5. [ ] **Only after Step 4 succeeds, transfer the bound to the exact target.** Combine (CA-exact), F(pi/4)<=q and (CA-integrated) to obtain F(0)<=q+Aq(1+U) uniformly over finite positive-definite C and all theta. For any original singular Sigma, apply the proven estimate to C_epsilon=(Sigma+epsilon I)/(1+epsilon), without changing means or labels; all earlier constants must be independent of epsilon. Adding the common anchor alone can leave covariance singular, so Steps 1--4 use this positive-definite regularization rather than asserting that the unregularized path has densities. Couple its Gaussian vector to the original one and show almost-sure convergence away from the finitely many coordinate-threshold boundaries. Those boundaries have probability zero because every coordinate has variance one. Dominated convergence then transfers only the FDR values for each fixed finite model. Do not infer convergence of facet fluxes or of their integrated negative variation from FDR continuity; neither flux limit is needed. Only then take the full all-model supremum; do not interchange it with a nonuniform limit. Prove an elementary U<=C0 sqrt(log(1/q)) bound on a universal interval and extract finite universal target constants. Leave the target untouched unless the complete proof has passed fresh independent verification and the native process permits its proof update.

## Verification

Check all signs and factors against the exact two-test formula, verify the finite endpoint proof with negative null means, and reconstruct the arbitrary-N active facet masks independently. The novel object is the integrated actual distance-weighted signed contraction (CA-integrated); none of its individual faces, positive packets, marks or pointwise derivatives is silently substituted for it. Successful Steps 1--4 yield q+Aq(1+U); Step 5 then yields precisely the target's all-finite-model order upper bound, including singular covariance and arbitrary q-dependent parameters. Failure at Step 4 leaves only calibrated finite identities and the exact unresolved remainder. Any prospective full proof needs a fresh independent review of every essential inequality and the limit, not just the algebra or a numerical probe.

## Assumed definitions

Use the approved definitions gaussian_multiple_testing_model, gaussian_test_pvalues, benjamini_hochberg_step_up, false_discovery_rate and gaussian_worst_case_bh_fdr already listed by the target. No draft definition, unproved dependency or external theorem is assumed. The source idea, marked-moment proposal, all earlier partial identities and the online technique are research guidance only and are reproved wherever used. Gaussian density differentiation, conditioning, finite Rice calculus, finite PRDS summation and the continuity transfer are explicit obligations of this plan.

## Difference from failed plans

- **plan_252211621cea:** The signed-label half-line occupation route ended with a scalar endpoint equal to weighted unknown FDR. This trial changes covariance toward a proved nonnegative-correlation endpoint and charges only the integrated negative covariance flux. It must not close its budget by identifying a residual with unknown FDR.
- **plan_503f8fddcbb5:** The common-shift entrant allocation left signed record faces minus favorable bulk uncontrolled. This path rotates standardized Gaussian coordinates toward an independent common anchor while preserving marginal variances and original means. Its exact coefficients are d_ij and its target is the integrated path derivative, rather than total common-shift positive variation.
- **plan_ee2f7b97740a:** The compatible Hall-cut transport left a non-potential circulation and inverse-noise losses. The present trial uses an explicit covariance path and finite Gaussian face densities, with no Hall-cut maximum, rejection-set potential assumption or free inverse-covariance score estimate. Its new allocation may still fail and must expose that failure.
- **plan_one_sided_order_actual_mean_global_flux_20261106:** That plan's marginal-critical-level envelope counted inactive cascade levels and admitted an N-squared obstruction. Here every four-cell mixed jump and every Rice packet keeps its actual predecessor and largest-rank mask; the exact alternative-dilution term remains in the Abel sum. Dropping those masks would repeat the old failure.
- **plan_one_sided_order_gaussian_interpolation_sdp_20261106:** The old independence-to-Sigma interpolation sought a diagonal completion for a signed matrix with coefficient Sigma_ij. This path ends at nonnegative correlations halfway to J and keeps the actual nonnegative squared distances 1-C_ij. It seeks an integrated scalar contraction, without diagonal completion or a pointwise universal derivative envelope.
- **plan_one_sided_order_negative_contact_transport_20261106:** The negative-contact allocation encountered inverse-noise and weighted negative-degree terms after diagonal splitting and cellwise integration by parts. The angular common-anchor path has standardized unit coordinate velocities, finite total angle and actual full covariance-distance coefficients. No row-degree or conditional-variance bound is assumed to remove multiplicity; it must be resolved in the signed integrated rank allocation.
- **plan_one_sided_order_three_face_noise_packing_20261106:** That integrated Gram-energy budget was obstructed because an independent maximization against Q removed a true small covariance coefficient. This plan never maximizes against a new covariance: it retains exactly d_ij at every face and integrates the entire signed scalar sum before its positive part. The independent-equicorrelation transition-layer diagnostic is a reason to avoid a pointwise shortcut, not evidence that the new gate already holds.

## Progress

Execution checkpoint 2026-11-07. The workspace root is not a Git repository (checked). At entry the plan SHA-256 was `5b1726e0037522688f9d11fc06e5815f75f2ef97570da6d188723a846914dd47`; the untouched target SHA-256 is `7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305`. All assertions below are derivations in this execution, not approved results. The online source is inspiration only; no conclusion from it is assumed.

### Step 1: path and endpoint, including negative original null means

Fix finite N, q in (0,1), original labels I0={i:theta_i<=0}, and positive-definite correlation C. Write S=barPhi, phi for its density, t_r=qr/N, u_r=S^{-1}(t_r), and U=u_N. The path in the plan has covariance C_s=cos^2(s)C+sin^2(s)J. For nonzero z,
$$
z^{\mathsf T}C_sz\ge\tfrac12\lambda_{\min}(C)\|z\|^2>0.
$$
Its diagonal is one. A Gram representation C_ij=<v_i,v_j> with unit v_i gives d_ij=1-C_ij=||v_i-v_j||^2/2>=0; differentiation gives dot C_s,ij=2 sin(s)cos(s)d_ij for i!=j and zero on the diagonal. At s=pi/4 every correlation is (1+C_ij)/2>=0. Means and labels never change.

Here is a complete finite endpoint argument, valid for every positive-definite correlation D with D_ij>=0, and all original means. A deterministic BH vector has exactly its largest qualifying rank many rejections: if its rank is r and more than r p-values are <=t_r, the next rank also qualifies, a contradiction. Force p_i to zero and let R_i^0 be the resulting largest rank (always >=1). Lowering a p-value cannot decrease BH rank. Moreover
$$
\{i\in\mathcal R,\ R=r\}
=\{p_i\le t_r,\ R_i^0=r\}. \tag{P1}
$$
For the forward implication, at every h>r, the rejected i already contributes one to the original count at t_h; forcing it to zero changes none of these counts and cannot create a new h. For the reverse implication, the count at t_r in the original vector equals the forced count, so its rank is at least r and at most the forced rank r. This also proves (P1) with multiplicities and non-strict comparisons.

Condition on the centered i-coordinate X_i=x. Gaussian regression gives the other coordinates as theta_j+D_ji x+W_j, with one residual Gaussian vector W independent of x. Since D_ji>=0, this is coordinatewise increasing in x under the same W. Hence R_i^0 is nondecreasing in x, and P(R_i^0<=r | X_i=x) is nonincreasing. Conditioning on p_i<=t is conditioning X_i>=S^{-1}(t)-theta_i. As t increases this truncated scalar law decreases stochastically: for a nonincreasing g its upper-tail average increases (split the larger tail into the old tail and the added lower interval). Consequently
$$
G_r(t):=P(R_i^0\le r\mid p_i\le t)
\quad\hbox{is nondecreasing in }t.
$$
No residual independence among outsiders is used. For an original null i, H_i(t):=P(p_i<=t)=S(S^{-1}(t)-theta_i)<=t since theta_i<=0. All conditioning events have positive probability. Thus its exact FDR contribution satisfies
$$
\begin{aligned}
E\frac{1_{\{i\in\mathcal R\}}}{R\vee1}
&=\sum_{r=1}^N\frac{H_i(t_r)}r\{G_r(t_r)-G_{r-1}(t_r)\}\\
&\le\frac qN\sum_{r=1}^N\{G_r(t_r)-G_{r-1}(t_r)\}
\le\frac qN.
\end{aligned} \tag{P2}
$$
Here G_0=0, G_N=1, each bracket is nonnegative, and the last sum equals 1+sum_{r=1}^{N-1}[G_r(t_r)-G_r(t_{r+1})]<=1. Sum (P2) over the unchanged I0 to obtain F(pi/4)<=q|I0|/N<=q. Negative null means were used through their actual H_i and conditional thresholds. Alternatives' means were unrestricted. For N=1, FDR is S(U-theta_1)<=q if theta_1<=0 and zero otherwise, directly.

### Step 2: exact two-test formula and integrated variation

Take N=2 with exactly one null, first theta_1=0, theta_2=mu>0; a=S^{-1}(q/2), b=S^{-1}(q), c=b-mu. There are two rejections exactly when T_1>=b and T_2>=b; their FDP is 1/2. The only other event with nonzero FDP is the sole null rejection, T_1>=a and T_2<b; its FDP is one. The sole alternative rejection and no rejection have FDP zero. For the standardized pair (X,Y), put Q_r(v,w)=P_r(X>=v,Y>=w). Therefore
$$
F(s)=q/2-Q_{\rho_s}(a,c)+\tfrac12Q_{\rho_s}(b,c). \tag{P3}
$$
For |r|<1, the bivariate density p_r satisfies
$$
\partial_r p_r=\partial_x\partial_y p_r.
$$
Indeed both sides divided by p_r equal r/(1-r^2)+[(x-ry)(y-rx)]/(1-r^2)^2. On every compact correlation interval inside (-1,1), derivatives are bounded by a fixed polynomial times an integrable Gaussian envelope. Differentiation under the integral and two integrations by parts yield
$$
\partial_r Q_r(v,w)=p_r(v,w)=\phi_2(v,w;r)\ge0. \tag{P4}
$$
The boundary terms at infinity vanish by Gaussian decay. With t=sin^2(s), rho_t=(1-t)rho+t, (P3) gives
$$
\frac{dF}{dt}=(1-\rho)\{-\phi_2(a,c;\rho_t)+\tfrac12\phi_2(b,c;\rho_t)\}.
$$
Since 1-rho>=0, its negative variation obeys
$$
\begin{aligned}
\int_0^{1/2}(-F_t')_+\,dt
&\le\int_\rho^{(1+\rho)/2}\phi_2(a,c;r)\,dr\\
&=Q_{(1+\rho)/2}(a,c)-Q_\rho(a,c)
\le Q_1(a,c)\le S(a)=q/2. \tag{P5}
\end{aligned}
$$
The last comparison follows from (P4) and continuity. In detail, couple Y_r=rX+sqrt(1-r^2)Z with independent standard X,Z. At r->+1 or -1, both threshold indicators converge almost surely except where X equals one of finitely many constants, a probability-zero event. Dominated convergence proves Q continuity up to the endpoints; Q_1(a,c)=S(max(a,c)). For rho=-1, (P5) is the improper integral on (-1,0] and monotone convergence of the nonnegative density integral applies; absolute continuity and the variation bound extend to the closed endpoint because the derivative's absolute value is bounded by the sum of two integrable tail derivatives. For rho=1 the path is constant. No facet-density assertion at a singular endpoint is needed.

For theta_1<=0 replace a,b in its standardized coordinate by A=a-theta_1 and B=b-theta_1. The first term in (P3) becomes S(A), and (P5) is bounded by S(A)<=q/2. This keeps the original label and mean. If both coordinates are null, write A_i=a-theta_i, B_i=b-theta_i. Directly enumerating the union of the two rank-one events and the rank-two event gives
$$
F=S(A_1)+S(A_2)+Q_r(B_1,B_2)-Q_r(A_1,B_2)-Q_r(B_1,A_2).
$$
Its negative variation is at most S(A_1)+S(A_2)<=q by (P4), since the positive Q_r(B_1,B_2) derivative can be retained favorably. If neither coordinate is null then F=0 identically. These calculations calibrate finite factors and signs; they prove no general-N budget.

### Step 3: deterministic complete double-facet table and distance contraction

Fix i<j and a background vector off every grid hyperplane. Let eta_l=1_{l in I0}. For h=1,...,N define
$$
n_h=\#\{\ell\ne i,j:T_\ell>u_h\},\qquad
m_h=\#\{\ell\ne i,j:T_\ell>u_h,\ \ell\in I0\}.
$$
Set n_0=m_0=0. At the facet T_i=u_k,T_j=u_l, let alpha,beta in {0,1} denote scores just below/above their respective thresholds. Use sufficiently small displacements so no other grid plane is crossed. The exact counts are
$$
\begin{aligned}
B_h&=n_h+1_{h>k}+1_{h>l},\\
R_{\alpha\beta}&=\max\bigl(\{0\}\cup\{h:B_h+\alpha1_{h=k}+\beta1_{h=l}\ge h\}\bigr),\\
V_{\alpha\beta}&=m_{R_{\alpha\beta}}+
\eta_i[1_{R_{\alpha\beta}>k}+\alpha1_{R_{\alpha\beta}=k}]
+\eta_j[1_{R_{\alpha\beta}>l}+\beta1_{R_{\alpha\beta}=l}],\\
f_{\alpha\beta}&=V_{\alpha\beta}/(R_{\alpha\beta}\vee1).
\end{aligned} \tag{P6}
$$
In the V formula take V=0 if R=0. Let b=R_00. Formula (P6) determines every rank, true-null count and zero-rank convention without a hypothesis about cascade size.

Here is its simplified complete table. The following are the only possibly nonzero mixed coefficients; every other cell has Delta_ij^{kl}f=0. In active rows below write f_b=m_b/(b vee 1), so f_0=0.

| Threshold indices | Exact active mask | Four ranks (00,10,01,11) | Mixed coefficient |
| --- | --- | --- | --- |
| k<l | b<k, n_k=k-1, n_l=l-2 | (b,k,l,l) | f_b-(m_k+eta_i)/k |
| l<k | b<l, n_l=l-1, n_k=k-2 | (b,k,l,k) | f_b-(m_l+eta_j)/l |
| k=l=r | b<r, n_r=r-2 | (b,b,b,r) | (m_r+eta_i+eta_j)/r-f_b |

For the first row the four null counts are (m_b,m_k+eta_i,m_l+eta_i+eta_j,m_l+eta_i+eta_j). For the second row they are (m_b,m_k+eta_i+eta_j,m_l+eta_j,m_k+eta_i+eta_j). For the third they are (m_b,m_b,m_b,m_r+eta_i+eta_j). Thus the table covers zero predecessor rank, all cascades, original null/null, null/alternative, alternative/null, and alternative/alternative labels. In particular alternative/alternative coefficients are not set to zero: background null counts can give nonzero changes.

Proof of completeness: a single flag at a distinct threshold changes qualification only at its own rank. Its change can affect the maximum only if that rank exceeds b and its unflagged count is exactly one short. If k<l, the only new rank created by alpha is k with n_k=k-1; the only new rank created by beta is l with n_l+1=l-1. If both are effective and b<k, (P6) gives the first row. If only one is effective, or b lies between k and l, the smaller-index flag cannot change the outcome across both beta states and the mixed difference is zero. If both flags are ineffective, it is also zero. No hidden null-count change remains when the rank is fixed: the rejection set at a fixed largest rank has exactly that many members, so a threshold flip at that same rank cannot add a member while keeping the largest rank fixed. Equivalently if a baseline rank equals k or l, its just-below crossing coordinate implies the next larger rank already qualifies, a contradiction; at N the background count is too small. For k=l=r, the only possible nontrivial new qualification needs n_r=r-2 and both flags. The tempting n_r=r-1 case with b<r is impossible: if r<N, the n_r background coordinates and both near-u_r coordinates all exceed u_{r+1}, so r+1 already qualifies in the 00 cell; for r=N there are at most N-2 background coordinates. The remaining n_r cases either never qualify r or were already qualified. This proves all rows and zero cases for every finite N; no three-face identity is assumed.

A finite exact-arithmetic diagnostic independently enumerated N=2,...,5, all coordinate pairs, every background threshold cell, every original null/alternative label pattern and every (k,l). There were 1,767,280 comparisons (164,401 nonzero mixed jumps); every direct four-cell Fraction calculation agreed with this table. This is an algebra/sign check in addition to the preceding proof, not evidence for the later analytic bound.

For positive-definite C_s, let p_s be the full centered Gaussian density. Its covariance derivative follows, for example, by differentiating its Fourier transform exp(-xi^T C_s xi/2):
$$
\partial_s p_s=\tfrac12\sum_{a,b}\dot C_{s,ab}\partial_a\partial_b p_s
=\sum_{i<j}\dot C_{s,ij}\partial_i\partial_j p_s. \tag{P7}
$$
The last equality uses the zero diagonal derivative and both ordered off-diagonal terms, so there is no remaining factor 1/2. The function f(theta+x) is constant on a finite grid of rectangles. Its distributional mixed derivative is exactly the finite sum of delta masses on x_i=u_k-theta_i,x_j=u_l-theta_j, weighted by the four-cell jumps (P6). Integrating (P7) against f and integrating by parts twice yields
$$
\begin{aligned}
H_{ij}(s)&=\sum_{k,l=1}^N p_{ij,s}(u_k-\theta_i,u_l-\theta_j)
 E_s[\Delta_{ij}^{kl}f\mid T_i=u_k,T_j=u_l],\\
F'(s)&=2\sin(s)\cos(s)\sum_{i<j}(1-C_{ij})H_{ij}(s). \tag{P8}
\end{aligned}
$$
One can avoid any appeal to distribution theory by integrating the density over each finite grid rectangle and summing its four boundary terms; the same coefficient is obtained. In this fixed finite model the eigenvalues of C_s are bounded below by lambda_min(C)/2 and above by N, uniformly over the compact path. Density derivatives have integrable Gaussian-polynomial envelopes, uniformly in s; differentiation under the integrals is valid. The finitely many two-coordinate conditional densities and face integrals are finite and continuous in s. Thus F is continuously differentiable and (P8) is integrable on the entire path, with constants allowed to depend on this fixed model. This is not yet a uniform estimate.

More explicitly, the actual signed distance flux in (P8) is the sum of the diagonal row's p_{ij,s}(u_r-theta_i,u_r-theta_j) times [(m_r+eta_i+eta_j)/r-f_b], and the two off-diagonal rows' densities times the negative of the corresponding selected-minus-predecessor FDP, all with exactly the masks in the table, conditional expectations under C_s, and coefficient d_ij=1-C_ij. No maximum over a separate Gram matrix or absolute row sum has appeared. At N=2 the only mixed coefficients are Delta^{12}=-eta_i, Delta^{21}=-eta_j and Delta^{22}=(eta_i+eta_j)/2. For eta_i=1,eta_j=0 this gives H=-phi_2(a,c;rho_s)+(1/2)phi_2(b,c;rho_s), exactly (P3)--(P5), also with shifted actual means.

### Step 4a: actual single-facet packets and finite marked crossing calculus

Write W_i(s)=cos(s)X_i+sin(s)Z0 and L_i(s)=-sin(s)X_i+cos(s)Z0 for standardized score and angular velocity. Both have variance one and covariance zero, so they are independent at each fixed s. An increasing-score crossing at T_i=u_k changes qualification only at rank k. If active, its before/after ranks are b<k and k, respectively; its actual rejection sets are nested. Let a be the number of new original nulls and c the number of new original alternatives, so k=b+a+c. Put f_b=V_b/(b vee 1), f_0=0. Then, retaining both signs,
$$
A_i^k=f_+-f_-=
\frac{V_b+a}{k}-f_b
=\frac{(1-f_b)a-f_b c}{k}
=\frac1k\sum_{\ell\in E_i^k}(\eta_\ell-f_b), \tag{P9}
$$
where E_i^k is exactly the newly rejected set, including the trigger i. Off the active mask A_i^k=0. Thus this packet never counts an inactive threshold or an arbitrary outsider. For k<l in the table, crossing i at u_k has jump f_k-f_b when j is below u_l, and zero when j is above (both ranks then l). Its difference is f_b-f_k. At a diagonal active facet, i has zero jump with j below and jump f_r-f_b with j above. The symmetric argument covers l<k. All other masks cancel as in (P6). This explicitly reproduces every mixed coefficient from the single-facet jumps.

For completeness the pathwise crossing formula is finite here. Each W_i(s)-x is a nonconstant sinusoid minus a constant and has finitely many roots (at most two on this interval), almost surely. A tangent root would force sqrt(X_i^2+Z0^2)=|x|, a probability-zero event because (X_i,Z0) has a density. Conditional on X_i,Z0, the finitely many roots of coordinate i are fixed; positive definiteness makes the conditional law of X_j nondegenerate, so a second coordinate lies at any specified grid threshold at those times with probability zero. Thus there are no simultaneous crossings. The original non-strict convention matters only at the finitely many crossing times; the oriented before/after jumps are exactly (P9).

On each monotone neighborhood of a simple root, the elementary change of variables y=W_i(s) gives the one-dimensional crossing formula. Apply it with a narrow density approximation to delta_x and a bounded mark; partition into the finitely many monotone intervals. The number of roots is deterministically bounded by 2N^2, making passage to expectations and the limiting crossing count integrable. The marks used here are the finite-grid surface traces, bounded functions of the other coordinates and of the nonzero velocity; they are locally constant or continuous at almost every crossing because simultaneous crossings and tangencies have probability zero. Their conditional Gaussian expectations have the corresponding continuous surface versions, so conditioning and the shrinking-tube limit are legitimate at the specified x. This gives, for a time interval B and each such crossing mark G,
$$
E\!\sum_{\substack{s\in B:W_i(s)=x}}G(s)
=\int_B\phi(x)E[|L_i(s)|G(s)\mid W_i(s)=x]\,ds. \tag{P10}
$$
For signed oriented jumps use G=sign(L_i)A_i^k, obtaining
$$
F'(s)=\sum_{i=1}^N\sum_{k=1}^N
\phi(u_k-\theta_i)E[L_i(s)A_i^k\mid W_i(s)=u_k-\theta_i]. \tag{P11}
$$
This first holds almost everywhere from (P10); the continuous finite Gaussian boundary integrals agree with (P8), so it is the same integrable signed derivative. In particular independence of L_i from W_i does not assert independence from the active mask or mark.

Here is the promised marked estimate, derived rather than imported from the online source. If a standardized outsider W_l has correlation r_s with W_i=x, let sigma=sqrt(1-r_s^2) and G=(W_l-r_s x)/sigma when sigma>0. Conditionally on W_i=x, (L_i,G) is a jointly centered standard normal pair, possibly singular. Write L_i=alpha G+sqrt(1-alpha^2)H with independent standard H; alpha=+-1 is interpreted directly. For a one-sided mark T_l>=v, set h=(v-theta_l-r_s x)/sigma. If h>=0, regression and the triangle inequality give
$$
\begin{aligned}
E[|L_i|1_{T_l\ge v}\mid W_i=x]
&\le |\alpha|\!\int_h^\infty z\phi(z)\,dz
+\sqrt{1-\alpha^2}\sqrt{2/\pi}\,S(h)\\
&\le\phi(h)+\sqrt{2/\pi}\,S(h)=B(h).
\end{aligned} \tag{P12}
$$
For h<0 simply bound by E|L_i|=sqrt(2/pi), defining B(h) accordingly. If sigma=0 then W_l=r_s x conditionally and the exact expectation is sqrt(2/pi) times the deterministic mark indicator; no inverse-variance factor is introduced. Singular conditional regression with |alpha|=1 also obeys the same calculation. Along this path Cov(L_i,W_l)=sin(s)cos(s)d_il, so these moments keep the actual distance coefficients and do not change the outside law.

The naked neighbor estimate cannot pay arbitrary alternative multiplicity. For example, take C=I, fix s0 in (0,pi/4), choose x=u_k>0 and v=x, and set every outside alternative mean theta_l=(1-sin^2(s0))x>0. At the null crossing W_i=x, each outsider has r_s0=sin^2(s0), hence h=0. There can be arbitrarily many such lawful alternatives. Central symmetry of the conditional pair (L_i,G) gives E[|L_i|1_{G>=0}]=sqrt(2/pi)/2 for every outsider, even when L_i and G are dependent. Therefore the sum of these unweighted marked moments grows exactly linearly in their number. This does not refute the signed rank-weighted gate, whose actual masks and denominators must still resolve that multiplicity.

### Step 4b: concrete Abel allocation, complete interfaces, and its terminal remainder

The following calculation performs the proposed signed collation before estimating or conditioning marks. Let I_i^k be the exact active single-facet mask, b its predecessor rank, and use (P9) throughout. For h=1,...,N define the truncated unweighted packet flux
$$
J_h(s)=\sum_i\sum_{k\le h}\phi(u_k-\theta_i)
 E\!\left[L_i I_i^k\{a-f_b(k-b)\}\mid W_i=u_k-\theta_i\right]. \tag{P13}
$$
The exact finite Abel identity gives
$$
F'(s)=\frac{J_N(s)}N+\sum_{h=1}^{N-1}\frac{J_h(s)}{h(h+1)}. \tag{P14}
$$
Every k here is the actual upper selected rank; the cutoff k<=h is the requested actual R<=h mask. All packets are under the same original angular path law. Equations (P8) and (P11) show that (P14) is exactly the original d_ij-contracted flux, not an unrelated bound.

To expose all rank/cell interface cancellations rather than merely renaming J_h, define two genuine finite-grid potentials
$$
M_h(T)=V(T)1_{1\le R(T)\le h},\qquad
Q_h(T)=R(T)1_{1\le R(T)\le h}.
$$
At an oriented active crossing b->k, their jumps are
$$
\begin{array}{c|ccc}
 & k\le h & b\le h<k & h<b\\ \hline
\Delta M_h & a & -V_b & 0\\
\Delta Q_h & k-b & -b & 0.
\end{array} \tag{P15}
$$
Thus the exact entry/dilution combination satisfies, including b=0,
$$
1_{k\le h}k\Delta f=\Delta M_h-f_b\Delta Q_h. \tag{P16}
$$
The interface row cancels because V_b=b f_b, without replacing or dropping either signed boundary. Define the explicit remaining predecessor/interface flux
$$
\begin{aligned}
K_h(s)={}&\sum_i\sum_{k\le h}\phi(u_k-\theta_i)
 E[L_i I_i^k f_b(k-b)\mid W_i=u_k-\theta_i]\\
&-\sum_i\sum_{k>h}\phi(u_k-\theta_i)
 E[L_i I_i^k V_b1_{b\le h}\mid W_i=u_k-\theta_i].
\end{aligned} \tag{P17}
$$
The second line is the full cutoff-crossing interface; it is absent only for h=N. Finite Rice calculus applied to M_h, using (P15), proves
$$
J_h(s)=\frac d{ds}E M_h(T(s))-K_h(s). \tag{P18}
$$
This establishes the terminal, Abel and interface remainders explicitly, with arbitrary means, all cascades and both packet labels retained.

The final weighted cancellation is exact but circular. Set w_N=1/N and w_h=1/[h(h+1)] for h<N. For every finite state,
$$
\sum_{h=1}^N w_h M_h(T)=f(T),\qquad
\sum_{h=1}^N w_h Q_h(T)=1_{R(T)>0}. \tag{P19}
$$
Indeed the coefficient of V, or of R, in a state of positive rank r is 1/N+sum_{h=r}^{N-1}1/[h(h+1)]=1/r. Across any crossing with b>0, the second potential has zero jump; if b=0 its jump is one but f_b=0. Consequently the full signed weighted sum of (P17) cancels pointwise at every crossing:
$$
\sum_{h=1}^N w_h K_h(s)=0. \tag{P20}
$$
Substituting (P18)--(P20) into (P14) returns F'(s)=d E f(T(s))/ds. On the full interval, the exact terminal formula is
$$
\sum_{h=1}^N w_h\!\int_0^{\pi/4}\!J_h(s)\,ds
=F(\pi/4)-F(0), \tag{P21}
$$
and the unbounded initial term is the original unknown FDR, not an explicit small endpoint. Keeping only individual K_h pieces would destroy the cancellation in (P20). Applying the marked absolute moment bound before that cancellation instead leaves the actual unsigned packet functional
$$
\mathcal B=\int_0^{\pi/4}\!\sum_{i,k}\phi(u_k-\theta_i)
 E\!\left[|L_i|I_i^k\frac{(1-f_b)a+f_b c}{k}\mid W_i=u_k-\theta_i\right]ds, \tag{P22}
$$
for which this execution has no dimension-free small-q estimate. No claim that B is bounded or that it must be unbounded is made. In particular (P12) cannot remove the multiplicity in (P22) by itself. Replacing its masks by all critical levels would repeat the known invalid allocation and is not used.

## Failure

The first unresolved necessary step is **Step 4, (CA-integrated)**. Steps 1--3 and the finite identities (P9)--(P21) are established above. After the specified actual-mask Abel collation, the exact remaining quantity needing an external estimate is
$$
\int_0^{\pi/4}\!
\left[-\frac{J_N(s)}N-\sum_{h=1}^{N-1}\frac{J_h(s)}{h(h+1)}\right]_+ds
=\int_0^{\pi/4}[-F'(s)]_+ds. \tag{P23}
$$
By (P8), this is exactly the actual integrated signed d_ij-contracted flux in the plan. The terminal/interface calculation (P15)--(P21) cancels completely back to the unknown FDP/FDR; it supplies no independent bound of order q(1+U). Bounding only positive entry packets or naked outsider marks would lose signed dilution and multiplicity, and neither is a substitute for (P23). A further substantive inequality controlling (P23), or an independent bound on a valid stronger functional such as (P22), is required. It has not been proved. This is failure of the specified certificate/allocation, not a counterexample to (CA-integrated) or to the universal one-sided target.

Step 5 is not executed because its premise has failed. In particular no regularized facet-variation limit or uniform PSD passage is asserted. The target statement and its Proof region have not been edited; all original finite-model, arbitrary-mean, arbitrary-PSD, q-dependent quantifiers remain unchanged. Parent loop owner alone reports this failure and manages native state.
