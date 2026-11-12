---
title: Covariance-preserving Gaussian rotation and pooled transport of paired BH rank layers
type: plan
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
inspired_by:
  - idea_b7d1dda1975d
  - idea_310317024935
  - idea_31a7cd7cb5ad
  - idea_7d718e40cb44
  - idea_122098eaa454
  - idea_9692ea16c23a
---

## Goal

Target: [Sharp uniform upper-bound target for two-sided Gaussian BH](../assets/gaussian_bh_two_sided_sharp_upper.md).

Prove the unchanged unrestricted statement by pooling the null contributions across a covariance-preserving Gaussian circle and across both antipodal largest BH ranks. The proposed new tool is an explicitly specified, unbalanced transport problem for a signed **aggregate rank-layer ledger**. Its sources and sinks are not assigned fixed budgets per null. The same alternatives determine both ranks and hence all the ledger's gates. The transport cost below is a falsifiable candidate, not a proved Gaussian inequality.

The first gate is finite and precedes the proposed sharp estimate: derive the exact paired ledger, implement its finite transport primal and dual, and check the candidate on dimensions one, two and three and on the recorded single-null staircase. In particular, establish a dimension-uniform coarse cost bound on the staircase before attempting a general sharp bound. Failure of this candidate cost ends this plan; it does not falsify the target. Defining a remainder to be the original FDR excess, or merely assigning that remainder the desired constant, does not complete any step.

The context pack contains no Library analogues section. Native library searches for `Gaussian BH two-sided sharp upper bound`, `Gaussian rotation circle antipodal coarea rank pairing`, and `Gaussian excursion level crossing Rice surface area BH` returned no results. No library statement is used or proof adapted. The additional native read of [Test antipodal rank pairing under a covariance-preserving two-copy Gaussian rotation](../ideas/idea_b7d1dda1975d.md) was needed because that proposed mechanism was recorded after the pack was generated. Its suggestion is rederived here rather than assumed.

## Plan

