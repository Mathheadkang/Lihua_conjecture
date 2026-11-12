---
type: plan
title: Universal one-sided order through three-face contact and noise-scale packing
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by:
  - idea_ec681eb191fb
  - idea_08af2260a0c7
  - idea_4a84c3f3903c
  - idea_569be86e386c
  - idea_b4f2e9366ee9
adapts:
  - gaussian_conditional_tail_density_replica_bound
---

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the statement without changing any quantifier: finite universal constants and a universal small-q interval, all finite N, all means, all unit-diagonal PSD covariances including singular ones, and the actual true-null set I_0={i:theta_i<=0}. Ordinary BH always uses the largest qualifying rank and non-strict inequalities. Dimension, means, covariance, rank, null proportion and every other model parameter may vary with q. No sharp constant is sought.

The new information is the exact reduction to three active leave-two-out faces and the maximal-rank constraints on the intervening background counts. A scoped read-only audit is recorded in [Fresh scoped audit of the exact three-face rank identity](../ideas/idea_08af2260a0c7.md); the identity must nevertheless be proved in full during execution. Neither that audit nor the approved deterministic-level scalar lemma proves the matrix estimate below. The primary unproved gate is an integrated contact/Gram-energy budget, allowing its mass to concentrate in thin noise or rank layers. The previously proposed pointwise noise-log bound remains an optional sufficient attempt. Failure of that stronger attempt alone does not fail this plan; the first mandatory failure is inability to establish the integrated budget by the concrete packing mechanism below. Such failure is not a counterexample to the target.

Planning-time library searches for Gaussian BH interpolation, conditional tail-density replicas, maximal-rank empty gaps and PSD weighted packing returned no analogue. The canonical scalar proof named in `adapts` was read; it is adapted and rederived here rather than added silently as a new black-box dependency of the target.

## Plan

1. [x] **Fix the original means and reconstruct the interpolation.** Work first with N>=2 and 0<q<=S(1), where S=barPhi, U=S^{-1}(q)>=1, t_k=qk/N and u_k=S^{-1}(t_k). Set alpha_i=1{i in I_0}, and let f be the actual FDP, valued in [0,1]. For eta>0 and a in [0,1], use independent X~N(0,Sigma), epsilon~N(0,I_N) and
   $$
   \nu=\nu_{a,\eta}=\frac{1-a+\eta^2}{1+\eta^2},\qquad
   T=\theta+\sqrt{1-\nu}\,X+\sqrt\nu\,\varepsilon,
   \qquad \mathcal F_\eta(a)=\mathbb E f(T).
   $$
   The diagonal covariance stays one, the original labels stay fixed, and all residual coordinates are independent conditional on X. Prove the independent starting inequality F_eta(0)<=q|I_0|/N by the force-zero BH argument and marginal superuniformity for theta_i<=0. Do not assert equality for negative null means. Treat N=1 and I_0 empty separately. Reprove the finite-grid Gaussian differentiation formula by differentiating the positive-definite density and integrating on its cells; no external Price identity is assumed.

2. [x] **Reproduce the complete three-face identity, with ties and c=0.** Fix all p-values except i,j and define c=R(1,1), s=R(0,1)=R(1,0), r=R(0,0). Prove preservation of the maximal rank when a selected coordinate is replaced by zero or an unselected coordinate by one; use it to prove r>=s+1>=c+2 and the exact partition: rank r when both p_i,p_j<=t_r; rank s when p_i<=t_s,p_j>t_r or vice versa; rank c otherwise. Do not infer equality of the two forced ranks from any symmetry of the null labels.

   Let v_k be the number of background true nulls at p<=t_k, with v_0=0. Put
   $$
   F_c=\frac{v_c}{c\vee1},\quad
   F_s^i=\frac{v_s+\alpha_i}{s},\quad
   F_s^j=\frac{v_s+\alpha_j}{s},\quad
   F_r=\frac{v_r+\alpha_i+\alpha_j}{r}.
   $$
   Prove the FDP partition itself and then, in statistic coordinates, its distributional mixed derivative
   $$
   \partial_i\partial_j f
   =(F_r-F_c)\delta_{(u_r,u_r)}
   -(F_s^i-F_c)\delta_{(u_s,u_r)}
   -(F_s^j-F_c)\delta_{(u_r,u_s)}.
   $$
   Check all orientations, p endpoints, repeated background p-values, adjacent ranks, c=0, N=2, and null/alternative labels. Include the proof in Progress; a reference to the exploratory idea is insufficient.

   For deterministic w define
   $$
   d_i(w\mid X)=\nu^{-1/2}\phi\left(\frac{w-\theta_i-\sqrt{1-\nu}X_i}{\sqrt\nu}\right).
   $$
   Integrate first over the background residuals and X to obtain the deterministic symmetric matrix with diagonal zero and
   $$
   \begin{aligned}
   K_{ij}=\mathbb E\big[&(F_r-F_c)d_i(u_r\mid X)d_j(u_r\mid X)\\
   &-(F_s^i-F_c)d_i(u_s\mid X)d_j(u_r\mid X)\\
   &-(F_s^j-F_c)d_i(u_r\mid X)d_j(u_s\mid X)\big],\qquad H_{ij}=K_{ij}/2.
   \end{aligned}
   $$
   All ranks and v's inside this expectation are functions of the same original background observations. Establish
   $$
   \mathcal F_\eta'(a)=\frac{\langle\Sigma,H\rangle}{1+\eta^2}.
   $$
   For a deterministic symmetric H define beta(H)=max{<H,Q>: Q>=0, Q_ii=1}. Prove the finite dual diagonal-completion identity if used. Crucially beta is applied after the full Gaussian expectation defining H. No expectation of a pointwise beta replaces it.

3. [x] **Build an exact finite representation of the active-rank events before bounding them.** For the background put L_k=#{ell not in {i,j}:p_ell<=t_k}. The three forced ranks are exactly R_b=max({0} union {k:b+L_k>=k}) for b=0,1,2, with forced zeros counted and forced ones excluded. Derive the exact joint constraints defining (c,s,r), including L_r=r-2 and L_{r+h}-L_r<=h-1 for every h>=1 with r+h<=N. In particular the adjacent gap (t_r,t_{r+1}] is empty when r<N. Prove these assertions directly; the exploratory gap observation has not received native verification. Keep the r=N endpoint separate.

   Conditional on X, introduce the deterministic band probabilities
   $$
   \pi_{\ell k}(X)=\Pr\{t_{k-1}<p_\ell\le t_k\mid X\},\quad t_0=0,
   \qquad \pi_{\ell\infty}(X)=\Pr\{p_\ell>q\mid X\}.
   $$
   Expand the finite polynomial
   $$
   \prod_{\ell\notin\{i,j\}}
   \left[\pi_{\ell\infty}z_\infty+
   \sum_{k=1}^N\pi_{\ell k}z_k w_k^{\alpha_\ell}\right].
   $$
   Coefficient extraction under the full rank constraints gives the probability of each (c,s,r) event; derivatives in w give v_c,v_s,v_r. Write this coefficient rule explicitly, so contact probabilities and their numerator weights are checkable finite sums, rather than an assumed rank decoupling. For a fixed gap only, prove its empty probability is product_ell(1-pi_ell,gap)<=exp(-sum_ell pi_ell,gap). The rank-selected gap is not independent of the background. Any use of this product must occur after summing over fixed rank events in the exact representation, retaining or rigorously bounding their other constraints.

4. [ ] **First mandatory unproved analytic gate: prove an integrated Gaussian-weighted three-face/gap Gram-energy packing budget.** Establish a finite universal A, independent of every model parameter and eta, such that
   $$
   \boxed{\displaystyle
   \int_0^1\frac{\beta(H_{a,\eta})}{1+\eta^2}\,da
   \le Aq(1+U).}
   \tag{IG3}
   $$
   Here is the explicit finite-sum version to prove using Step 3. Let C_{ij}^{csr}(a,eta) be the expectation of the entire three-term bracket defining K_ij in Step 2, multiplied by the indicator of the joint background event (R_0,R_1,R_2)=(c,s,r). Its numerator counts remain inside that expectation and are extracted from the marked polynomial. For every Borel measurable, deterministic path of PSD unit-diagonal matrices Q(a), prove
   $$
   \int_0^1\frac{1}{1+\eta^2}
   \sum_{i<j}\ \sum_{\substack{0\le c<s<r\le N}}
   Q_{ij}(a)C_{ij}^{csr}(a,\eta)\,da
   \le Aq(1+U).
   \tag{IE}
   $$
   Q may depend on the original model, a and eta, but never on X or the residual observations. Prove the equivalence of (IE) and (IG3), for example by measurable near-maximizers from a countable dense subset of the compact elliptope. Beta is still taken after the full Gaussian average. Thus this finite summed integrated-energy inequality is the actual gate, not a pointwise conditional matrix estimate.

   Preserve and test, as an optional sufficient route, the original stronger proposal: for a universal B,
   $$
   \boxed{\displaystyle
   \beta(H_{a,\eta})\le
   Bq(1+U)\frac{1+\sqrt{\log(1/\nu_{a,\eta})}}{\sqrt{\nu_{a,\eta}}}.}
   \tag{G3}
   $$
   This pointwise (G3) would give A=5B, but is not mandatory. It imposes a dimension-uniform upper modulus for FDR increments along the interpolation path, stronger than the target's total order budget. It does not by itself control absolute increments, since beta(-H) is not bounded here. Narrow layers near critical mean-mixture branches are a possible obstacle to such a majorant, not a proved counterexample to it. Do not discard a valid O(q(1+U)) integrated charge merely because it lacks a universal pointwise envelope. Neither (IG3), (IE), nor (G3) is assumed. Attempt the following mechanism and save the first mandatory inequality that remains unproved.

   (a) For each fixed feasible triple (c,s,r), insert the three signed contact terms into the coefficient representation of Step 3. For arbitrary deterministic Gram systems Q_ij(a)=<z_i(a),z_j(a)>, ||z_i(a)||=1, expand the entire pair sum and pair the r-r contact with the s-r and r-s contacts before any upper bound. Seek an explicit summation-by-parts identity in the cumulative counts whose quadratic terms are Gram energies ||sum_ell b_ell z_ell(a)||^2 and their differences. Display the coefficients and every endpoint term. Integrate these finite signed sums in a before imposing pointwise upper envelopes. The target is (IE), permitting large charges on narrow parameter intervals. This must be an equality or a proved inequality for the Gaussian-averaged expression; a claimed conditional negative-Gram sign or an unsigned raw-layer trace estimate is not available. The top raw all-null layer J-I has beta=N(N-1).

   (b) Use the retained maximal-rank constraints to charge contact density to the adjacent empty gap, or to the longer deficits L_{r+h}-L_r<=h-1. Start with exact normal formulas for a fixed gap mass and the ratio of its endpoint density to its mass. Derive the a-derivative of each fixed-band probability in the polynomial, retaining both the varying shared mean and residual variance. Attempt an averaged integrated-energy identity in which the paired contact terms are controlled by finite differences of the marked polynomial's Gram energies plus explicit null-weighted remainders. Display all derivative, endpoint and remainder terms, and prove their total charge is O(q(1+U)); do not assume selected ranks are monotone in a or omit shared-mean derivatives. If a-dependent Gram vectors are used in an integration by parts, justify every resulting derivative term; an alternative coefficientwise argument valid for arbitrary measurable Q(a) avoids such differentiation. The certificate must establish (IE) uniformly for those arbitrary paths.

   Split short and long standardized gaps as needed. As a subsidiary attempt at the optional pointwise (G3), truncate the conditional standardized endpoint scores at
   $$
   L_\nu=\sqrt{2\log(e/\nu)}.
   $$
   On the moderate-score part, try to control the paired Gram-energy increments by fixed-gap occupancy probabilities with total averaged charge O(L_nu). On the complement, retain the Gaussian tail factor and prove a summable bound compensating the residual density supremum; a union bound over all coordinates is unacceptable. If this pointwise splitting fails, retain the exact signed expressions and try the integrated identity above rather than declaring failure solely at (G3). For r=N use the terminal band and the three signed terms directly, since there is no adjacent gap. The mandatory outcome is an explicit finite integrated summation inequality with universal A; a log N, rank count, directional entropy or eta-dependent remainder does not prove it. The energy identity, truncation and proposed packing are proof attempts, not asserted estimates.

   (c) Reproduce the canonical deterministic-level replica proof in the adapted scalar lemma: independent residual copies, average/difference Jacobian 1/2, the bivariate tail-density estimate, and weighted Cauchy--Schwarz. It yields, for deterministic v>=U and deterministic w,z,
   $$
   \mathbb E[p_i(v\mid X)d_j(w\mid X)d_k(z\mid X)]
   \le \frac{q(1+U)}{\sqrt\nu},\qquad i\in I_0.
   $$
   Apply this only to fixed grid levels after the rank/gap weighting has been justified. The necessary null-tail weight must be derived from the coefficient expansion and its averaging; it cannot be inserted for free. A conditional Gaussian mean need not remain <=0, so use the original global null condition only. Preserve the background event whenever deleting it destroys the summability from (b). Do not replace the selected u_r,u_s by a supremum inside the scalar lemma or switch expectation and supremum: [Fixed-level scalar bounds do not extend to arbitrary measurable rank-like levels](../ideas/idea_569be86e386c.md) gives a checked auxiliary obstruction even at N=2.

   The required outcome of (a)--(c) is (IE), hence (IG3), uniform over every deterministic measurable Gram path after full Gaussian averaging. The optional pointwise (G3) is another sufficient way to obtain that outcome. Neither a formal Gram expansion nor the scalar bound alone suffices. If the concrete contact/gap/energy attempts establish neither the integrated gate nor its pointwise sufficient route, stop at this first mandatory gate and record the precise missing pairing, occupancy, null-tail or time-integrated rank-sum estimate. Do not substitute row absolute sums, all N^2 grid faces, or a restricted covariance class.