1. [x] **Construct the actual two-copy law and an exact finite paired ledger.** Write \(J=\{i:\theta_i=0\}\), \(Q=\overline\Phi\), \(U=Q^{-1}(q/2)\), and \(t_k=Q^{-1}(qk/(2N))\). Initially take \(U\geq1\). On one probability space draw independent vectors \(X,X'\sim N_N(0,\Sigma)\), with the generating covariance \(\Sigma\), and for \(0\leq\alpha<\pi\) put
   $$
   Z(\alpha)=X\cos\alpha+X'\sin\alpha,\qquad
   T^\pm(\alpha)=\theta\pm Z(\alpha).
   \tag{R1}
   $$
   Each arm has exactly the original law, for singular as well as nonsingular \(\Sigma\). Let \(r_\pm(\alpha)\) be the actual ordinary-BH largest ranks, not selected population roots or forced-zero substitutes. Define
   $$
   v_h(\alpha)=\#\{i\in J:|Z_i(\alpha)|\geq t_h\},\quad
   a_h(\alpha)=v_h(\alpha)/h\ (1\leq h\leq N),\quad a_0=0,
   $$
   $$
   L_h(\alpha)=\mathbf1\{r_+(\alpha)\leq h\}
                  +\mathbf1\{r_-(\alpha)\leq h\},\quad 0\leq h<N.
   $$
   Check, including \(r_\pm=0\), that the paired FDP is
   $$
   f_*(\alpha)=\frac{a_{r_+(\alpha)}(\alpha)+a_{r_-(\alpha)}(\alpha)}2
   =a_N(\alpha)+\frac12\sum_{h=0}^{N-1}
      (a_h(\alpha)-a_{h+1}(\alpha))L_h(\alpha).
   \tag{R2}
   $$
   The first equality uses the fact that the null absolute statistics are identical on the two arms, while their rejection thresholds can differ. The second is finite telescoping, with the \(h=0\) term retained.

   Cut the quotient circle \(\mathbb R/(\pi\mathbb Z)\) at every root of \(\theta_i\pm Z_i(\alpha)=\pm t_k\). Conditional on \(X,X'\), this gives finitely many open cells \(I_e\), of lengths \(\ell_e\), on which all ranks and counts in (R2) are constant. Handle coincident roots and tangencies by the actual non-strict BH convention; do not perturb a tie into a different rank. Denote these constants by \(a_{e,h},L_{e,h}\), and put
   $$
   w_{e,h}=\frac{\ell_e}{2}(a_{e,h}-a_{e,h+1})L_{e,h},\quad
   d_{e,h}=(w_{e,h})_+,\quad s_{e,h}=(-w_{e,h})_+.
   \tag{R3}
   $$
   Prove the exact normalization identities
   $$
   A=\frac1\pi\sum_e\ell_e f_{*,e},\qquad
   B=\frac1\pi\sum_e\ell_e a_{e,N},\qquad
   \pi(A-B)=D-S,
   \tag{R4}
   $$
   where \(D=\sum d_{e,h}\), \(S=\sum s_{e,h}\). By Fubini and (R1), \(\mathbb EA=\operatorname{FDR}_{\rm BH}^{(2)}\) and
   $$
   \mathbb EB=\frac1{\pi N}\int_0^\pi\sum_{i\in J}
          \Pr(|Z_i(\alpha)|\geq U)\,d\alpha=q|J|/N.
   \tag{R5}
   $$
   This \(B\) is a fixed-threshold null-count statistic, not the FDR of a purported independent reference BH procedure. Its expectation needs no independence of nulls, conditional phases, or radii. Its conditional value may be close to one.

2. [x] **Mandatory finite-array gate: specify and test the pooled transport cost.** Refine the circular cells if necessary. For vertices \(u=(e,h)\), \(v=(f,g)\), fix the cost
   $$
   c_{uv}=\min\left\{1,
       \sup_{\alpha\in I_e,\,\beta\in I_f}\sin^2(\alpha-\beta)
       +\frac{(t_{h+1}-t_{g+1})^2}{1+U^2}\right\}.
   \tag{R6}
   $$
   The angular part measures the residual variance of a Gaussian rotation; the other part measures threshold displacement. These choices, including their coefficients, are fixed for this plan. They are not to be multiplied by a fitted factor to recover the target constant after testing. The masses in (R3), and consequently this whole optimization, retain all amplitudes, means and both complete rank paths.

   Let \(\gamma_{uv}\geq0\) range over **all** subcouplings with \(\sum_v\gamma_{uv}\leq d_u\) and \(\sum_u\gamma_{uv}\leq s_v\). Permit mass from any null-count layer to use any sink; do not preserve an anchor-null label. Define the finite LP
   $$
   C_{\mathcal P}=\min_\gamma\left\{
         D-\sum_{u,v}\gamma_{uv}+\sum_{u,v}c_{uv}\gamma_{uv}\right\}.
   \tag{R7}
   $$
   Derive its dual
   $$
   C_{\mathcal P}=\max\left\{\sum_u\psi_u d_u-\sum_v\varphi_v s_v:
     0\leq\psi_u,\varphi_v\leq1,\quad \psi_u-\varphi_v\leq c_{uv}\right\}.
   \tag{R8}
   $$
   Thus every dual-feasible pair gives a finite obstruction to a proposed transport upper bound. Check \(D-S\leq C_{\mathcal P}\leq D\), prove monotonicity under common cell refinement, and define \(C_*\) by the decreasing refinement limit. For each fixed finite array, the limit must agree with transport of the piecewise constant charge densities with the pointwise version of (R6). No dimension-uniform mesh error is assumed. In particular
   $$
   A\leq B+C_*/\pi.
   \tag{R9}
   $$
   This is a stronger, nonnegative transport cost, not a definition of \(\pi(A-B)\): a matched unit still pays its angular/threshold cost, a unit without a sink pays one, and negative total excess does not force zero cost.

   Perform the following finite checks before proceeding. They concern (R2)--(R9) and the usefulness of the specified cost, not numerical proof of the conjecture.
   - For \(N=1\), check arbitrary conditional sinusoid amplitude, including amplitude much larger than \(U\). With a null, (R2) gives \(f_*=a_N\), all \(w\) vanish, and \(C_*=0\); without a null FDP vanishes. This rules out an erroneous deterministic \(qU\) bound on conditional \(A\) or \(B\).
   - For \(N=2,3\), compare direct sorted-p-value BH to (R2) on each exact arc cell for all null labelings, equal and unequal boundary ranks, rank holes, \(R=0\), coincident roots and tangencies. Check primal/dual feasibility and objective equality on bounded explicit examples: independent nulls, identical and antipodal nulls, an alternative with large mean, and a mixed-sign correlation Gram matrix. The paired ledger must remain valid when a single boundary changes both ranks by different amounts.
   - In the rank-one staircase of [A single-null Gaussian staircase rules out the null-proportion sharp budget](../ideas/idea_310317024935.md), use \(X=Z\mathbf1\), \(X'=W\mathbf1\), \(\theta_1=0\), \(\theta_{j+1}=-2t_j\), and its specified \(N=\lceil q/Q(2U)\rceil\). Derive the circle cells from the exact largest-rank counts, retaining the \([U,2U]\) strip and both sign branches outside it. Compute the ledger and a feasible pooled coupling, or a dual obstruction. Require an analytic coarse estimate \(\mathbb EC_*\leq Cq(1+U)\) for this family with a numerical \(C\) independent of \(U,N\); a few bounded deterministic cases only diagnose the algebra. There is no proposed extra \(1/N\) factor. A superlinear-in-\(U\) obstruction to this coarse estimate fails this candidate tool, even though the family's FDR is at most \(q\).
   - Check the same coarse scale on independent arrays with growing \(N\), including the all-null case. Conditional radii remain dependent for general \(\Sigma\). A cost that already incurs an unavoidable harmonic loss on independence is rejected before the general argument.

   The small-dimensional arc and LP checks can be short deterministic local calculations. Prove the growing-family conclusions analytically; substantial searches or simulations, if justified, run only on UC Davis. Do not form the enormous staircase LP locally. If this gate fails, record the exact family, primal/dual witness and failed inequality and stop this plan.

3. [ ] **Construct the genuinely new Gaussian transport bound.** Only after step 2 survives, construct explicit feasible subcouplings in (R7), stable under refinement, rather than claiming the desired value for the optimizer. Equivalently, prove a capacitated Hall bound for the positive and negative **pooled** measures from (R3), with a specified matching rule and an explicit accounting of paid transport and unmatched mass. All-test rank paths control the gates; alternatives cannot be optimized independently on the two arms. The bound must close also for \(J=[N]\), \(J=\varnothing\), very small null fraction, and arbitrarily many primary alternatives.

   Two concrete evaluation tools are available to derive, not assumed theorems. First, at each angle \((Z(\alpha),\dot Z(\alpha))\) consists of independent centered Gaussian vectors with covariance \(\Sigma\). Derive the marked finite-circle coarea formula for every wall \(\theta_i\pm Z_i=\pm t_k\), with density \(\phi(\pm t_k-\theta_i)\), velocity factor \(|\dot Z_i|\), and the **actual conditional law** of all remaining coordinates and velocities. Use it to evaluate the paid rank-transition charges of an exhibited flow. Both alternative and null walls enter that accounting. A componentwise absolute-value sum losing the common ranks is not an admissible replacement.

   Second, if \(R_i^2=X_i^2+(X_i')^2\), derive
   $$
   \mathbb E\exp\left(-\tfrac12\sum_i z_i R_i^2\right)
       =\det(I+\Sigma\operatorname{Diag}(z))^{-1},\qquad z_i\geq0,
   \tag{R10}
   $$
   directly from two Gaussian quadratic integrals. This and the marginal Rayleigh tail \(\Pr(R_i\geq x)=e^{-x^2/2}\) can evaluate joint capacity bounds; neither makes the radii independent or supplies MTP2. Any additional entropy, determinant, or Gaussian rearrangement inequality carrying the flow estimate must be proved with its precise hypotheses, or the plan remains incomplete. Do not invoke a dimension-dependent Gaussian perimeter bound as a dimension-free conclusion.

   The concrete analytic obligation for this fixed transport cost is to prove numerical \(C,U_0\), independent of \(N,\theta,\Sigma\), such that
   $$
   \mathbb EC_*
     \leq \frac{\pi qU}{2\sqrt{2\pi}}+C\pi q(1+\log U),\qquad U\geq U_0.
   \tag{R11}
   $$
   A uniform \(o(qU)\) replacement for the displayed remainder is also sufficient if proved explicitly. (R11) is an unproved obligation for an independently specified LP, not a black-box assumption. Producing only (R2), (R8), (R9), or a restatement of (R11) as a lemma is failure at this step. Success requires an actual flow/capacity argument with its Gaussian expected cost estimated separately. The ledger's factor \(1/2\) alone does not prove the leading coefficient in (R11).

4. [ ] **Remove auxiliary regularization without changing the law or quantifiers.** Establish step 3 first for positive-definite \(\Sigma\) if needed. For a fixed finite endpoint, couple \(\Sigma_\eta=(1-\eta)\Sigma+\eta I\) to the original vector and show convergence of actual BH FDP away from its finitely many threshold walls. Every individual statistic has a continuous unit-variance marginal, so those walls have zero probability, even if the endpoint is singular. Bounded FDP then transfers the uniform FDR bound from (R9)--(R11). It is not necessary to assume that endpoint crossing multiplicities or \(C_*\) themselves are continuous: use (R11)'s uniformity before taking the fixed-model limit. Treat identical coordinates and simultaneous circle crossings directly in step 2. The circle construction is not a rank-two Gaussian factor reduction, and no conditional amplitude is bounded by one.

5. [ ] **Close exactly the original uniform statement.** Combine (R5), (R9), and the proved (R11) to obtain
   $$
   \operatorname{FDR}_{\rm BH}^{(2)}
       \leq q|J|/N+\frac{qU}{2\sqrt{2\pi}}+Cq(1+\log U)
       \leq q+\frac{qU}{2\sqrt{2\pi}}+Cq(1+\log U).
   \tag{R12}
   $$
   There is deliberately no null-fraction multiplier on the transport term or its remainder. Verify from elementary normal-tail estimates that \(U/\sqrt{2\log(1/q)}\to1\) and \((1+\log U)/U\to0\). Constants and the small-\(q\) cutoff must be independent of the entire finite model before taking the supremum defining \(F_2\). This yields exactly the target constant \(1/(2\sqrt\pi)\). If any earlier gate fails, do not execute this closing step or claim a completed proof.

## Verification

The independently checkable finite outputs are the actual arc table, both maximal ranks, the signed aggregate ledger (R2)--(R4), and the primal/dual transport witnesses (R7)--(R8). These expose sign, tie, normalization and rank-jump errors before any asymptotics. The baseline expectation (R5) is a direct marginal/Fubini calculation for a defined statistic. In particular its \([0,\pi)\) average has factor \(1/\pi\), while the paired FDP has the internal factor \(1/2\); neither a second half-factor nor an independent-BH reference is inserted.

The first substantive obstruction test is the coarse Gaussian cost of the **fixed** LP on the staircase and independence, not a per-null sharp inequality. The principal unproved new result is the exhibited global flow with (R11); this can be stronger than the target and can fail without refuting it. It must be checked using the original means and covariance and actual largest ranks. The determinant identity, Rayleigh marginals, coarea identities and finite LP duality do not by themselves imply (R11). No all-null Simes inequality, covariance convexity, MTP2, positive signed-face ordering, or nonnegative cluster expansion is assumed.

Only (R11) together with the identities closes (R12). A failure is recorded as a method obstruction with a frozen finite-family witness or an explicit unresolved capacity inequality. Preserve all verified identities without promoting the unchanged draft target to proved or falsified. New approval, changes of settings, or loop advancement are outside this plan.

## Assumed definitions

All definitions used are approved: [Definition (Gaussian multiple-testing model)](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [Definition (ordinary Benjamini-Hochberg step-up procedure)](../definitions/benjamini_hochberg_step_up.md), [Definition (false discovery rate)](../definitions/false_discovery_rate.md), and [Definition (uniform worst-case Gaussian BH false discovery rate)](../definitions/gaussian_worst_case_bh_fdr.md).

No draft definition or unproved dependency is assumed. The motivating ideas, prior rank identities, proposed transport estimate and determinant/coarea tools are to be derived or tested in this plan. In particular (R11) is not an assumed dependency, and no one-sided sharp-bound claim is imported.

## Difference from failed plans

- [Signed Gaussian face budget for the unrestricted two-sided BH upper bound](plan_two_sided_signed_face_budget_20261104.md): local opposite-sign face ordering is not used. Two actual antipodal ranks share one global null-count ledger; all signs survive until pooled transport. The finite transport and its costs are explicit, so the missing cancellation is a testable new obligation rather than a named face-sum estimate.
- [Centered folded-tail null-noise interpolation and a signed completion test](plan_two_sided_null_noise_folded_completion_20261104.md): the generating covariance is never paired with an arbitrary dual correlation matrix. Both copies always have the actual \(\Sigma\), and no diagonal covariance-completion support function is used. The LP dual varies scalar transport potentials on actual arc cells, not a second covariance.
- [Fixed within-label covariance blocks and nuclear transport of signed BH corners](plan_two_sided_fixed_label_blocks_20261104.md): there is no cross-block nuclear norm, residual-variance interpolation, or unproved sign of the integrated \(G_{ax}\) score. The proposed transport joins angular/rank masses of the actual BH procedures. Its Gaussian expectation must include all walls and also handle the all-null case; fixing within-label blocks is not treated as sufficient.
- [Finite signed Gaussian clusters and reciprocal-rank charging for two-sided BH](plan_two_sided_signed_forest_rank_cells_20261104.md): the false \(|J|/N\) sharp budget is discarded. Only the explicitly computed baseline carries that fraction. The source/sink ledger is pooled over all nulls before transport, while every gate uses both complete all-test rank paths. The single-null staircase is a mandatory coarse-cost test and may use a global order-\(qU\) capacity; no order-\(qU/N\) assertion is imposed. The completed forest/cumulant identities are not repackaged as a positive capacity theorem.

## Failure

The plan fails at step 3. The finite ledger and LP are valid; the single-null staircase and all independent arrays pass the coarse gates proved below. No dimension-uniform angular flow or capacitated Hall estimate establishing (R11) has been obtained. The available rank-only flow leaves an unmatched term controlled by the original FDR, so using it in (R9) is circular. This is an unresolved proof obligation, not a counterexample to (R11) or the target. Steps 4 and 5 were not executed; the target asset is untouched.

### Exact ledger and finite/continuum transport

For independent copies with the actual covariance \(\Sigma\), \(X\cos\alpha+X'\sin\alpha\) is centered jointly Gaussian with covariance \(\Sigma\), also when \(\Sigma\) is singular. Both arms therefore have the original model law. This asserts neither coordinate independence nor a bound on conditional amplitudes.

The largest qualifying BH rank equals its rejection count: more than \(r\) p-values below \(qr/N\) would make rank \(r+1\) qualify. Thus the null FDP is exactly \(a_r\), also for \(r=0\) because \(a_0=0\). The elementary identity
$$
a_r=a_N+\sum_{h=0}^{N-1}(a_h-a_{h+1})\mathbf1\{r\leq h\}
$$
for every \(0\leq r\leq N\), averaged for the two actual ranks, proves (R2), including ties. Each nonconstant wall \(A\cos\alpha+B\sin\alpha=b\) has finitely many roots. An identically equal wall is retained as a permanent non-strict inequality, without adding cuts. Coincident roots are one cut; tangencies create no false sign change. Under \(\alpha\mapsto\alpha+\pi\), the arms swap and the aggregate ledger is unchanged. On every resulting open cell the ranks and counts are constant. Endpoint values follow the actual non-strict rule and do not change the integrals. Integration proves (R3)--(R4), with \(w=d-s\). Bounded FDP permits Fubini, proving \(\mathbb EA=\operatorname{FDR}\); marginal standard normality gives \(\mathbb EB=q|J|/N\). No independent reference BH procedure is introduced.

For (R8), write (R7) as \(D-\max_\gamma\sum(1-c_{uv})\gamma_{uv}\). The capacitated matching maximum has dual
$$
\min_{a_u,b_v\geq0}\left\{\sum_u a_ud_u+\sum_v b_vs_v:
a_u+b_v\geq1-c_{uv}\right\}.
$$
The primal is feasible and bounded. Finite LP duality applies; since \(0\leq1-c\leq1\), truncating \(a,b\) above one preserves feasibility. Substitution \(\psi=1-a,\varphi=b\) gives exactly (R8). The zero coupling proves \(C_{\mathcal P}\leq D\); total matched mass at most \(S\) proves \(D-S\leq C_{\mathcal P}\). The objective is nonnegative.

Refinement splits each signed mass proportionally to cell length without changing its sign. Lifting any coarse coupling with these proportions decreases its supremum costs, proving monotonicity. Define the continuum problem using the piecewise constant measures on circle times layer and the pointwise cost. Any discrete coupling lifts with no greater pointwise cost. Conversely, projecting any continuum coupling onto a partition of maximum cell diameter \(\delta\) increases its cost by at most \(2\delta\min(D,S)\), because \(|(\sin^2)'|\leq1\). Hence, for the continuum infimum \(C_{\rm cont}\),
$$
C_{\rm cont}\leq C_{\mathcal P}\leq C_{\rm cont}+2\delta\min(D,S).
$$
The cofinal decreasing refinement limit therefore equals \(C_{\rm cont}=C_*\) for each fixed finite array. This is not a dimension-uniform mesh assertion. Passing \(D-S\leq C_{\mathcal P}\) to the limit proves (R9).

### Small finite checks and a displayed LP witness

For \(N=1\) with a null, \(r_+=r_-=\mathbf1\{|Z|\geq U\}\), so the only possible charge is \(-a_1L_0/2=0\), even at equality. Thus \(C_*=0\) for arbitrary conditional amplitudes. Without a null, FDP and ledger vanish. For a null sinusoid of amplitude \(R>U\), \(A=B=2\arccos(U/R)/\pi\), which tends to one as \(R/U\) grows. No deterministic conditional \(O(qU)\) bound is used.

Short deterministic local calculations at \(q=0.1\) checked 48 arrays on all 332 exact open arc cells, using roots
\(\operatorname{atan2}(B,A)\pm\arccos(b/\sqrt{A^2+B^2})\). For each \(N=2,3\), every null mask was checked; null means were zero and alternative means \(8(-1)^i\), with indices \(i=0,\ldots,N-1\). Four choices of copies, truncated to \(N\), were:

- \((X,X')=((3,1,2),(0.7,2.8,-3))\), admissible under \(\Sigma=I\);
- \((X,X')=((4,4,4),(1,1,1))\), for identical coordinates;
- \(X_i=4(-1)^i,\ X'_i=(-1)^i\), for antipodal coordinates;
- \(X_i=3v_{i1}+1.5v_{i2},\ X'_i=-1.8v_{i1}+2.7v_{i2}\), with \(v_1=(1,0),v_2=(-0.7,\sqrt{0.51}),v_3=(0.2,-\sqrt{0.96})\), and the mixed-sign correlation Gram matrix \(\Sigma_{ij}=v_i^{\mathsf T}v_j\).

On every cell, sorted-p-value BH, largest qualifying count, direct FDP and (R2) agreed; the largest ledger discrepancy was zero at machine precision. Finite primal and dual objectives agreed within \(10^{-8}\). These bounded calculations diagnose algebra; they are not expectation proofs. Identical and antipodal fixtures include rank holes and simultaneous jumps. The explicit p-vector \((0.075,0.075)\) at \(q=0.1,N=2\) fails rank one and qualifies at rank two.

A shared null wall with unequal jumps is \(N=2,\theta=(0,2),X=(-1,0.3),X'=(U,-0.2)\). At \(\alpha=\pi/2\), the null equals \(U\), and the alternative statistics are \(1.8,2.2\), with \(U<1.8<t_1<2.2\). The actual rank pair changes from \((0,1)\) to \((2,2)\); equality already gives \((2,2)\). Its jumps have sizes two and one. Tangency fixtures \(X=(U,4,\ldots,4),X'=0,\theta=0\), in dimensions two and three, include the tangent null exactly at its peak and exclude it on adjacent cells. The non-strict ledger identity holds at the isolated endpoint as well.

One displayed LP fixture is \(N=2,\theta=0,X=(3,1),X'=(0.7,2.8)\). Number cells from zero. Successive endpoints, rounded for display, are
$$
(0,\ 0.2432057142,\ 0.3767400561,\ 1.1104248904,\
1.2367722104,\ 2.0788047167,\ 2.2123390586,\
2.3632843097,\ 2.4896316297,\ \pi).
$$
Their common ranks are \((1,2,2,2,1,0,0,0,1)\), and count pairs \((v_1,v_2)\) are
\((1,1),(1,2),(2,2),(1,2),(1,1),(0,1),(0,0),(0,1),(1,1)\).
All nonzero charges lie at \(h=1\). Positive cells \(0,4,8\) have masses
\((0.1216028571,0.4210162531,0.3259805119)\); negative cells \(5,7\) have masses
\((0.06676717095,0.06317366000)\), exactly half their cell lengths before rounding. The supremum cost matrix is
$$
\begin{pmatrix}
0.9315032557&0.7274374742\\
0.6856168757&0.9022765309\\
0.7633779621&0.4929104181
\end{pmatrix}.
$$
Match the first sink completely from the second positive vertex and the second sink completely from the third positive vertex; all other entries vanish. Source capacities suffice. The dual \(\psi=(1,1,1)\), \(\varphi=(1-c_{10},1-c_{21})=(0.3143831243,0.5070895819)\) is feasible since the selected costs minimize their columns. Both objectives equal \(0.8155744455\), whereas \(D-S=0.7386587912\). Exact masses and costs are specified by the root formulas and (R3),(R6); the displayed numbers are diagnostics. This explicitly distinguishes transport cost from signed excess.

### Exact staircase counts and a uniform single-null budget

The native read of [A single-null Gaussian staircase rules out the null-proportion sharp budget](../ideas/idea_310317024935.md) was needed to verify the finite family and indexing, not to import its prior proof. Write its scalar circle coordinate as \(s\). Its alternatives are \(s-2t_j\), \(j=1,\ldots,N-1\). For every real \(s\), set
$$
n_h(s)=\mathbf1\{|s|\geq t_h\}+
\sum_{j=1}^{N-1}\left(\mathbf1\{s\leq2t_j-t_h\}
                        +\mathbf1\{s\geq2t_j+t_h\}\right).
$$
Exactly,
$$
r_+(s)=\max(\{0\}\cup\{h:n_h(s)\geq h\}),\qquad r_-(s)=r_+(-s).
$$
Both sign branches outside \([U,2U]\) remain present. Cut the sinusoid at every preimage of \(\pm t_h\) and \(\pm(2t_j\pm t_h)\) within its amplitude range. These are the complete finite cells; no population-rank approximation replaces the largest qualifying ranks.

Put \(k(s)=\min\{h:|s|\geq t_h\}\), or \(N+1\) if empty. For \(k\leq N\), the only possible negative density is \(-L_{k-1}/(2k)\) at \(h=k-1\); the positive densities are \(L_h/[2h(h+1)]\) at \(k\leq h<N\). All other entries vanish; when \(k=N+1\) the ledger is zero. This computes the exact staircase ledger using both sign branches without building its enormous LP.

For any model, let \(m=|J|\) and \(v_{h+1}=v_h+b_{h+1}\), \(b_{h+1}\geq0\). For \(h\geq1\),
$$
(a_h-a_{h+1})_+
=\left(\frac{v_h}{h(h+1)}-\frac{b_{h+1}}{h+1}\right)_+
\leq\frac{v_h}{h(h+1)}.
$$
The \(h=0\) charge is nonpositive, and \(L_h/2\leq1\). Marginal normality therefore gives
$$
\mathbb EC_*\leq\mathbb ED
\leq\frac{\pi qm}{N}\sum_{h=1}^{N-1}\frac1{h+1}
=\frac{\pi qm}{N}(H_N-1).
$$
For the staircase \(m=1\), \(H_N-1\leq N\) proves \(\mathbb EC_*\leq\pi q\leq\pi q(1+U)\), at its exact \(N=\lceil q/Q(2U)\rceil\). The zero subcoupling is a feasible primal witness sufficient for this coarse estimate. This is not the refuted sharp null-proportion budget: the general estimate retains the harmonic factor, with no sharp per-null conclusion.

### A rank-pooled flow and the independent-array coarse gate

The following deterministic flow applies at a fixed angle. For one actual arm rank \(r<N\), put
$$
b_h=(a_h-a_{h+1})\mathbf1\{r\leq h\},\qquad
x_h=t_{h+1}/\sqrt{1+U^2},\qquad \delta=a_N-a_r.
$$
Add artificial signed mass \(\delta\) at layer \(r\). The resulting measure has total zero and prefix \(a_N-a_{h+1}\) through layer \(h\geq r\). Send that prefix along the finite layer chain toward its deficit. Decompose the chain flow into source-to-sink paths; every path is monotone, so its length equals endpoint distance. The ordinary distance cost is
$$
W_r=\frac1{\sqrt{1+U^2}}\sum_{k=r+1}^{N-1}
 |a_k-a_N|(t_k-t_{k+1}).
$$
If \(\delta\geq0\), discard paths starting at the artificial source, freeing sink capacity. If \(\delta<0\), discard paths ending at the artificial sink and pay one for the resulting unmatched real mass, at most \(-\delta\). Thus, for the metric \(d(h,g)=\min\{1,|x_h-x_g|\}\), the one-arm unbalanced cost is at most \((a_r-a_N)_++W_r\). The case \(r=N\) has zero ledger; at \(r=0\), the same prefix formula holds with \(a_0=0\) and \(\delta\geq0\).

The original squared cost is not a metric, so its signed-measure subadditivity cannot be presumed when merging arms. For the metric \(d\), the finite dual reduces to
\(\sup_f\sum_h f(h)b_h\), over \(0\leq f\leq1,\ |f(h)-f(g)|\leq d(h,g)\). Indeed, extend feasible sink potentials by \(f(h)=\min\{1,\inf_g(\varphi(g)+d(h,g))\}\). This is Lipschitz, dominates \(\psi\) at sources and is at most \(\varphi\) at sinks; conversely take \(\psi=\varphi=f\). This support function is positively homogeneous and subadditive. Apply it to the two half-ledgers and note that at the same angle the original cost is \(\min\{1,|x_h-x_g|^2\}\leq d(h,g)\).

The finite chain/quantile algorithm uses sums, positive parts and minima of capacities, hence is Borel measurable in the angle. Integrating its same-angle couplings, then merging the two arms by the metric argument, gives the genuine pooled bound
$$
C_*\leq\int_0^\pi\left[
\frac12\sum_{\sigma\in\{+,-\}}(a_{r_\sigma}-a_N)_+
+\frac1{\sqrt{1+U^2}}\sum_{k=1}^{N-1}
 |a_k-a_N|(t_k-t_{k+1})\right]\,d\alpha.
\tag{F1}
$$
Only nonnegative rank gates were dropped from this upper bound, not from the ledger itself.

Now assume explicitly \(\Sigma=I\). Joint Gaussianity then gives independent coordinates; all null p-values are independent uniforms and independent of all alternative p-values. Set \(p=qm/N\). Since \(v_k\) is binomial of mean \(pk\),
$$
\mathbb E|a_k-a_N|
\leq\min\{2p,\sqrt{p/k}+\sqrt{p/N}\}
\leq\min\{2p,2\sqrt{p/k}\}.
\tag{F2}
$$
The two bounds use, respectively, nonnegativity with equal means and the two binomial variance bounds plus triangle inequality. They do not require \(v_k,v_N\) to be independent.

The independent-BH FDR identity needed here is proved separately. Force null \(i\)'s p-value to zero, with largest rank \(R^i\geq1\). If \(p_i\leq qR^i/N\), rank \(R^i\) still qualifies after restoring \(p_i\), and increasing a p-value cannot increase the rank; hence \(R=R^i\) and \(i\) is rejected. Conversely, if \(i\) is rejected at rank \(R\), forcing it to zero changes no order statistic beyond \(R\) and cannot create a larger qualifying rank, so \(R^i=R\). Therefore
$$
\frac{\mathbf1\{i\text{ rejected}\}}{R\vee1}
=\frac{\mathbf1\{p_i\leq qR^i/N\}}{R^i}.
$$
Here \(R^i\) is independent of uniform \(p_i\), giving conditional expectation \(q/N\). Summing proves \(\mathbb Ea_{r_\pm}=p\). These auxiliary forced-zero ranks are used only for this expectation proof; all transport ranks remain the actual two original ranks. Marginal Gaussianity alone would not justify the independence step.

Write \(\phi(t)=(2\pi)^{-1/2}e^{-t^2/2}\). The Mills upper bound \(Q(t)/\phi(t)\leq1/t\) yields
$$
t_k-t_{k+1}\leq\frac{\log(1+1/k)}U\leq\frac1{Uk}.
$$
For \(p>0\), split at \(\lfloor1/p\rfloor\), bound the first part by a harmonic sum, and bound the remainder by the integral of \(k^{-3/2}\). Since \(p\leq q\leq2Q(1)<e^{-1}\),
$$
\sum_{k=1}^{N-1}\frac{\min(2p,2\sqrt{p/k})}{k}
\leq2p\log(1/p)+8p
\leq2q\log(1/q)+8q.
$$
For \(p=0\), every ledger mass is zero. The Mills lower bound
\(Q(U)\geq U\phi(U)/(1+U^2)\) gives \(q\geq\phi(U)/U\) for \(U\geq1\).
Using \(\log U\leq(U^2-1)/2\) and \(\log(2\pi)<2\), it follows that \(\log(1/q)\leq3U^2/2\). Thus (F1)--(F2), and \((a_r-a_N)_+\leq a_r\), prove for every dimension, every mean vector and \(\Sigma=I\),
$$
\mathbb EC_*
\leq\pi p+\frac{\pi[2q\log(1/q)+8q]}{U\sqrt{1+U^2}}
\leq(4+4\sqrt2)\pi q<10\pi q,\qquad U\geq1.
\tag{F3}
$$
This includes growing all-null independent arrays. A read-only independent check confirmed the artificial-mass prefixes, the cases \(r=0,N\), the metric step needed to merge arms and the independence calculation. No harmonic-loss obstruction for the actual pooled LP was found.

### The remaining noncircular Gaussian obligation

For arbitrary \(\Sigma\), (F1)'s first expected term is controlled here only by
$$
\frac12\sum_\sigma\mathbb E(a_{r_\sigma}-a_N)_+
\leq\operatorname{FDR}_{\rm BH}^{(2)}.
$$
The independent leave-one-out conditional-uniform step is unavailable under dependence. Even if the second term of (F1) were bounded, substituting
\(\mathbb EC_*/\pi\leq\operatorname{FDR}+\text{remainder}\) into (R9) gives only
\(\operatorname{FDR}\leq q|J|/N+\operatorname{FDR}+\text{remainder}\), a circular inequality. Moreover (F2)'s binomial variances do not extend to arbitrary covariance. Using only equal marginal means gives \(2p\) and a threshold-length dependence on \(t_1-U\), which is not uniform in dimension. Neither defect is a lower bound on the optimal LP.

What is required is an additional feasible angular/rank flow, or a proved capacitated Hall inequality for the actual jointly gated signed measures, that bounds both unmatched mass and paid cost under arbitrary covariance with (R11)'s leading coefficient and a uniform smaller-order remainder. No such inequality was obtained; determinant identities, Rayleigh marginals and finite LP duality do not supply it. Promoting that missing assertion to a lemma would only rename the central obligation. The passed finite, staircase and independence gates therefore do not establish the unrestricted budget, and do not refute it.