5. [ ] **Use only the proved total budget, then cover singular covariance.** From (IG3), the exact outer factor 1/(1+eta^2), and Sigma PSD with unit diagonal, obtain F_eta(1)<=q*pi_0+Aq(1+U). No dimension-uniform upper modulus for pathwise FDR increments is required. If the optional pointwise (G3) was proved instead, its noise envelope is decreasing as a function of nu and nu_{a,eta}>=1-a; prove by substitution that
   $$
   \int_0^1\frac{1+\sqrt{\log(1/\nu_{a,\eta})}}{\sqrt{\nu_{a,\eta}}}\,da
   \le 2+\sqrt{2\pi}<5.
   $$
   In that optional case set A=5B. Only after establishing a finite universal A let eta decrease to zero for each fixed finite original model. Couple T_{1,eta} with theta+X; the finitely many marginal grid boundary events have probability zero even for singular Sigma. Bounded dominated continuity transfers the same universal bound to that model. No exchange of a dimension supremum and a limit is needed. Prove U<=sqrt(2log(1/q)) by a Gaussian tail estimate, choose a universal q_0<=min{S(1),e^{-1}}, and obtain the target q*sqrt(log(1/q)) with an explicit finite universal constant expressed in A. Do not optimize it.

## Verification

Execution must preserve complete proofs of Steps 1--3 and every successful part of Step 4 in Progress, with the first unresolved essential estimate named exactly. The plan succeeds only if (IG3), equivalently (IE), is established with a finite universal A and Step 5 closes the full supremum. The optional pointwise (G3) suffices with A=5B but is not an acceptance requirement. Finite-N checks, numerical probes, scalar estimates, and scoped audits cannot replace the Gaussian-weighted integrated matrix proof. Every old failure and auxiliary obstruction remains intact. After any claimed success, obtain a fresh whole-proof native verification; neither the prior scoped reviewer nor researcher approval of the scalar helper verifies this target.

## Assumed definitions

Only the target's approved definitions are used: the Gaussian multiple-testing model, Gaussian p-values, ordinary BH, FDP/FDR, and the uniform worst-case envelope. There are no assumed draft definitions, unproved dependencies, packing lemmas, independence assertions for selected ranks, or unproved target conclusions. The three-face and gap ideas are sources of obligations, not premises. The canonical scalar helper is rederived as described below because it is not presently listed as a black-box dependency of the target.

## Adapted from

- [Gaussian conditional tail-density replica bound at deterministic levels](../assets/gaussian_conditional_tail_density_replica_bound.md): reproduce its Proof Steps 2--7 in Step 4(c). Its hypotheses hold for every deterministic grid level u_k>=U, with the original theta_i<=0, unit PSD Sigma, and positive residual variance nu. All other means and covariance ranks remain unrestricted. Its independent-replica device is auxiliary and does not make a selected BH rank independent of the observations. The new work is the integrated signed coefficient/Gram and active-gap aggregation of Step 4(a)--(b); neither that total budget nor the optional pointwise noise envelope appears in the scalar proof. Its elementary Mills and Gaussian calculations are rederived, without importing any theorem from the failed plan.

## Difference from failed plans

- `plan_one_sided_order_actual_mean_global_flux_20261106`: replaces a positive jump budget and inactive-crossing envelope by the exact three signed leave-two-out faces of the actual FDP. Maximal-rank background constraints stay inside the Gaussian average, including full cascades; no separately centered negative-null counterfactual or marginal crossing count is substituted. The new proposed mechanism pairs Gram-energy increments and charges contacts to active gaps, rather than bounding all positive flux.
- `plan_one_sided_order_gaussian_interpolation_sdp_20261106`: keeps its correctly normalized interpolation but replaces the all-N^2 boundary-grid enumeration and row-absolute completion by exactly three faces per pair, an explicit finite coefficient description of the joint maximal ranks, and Gaussian-averaged contact/gap/Gram-energy packing integrated before upper envelopes. The primary gate permits concentration in thin noise/rank layers; the original pointwise sqrt(log(1/nu)) proposal is preserved only as a sufficient attempt. Merely renaming the old integrated SDP budget or changing a noise factor would not solve its obstruction: the new obligation is an explicit signed three-contact and active-occupancy energy certificate for (IE), without label or rank multiplicity. Pointwise unweighted completion, arbitrary random-level scalar strengthening, and expectation/supremum exchanges remain forbidden.

## Progress

### Execution checkpoint 1: original means, exact ranks and signed interpolation (Steps 1–2)

All arguments below fix an arbitrary admissible finite model; $\alpha_i=\mathbf1\{\theta_i\le0\}$ is never recomputed from a conditional mean. Write $S=\overline\Phi$, $0<q\le S(1)$, $t_k=qk/N$, $u_k=S^{-1}(t_k)$, and $t_0=0$. For any deterministic p-vector let $M_k=\#\{i:p_i\le t_k\}$. Its maximal qualifying rank is $R=\max(\{0\}\cup\{k:M_k\ge k\})$. For $R>0$ one has $M_R=R$: otherwise $M_R\ge R+1$ implies $M_{R+1}\ge R+1$ when $R<N$, a contradiction, while $M_N\le N$. Thus this rank equals the rejection count, including ties. When $R=0$, $M_k<k$ at every positive rank.

If a rejected coordinate is replaced by zero, rank $R$ remains qualifying; for every $k>R$ it was already counted because $p_i\le t_R<t_k$, so the count at $k$ does not increase. Hence the rank stays $R$. If an unrejected coordinate is replaced by one, the count at $R$ is unchanged and counts at higher ranks cannot increase, so again the rank stays $R$. These are deterministic statements, valid at threshold equalities and for repeated p-values. In the first statement the original $R$ is positive; in the second $R=0$ is allowed.

For the independent vector $T=\theta+\varepsilon$, let $R_i$ be its rank after forcing $p_i=0$. Then $R_i\ge1$, depends only on the other coordinates, and
$$
\frac{\mathbf1\{i\text{ rejected}\}}{R\vee1}
=\frac{\mathbf1\{p_i\le t_{R_i}\}}{R_i}.
$$
The forward implication uses the zero replacement just proved. Conversely, if $p_i\le t_{R_i}$, the original count at $R_i$ equals the forced count, while reducing a p-value cannot decrease the maximal rank; thus the original rank is $R_i$ and $i$ is rejected. For $\theta_i\le0$, $\Pr(p_i\le t)=S(S^{-1}(t)-\theta_i)\le t$. Independence of $p_i$ and $R_i$ therefore gives an expectation at most $q/N$ per true null. Summation proves $\mathcal F_\eta(0)\le q|I_0|/N$, with no equality claim for negative means. When $N=1$, FDR is $\mathbf1\{\theta_1\le0\}\Pr(p_1\le q)\le q$ at every covariance and needs no interpolation. If $I_0$ is empty, FDP is identically zero for every $N$.

For $N\ge2$ fix background coordinates outside $i,j$. Put $L_k=\#\{\ell\ne i,j:p_\ell\le t_k\}$. Replacing the two removed coordinates by $b$ zeros and $2-b$ ones gives
$$
R_b=\max(\{0\}\cup\{k\in[N]:b+L_k\ge k\}),\qquad b=0,1,2.
$$
The formula follows because $q<1$ excludes the forced ones from every count, and every positive threshold includes the forced zeros. In particular $c=R_0$, $s=R_1$ (the same rank for either position of the single zero), and $r=R_2$. The equality of the two single-zero ranks follows from these counts, without any hypothesis on $\alpha_i,\alpha_j$. One has $R_b\ge b$, $R_0\le N-2$, $R_1\le N-1$, and $b+L_{R_b}=R_b$, where $L_0=0$. The last equality for $b=0,R_b=0$ uses this convention; otherwise it is the rejection-count identity above. Since $L_{R_b+1}\ge L_{R_b}$, rank $R_b+1$ qualifies with $b+1$ forced zeros. Hence $r\ge s+1\ge c+2$.

For arbitrary inserted $p_i,p_j\in[0,1]$, no rank above $r$ can qualify because even two forced zeros cannot make it qualify. If both inserted p-values are at most $t_r$, rank $r$ qualifies and is the answer. Outside that case, if $p_i\le t_s$ and $p_j>t_r$, rank $s$ qualifies; for $s<k\le r$ only $i$ can be counted and $1+L_k<k$ by maximality of $s$, so the answer is $s$. The same proof applies with $i,j$ interchanged. In every other case no $k>c$ qualifies: if both inserted p-values were counted at such a $k\le r$, both would be at most $t_r$; if exactly one were counted, $k\le s$ by maximality of $s$, that p-value would be at most $t_s$, and the other would have to exceed $t_r$ since the first case is excluded. Either alternative is a case already removed. Background rank $c>0$ itself qualifies; when $c=0$ the preceding argument excludes every positive rank. Thus the exact three-region rank partition in Step 2 holds, including all endpoints. In the rank-$c$ region neither inserted coordinate is counted at $t_c$, since that would yield a rank-$s$ case. In the two rank-$s$ regions exactly the specified inserted coordinate is counted; in rank $r$ both are counted. It follows that the FDP values are exactly $F_c,F_s^i,F_s^j,F_r$ as in Step 2, with $F_c=0$ if $c=0$.

In statistic coordinates put $A_i=\mathbf1\{T_i\ge u_r\}$, $B_i=\mathbf1\{T_i\ge u_s\}$, and define $A_j,B_j$ likewise. Since $s<r$, $u_s>u_r$ and $B_i\le A_i$. The partition just proved gives the exact identity
$$
f=F_c+(F_r-F_c)A_iA_j
 +(F_s^i-F_c)B_i(1-A_j)
 +(F_s^j-F_c)(1-A_i)B_j.
$$
As distributions in $(T_i,T_j)$, the derivative of $\mathbf1\{x\ge u\}$ is the positive point mass $\delta_u$. Differentiating the displayed identity yields
$$
\partial_i\partial_j f=(F_r-F_c)\delta_{(u_r,u_r)}
 -(F_s^i-F_c)\delta_{(u_s,u_r)}
 -(F_s^j-F_c)\delta_{(u_r,u_s)}.
$$
The orientation uses statistic coordinates, not increasing p-values. Equality values of f are fixed by the original non-strict BH convention; the distributional derivative is insensitive to isolated boundary values. For $N=2$ the empty background gives $(c,s,r)=(0,1,2)$ and $v_c=v_s=v_r=0$, so the same formula includes every choice of the two null labels. None of the preceding arguments assumes distinct background values or nonadjacent ranks.

Now let $C_a=I+a(\Sigma-I)/(1+\eta^2)$, $\eta>0$. Its least eigenvalue is at least $\eta^2/(1+\eta^2)>0$; its diagonal is one and its mean remains the original $\theta$. For its density $g_a(x)$, writing $y=x-\theta$ and $D=(\Sigma-I)/(1+\eta^2)$, direct differentiation gives
$$
\partial_a g_a=\tfrac12\{y^{\mathsf T}C_a^{-1}DC_a^{-1}y-\operatorname{tr}(C_a^{-1}D)\}g_a
=\tfrac12\sum_{i,j}D_{ij}\partial_i\partial_jg_a.
$$
Indeed $\partial_i\partial_jg_a=[(C_a^{-1}y)_i(C_a^{-1}y)_j-(C_a^{-1})_{ij}]g_a$. The covariance eigenvalues are uniformly bounded above and away from zero on this fixed path, so the density derivatives have an integrable polynomial-times-Gaussian majorant. Since $0\le f\le1$, differentiation under the integral is valid. Partitioning each statistic axis at its finitely many $u_k$, integrate $\int f\partial_i\partial_jg_a$ twice by parts on these cells. The endpoint terms at infinity vanish by Gaussian decay, all interior jumps combine into the distributional mixed derivative just established, and $D_{ii}=0$ removes the pure second derivatives. This proves, without an imported differentiation identity,
$$
\mathcal F_\eta'(a)=\frac1{1+\eta^2}\sum_{i<j}\Sigma_{ij}K_{ij}
=\frac{\langle\Sigma,H\rangle}{1+\eta^2},\qquad H_{ij}=K_{ij}/2,\quad H_{ii}=0.
$$
Here the matrix pairing sums over ordered indices. To identify $K_{ij}$, represent the covariance as $T=\theta+\sqrt{1-\nu}X+\sqrt\nu\varepsilon$ with $\nu=(1-a+\eta^2)/(1+\eta^2)$ and independent $X\sim N(0,\Sigma)$, $\varepsilon\sim N(0,I)$. Conditional on $X$, all residual coordinates are independent and have density $d_i(w\mid X)$ in Step 2. Integrating the three point masses against the two conditional densities, then averaging over the unchanged background residuals and $X$, gives exactly the three-term $K_{ij}$ formula in Step 2. Positive $\nu$ bounds the densities, so all these finite integrations are justified. Ranks and numerator counts remain functions of that same background in all three terms. This establishes Steps 1–2 without using the target conclusion or the proposed matrix budget. No diagonal-completion duality is used here or needed below.

### Execution checkpoint 2: full rank constraints and marked coefficient formula (Step 3)

Let $\mathbf n=(n_1,\ldots,n_N,n_\infty)$ be nonnegative integer band occupancies summing to $N-2$, and $\ell_k(\mathbf n)=\sum_{h\le k}n_h$, with $\ell_0=0$. Define $\mathcal E_{csr}$ by the following simultaneous constraints:
$$
\begin{array}{lll}
\ell_c=c,&\ell_k\le k-1& (k>c),\\
\ell_s=s-1,&\ell_k\le k-2& (k>s),\\
\ell_r=r-2,&\ell_k\le k-3& (k>r).
\end{array}
$$
Here $0\le c<s<r\le N$; when $c=0$ its equality means $\ell_0=0$ and its inequality is imposed at every $k\ge1$. Each row says precisely that the indicated forced rank qualifies and every larger rank fails, using the rejection-count equality from checkpoint 1. Conversely those equalities and failures force $(R_0,R_1,R_2)=(c,s,r)$. Thus these are necessary and sufficient joint constraints, not merely necessary gap conditions. Empty constraint sets are allowed.

At the largest forced rank, $L_r=r-2$ and, for $h\ge1$ with $r+h\le N$,
$$
L_{r+h}-(r-2)\le (r+h-3)-(r-2)=h-1.
$$
In particular $L_{r+1}=L_r$ when $r<N$, so $(t_r,t_{r+1}]$ contains no background p-value. There is no such adjacent gap if $r=N$; the same exact constraints still apply, with the last row's inequalities empty and $L_N=N-2$. The first and second rows analogously imply empty immediately following bands at $c$ (including band 1 when $c=0$) and $s$. They retain all longer cascade deficits; none is replaced by a single-gap event.

For fixed $X$ use the polynomial $P_{ij}(\mathbf z,\mathbf w\mid X)$ displayed in Step 3, with deterministic conditional probabilities $\pi_{\ell k}$ and $\pi_{\ell\infty}$. Conditional residual independence shows directly by distributivity that each coefficient is the sum of products of probabilities over assignments having that band-count and marked-null-count vector. Define
$$
A_{\mathbf n}(X)=[\mathbf z^{\mathbf n}]P_{ij}(\mathbf z,\mathbf1\mid X),\qquad
B_{\mathbf n,k}(X)=[\mathbf z^{\mathbf n}]
\left.\sum_{h=1}^k w_h\partial_{w_h}P_{ij}(\mathbf z,\mathbf w\mid X)\right|_{\mathbf w=\mathbf1},\quad B_{\mathbf n,0}=0.
$$
The marking multiplies a monomial by its number of background true nulls in the first $k$ bands. Consequently
$$
\Pr\{(R_0,R_1,R_2)=(c,s,r)\mid X\}=\sum_{\mathbf n\in\mathcal E_{csr}}A_{\mathbf n}(X),
$$
$$
\mathbb E[v_k\mathbf1\{(R_0,R_1,R_2)=(c,s,r)\}\mid X]
=\sum_{\mathbf n\in\mathcal E_{csr}}B_{\mathbf n,k}(X).
$$
For each feasible $\mathbf n$ abbreviate
$$
g_c=\frac{B_{\mathbf n,c}}{c\vee1},\quad
g_s^i=\frac{B_{\mathbf n,s}+\alpha_iA_{\mathbf n}}s,\quad
g_s^j=\frac{B_{\mathbf n,s}+\alpha_jA_{\mathbf n}}s,\quad
g_r=\frac{B_{\mathbf n,r}+(\alpha_i+\alpha_j)A_{\mathbf n}}r.
$$
Then the exact finite contact coefficient of Step 4 is
$$
\begin{aligned}
C_{ij}^{csr}=\mathbb E_X\sum_{\mathbf n\in\mathcal E_{csr}}\big[&
(g_r-g_c)d_i(u_r)d_j(u_r)\\
&-(g_s^i-g_c)d_i(u_s)d_j(u_r)
 -(g_s^j-g_c)d_i(u_r)d_j(u_s)\big].
\end{aligned}
$$
Conditional densities in this formula all mean $d(\cdot\mid X)$. This formula keeps the same $\mathbf n$ and its three marked counts in the three signed terms. It gives $K_{ij}=\sum_{c<s<r}C_{ij}^{csr}$, and no selected rank has been made independent of its defining observations.

For any fixed deterministic gap $G$ in p-space, conditional residual independence also gives
$$
\Pr\{p_\ell\notin G\text{ for every }\ell\ne i,j\mid X\}
=\prod_{\ell\ne i,j}(1-\pi_{\ell,G}(X))
\le\exp\left(-\sum_{\ell\ne i,j}\pi_{\ell,G}(X)\right).
$$
The inequality is $1-x\le e^{-x}$ for $x\in[0,1]$, multiplied over finitely many factors. This is an exact fixed-gap calculation followed by a bound; for $G=(t_r,t_{r+1}]$ its probability only upper-bounds the sum over the more constrained $\mathcal E_{csr}$. A different $r$ gives a different gap event, so these bounds cannot be summed as disjoint probabilities. This establishes Step 3.

### Execution checkpoint 3: integrated gate equivalence and an exact Gram identity (part of Step 4(a))

For fixed finite model and $\eta>0$, each entry of $H_a$ is continuous in $a$: its finite boundary-density integral from checkpoint 1 has a continuous Gaussian integrand and a uniform integrable majorant because $C_a$ stays positive definite. The elliptope $\mathcal Q_N=\{Q\succeq0:Q_{ii}=1\}$ is compact: $|Q_{ij}|\le1$, and the defining constraints are closed. Thus $\beta(H_a)$ is a continuous, nonnegative function, the nonnegativity following from $I\in\mathcal Q_N$ and $H_{ii}=0$. Fix a countable dense sequence $Q^m$ in $\mathcal Q_N$. Continuity of the pairing in $Q$ gives $\beta(H_a)=\sup_m\langle Q^m,H_a\rangle$. For each $\epsilon>0$ choose at each $a$ the first $m$ for which this pairing exceeds $\beta(H_a)-\epsilon$. This defines a Borel measurable deterministic path $Q_\epsilon(a)$. For any such path,
$$
\langle Q(a),H_a\rangle=\sum_{i<j}\sum_{c<s<r}Q_{ij}(a)C_{ij}^{csr}(a,\eta)\le\beta(H_a).
$$
Hence (IG3) implies (IE); conversely applying (IE) to $Q_\epsilon$, and then letting $\epsilon\downarrow0$, proves (IG3). All integrands are bounded for this fixed finite model and positive $\eta$. No exchange with a conditional expectation is used, and no SDP duality is needed.

Here is an exact signed Gram-energy expansion before upper bounds. It supplies a concrete identity for the proposed packing attempt, not a bound. Use full band assignments $\mathbf b=(b_1,\ldots,b_N)\in\{1,\ldots,N,\infty\}^N$ and write $f(\mathbf b)$ for their FDP: $R(\mathbf b)=\max(\{0\}\cup\{k:\#\{i:b_i\le k\}\ge k\})$ and $f(\mathbf b)=\sum_i\alpha_i\mathbf1\{b_i\le R\}/(R\vee1)$. The infinite band is ordered after every finite band. Conditional on $X$, put $\mu_i=\theta_i+\sqrt{1-\nu}X_i$, $x_{ik}=(u_k-\mu_i)/\sqrt\nu$, and $\phi(x_{i0})=0$ for $u_0=+\infty$. The residual first moments in each band are
$$
m_{ik}=\int_{x_{ik}}^{x_{i,k-1}}e\phi(e)\,de
=\phi(x_{ik})-\phi(x_{i,k-1}),\qquad
m_{i\infty}=\int_{-\infty}^{x_{iN}}e\phi(e)\,de=-\phi(x_{iN}).
$$
In particular $\sum_bm_{ib}=0$, including the terminal band, and $m_{ik}=\sqrt\nu[d_i(u_k)-d_i(u_{k-1})]$. Positive $\nu$ makes each $\pi_{ib}$ strictly positive. Set $h_{ib}=m_{ib}/\pi_{ib}$ and $P(\mathbf b\mid X)=\prod_i\pi_{i b_i}$. Integrating $\partial_i\partial_j$ twice against the independent conditional Gaussian densities, or equivalently using $\partial_i\partial_jg=\varepsilon_i\varepsilon_jg/\nu$ for $i\ne j$, gives
$$
K_{ij}=\frac1\nu\mathbb E_X\sum_{\mathbf b}f(\mathbf b)P(\mathbf b\mid X)h_{i b_i}h_{j b_j}.
$$
For any fixed deterministic Gram representation $Q_{ij}=\langle z_i,z_j\rangle$, $\|z_i\|=1$, it follows that
$$
\boxed{\displaystyle
\langle Q,H\rangle=\frac1{2\nu}\mathbb E_X\sum_{\mathbf b}f(\mathbf b)P(\mathbf b\mid X)
\left(\left\|\sum_i h_{i b_i}z_i\right\|^2-\sum_i h_{i b_i}^2\right).}
\tag{GE}
$$
This identity is also $\langle Q,H\rangle=(2\nu)^{-1}\mathbb E[f(T)(\|\sum_i\varepsilon_i z_i\|^2-\sum_i\varepsilon_i^2)]$: conditional residual variances cancel between the two quadratic expressions, leaving exactly the band means in (GE). The negative diagonal is $\sum_i\varepsilon_i^2$ inside the FDP weight; replacing it by $N$ inside that weight would be incorrect. Gaussian integrability and $f\le1$ justify the calculation for fixed $N,\eta$.

For fixed other bands, substituting the endpoint differences for $m_i,m_j$ in the double sum is a discrete summation by parts. Its interior coefficients are precisely the mixed differences of $f$; checkpoint 1 proves they are zero except for the three contact pairs, with coefficients $F_r-F_c,-(F_s^i-F_c),-(F_s^j-F_c)$. Its exterior endpoint at $+\infty$ has $\phi(x_{i0})=0$; the lower terminal contribution is $m_{i\infty}=-\phi(x_{iN})$. These are all endpoints, so summing first by pairs recovers exactly the $C_{ij}^{csr}$ formula of checkpoint 2. Thus (GE) already pairs all three faces globally and retains every maximal-rank and truth-count constraint. The bracket can have either sign; no conditional negative-Gram assertion has been made. A uniform integrated upper bound on its full Gaussian average remains to be proved.

### Execution checkpoint 4: an auxiliary obstruction to the mandatory integrated budget itself

The following construction concerns (IG3)/(IE), not the target FDR order. It retains the entire signed matrix, so it is not an unsigned-envelope or random-level objection. Its first observation is exact: if the original covariance is $\Sigma_\rho=(1-\rho)I+\rho J$, where $J$ is the all-ones matrix, then $H_{ii}=0$ implies $\langle\Sigma_\rho,H\rangle=\rho\langle J,H\rangle$. Since $J$ is a deterministic PSD unit-diagonal matrix, the already proved interpolation identity gives
$$
\int_0^1\frac{\beta(H_a)}{1+\eta^2}\,da
\ge\int_0^1\frac{\langle J,H_a\rangle}{1+\eta^2}\,da
=\frac{\mathcal F_\eta(1)-\mathcal F_\eta(0)}\rho.
\tag{OB1}
$$
Thus (IG3) would impose a dimension-uniform $O(\rho)$ upper bound on every upward FDR change from independence along equicorrelation. This implication does not require a pointwise noise modulus or a derivative limit. We construct an upward change bounded away from zero while $\rho\downarrow0$ and $q$ is fixed.

Fix any $q\in(0,10^{-2}]$, set $c_*=6$, $y_0=1/2$, and define
$$
\kappa=2\log(2/q-e^{-3}),\qquad L=\kappa+6,\qquad
g(y)=\log\left[\frac q2(e^{-6y}+e^{\kappa y})\right],\qquad
h(y)=\frac1{1+e^{Ly}}.
$$
Then $\kappa>6$, $g(0)=\log q<0$, $g(y_0)=0$, $g'(y)\ge g'(0)=(\kappa-6)/2>0$ for $y\ge0$, and
$$
h_0=h(y_0)=\frac q2e^{-3},\qquad d=g'(y_0)=\kappa-Lh_0>0,\qquad
e=g''(y_0)=L^2h_0(1-h_0).
$$
Here $d<\kappa$. Take even $N\to\infty$, put $w_N=\sqrt{2\log N}$, and give exactly $N/2$ true nulls mean $-6/w_N$ and $N/2$ alternatives mean $\kappa/w_N$. These labels satisfy the exact original one-sided null definition. Let $D_N(v)$ denote the actual ordinary-BH FDR for these means and equicorrelation $v$. All matrices $\Sigma_v$ with $0\le v<1$ are admissible.

We first prove the needed conditional finite-model limit. Fix sufficiently small $t\ge0$ and $\lambda$ in a sufficiently small fixed interval about zero. The observations, conditional on a common factor with $\lambda=\sqrt t Z$, are independent with means $(a+\lambda)/w_N$ ($a=-6$ or $\kappa$) and variance $1-t/w_N^2$. Define
$$
B_{\lambda,t}(y)=\exp(g(y)+\lambda y-ty^2/2).
$$
There are constants $\delta>0,t_*>0$ such that, for $|\lambda|\le\delta$ and $0\le t\le t_*$, the exponent is strictly increasing on $[0,1]$, is negative at $y=0.4$ and positive at $y=0.6$. Indeed these assertions hold with strict margins at $(\lambda,t)=(0,0)$, and its derivative is at least $(\kappa-6)/2-\delta-t_*$. Reduce $\delta,t_*$ so this is positive and the two margins persist. Let $y(\lambda,t)\in(0.4,0.6)$ be its unique zero. We claim that conditional FDP converges in probability, and hence its conditional expectation converges, to $h(y(\lambda,t))$.

Here are all concentration and tail details for this claim. For $x>0$, integration of $-\phi'(s)=s\phi(s)$ gives $S(x)\le\phi(x)/x$. Integration by parts gives
$$
S(x)=\frac{\phi(x)}x-\int_x^\infty\frac{\phi(s)}{s^2}\,ds
\ge\frac{\phi(x)}x-\frac{S(x)}{x^2},
$$
so $x\le\phi(x)/S(x)\le x+x^{-1}$. For $U=S^{-1}(q)\le x\le w_N$, put
$$
z=\frac{x-(a+\lambda)/w_N}{\sqrt{1-t/w_N^2}}.
$$
Uniformly in this interval, $z-x=-(a+\lambda)/w_N+tx/(2w_N^2)+O(w_N^{-3})$, with bounded fixed $a,\lambda,t$. Integrating the logarithmic derivative $-\phi/S$ between $x$ and $z$ and using the preceding hazard bounds shows uniformly that
$$
\log\frac{S(z)}{S(x)}
=\frac{(a+\lambda)x}{w_N}-\frac{t x^2}{2w_N^2}+o(1).
\tag{OB2}
$$
For example the error in replacing the hazard by its argument is at most $O(|z-x|)$ since $z,x\ge U/2$ for large $N$; the squared-argument expansion has error $o(1)$. Consequently at every BH grid threshold $x=u_k\le w_N$,
$$
\frac{\mathbb E[M_k\mid Z]}k
=B_{\lambda,t}(u_k/w_N)+o(1),\qquad
\frac{\mathbb E[V_k\mid Z]}k
=\frac q2\exp\left((-6+\lambda)\frac{u_k}{w_N}-\frac t2\frac{u_k^2}{w_N^2}\right)+o(1),
\tag{OB3}
$$
uniformly, because $t_k=S(u_k)=qk/N$ exactly. Here $M_k$ and $V_k$ count all and null observations at that fixed threshold.

Fix any small $\epsilon>0$ with $0<y-\epsilon<y+\epsilon<1$, where $y=y(\lambda,t)$. The grid rank nearest $N S((y+\epsilon)w_N)/q$ diverges at a positive polynomial rate: the Mills bounds above give $\log(NS(bw_N))/\log N\to1-b^2$ for each $b\in(0,1)$. Its threshold divided by $w_N$ tends to $y+\epsilon$ (rounding changes the tail probability by a relative $o(1)$), and (OB3) makes its expected count exceed its rank by a fixed positive proportion. It qualifies with probability tending to one. Conversely all ranks above $N S((y-\epsilon)w_N)/q$ have normalized thresholds at most $y-\epsilon+o(1)$ and expected count at most $(1-\gamma)k$, for a fixed $\gamma>0$, by monotonicity and (OB3). None qualifies with probability tending to one.

For completeness, the concentration used in both assertions is elementary and applies to these nonidentical Bernoulli sums: independence and $1+p(e^s-1)\le\exp(p(e^s-1))$ give $\mathbb E e^{sM}\le\exp((e^s-1)\mathbb EM)$. Markov's inequality with fixed positive or negative $s$ gives an $\exp(-C k)$ error when the mean and the rank differ by a fixed proportion of $k$. Likewise, when the mean is at most $C_0k$, the same formula with a sufficiently small $s$ of either sign gives $\Pr(|M-\mathbb EM|>\epsilon k)\le2e^{-C_1k}$. Union over at most $N$ grid ranks still tends to zero whenever the smallest rank under consideration diverges polynomially. This proves the upper nonqualification assertion and the lower qualification assertion, and proves uniformly that $(V_k-\mathbb EV_k)/k\to0$ over ranks above the lower qualifying rank. No rank-selected gap independence is used.

It follows that $u_R/w_N\to y$ in conditional probability and $R\to\infty$. Applying the null-count part of (OB3) at this random rank is valid by that uniform concentration. Since $M_R=R$ and $R>0$ with probability tending to one,
$$
\frac{V_R}R\ \longrightarrow\ \frac q2e^{(-6+\lambda)y-ty^2/2}
=h(y).
\tag{OB4}
$$
The last equality uses $B_{\lambda,t}(y)=1$. This proves the claim for each fixed $|\lambda|\le\delta,t\le t_*$. FDP is bounded by one, so convergence in probability also gives convergence of the conditional expectation. In particular $D_N(0)\to h_0$.

We next show that a fixed small positive $t$ produces a strictly larger limiting FDR. The implicit-function Taylor expansion at $(\lambda,t)=(0,0)$, justified by $d>0$, is
$$
y(\lambda,t)=y_0-\frac{y_0}d\lambda
+\left(\frac{y_0}{d^2}-\frac{e y_0^2}{2d^3}\right)\lambda^2
+\frac{y_0^2}{2d}t
+O(|\lambda|^3+|\lambda|t+t^2).
$$
The remainder is bounded uniformly on a sufficiently small rectangle. Since $h'=-Lh(1-h)$ and $h''=L^2h(1-h)(1-2h)$, substitution of $\lambda=\sqrt t Z$ and integration over $|\sqrt t Z|\le\delta$ gives
$$
\mathbb E\left[h(y(\sqrt t Z,t))\mathbf1\{|\sqrt t Z|\le\delta\}\right]
=h_0+Kt+o(t),
$$
$$
K=h'(y_0)\left(\frac{y_0}{d^2}-\frac{e y_0^2}{2d^3}+\frac{y_0^2}{2d}\right)
+\frac{h''(y_0)y_0^2}{2d^2}
=\frac{Lh_0(1-h_0)y_0}{2d^2}\left(\frac{6\kappa y_0}d-2\right)>0.
\tag{OB5}
$$
To check the simplification, the bracket before cancellation is $-2+y_0[-d+L(1-2h_0)+e/d]$; using $d=\kappa-Lh_0$, $e=L^2h_0(1-h_0)$ reduces the square bracket to $6\kappa/d$. Positivity follows from $6y_0=3$ and $d<\kappa$. The truncated Gaussian first moment is zero, its second moment tends to one, its missing mass and polynomial moments are $o(t^m)$ for every fixed $m$, and the integrated remainder is $O(t^{3/2})+O(t^2)$. These facts justify every expectation in this Taylor calculation; no derivative of a finite-$N$ limit is taken.

The actual equicorrelated model with correlation $t/w_N^2$ has the independent conditional representation just used, with $Z\sim N(0,1)$. Bounded convergence on $|\sqrt t Z|\le\delta$, and nonnegativity of FDP outside it, give
$$
\liminf_{N\to\infty}D_N(t/w_N^2)
\ge h_0+Kt+o(t).
$$
Choose once and for all a sufficiently small fixed $t>0$ so the right side is at least $h_0+Kt/2$. Since $D_N(0)\to h_0$, for all sufficiently large even $N$,
$$
D_N(t/w_N^2)-D_N(0)\ge Kt/4>0.
\tag{OB6}
$$
This is a fixed-$q$ positive FDR increase under a correlation tending to zero; it is entirely consistent with both FDRs being much smaller than $q$.

Finally take the original covariance $\Sigma_{\rho_N}$ with $\rho_N=2t/w_N^2$ and fix $\eta=1$. Its interpolation starts at independence and ends at correlation $t/w_N^2$, with unchanged original means and labels. Combining (OB1) and (OB6) yields
$$
\boxed{\displaystyle
\int_0^1\frac{\beta(H_{a,1})}{2}\,da
\ge\frac{Kt/4}{2t/w_N^2}=\frac K8w_N^2\ \longrightarrow\ \infty.}
\tag{OB7}
$$
For this fixed $q$, the proposed right side $Aq(1+S^{-1}(q))$ is fixed for every finite $A$. Therefore no such universal $A$ can satisfy (IG3). The same exact calculation with the single deterministic Gram path $Q(a)=J$ disproves (IE). This obstruction already occurs at fixed positive regularization $\eta=1$, in admissible positive-definite equicorrelation models with strictly negative null means. It does not use a row-absolute bound, a selected-level scalar strengthening, conditional negative-Gram claims, or an exchange of expectation and supremum. It refutes this plan's auxiliary gate and says nothing against the main universal FDR upper bound.

A short standard-library numerical diagnostic checked only (OB5): for $q=0.01$, $\kappa=10.5961368004$, $h_0=0.000248935342$, $d=10.5920054354$, and $K=9.21460972\times10^{-6}$. Direct Simpson quadrature of the implicit root gave difference quotients $9.21434554\times10^{-6}$ at $t=0.001$ and $9.21196768\times10^{-6}$ at $t=0.01$. These numbers support the algebra but play no role in the proof of (OB7). The initial NumPy diagnostic was unavailable; the actual check used only Python's standard library. All mathematical claims above still require fresh independent checking as an auxiliary gate obstruction, not main-target verification.

## Failure

The first mandatory failure is Step 4, specifically (IG3), equivalently (IE). Execution checkpoints 1–3 preserve complete proofs of Steps 1–3, the gate equivalence, and an exact signed Gram expansion retaining all ranks and labels. Checkpoint 4 gives a counterexample construction to the proposed budget itself: in admissible equicorrelation models with half the original means negative and half positive, at every fixed $q\in(0,10^{-2}]$, equations (OB1)–(OB7) force the integrated charge to diverge like a positive constant times $\log N$, even at fixed $\eta=1$ and with the deterministic Gram path $Q=J$. This is a signed Gaussian-averaged obstruction, not a failure caused by discarding rank events or by demanding the optional pointwise bound (G3).

The mechanism is that the budget maximizes against a covariance $Q$ independently of the original covariance. For $\Sigma_\rho=(1-\rho)I+\rho J$, it removes the small factor $\rho$ that is present in the exact FDR derivative. An $O(1)$ upward FDR change over $\rho\downarrow0$ therefore costs $O(1/\rho)$ in the proposed charge. Retaining the true scalar contraction $\langle\Sigma,H\rangle$ could avoid this obstruction; controlling that contraction uniformly would be a new proof task, not a completion of this plan or a consequence of the current calculations.

No proof was put in the target asset, no target statement or dependency was changed, and the main universal FDR theorem remains unproved. The auxiliary budget counterexample needs a fresh independent audit before being reused as established research evidence. The optional (G3) cannot rescue this plan because it would imply the already obstructed integrated budget. Step 5 and the unused scalar-replica adaptation were not invoked after this mandatory obstruction.

## Post-execution scoped review record

On 6 November 2026, the parent execution reported the fresh STRICT read-only review `audit_integrated_beta_obstruction_fresh`: it confirmed the complete auxiliary obstruction (OB1)–(OB7), conditional on the exact interpolation identity, which a separate prior fresh review had confirmed. The audited mathematical region was lines 292–398 of this plan, with SHA256 `a5654df6756657aa2c3f3296648c0517e4beb71651caa527d4459818e8948b78` when those lines are joined with their terminal newline. The review checked uniform Mills-tail ratios, maximal-root Chernoff concentration, the conditional FDP limit, truncated-Gaussian Taylor expansion, the sign of $K$, and the path/correlation normalization. This post-review record supplements the contemporaneous caveats above without rewriting them. Its scope is the counterexample to (IG3)/(IE), and consequently to any earlier unweighted integrated SDP budget identical to this one; it is neither a main-FDR counterexample nor a proof or researcher approval of the target. The plan remains failed and the target remains draft and unproved.

### Additional fixed-gap density support, not used in (OB1)–(OB7)

For $Y\sim N(\mu,s^2)$ with $s>0$, let $d(x)=s^{-1}\phi((x-\mu)/s)$, fix $h>0$, and put $C=e/\sqrt{2\pi}$. Then
$$
d(x)^2\le\frac{C}{s\min(h,s)}\Pr\{x-h\le Y\le x\}.
\tag{GD1}
$$
To prove this, set $z=(x-\mu)/s$ and $a=h/s$. For $0<a\le1$, unimodality of $\phi$ gives $P=\int_{z-a}^z\phi(v)\,dv\ge a\min\{\phi(z-a),\phi(z)\}$. Moreover $\phi(z)\le1/\sqrt{2\pi}$ and
$$
\frac{\phi(z)^2}{\phi(z-a)}
=\frac1{\sqrt{2\pi}}\exp\left(-\frac{(z+a)^2}{2}+a^2\right)
\le\frac e{\sqrt{2\pi}}=C.
$$
Thus $\phi(z)^2\le CP/a$, and dividing by $s^2$ proves (GD1) when $h\le s$. If $a>1$, apply the just-proved case to the final subinterval $[x-s,x]\subseteq[x-h,x]$, giving $d(x)^2\le C\Pr(x-h\le Y\le x)/s^2$. This completes (GD1) for every $\mu,x,h,s$ without a score restriction. Reflecting $Y$ and $x$ proves the same bound with the right gap $[x,x+h]$.

For finitely many independent $Y_j\sim N(\mu_j,s^2)$, arbitrary means, a common fixed interval $I=[x-h,x]$, and $g_j=\Pr(Y_j\in I)$, apply (GD1) and multiply by the nonnegative absence probabilities to obtain
$$
\sum_j d_j(x)^2\prod_{\ell\ne j}(1-g_\ell)
\le\frac{C}{s\min(h,s)}\sum_jg_j\prod_{\ell\ne j}(1-g_\ell)
=\frac{C}{s\min(h,s)}\Pr\{\#\{j:Y_j\in I\}=1\}
\le\frac{C}{s\min(h,s)}.
\tag{GD2}
$$
The equality holds because the events with exactly the specified single occupant are disjoint, and independence gives their displayed probabilities. The right-gap version follows identically. Conditional on a sigma-field making the coordinates independent, these statements apply pointwise when $x,h,s$ and the conditional means are known given that sigma-field. In particular, they permit $X$-measurable choices under the interpolation's independent residual representation. They do not permit selecting a BH rank from the residual observations and then treating the residuals as independent after that selection.

The source of (GD1)–(GD2) was the parent's fixed-gap squared-density proposal during this execution. The parent subsequently reported the fresh full STRICT review `audit_gaussian_gap_density_fresh`, which confirmed the constant $e/\sqrt{2\pi}$, all scalar parameter cases, and the fixed-gap diagonal packing identity and its conditional scope. The calculation above is written out independently so the support is self-contained. It was not used in the budget obstruction, is not a three-face PSD domination or a cross-rank summation estimate, and does not establish a null-tail-weighted main FDR budget.
