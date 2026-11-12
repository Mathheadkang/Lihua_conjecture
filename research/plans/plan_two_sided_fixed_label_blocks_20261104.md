---
type: plan
title: Fixed within-label covariance blocks and nuclear transport of signed BH corners
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
inspired_by: [idea_f8434ba89f54, idea_63d2ef1d26bf, idea_8ccb5a5a1c27, idea_7d718e40cb44, idea_45ea077b792d]
adapts: []
---

## Goal

Target: [Sharp uniform upper-bound target for two-sided Gaussian BH](../assets/gaussian_bh_two_sided_sharp_upper.md).

Prove the unchanged unrestricted upper bound by a precisely constrained repair of the signed-corner method. Keep the independent-null reference path, but permit a dual covariance to vary only its null/alternative cross block: both complete within-label covariance blocks must equal those of the generating endpoint. This gives an explicit whitened nuclear-norm cost. It is a stronger object than the physical scalar FDR increment, and its sharp bound must be proved or refuted; no such bound is assumed here.

The two recorded divergent dual matrices fail this new admissibility condition. This algebraic fact removes those particular witnesses, but does not prove a uniform budget or rule out a replacement witness. A mandatory first test evaluates the actual new cost, including its cross-block nuclear term, on the recorded families before any general estimate is used. All new analytic predictions below remain provisional until execution and independent checking.

Library searches for `Gaussian BH two-sided`, `Gaussian covariance completion block constrained`, and `signed Gaussian boundary block covariance nuclear norm` returned no results. No library statement is cited and no library proof is adapted. The additional native read of [Proof note and bounded independent check of the completion obstruction](../ideas/idea_63d2ef1d26bf.md) was needed because fixing only the alternative block leaves its one-sided negative-null witness admissible. Its negative null means are outside this target's true-null class; it is a method diagnostic, not a two-sided counterexample.

## Plan

1. [x] **Reconstruct the physical identity without changing its reference law.** Initially fix a finite positive-definite endpoint covariance, put $J=\{i:\theta_i=0\}$ and $A=[N]\setminus J$, and write $P=\operatorname{Diag}(\mathbf1_J)$ and $Q=I-P$. For independent $G\sim N(0,\Sigma)$ and $E\sim N(0,I)$ use

   $$
   T_r=\theta+(Q+rP)G+\sqrt{1-r^2}\,PE,\qquad
   C_r=(Q+rP)\Sigma(Q+rP)+(1-r^2)P,\qquad 0\le r\le1.
   $$

   With the fixed true-null labels, let $f_q$ be the actual ordinary-BH FDP and $H(r)=\mathbb Ef_q(T_r)$. Reprove the forced-zero identity, including largest qualifying ranks and ties, to get the exact reference value $H(0)=q|J|/N$: every null at $r=0$ is independent of every other coordinate. The null block at $r=0$ is $I_J$, not the generating block $\Sigma_{JJ}$.

   Reconstruct the four-cell signed threshold stencils at $\pm t_k$, where $t_k=\overline\Phi^{-1}(qk/(2N))$, and their exact conditional Gaussian corner integrals $L_{ij}(r)$. Derive density differentiation and integration by parts, retaining the four signs and the actual largest-rank gates. Set $M_{ii}=0$, $M_{ij}=2rL_{ij}$ for $i,j\in J$, $M_{ij}=L_{ij}$ for a cross pair, and $M_{ij}=0$ for $i,j\in A$, and define $K=\frac12\int_0^1M(r)\,dr$. Establish

   $$
   H(1)=q|J|/N+\operatorname{tr}(\Sigma K),\qquad K_{AA}=0.
   \tag{P}
   $$

   Treat $J=\varnothing$ and $N=1$ directly. These are calculations to reprove, not statements imported as approved dependencies from a failed plan.

2. [x] **Derive the repaired completion and its explicit cost.** Write $S=\Sigma_{JJ}$ and $B=\Sigma_{AA}$ for the generating endpoint blocks. Define

   $$
   \mathfrak C_{S,B}(K)=\max\{\operatorname{tr}(\Gamma K):\Gamma\succeq0,\ \Gamma_{JJ}=S,\ \Gamma_{AA}=B\}.
   \tag{C}
   $$

   These fixed blocks belong to the dual optimization only; they do not replace the reference covariance in step 1. For positive-definite $S,B$, whiten the cross block to prove that every feasible $\Gamma$ has $\Gamma_{JA}=S^{1/2}WB^{1/2}$ with $\|W\|_{\mathrm{op}}\le1$. With

   $$
   G_0=S^{1/2}K_{JJ}S^{1/2},\qquad Z=S^{1/2}K_{JA}B^{1/2},
   $$

   prove the exact finite-dimensional formula

   $$
   \mathfrak C_{S,B}(K)=\operatorname{tr}(G_0)+2\|Z\|_*\ \ge\ \operatorname{tr}(\Sigma K).
   \tag{N}
   $$

   Here $\|Z\|_*$ is the sum of the singular values, not the norm of an entrywise absolute-value matrix. Derive also the primal form

   $$
   \inf_{D=D^{\mathsf T},\ F=F^{\mathsf T}}
   \left\{\operatorname{tr}(SD)+\operatorname{tr}(BF):
   \begin{pmatrix}D-K_{JJ}&-K_{JA}\\-K_{AJ}&F\end{pmatrix}\succeq0\right\}.
   \tag{B}
   $$

   Check equality directly using a singular-value decomposition $Z=\sum_\ell s_\ell u_\ell v_\ell^{\mathsf T}$ and the PSD factorization $\sum_\ell s_\ell(u_\ell,-v_\ell)(u_\ell,-v_\ell)^{\mathsf T}$ after whitening. The block $D$ is unrestricted symmetric; imposing diagonality or positivity on it would discard the signed null-block contribution and create another relaxation. Handle an empty $A$ by $\mathfrak C_{S,\varnothing}(K)=\operatorname{tr}(SK_{JJ})$, without invoking an unproved Gaussian Simes inequality.

3. [ ] **Evaluate the exact new cost on the obstructions before seeking a sharp budget.** First verify the following algebraic stress test. In an exchangeable $n+n$ array write $S=(1-\rho_0)I_n+\rho_0\mathbf1\mathbf1^{\mathsf T}$, $B=(1-\rho_1)I_n+\rho_1\mathbf1\mathbf1^{\mathsf T}$, let $k_{00}$ be the common off-diagonal $JJ$ entry of $K$, and let $k_{01}$ be its common cross entry. Then (N) is exactly

   $$
   n(n-1)\rho_0 k_{00}
   +2n\sqrt{[1+(n-1)\rho_0][1+(n-1)\rho_1]}\,|k_{01}|.
   \tag{E}
   $$

   Apply (E) to the centered weak-common-gate family in the failed folded-tail plan: $z_N=\sqrt{2c\log N}$, $\rho=\lambda/z_N^2$, null means zero, alternative means $\alpha/z_N$, $\cosh\alpha=2/q-1$, and endpoint correlations $\rho_0=\rho_1=\rho$ with cross correlation $\rho$. Its old witness $\Gamma=\mathbf1\mathbf1^{\mathsf T}$ is inadmissible because both required blocks have off-diagonals $\rho<1$. In particular, the null term in (E) is weighted by $\rho$, rather than by one. Nonetheless the cross term must be evaluated, not declared harmless from witness inadmissibility.

   Prove or refute the needed convergence of the two component sensitivities. Introduce distinct small conditional null and alternative shifts $a,b$ with covariance parameters $x,y,c_*$, and the local largest-root equation

   $$
   \tfrac12e^{-xs^2/2}\cosh(as)
   +\tfrac12e^{-ys^2/2}\cosh((\alpha+b)s)=1/q,
   \quad \operatorname{Var}(a)=x,\ \operatorname{Var}(b)=y,\ \operatorname{Cov}(a,b)=c_*.
   $$

   Use separate $x$ and $c_*$ derivatives to recover $k_{00}$ and $k_{01}$ along $x=r^2\lambda$, $y=\lambda$, $c_*=r\lambda$. The provisional local diagnostic is an averaged physical increment

   $$
   \frac q2\left(\frac{3c_*^2}{\alpha^2}-\frac{x^2}{\alpha\sinh\alpha}\right)
   +o((x+y)^2).
   $$

   Recompute this expansion and its derivatives; scalar FDR convergence alone does not justify covariance-derivative convergence. Establish score domination or a finite-array differentiated calculation, with Gaussian truncation and uniform localization of the largest BH root, before substituting any derivative into (E). The sign of $k_{01}$ also needs proof; do not replace its absolute value by its signed value from a numerical guess. Check the centered independent-alternative case $\rho_1=0$, cross correlation zero, separately: simultaneous reversal of all centered null coordinates should force $K_{JA}=0$, giving (E) equal to the physical increment and reproducing the recorded negative second-order diagnostic.

   Then test the one-sided negative-null family from idea_63d2ef1d26bf as a diagnostic of the completion algebra. Its old $\Gamma=\operatorname{diag}(\mathbf1\mathbf1^{\mathsf T},I_n)$ fails $\Gamma_{JJ}=S$. Reconstruct the corresponding one-sided $K$ and evaluate (E) with $\rho_0=\rho$, $\rho_1=0$, including its potentially nonzero cross term. In this out-of-scope model the physical identity is $H^{(1)}(1)-H^{(1)}(0)=\operatorname{tr}(\Sigma K^{(1)})$; negative null means do not give $H^{(1)}(0)=q/2$. Use the actual conservative independent reference. Require a proved bounded fixed-$q$ cost, rather than transferring the two-sided symmetry cancellation to negative means.

   Also compute (N) for arbitrary-mean two-coordinate models, independent nulls independent of all alternatives, and the regularized centered simplex. For one null and one alternative, (N) reduces to $2|K_{12}|$; no opposite-face ordering is inferred. For the all-null simplex the dual is a singleton and the cost equals $H(1)-q$, so the former free-correlation amplification is absent; its $q$-asymptotics still need proof. If either recorded family yields another divergent fixed-$q$ cost, or another admissible dual witness defeats every proposed universal budget, stop and fail this plan before step 4. Bounded fixed-$q$ tests are necessary diagnostics, not a proof of a small-$q$ bound.

4. [ ] **Construct a signed, covariance-weighted block certificate and prove its trace budget.** Only after step 3 survives, attempt the following precise stronger assertion, with universal finite $C_0,U_0$, for all $U\ge U_0$, $q=2\overline\Phi(U)$, all finite dimensions and means, and every positive-definite generating correlation matrix:

   $$
   \mathfrak C_{S,B}(K)
   \le \frac{qU}{2\sqrt{2\pi}}+C_0q\{1+\log(2+U)\}.
   \tag{T}
   $$

   First handle arbitrary all-null models explicitly. When $A=\varnothing$, $Z$ is empty and (T) is a bound for the physical signed null/null trace itself. Derive that bound from the all-null rank stencils with the same universal constants, or fail this plan at that obligation. The empty nuclear term and an atom factorization provide no bound on this trace. Neither the simplex test nor an unproved general Gaussian Simes assertion may fill this case.

   For nonempty $A$, an executable certificate task is to produce, from the finite signed corner/rank formula, vectors $a_\ell\in\mathbb R^{|J|}$ and $b_\ell\in\mathbb R^{|A|}$, or an absolutely convergent integral of such vectors, satisfying

   $$
   Z=\sum_\ell a_\ell b_\ell^{\mathsf T},\qquad
   \operatorname{tr}(G_0)+\sum_\ell(\|a_\ell\|^2+\|b_\ell\|^2)
   \le \frac{qU}{2\sqrt{2\pi}}+C_0q\{1+\log(2+U)\}.
   \tag{A}
   $$

   The identity for $Z$ and the trace estimate are separate checkable obligations. The PSD block matrix $\sum_\ell(a_\ell,-b_\ell)(a_\ell,-b_\ell)^{\mathsf T}$ then supplies (B), proving (T). Construct the atoms only after integrating the signed path and pairing both null-tail signs with their common actual largest-rank gates. Use the exact four-cell rank/count formula to telescope reciprocal ranks and keep the signed $\operatorname{tr}(G_0)$ available for cancellation with the atom energies. Derive the trace estimate by Gaussian integration and explicit Mills bounds, with the stated coefficient and a remainder independent of dimension, means, and both covariance blocks.

   An SVD proves the algebraic optimization formula (N), but supplies no Gaussian estimate for its trace. It does not by itself complete (A). Conversely, bounding the physical pairing $\operatorname{tr}(\Sigma K)$ and calling it (T) is invalid, since (T) optimizes over additional cross blocks. Absolute row sums, per-$r$ optimizations, independently selected per-null cutoffs, covariance convexity, and conditioning on all Gaussian factors are not substitutes for this certificate. If the required atoms or trace estimate cannot be established, retain the exact identities and mark the execution failed; do not install (T) or (A) as an unproved dependency equivalent in role to the target.

5. [ ] **Transfer the proved scalar bound to the exact unrestricted quantifiers.** Only after a complete proof of (T), combine (P) and (N) to get

   $$
   H(1)\le q+\frac{qU}{2\sqrt{2\pi}}+C_0q\{1+\log(2+U)\}.
   $$

   For a singular admissible endpoint, use $\Sigma_\delta=(1-\delta)\Sigma+\delta I$ and the coupling $\theta+\sqrt{1-\delta}\,G+\sqrt\delta\,E$. Each marginal is a nondegenerate unit-variance Gaussian. The finite collection of boundary events $p_i=qk/N$ therefore has probability zero, even if coordinates coincide identically. Away from those events the finite BH FDP is locally constant, so bounded convergence transfers the scalar estimate for each fixed model. No convergence of a whitened inverse, $K$, or a completion optimizer is needed. Finally prove $U/\sqrt{\log(1/q)}\to\sqrt2$ from Mills bounds and use the universal constants to choose $q_\varepsilon$ independently of $N,\theta,\Sigma$ before taking their supremum.

## Verification

Step 1 establishes the physical signed identity using an actually independent-null reference. Step 2 gives a different, explicitly computable cost with both generating within-label blocks fixed; actual $\Sigma$ is feasible, while the two recorded divergent dual matrices are not. Step 3 must check the whole cost on those families, not merely reject their old witnesses. Step 4 is the central new analytic obligation: the atom identity and its explicit energy budget imply a genuine block PSD certificate and hence (T). Only a proved (T) permits step 5, whose Gaussian-tail asymptotics yield the exact coefficient $1/(2\sqrt\pi)$ uniformly over the target's quantifiers. No assertion of success follows from an obstruction test, a formal local expansion, or a finite numerical computation.

## Assumed definitions

The definitions [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), [false discovery rate](../definitions/false_discovery_rate.md), and [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md) are approved in the context pack. No draft definition or unproved asset is assumed. The cited draft ideas and failed-plan calculations supply test cases to reconstruct. The new cost, covariance-score transfer, proposed local diagnostic, and estimates (T)/(A) are proof obligations of this pending plan, not established facts or assumptions.

## Difference from failed plans

- `plan_two_sided_null_noise_folded_completion_20261104`: replace the fully diagonal majorant and its unrestricted correlation dual by full symmetric within-label primal blocks, whose dual fixes both $\Gamma_{JJ}=\Sigma_{JJ}$ and $\Gamma_{AA}=\Sigma_{AA}$. The centered all-ones witness fails both equalities, and the negative-null alternative-block-preserving witness fails the first. Formula (E) exposes the actual new weights and cross term; a mandatory differentiated finite-array test must establish that no divergent cost survives before a sharp budget is attempted. The physical independent-null path is retained and not confused with either dual block.
- `plan_two_sided_signed_face_budget_20261104`: retain its exact rank algebra but replace pointwise opposite-face comparisons and a named scalar remainder by the explicit global covariance-weighted optimization (N) and the PSD atom certificate (A). The two-coordinate face-ordering obstruction is accepted; cancellation must occur after the common signed corners are integrated and the full generating blocks enter. No covariance convexity or rank-one reduction is presumed.


## Progress

Execution record, 2026-11-04; this attempt is closed as failed for the unresolved proof obligations specified under Failure. Steps 1 and 2 are proved below. Step 3 is only partly established: its exact finite-array cost, elementary cases, local population expansion, and relevant finite-array scores have been derived. Subsection 9 additionally proves bounded fixed-$q$ COMPLETE cost for the one-sided negative-null diagnostic, including its nuclear term, without transferring derivatives of a scalar limit. Subsection 10 bounds the common-gate finite-dimensional correction and reduces that family's bounded fixed-$q$ COMPLETE-cost test exactly to a uniform bound on the negative part of its integrated cross derivative. Subsection 11 proves the quadratic geometry of an optional retuned critical gate and an exact leading cancellation in a canonical smoothing integral; subsection 12 gives a finite-array regression identity but no uniform derivative estimate. Subsection 13 establishes the actual finite-$z$ critical retuning and an empirical-count scale that a derivative transfer would have to control. The negative-part bound has NOT been proved, and steps 3--5 remain unticked. No general trace budget, all-null Simes inequality, proof of the target, or counterexample to it is claimed. The target asset is unchanged; the earlier pending-checkpoint language below is historical.

### 1. Forced-zero reference and finite signed identity (settles step 1)

For a deterministic p-vector put
$$
C_h=\#\{i:p_i\le qh/N\},\qquad
R=\max(\{0\}\cup\{h:C_h\ge h\}).
$$
If $R>0$ and $C_R=s>R$, then $C_s\ge C_R=s$, contradicting maximality. Hence $C_R=R$, including ties, and this $R$ is the actual number of BH rejections.

Replace $p_i$ by zero and call the resulting largest rank $R_i^0\ge1$. Then
$$
\frac{\mathbf1\{i\in\mathcal R_q(p)\}}{R\vee1}
=\frac{\mathbf1\{p_i\le qR_i^0/N\}}{R_i^0}.
\tag{Pr1}
$$
If $i$ is rejected at rank $R$, its original p-value is already below every larger threshold; a rank larger than $R$ cannot become qualifying upon replacement. Thus $R_i^0=R$. Conversely, if $p_i\le qR_i^0/N$, rank $R_i^0$ also qualifies before replacement, whereas a larger rank cannot qualify because it did not qualify even after decreasing $p_i$. This proves (Pr1) with non-strict inequalities and arbitrary ties.

At the specified path's initial point, $C_0=I_J\oplus\Sigma_{AA}$. Each centered null p-value is uniform and independent of all remaining coordinates. Conditional on those coordinates, $R_i^0$ is fixed and (Pr1) has expectation $q/N$. Therefore
$$
H(0)=q|J|/N.
\tag{Pr2}
$$
The covariance $S=\Sigma_{JJ}$ used later in the dual has not been substituted for $I_J$ here. If $J=\varnothing$, FDP is identically zero. For $N=1$, FDR is $q$ for a centered null and zero for an alternative, and $K=0$.

Here is an explicit construction of every signed corner, retaining the actual largest ranks. For a pair $i\ne j$, fix all remaining coordinates. Let
$$
b_h=\min\{v:p_h\le qv/N\},
$$
with $b_h=N+1$ when the set is empty, and for $v=1,\ldots,N$ put
$$
n_v=\#\{h\ne i,j:b_h\le v\},\qquad
w_v=\#\{h\in J\setminus\{i,j\}:b_h\le v\}.
$$
At the $i$ and $j$ boundary levels $k,l$, respectively, let $u,v\in\{0,1\}$ indicate entry into the corresponding tail. The two coordinate bins are $k+1-u$ and $l+1-v$. To keep rank indices distinct from these indicators, define
$$
e_i(h;u)=\mathbf1\{h\ge k+1\}+u\mathbf1\{h=k\},\quad
e_j(h;v)=\mathbf1\{h\ge l+1\}+v\mathbf1\{h=l\},
$$
$$
r_{uv}=\max\bigl(\{0\}\cup
\{h:n_h+e_i(h;u)+e_j(h;v)\ge h\}\bigr).
\tag{Pr3}
$$
Thus every candidate rank, including a distant larger rank, is explicitly retained. Put $\ell_h=\mathbf1\{h\in J\}$ and
$$
F_{uv}=
\begin{cases}
0,&r_{uv}=0,\\
\{w_{r_{uv}}+\ell_i e_i(r_{uv};u)+\ell_j e_j(r_{uv};v)\}/r_{uv},
&r_{uv}>0.
\end{cases}
$$
For $a=\sigma t_k$, $b=\tau t_l$, $\sigma,\tau\in\{-1,1\}$, the mixed increasing-coordinate jump is
$$
\Delta_{ij}^{a,b}f=\sigma\tau(F_{11}-F_{10}-F_{01}+F_{00}).
\tag{Pr4}
$$
Indeed increasing through a positive boundary enters its tail; increasing through a negative boundary exits it. Formula (Pr3), rather than a selected qualifying rank, determines each of the four FDP values.

For $B_2=\{i,j\}$, $E=[N]\setminus B_2$, define
$$
L_{ij}(r)=\sum_{k,l=1}^N\sum_{\sigma,\tau=\pm1}
\varphi_{(C_r)_{B_2B_2}}
\left(\binom{\sigma t_k}{\tau t_l}-\theta_{B_2}\right)
\,\mathbb E\left[
\Delta_{ij}^{\sigma t_k,\tau t_l}f(T_E)
\,\middle|\,T_i=\sigma t_k,T_j=\tau t_l
\right].
\tag{Pr5}
$$
The conditional mean and covariance in this expression, for $y=(\sigma t_k,\tau t_l)^{\mathsf T}$, are
$$
\theta_E+(C_r)_{EB_2}(C_r)_{B_2B_2}^{-1}(y-\theta_{B_2}),\quad
(C_r)_{EE}-(C_r)_{EB_2}(C_r)_{B_2B_2}^{-1}(C_r)_{B_2E}.
$$
For an empty $E$ the expectation is the deterministic corner. The Schur complement is positive definite otherwise.

For a fixed positive-definite endpoint, $C_r$ is positive definite for all $r$: at zero this follows from its displayed block diagonal form, and for $r>0$ it follows by congruence with the invertible $Q+rP$ and addition of $(1-r^2)P$. Compactness gives a positive minimum eigenvalue for this fixed finite path. Differentiating the Gaussian density $\varphi_{C_r}(x-\theta)$ directly gives
$$
\frac{d\varphi_{C_r}}{dr}
=\frac12\left[
(x-\theta)^{\mathsf T}C_r^{-1}C'_rC_r^{-1}(x-\theta)
-\operatorname{tr}(C_r^{-1}C'_r)
\right]\varphi_{C_r}
=\frac12\sum_{i,j}(C'_r)_{ij}\partial_{ij}\varphi_{C_r}.
$$
The fixed-model eigenvalue bounds dominate these derivatives by a polynomial times an integrable Gaussian. Differentiation under the bounded FDP integral is valid. FDP is constant on the finite rectangular grid cut out by the thresholds $\pm t_k$. Integrating by parts on each cell twice and summing cancels interior edge terms into (Pr4), giving
$$
\int f_q(x)\partial_{ij}\varphi_{C_r}(x-\theta)\,dx=L_{ij}(r),\qquad i\ne j.
$$
The covariance diagonal has derivative zero. Its off-diagonal derivative is $2r\Sigma_{ij}$ on $J\times J$, $\Sigma_{ij}$ on a cross pair, and zero on $A\times A$. Consequently the prescribed symmetric matrices satisfy
$$
H'(r)=\tfrac12\operatorname{tr}(\Sigma M(r)),\qquad
H(1)=q|J|/N+\operatorname{tr}(\Sigma K),\quad
K=\tfrac12\int_0^1M(r)\,dr,\quad K_{AA}=0,\quad K_{ii}=0.
\tag{Pr6}
$$
All integrals here are finite for the fixed finite positive-definite model. No separate optimization at different $r$ has been made.

### 2. Exact both-block support function and primal (settles step 2)

Suppose first that $S,B$ are positive definite and nonempty. Write the cross block of a candidate $\Gamma$ as $X$. Congruence by $\operatorname{diag}(S^{-1/2},B^{-1/2})$ gives
$$
\Gamma\succeq0
\quad\Longleftrightarrow\quad
\begin{pmatrix}I&W\\W^{\mathsf T}&I\end{pmatrix}\succeq0,\qquad
W=S^{-1/2}XB^{-1/2}.
$$
Taking the Schur complement shows this is equivalent to $\|W\|_{\rm op}\le1$. Since $K_{AA}=0$, cyclicity of trace gives
$$
\operatorname{tr}(\Gamma K)=\operatorname{tr}(G_0)+2\langle W,Z\rangle_F.
$$
For a singular-value decomposition $Z=\sum_\ell s_\ell u_\ell v_\ell^{\mathsf T}$,
$$
\langle W,Z\rangle_F=\sum_\ell s_\ell u_\ell^{\mathsf T}Wv_\ell
\le\sum_\ell s_\ell,
$$
with equality for the contraction $W=\sum_\ell u_\ell v_\ell^{\mathsf T}$. This proves (N), including attainment. The actual $\Sigma$ is feasible, so its physical pairing is bounded above by this cost.

For completeness, weak duality with the block PSD constraint in (B) follows by pairing it with any feasible $\Gamma$:
$$
\operatorname{tr}(SD)+\operatorname{tr}(BF)-\operatorname{tr}(\Gamma K)\ge0.
$$
Whiten that primal constraint by $\operatorname{diag}(S^{1/2},B^{1/2})$, and set $\widetilde D=S^{1/2}DS^{1/2}$, $\widetilde F=B^{1/2}FB^{1/2}$. The choice
$$
\widetilde D=G_0+\sum_\ell s_\ell u_\ell u_\ell^{\mathsf T},\qquad
\widetilde F=\sum_\ell s_\ell v_\ell v_\ell^{\mathsf T}
$$
has constraint matrix
$$
\begin{pmatrix}\widetilde D-G_0&-Z\\-Z^{\mathsf T}&\widetilde F\end{pmatrix}
=\sum_\ell s_\ell
\binom{u_\ell}{-v_\ell}\binom{u_\ell}{-v_\ell}^{\mathsf T}\succeq0
$$
and objective $\operatorname{tr}(G_0)+2\sum_\ell s_\ell$. This matches weak duality and proves (B) without a Slater or attainment assumption. In particular, $D$ is unrestricted symmetric and includes the signed $K_{JJ}$ contribution.

If $A=\varnothing$, the dual is the singleton $\Gamma=S$, so the cost is $\operatorname{tr}(SK_{JJ})$. The primal is attained by $D=K_{JJ}$; every feasible $D$ has no smaller $S$-weighted trace. If $J=\varnothing$, $K=0$ and the cost is zero. No all-null probabilistic inequality was used.

### 3. Exact exchangeable cost and elementary tests (part of step 3)

Let $d_b=1+(n-1)\rho_b$, $b=0,1$. Exchangeability within each label class gives
$$
K_{JJ}=k_{00}(\mathbf1\mathbf1^{\mathsf T}-I),\qquad
K_{JA}=k_{01}\mathbf1\mathbf1^{\mathsf T}.
$$
Thus $\operatorname{tr}(SK_{JJ})=n(n-1)\rho_0k_{00}$. Also $S^{1/2}\mathbf1=\sqrt{d_0}\mathbf1$ and $B^{1/2}\mathbf1=\sqrt{d_1}\mathbf1$. The cross matrix $Z$ has its single possibly nonzero singular value $n\sqrt{d_0d_1}|k_{01}|$. This proves (E), including its signed first term and its absolute value only after the path has been integrated.

If centered nulls are independent of the entire alternative vector, the Gaussian density factors into a centered null-block density and an alternative density at every $r$. Under simultaneous sign reversal of all null coordinates, FDP is unchanged, the null-block density is unchanged, and its first derivative in any null coordinate changes sign. Therefore the mixed score integral $L_{ij}$ is zero for every cross pair, and $K_{JA}=0$. The completion cost is then exactly the physical increment $H(1)-q|J|/N$, bounded between $-q|J|/N$ and $1-q|J|/N$. If the null coordinates are also mutually independent, the density factors coordinatewise in each null, and coordinatewise evenness gives $L_{ij}=0$ for every relevant pair. In that case $K=0$.

For $N=2$ with one null, put
$$
u=\overline\Phi^{-1}(q/2),\quad v=\overline\Phi^{-1}(q/4),\quad
J_{ab}=\Pr(|T_1|\ge a,\ |T_2|\ge b).
$$
The FDP is one when $|T_1|\ge v,|T_2|<u$, and is one half when both absolute values exceed $u$. Hence, for any alternative mean,
$$
H=q/2+\tfrac12J_{uu}-J_{vu}.
$$
For nonzero correlation $\rho$, (Pr6) gives $K_{12}=(H-q/2)/(2\rho)$, and (N) is $2|K_{12}|$. At $\rho=0$, $K=0$ by the preceding independence argument. With two nulls, directly splitting the event of at least one rejection gives
$$
H=q+J_{uu}-J_{vu}-J_{uv}.
$$
Here $A$ is empty, so the cost is $H-q$, rather than $2|K_{12}|$. With no nulls it is zero. These cases exhaust the two-sided labels for arbitrary two-coordinate means.

For the regularized centered simplex, $\rho_\delta=-(1-\delta)/(N-1)$, $0<\delta<1$, exchangeability and (Pr6) give
$$
K_{ij}=\frac{H_\delta-q}{N(N-1)\rho_\delta}\quad(i\ne j),\qquad
\mathfrak C_{S,\varnothing}(K)=H_\delta-q.
$$
This proves a bounded fixed-$q$ cost and removes the old free-correlation amplification. It proves no dimension-uniform small-$q$ rate for $H_\delta-q$.

### 4. Full common-gate cost in terms of the required finite-array derivatives

Fix $q\in(0,1/2)$, $N=2n$, $z=\sqrt{2c\log N}$ with $c=1/100$, and $\alpha=\operatorname{arcosh}(2/q-1)$. Let $H_N(x,y,c_*)$ be the actual two-sided BH FDR with means $0,\alpha/z$ in the two groups, within-group off-diagonal covariances $x/z^2,y/z^2$, and cross covariances $c_*/z^2$, with all marginal variances one. Derivatives below are finite-dimensional derivatives in the open region where this full covariance is positive definite; they exist by the density argument above.

Let $L_{00,N},L_{01,N}$ denote the common null/null and cross corner values at those parameters. Direct covariance differentiation, counting unordered null pairs and all cross pairs, gives the exact identities
$$
\partial_x H_N=\frac{n(n-1)}{2z^2}L_{00,N},\qquad
\partial_{c_*}H_N=\frac{n^2}{z^2}L_{01,N}.
\tag{Pr7}
$$
For the weak common-gate endpoint, its independent-null path is $(x,y,c_*)=(r^2\lambda,\lambda,r\lambda)$. Therefore the COMPLETE fixed-block cost is exactly
$$
\mathfrak C_{S,B}(K_N)=
2\lambda\int_0^1r\,\partial_xH_N(r^2\lambda,\lambda,r\lambda)\,dr
+\left(\lambda+\frac{z^2-\lambda}{n}\right)
\left|\int_0^1\partial_{c_*}H_N(r^2\lambda,\lambda,r\lambda)\,dr\right|.
\tag{Pr8}
$$
Both terms, including the nonnegative nuclear term, are present. In contrast, the physical increment is
$$
H_N(\lambda,\lambda,\lambda)-q/2
=2\lambda\int_0^1r\,\partial_xH_N\,dr
+\lambda\int_0^1\partial_{c_*}H_N\,dr.
\tag{Pr9}
$$
Consequently even convergence of this entire scalar increment does not separately determine either integral in (Pr8), nor the sign inside its absolute value. The old all-ones witness fails the two fixed-block equalities, but that fact supplies no bound on (Pr8).

### 5. Local root expansion and scalar localization; no derivative transfer asserted

On a sufficiently small fixed neighborhood of $(a,b,x,y)=(0,0,0,0)$, the equation in step 3 has a smooth root $s=S(a,b,x,y)$ near one. To see the part relevant to the LARGEST BH threshold, its left side at the origin in these parameters is $(1+\cosh(\alpha s))/2$, with derivative $D=\alpha\sinh\alpha/2>0$ at $s=1$. On the compact interval $0\le s\le3/2$, its second derivative is strictly positive at the base and remains positive after reducing the parameter neighborhood. The value at $s=0$ is one. The implicit-function theorem and this convexity therefore give a unique first crossing near one, a uniform strict below-line margin on $0\le s\le S-\delta$, and an above-line margin at $S+\delta$, for each fixed sufficiently small $\delta>0$. No claim about other, later crossings at arbitrarily large $s$ is needed.

At the base, implicit differentiation gives
$$
S_a=0,\quad S_b=-1/\alpha,\quad
S_{aa}=-1/(\alpha\sinh\alpha),\quad S_{bb}=2/\alpha^2,\quad S_{ab}=0,
$$
$$
S_x=1/(2\alpha\sinh\alpha),\qquad
S_y=\cosh\alpha/(2\alpha\sinh\alpha).
$$
Giving $a,b$ weight one and $x,y$ weight two, this yields
$$
S^2=
1-\frac{2b}{\alpha}-\frac{a^2}{\alpha\sinh\alpha}
+\frac{3b^2}{\alpha^2}
+\frac{x+y\cosh\alpha}{\alpha\sinh\alpha}
+\text{terms of weighted degree at least three}.
$$
The local null FDP factor is $g=(q/2)e^{-xS^2/2}\cosh(aS)$. Its expansion through weighted degree four is obtained from
$$
e^{-xS^2/2}\cosh(aS)
=1+\frac{a^2-x}{2}S^2
+\frac{a^4-6xa^2+3x^2}{24}S^4
+\text{higher weighted degree}.
$$
For centered Gaussian $(a,b)$ with variances $x,y$ and covariance $c_*$,
$$
\mathbb E[(a^2-x)a^2]=2x^2,\quad
\mathbb E[(a^2-x)b^2]=2c_*^2,\quad
\mathbb E[a^4-6xa^2+3x^2]=0.
$$
Odd moments and the other constant multiples of $a^2-x$ vanish. Use a fixed smooth cutoff equal to one on a smaller root neighborhood and supported in the original neighborhood, and a bounded smooth extension of $g$ there. Gaussian tails outside the smaller neighborhood, including any fixed polynomial moments, are $O(\exp(-c_1/(x+y)))$ times a polynomial in $(x+y)^{-1}$. Taylor's theorem and Gaussian moments then prove for this localized population average $\mathcal H$,
$$
\mathcal H(x,y,c_*)=
\frac q2+\frac q2\left(\frac{3c_*^2}{\alpha^2}
-\frac{x^2}{\alpha\sinh\alpha}\right)+O((x+y)^{5/2}).
\tag{Pr10}
$$
The constants depend on this fixed $q$ and the chosen neighborhood. Applying Gaussian integration by parts to the smooth cutoff extension gives $\partial_{c_*}\mathbb E g=\mathbb E\partial_{ab}g$ and $\partial_x\mathbb E g=\mathbb E(\partial_xg+\tfrac12\partial_{aa}g)$. These formulas extend from positive-definite latent covariance to its semidefinite boundary by bounded convergence of the smooth derivatives. Applying the same Taylor argument to these derivatives gives
$$
\partial_x\mathcal H=-\frac{qx}{\alpha\sinh\alpha}+O((x+y)^{3/2}),\qquad
\partial_{c_*}\mathcal H=\frac{3qc_*}{\alpha^2}+O((x+y)^{3/2}).
\tag{Pr11}
$$
These are derivatives of $\mathcal H$, NOT yet derivatives of a limit of $H_N$.

Here is sufficient scalar finite-array localization, also explaining why it does not fill that gap. Conditional on $(a,b)$, the coordinates are independent within and between groups, with means $a/z,(\alpha+b)/z$ and residual variances $1-x/z^2,1-y/z^2$. Uniformly on the compact root neighborhood and $U=\overline\Phi^{-1}(q/2)\le u\le3z/2$, integration of the normal hazard between $u$ and $(u\mp m/z)/\sqrt{1-v/z^2}$ gives
$$
\frac{\Pr(|m/z+\sqrt{1-v/z^2}\epsilon|\ge u)}
{2\overline\Phi(u)}
=e^{-vs^2/2}\cosh(ms)+o_N(1),\quad s=u/z.
$$
Indeed the normal argument changes by $O(1/z)$, and the logarithm of each one-sided tail ratio is $\pm ms-vs^2/2+O(1/z)$ by the bounds $u<\varphi(u)/\overline\Phi(u)<u+1/u$ on a fixed positive lower interval.

For each conditional group, a grid of $\lceil N^{1/4}\rceil$ true-CDF quantiles, Chebyshev with error $N^{-1/4}$ at every grid point, a union bound, and monotonicity give uniform empirical-CDF error at most $3N^{-1/4}$ with conditional failure probability $O(N^{-1/4})$. The constants are independent of $(a,b)$. Put $t_{\min}=2\overline\Phi(3z/2)$; Mills bounds give $t_{\min}\asymp N^{-9c/4}/\sqrt{\log N}$. Thus empirical error and BH grid spacing $q/N$ are both $o(t_{\min})$. The below-line margin rules out EVERY larger BH grid threshold up to $q$; a grid threshold near $2\overline\Phi((S+\delta)z)$ qualifies and exceeds $t_{\min}$. Hence the actual largest BH threshold has scaled normal score tending to $S$ conditionally on the root neighborhood. Its actual FDP tends to $g$ there, since the relative empirical null-CDF error vanishes. Boundedness of FDP and Gaussian truncation justify the corresponding localized scalar expectations.

In the centered independent-alternative diagnostic $y=c_*=0$, the exact symmetry result in subsection 3 already eliminates the entire nuclear term. The scalar argument and (Pr10), without differentiating any finite-array limit, give
$$
\limsup_{N\to\infty}
\left|H_N(\lambda,0,0)-\left(\frac q2-
\frac{q\lambda^2}{2\alpha\sinh\alpha}\right)\right|
=o(\lambda^2)\quad(\lambda\downarrow0).
\tag{Pr12}
$$
This notation does not assume existence of the full $N$ limit for a fixed $\lambda$. The exponentially small omitted Gaussian probability and the Taylor remainder give the stated bound on both limiting envelopes. The COMPLETE cost here is $H_N(\lambda,0,0)-q/2$ and is uniformly bounded for fixed $q$.

If the integrated derivatives in (Pr8) could be transferred to (Pr11) with suitable error, the resulting local predicted cost would be
$$
\frac{q\lambda^2}{2}
\left(\frac3{\alpha^2}-\frac1{\alpha\sinh\alpha}\right)
+o(\lambda^2).
$$
This last substitution is CONDITIONAL and is not a proved evaluation of the common-gate finite-array cost. In particular, the finite-array sign of $\int\partial_{c_*}H_N\,dr$ has not been established.

### 6. Exact scores identify the missing domination, including the degenerate path

The following finite-array representation gives a concrete starting point for the missing differentiated calculation. Subtract the group means $\theta$ and let
$$
U_0=z\,\overline{(T-\theta)}_J,\qquad
U_1=z\,\overline{(T-\theta)}_A,\qquad
v_N(t)=t+(z^2-t)/n.
$$
The vector $U=(U_0,U_1)^{\mathsf T}$ has covariance
$$
V_N=\begin{pmatrix}v_N(x)&c_*\\c_*&v_N(y)\end{pmatrix}.
$$
In orthonormal within-group contrast bases the residual vectors $R_0,R_1$ are independent Gaussian vectors of dimension $n-1$, with variances $h_x=1-x/z^2$ and $h_y=1-y/z^2$. They are independent of $U$. Direct differentiation of these three Gaussian densities gives the exact scores
$$
S_{c_*,N}=(V_N^{-1}U)_0(V_N^{-1}U)_1-(V_N^{-1})_{01},
\quad \partial_{c_*}H_N=\mathbb E[f_q S_{c_*,N}],
\tag{Pr13}
$$
$$
S_{x,N}=
\frac{1-1/n}{2}\left((V_N^{-1}U)_0^2-(V_N^{-1})_{00}\right)
-\frac{1}{2z^2h_x}
\left(\frac{\|R_0\|^2}{h_x}-(n-1)\right),
\quad \partial_xH_N=\mathbb E[f_q S_{x,N}].
\tag{Pr14}
$$
Thus a proof must handle the contrast score as well as the common-mean score.

On the common-gate path the limiting latent covariance is rank one for every $r>0$. For $r$ in any fixed compact subinterval of $(0,1]$, the smaller eigenvalue of $V_N$ is of order $z^2/n$. Wick's formula gives
$$
\mathbb E S_{c_*,N}^2
=(V_N^{-1})_{00}(V_N^{-1})_{11}
+(V_N^{-1})_{01}^2,
$$
so its square root grows on the order of $n/z^2$ there. The contrast part of (Pr14) also has square-root second moment of order $\sqrt n/z^2$. Scalar bounded convergence, or the preceding unweighted empirical-CDF failure probability, therefore supplies no score domination. This is a missing proof step, not a proof that derivative transfer is false. A fresh continuation must establish cancellations or stronger conditional estimates sufficient for these exact signed score expectations, including a justified treatment of $r$ near zero, before replacing them by (Pr11).

### 7. One-sided negative-null diagnostic: exact full cost and actual reference

Use the recorded constants $\beta=10$, $\eta=(q/2)e^{-\beta}$ and $\alpha=\log(2/q-e^{-\beta})$, with null means $-\beta/z$ and alternative means $\alpha/z$. Define $H_N^{(1)}(x,y,c_*)$ using the same covariance parameters and fixed negative-mean null labels. Repeating (Pr3)--(Pr6) with the one-sided thresholds $\overline\Phi^{-1}(qk/N)$ gives the one-sided signed matrix $K^{(1)}$; at each threshold increasing a coordinate enters its tail, so the four-cell sign is positive. The reference is now
$$
H_N^{(1)}(0,0,0)=
\sum_{i\in J}\mathbb E\left[
\frac{\overline\Phi(\overline\Phi^{-1}(qR_i^0/N)+\beta/z)}
{R_i^0}\right]\le q/2.
\tag{Pr15}
$$
This is the exact forced-zero formula, using each null's conservative CDF. It is not $q/2$. The deterministic root at the independent reference satisfies
$$
\tfrac12e^{-\beta s}+\tfrac12e^{\alpha s}=1/q,\qquad s=1.
$$
The left side is strictly convex, starts below $1/q$, grows to infinity, and has positive derivative at $1$ (indeed $\alpha(2/q-e^{-\beta})>\beta e^{-\beta}$). Hence $1$ is its unique positive crossing. The same uniform tail-ratio, quantile-grid concentration and largest-threshold localization argument above, without Gaussian mixing at this reference, proves
$$
H_N^{(1)}(0,0,0)\longrightarrow\eta.
$$

For the actual negative-null endpoint and path $(x,y,c_*)=(r^2\lambda,0,0)$, (E) and the one-sided versions of (Pr7) give the exact FULL cost
$$
\mathfrak C_{S,I}(K_N^{(1)})
=H_N^{(1)}(\lambda,0,0)-H_N^{(1)}(0,0,0)
+w_N\left|\int_0^1\partial_{c_*}H_N^{(1)}(r^2\lambda,0,0)\,dr\right|,
\tag{Pr16}
$$
$$
w_N=\frac{z^2}{n}
\sqrt{1+\frac{(n-1)\lambda}{z^2}}
=\sqrt{\frac{z^2}{n}\left(\lambda+\frac{z^2-\lambda}{n}\right)}.
$$
The old witness $\operatorname{diag}(\mathbf1\mathbf1^{\mathsf T},I)$ fails the prescribed null block. The first term in (Pr16) is bounded in absolute value by one. Although $w_N\to0$, this alone proves nothing about the cross term. Negative means remove the centered-null sign symmetry. The exact cross score is still (Pr13), and here at $c_*=0$ it reduces to $U_0U_1/(v_N(r^2\lambda)v_N(0))$, with $U$ defined after subtracting the now nonzero means. The full cross term is bounded in subsection 9 by a finite-array score argument.

### 8. Singular scalar reduction, conditional on a proved uniform scalar bound

This reduction does not complete step 5, whose premise (T) is unproved. For each fixed finite singular correlation endpoint, let $G\sim N(0,\Sigma)$, $E\sim N(0,I)$ independently, and
$$
T_\delta=\theta+\sqrt{1-\delta}\,G+\sqrt\delta\,E.
$$
It converges almost surely to $\theta+G$ and has covariance $(1-\delta)\Sigma+\delta I\succ0$. Each coordinate of the limit is a nondegenerate variance-one Gaussian. Thus every event $p_i=qk/N$ has probability zero; their finite union does also. Off that union, every coordinate remains in its original threshold cell for all sufficiently small perturbations, and the deterministic rank/count formula makes FDP locally constant. Bounded convergence therefore transfers any dimension-uniform scalar FDR upper bound from the positive-definite approximants. Identical coordinates and other singularities cause no additional exception. This requires no convergence of $K$, an inverse block, or a dual optimizer.

The same elementary Mills inequalities used above imply
$$
\log(1/q)=U^2/2+\log U+O(1),\qquad
U/\sqrt{\log(1/q)}\longrightarrow\sqrt2
$$
for $q=2\overline\Phi(U)\downarrow0$. If (T) were proved with universal constants, the scalar and asymptotic transfer in step 5 would consequently have the stated coefficient. No such premise is supplied by this checkpoint.

### 9. Bounded complete negative-null diagnostic by a paired finite-array score

Fix the $q,\beta,\alpha$ of subsection 7 and any fixed $\lambda>0$. All constants in this subsection may depend on these fixed parameters; no small-$q$ budget is asserted. Put $\kappa=2c=1/50$, so $z^2=\kappa\log(2n)$, and write
$$
\varepsilon_N=z^2/n,\qquad
v(r)=\varepsilon_N+(1-1/n)\lambda r^2,
\qquad w_N=\sqrt{\varepsilon_N v(1)}.
$$
We prove
$$
\sup_{n\ \mathrm{sufficiently\ large}}
w_N\left|\int_0^1\partial_{c_*}H_N^{(1)}(r^2\lambda,0,0)\,dr\right|<\infty.
\tag{Pr17}
$$
Together with (Pr16), this proves bounded complete cost for this recorded diagnostic. It establishes neither convergence nor a sign for the cross derivative.

**A uniform conditional FDP approximation near the independent reference.** For $x\ge0$ small let $F_{N,x}(a,b)$ be the conditional expectation of the actual one-sided BH FDP given $U_0=a,U_1=b$ at $(x,0,0)$. Gaussian orthogonal decomposition gives the following exact conditional representation, with two independent iid standard-normal samples:
$$
T_{0i}=(-\beta+a)/z+\sqrt{1-x/z^2}(\xi_i-\overline\xi),\qquad
T_{1i}=(\alpha+b)/z+(\zeta_i-\overline\zeta).
\tag{Pr18}
$$
In particular, conditioning on sample means does NOT leave independent coordinates; the sample-centering terms in (Pr18) must be retained.

There are fixed $a_0,b_0,x_0,L,C>0$ such that for all large $n$, $|a|\le a_0$, $|b|\le b_0$, and $0\le x\le x_0$,
$$
|F_{N,x}(a,b)-g(a,b,x)|\le C/z^2,\qquad
|\partial_a g(a,b,x)|\le L.
\tag{Pr19}
$$
Here $S=S(a,b,x)$ is the first positive crossing near one of
$$
\tfrac12e^{(-\beta+a)s-xs^2/2}
+\tfrac12e^{(\alpha+b)s}=1/q,
\qquad
g(a,b,x)=\tfrac q2e^{(-\beta+a)S-xS^2/2}.
$$
At $(a,b,x)=(0,0,0)$ the crossing is one, with strictly positive derivative as proved in subsection 7. On $0\le s\le3/2$ the second derivative of the left side is strictly positive at the base. Shrink the parameter box so it stays strictly positive, the first crossing stays in a fixed neighborhood of one, and the crossing derivative stays uniformly positive. The implicit-function theorem then gives smooth $S,g$ and the stated derivative bound.

Here are quantitative details for (Pr19). For $m,v$ in the resulting compact parameter ranges and any fixed $d>0$, uniformly for $d\le s\le3/2$,
$$
\frac{\overline\Phi((sz-m/z)/\sqrt{1-v/z^2})}{\overline\Phi(sz)}
=e^{ms-vs^2/2}\{1+O(z^{-2})\}.
\tag{Pr20}
$$
Indeed the argument changes from $sz$ by $O(z^{-1})$; its square changes by $-2ms+vs^2+O(z^{-2})$, and the prefactor ratio in the Mills expansion $\overline\Phi(t)=\varphi(t)t^{-1}\{1+O(t^{-2})\}$ is $1+O(z^{-2})$. The estimates are uniform because $s\ge d$. For $u$ between $\overline\Phi^{-1}(q)>0$ and $dz$, the hazard bound $\varphi(u)/\overline\Phi(u)\le u+C_q$ gives the upper bound $\exp(Cd+Cd^2+o(1))$ for either tail ratio. Choose $d>0$ small enough to keep their average uniformly below $1/q$. Thus the lack of (Pr20) at $s=0$ cannot hide an earlier qualifying threshold.

For an iid normal sample, use $\lceil n^{1/4}\rceil$ normal-quantile grid points. At each point Chebyshev bounds a CDF error exceeding $n^{-1/4}$ by $O(n^{-1/2})$. A union bound and monotonicity give uniform CDF error $O(n^{-1/4})$ except on an event of probability $O(n^{-1/4})$. Also $\Pr(|\overline\xi|>n^{-1/4})=O(n^{-1/2})$. On their intersection,
$$
\sup_t\left|n^{-1}\sum_i\mathbf1\{\xi_i-\overline\xi\le t\}-\Phi(t)\right|
\le C n^{-1/4},
$$
since $\Phi$ is Lipschitz. The same holds for the second group. These events and their probabilities are independent of $a,b,x$, so they apply uniformly to (Pr18).

Let $t_*=\overline\Phi(3z/2)\asymp N^{-9c/4}/z$. At every BH threshold with normal score at most $3z/2$, relative empirical-CDF error is $O(n^{-1/4}/t_*)$. Since $9c/4=9/400<1/4$, both this error and $(Nt_*)^{-1}$ vanish polynomially and are $o(z^{-2})$. Formula (Pr20), the uniform below-line margin, and the positive crossing derivative therefore put the actual LARGEST BH threshold within $O(z^{-2})$ of $S$ in scaled normal score: every larger p-value threshold is excluded, and a BH grid point within $O((Nt_*)^{-1})$ of a score just beyond this window qualifies. On the same event, the ratio of the actual null count to the actual rejection count differs from $g$ by $O(z^{-2})$. On the exceptional event use $0\le\mathrm{FDP}\le1$. Its probability is $o(z^{-2})$, proving (Pr19). This proof concerns conditional finite-array expectations, not derivatives of their scalar limits.

**Pair the score before integrating the path.** At $(r^2\lambda,0,0)$ the variables $A=U_0$ and $B=U_1$ are independent normals with variances $v(r)$ and $\varepsilon_N$. The exact score identity gives
$$
\partial_{c_*}H_N^{(1)}(r^2\lambda,0,0)
=\mathbb E\left[F_{N,r^2\lambda}(A,B)\frac{AB}{v(r)\varepsilon_N}\right].
\tag{Pr21}
$$
Set $\rho=\min(1,\sqrt{x_0/\lambda})>0$ and $\delta_N=C/z^2$. For $r\le\rho$, pair $a$ with $-a$ on the rectangle $|a|\le a_0,|b|\le b_0$. Formula (Pr19) gives
$$
|F_{N,r^2\lambda}(a,b)-F_{N,r^2\lambda}(-a,b)|
\le2L|a|+2\delta_N.
$$
For $X\sim N(0,t)$,
$$
\mathbb E|X|=\sqrt{2t/\pi},\qquad
\mathbb E[|X|\mathbf1\{|X|>d\}]=\sqrt{2t/\pi}e^{-d^2/(2t)}.
$$
Use this identity and $0\le F_{N,x}\le1$ on the complement of the rectangle. The pairing and the two tail bounds imply
$$
|\partial_{c_*}H_N^{(1)}|
\le\sqrt{2/\pi}\frac{L}{\sqrt{\varepsilon_N}}
+\frac{2/\pi}{\sqrt{v(r)\varepsilon_N}}
\left\{\delta_N+e^{-a_0^2/(2v(r))}
+e^{-b_0^2/(2\varepsilon_N)}\right\}
\quad(0\le r\le\rho).
\tag{Pr22}
$$
For $r\ge\rho$, the unrestricted first-moment bound is
$$
|\partial_{c_*}H_N^{(1)}|\le\frac{2/\pi}{\sqrt{v(r)\varepsilon_N}}.
\tag{Pr23}
$$
These finite-$n$ inequalities include $r=0$ since $v(0)=\varepsilon_N>0$.

For $n\ge2$ put $d_\lambda=\lambda/2$, so $v(r)\ge\varepsilon_N+d_\lambda r^2$. Also $w_N/\sqrt{\varepsilon_N}=\sqrt{v(1)}\le\sqrt{\lambda+\kappa}$. The only growing integral in (Pr22) is
$$
I_N=\int_0^\rho\frac{dr}{\sqrt{v(r)}}
\le d_\lambda^{-1/2}\operatorname{arsinh}
\left(\rho\sqrt{d_\lambda/\varepsilon_N}\right)
=O(1+\log n).
$$
Because $z^2=\kappa\log(2n)$, $\delta_N I_N=O(1)$. Both Gaussian tails have uniform integrable bounds: the elementary maximum
$$
\sup_{t>0}t^{-1/2}e^{-d^2/(2t)}=1/(d\sqrt e)
$$
gives
$$
\int_0^\rho\frac{e^{-a_0^2/(2v(r))}}{\sqrt{v(r)}}\,dr
\le\frac{\rho}{a_0\sqrt e},\qquad
e^{-b_0^2/(2\varepsilon_N)}I_N
\le\frac{\rho}{b_0\sqrt e}.
$$
Finally $\int_\rho^1v(r)^{-1/2}\,dr\le d_\lambda^{-1/2}\log(1/\rho)$. Multiplying (Pr22)--(Pr23) by $w_N$, integrating, and using these estimates proves (Pr17), even with the absolute value inside the integral. The finitely many smaller $n$ for which the prescribed endpoint is positive definite contribute only finite fixed-model costs. No assertion is made for an $n$ where the covariance prescription is inadmissible.

The score inequality and all its tail factors were independently checked in a read-only local lemma check. The negative-null model remains outside the two-sided target; this closes its diagnostic bounded-cost obligation only. This argument does not control the rank-one common-gate scores in (Pr13)--(Pr14): there both group means have nonvanishing correlated variance and the small eigenvalue occurs transversely along the entire path. The $O(z^{-2})$ conditional approximation above is not enough to multiply those scores, whose norm is $O(n/z^2)$.

### 10. Common-gate correction and the exact remaining negative-part test

Fix $q\in(0,1/2)$ and $\lambda>0$ as in subsection 4. For each admissible finite $N=2n$ with $z^2>\lambda$, define
$$
\mathcal A_N=2\lambda\int_0^1r\,\partial_xH_N(r^2\lambda,\lambda,r\lambda)\,dr,
\qquad
\mathcal B_N=\int_0^1\partial_{c_*}H_N(r^2\lambda,\lambda,r\lambda)\,dr,
$$
$$
\Delta_N=H_N(\lambda,\lambda,\lambda)-q/2,
\qquad \eta_N=(z^2-\lambda)/n>0,
\qquad (\mathcal B_N)_-=\max\{-\mathcal B_N,0\}.
$$
All these are actual finite-array quantities. Equations (Pr8)--(Pr9), with no derivative limit or sign assumption, give
$$
\mathfrak C_{S,B}(K_N)
=\mathcal A_N+(\lambda+\eta_N)|\mathcal B_N|
=\Delta_N+2\lambda(\mathcal B_N)_-+\eta_N|\mathcal B_N|.
\tag{Pr24}
$$
In particular, a large positive $\mathcal B_N$ cancels with the signed null-block contribution in the complete cost. Separate absolute bounds on these two integrated components are stronger than this bounded-cost test requires.

Here is a uniform finite-array bound for the last term in (Pr24). Along the path, the exact group-mean covariance from subsection 6 is
$$
V_N(r)=
\begin{pmatrix}(z^2-r^2\lambda)/n&0\\0&\eta_N\end{pmatrix}
+\lambda\binom{r}{1}\binom{r}{1}^{\mathsf T}
\succeq\eta_N I_2,\qquad 0\le r\le1.
\tag{Pr25}
$$
Indeed the first diagonal remainder is at least $\eta_N$, including at both endpoints. Write $A_N(r)=V_N(r)^{-1}$ and $\Xi=\left(\begin{smallmatrix}0&1\\1&0\end{smallmatrix}\right)$. The cross score in (Pr13) is equivalently
$$
S_{c_*,N}=\tfrac12\{U^{\mathsf T}A_N\Xi A_NU-\operatorname{tr}(A_N\Xi)\},
\qquad \mathbb ES_{c_*,N}=0.
$$
For completeness, put $U=V_N^{1/2}Z$ with $Z\sim N(0,I_2)$. Expanding the fourth Gaussian moments gives $\operatorname{Var}(Z^{\mathsf T}DZ)=2\operatorname{tr}(D^2)$ for any symmetric $D$. Apply this with $D=A_N^{1/2}\Xi A_N^{1/2}$. Since (Pr25) implies $\|A_N\|_{\mathrm{op}}\le\eta_N^{-1}$ and $\|\Xi\|_F^2=2$, it follows that
$$
\mathbb ES_{c_*,N}^2
=\tfrac12\|A_N^{1/2}\Xi A_N^{1/2}\|_F^2
\le\tfrac12\|A_N\|_{\mathrm{op}}^2\|\Xi\|_F^2
\le\eta_N^{-2}.
$$
The exact score formula (Pr13) and $0\le f_q\le1$ now yield
$$
|\partial_{c_*}H_N|
=|\mathbb E[(f_q-1/2)S_{c_*,N}]|
\le\tfrac12(\mathbb ES_{c_*,N}^2)^{1/2}
\le\frac1{2\eta_N},
\qquad
\eta_N|\mathcal B_N|
\le\eta_N\int_0^1|\partial_{c_*}H_N|\,dr\le\frac12.
\tag{Pr26}
$$
This estimate holds for every admissible $n$ in this family, uniformly in $r$, and requires no separate treatment of $r\downarrow0$. The normalization, variance bound, and cancellation identity (Pr24) were independently checked in a read-only local lemma check.

Since $-q/2\le\Delta_N\le1-q/2$, equations (Pr24)--(Pr26) prove the exact useful comparison
$$
-q/2+2\lambda(\mathcal B_N)_-
\le\mathfrak C_{S,B}(K_N)
\le3/2-q/2+2\lambda(\mathcal B_N)_-.
\tag{Pr27}
$$
Consequently, for these fixed $q$ and $\lambda>0$, a dimension-uniform upper bound on the COMPLETE common-gate cost is equivalent to
$$
\sup_{\substack{n\ge1\\z^2>\lambda}}(\mathcal B_N)_-<\infty.
\tag{Pr28}
$$
No proof of (Pr28), or of the sign of $\mathcal B_N$, has been obtained here. The uniform bound $1/2$ controls only the finite-dimensional correction $\eta_N|\mathcal B_N|$; it neither bounds $|\mathcal B_N|$ nor supplies a remainder that vanishes on the small-$q$ scale in (T). In particular, it is insufficient to substitute the local population derivatives (Pr11) into (Pr8). Convergence of both component sensitivities would be a stronger possible route, rather than a necessary prerequisite to the bounded fixed-$q$ test (Pr28). No counterexample to the target or rigorous obstruction to this plan has been established by this reduction.

### 11. A retuned critical gate: exact quadratic geometry and a path-integral cancellation

This subsection is an optional stress test, prompted by the native read of [Tune a symmetric endpoint BH gate tangency to stress-test the fixed-block negative-score bound](../ideas/idea_f955fc275412.md). It retunes the fixed parameter $\lambda$ while retaining $\alpha=\operatorname{arcosh}(2/q-1)$. It does not evaluate the original small-$\lambda$ diagnostic, prove a finite-array derivative limit, or refute (Pr28). The geometry and the elementary smoothing identities below were independently checked in a read-only local lemma check.

**Existence and geometry of the critical endpoint.** Put $a=\alpha/2>0$. There is a unique $u>0$ satisfying
$$
\log\cosh u-\tfrac12u\tanh u=\log(1/q).
$$
Indeed the left side starts at zero, tends to infinity, and has derivative $(\tanh u-u\operatorname{sech}^2u)/2>0$: positivity follows from $\sinh(2u)>2u$. Define
$$
\lambda_{\rm crit}=a^2\frac{\tanh u}{u},\qquad t=u/a,\qquad M=1/q,
\qquad F(s,m)=e^{-\lambda_{\rm crit}s^2/2}\cosh(ms).
$$
The function $f(s)=F(s,a)$ on $s\ge0$ has the unique global maximizer $t>0$, with $f(t)=M$. To check uniqueness, its logarithmic derivative is $-\lambda_{\rm crit}s+a\tanh(as)$, and $\tanh w/w$ strictly decreases from one to zero for $w>0$. Also $f(0)=1<M$ and $f(s)\to0$.

Writing the latent alternative shift as $b=-a+v$, the population conditional ratio along the common-gate path becomes
$$
h_r(s,-a+v)=\tfrac12\{F(rs,a-v)+F(s,a+v)\}.
\tag{Pr29}
$$
In particular, $h_r(s,-a)=\{f(rs)+f(s)\}/2$. For every $0\le r<1$ its supremum in $s\ge0$ is strictly less than $M$: both summands are at most $M$, and equality would require $rs=s=t$, which is impossible. The strict gap follows by continuity and decay at infinity (at $r=0$ the first summand is the constant one). Thus the direction of the path perturbation at the exact midpoint is determined without a score approximation.

For a precise local expansion let $\delta=r-1$ and set
$$
A=F_{ss}(t,a)<0,\qquad B=F_{sm}(t,a),\qquad C=F_{mm}(t,a)=Mt^2>0.
$$
If $p=\tanh u$ and $h=\operatorname{sech}^2u$, direct differentiation gives
$$
A=Ma^2(h-p/u)<0,\qquad B=M(p+uh)>0.
$$
The global supremum $\mathscr E(r,v)=\sup_{s\ge0}h_r(s,-a+v)$ is attained at a unique smooth maximizer near $t$ for $(r,v)$ near $(1,0)$. To justify that it is the global one, choose a compact interval containing $t$ with a strict gap for $f$ outside a small neighborhood of $t$; (Pr29) preserves that gap under small parameter changes, including on the tail since $r$ stays bounded away from zero. On the remaining neighborhood $F_{ss}(t,a)<0$ and the implicit-function theorem give uniqueness.

At $(s,r,v)=(t,1,0)$ the first $r,v$ derivatives of (Pr29) vanish. Its second derivatives are
$$
h_{ss}=A,\quad h_{sr}=tA/2,\quad h_{sv}=0,\quad
h_{rr}=t^2A/2,\quad h_{rv}=-tB/2,\quad h_{vv}=C.
$$
Eliminating the maximizing $s$ by the implicit-function theorem therefore yields
$$
\mathscr E(1+\delta,v)-M
=\frac{t^2A}{8}\delta^2-\frac{tB}{2}\delta v+\frac C2v^2
+O((|\delta|+|v|)^3)
=\frac C2\{(v-d\delta)^2-e^2\delta^2\}
+O((|\delta|+|v|)^3),
\tag{Pr30}
$$
where
$$
d=\frac{tB}{2C}>0,\qquad
e=\frac{t\sqrt{B^2-AC}}{2C}>d,
\qquad e^2-d^2=-\frac{A}{4M}>0.
$$
For $\delta<0$ small the two nearby solutions of $\mathscr E(1+\delta,v)=M$ consequently satisfy
$$
v_\pm(\delta)=d\delta\pm e|\delta|+O(\delta^2).
\tag{Pr31}
$$
For example, divide (Pr30) at $v=\delta w$ by $\delta^2$ and apply the implicit-function theorem at its two simple roots. Between these two solutions the entire population ratio is below $1/q$ and has no qualifying positive root. The interval width is $2e(1-r)+O((1-r)^2)$, rather than a square root of $1-r$. None of these deterministic assertions identifies a finite-array BH FDP or its covariance derivative at this critical gate.

**An exact cancellation in the canonical symmetric smoothing problem.** Let $Z\sim N(0,1)$, $\sigma>0$, and $w_+=\max\{w,0\}$. Then
$$
\int_0^\infty\left\{\mathbb E\sqrt{(t^2+\sigma Z)_+}-t\right\}\,dt=0,
\tag{Pr32}
$$
whereas
$$
\int_0^\infty t\left\{\mathbb E\sqrt{(t^2+\sigma Z)_+}-t\right\}\,dt
=-\frac{\sigma^{3/2}}3\mathbb E(Z_+^{3/2})<0.
\tag{Pr33}
$$
Both integrals are absolutely convergent after taking the displayed expectation. For a proof, put $W=\sigma Z$. On $|W|\le t^2/2$, a Taylor expansion of $\sqrt{t^2+W}$ has its linear term canceled by symmetry and bounds the expected remainder by $O_\sigma(t^{-3})$. On the complementary event the Gaussian tail bounds the expectation by a polynomial in $t$ times $e^{-c_\sigma t^4}$. The integrands are bounded and integrable near zero. These estimates prove the claimed absolute convergence for weights one and $t$.

For $|w|\le L^2/2$, integrating the square root explicitly gives
$$
\int_0^L\{\sqrt{(t^2+w)_+}-t\}\,dt
=\frac w4+\frac w2\log(2L)-\frac w4\log|w|+O(w^2/L^2),
$$
with the continuous convention at $w=0$. Each of the three leading terms has zero expectation for the symmetric $W$. The contribution of $|W|>L^2/2$ tends to zero by the Gaussian tail; a bound by $L\sqrt{L^2+|W|}+L^2$ suffices for the actual integral there. This proves (Pr32). For the other weight the exact antiderivative is
$$
\int_0^L t\{\sqrt{(t^2+w)_+}-t\}\,dt
=\frac{(L^2+w)_+^{3/2}-w_+^{3/2}-L^3}{3}.
$$
Expand the first term as $L^3+(3/2)Lw+O(w^2/L)$ on $|w|\le L^2/2$. Its linear term again has zero expectation and the Gaussian tail vanishes. The limit is $-\mathbb EW_+^{3/2}/3$, proving (Pr33).

Thus even a valid reduction of a critical gate to a square-root smoothing profile would not establish a divergence of $\mathcal B_N$ from its pointwise large transverse derivatives: the leading constant-weight contribution can cancel exactly after the path is integrated. The next weight has a nonzero sign, but no reduction has identified its coefficient, the accompanying gate-amplitude terms, or an error bound for the actual finite-array signed score. Equations (Pr32)--(Pr33) concern only the stated elementary smoothing integrals. They are not asymptotics for $H_N$ or $\mathcal B_N$.

The remaining obligation (Pr28) therefore needs a BH-specific signed estimate along the whole rank-one path, or a finite-array critical-gate expansion that controls the integrated score and its remainders. The existing scalar localization error $O(z^{-2})$ does not provide it when multiplied by a score norm of order $n/z^2$. The quadratic gate calculation and the canonical cancellation neither prove a uniform negative-part bound nor exhibit a sequence violating it. The plan remains pending, with no new counterexample or completed sharp certificate.

### 12. Exact finite-array regression identity and the missing next coefficient

There is a useful exact representation of the cross derivative in (Pr28), distinct from differentiating a population limit. For fixed admissible $x,y<z^2$, let $G_{N,x,y}(a,b)$ be the expected actual BH FDP of independent coordinates with null distribution $N(a/z,1-x/z^2)$ and alternative distribution $N((\alpha+b)/z,1-y/z^2)$, retaining the original null labels. It is a bounded smooth function of $a,b$: differentiate the product Gaussian density under the bounded FDP integral. Each derivative has a finite global bound for this fixed $n,x,y$, given by the $L^1$ norm of a Gaussian density derivative. These bounds are NOT asserted to be uniform in dimension.

For $y>0$, $x>0$, and $|c_*|<\sqrt{xy}$, take independent $B_0\sim N(0,y)$ and $Z\sim N(0,1)$ and put
$$
A_0=(c_*/y)B_0+sZ,\qquad s^2=x-c_*^2/y.
$$
This latent representation has precisely the covariance of $H_N(x,y,c_*)$. Differentiating it with $x,y$ fixed, and integrating $Z$ by parts, gives
$$
\partial_{c_*}H_N(x,y,c_*)
=\mathbb E\left[\left(\frac{B_0}{y}-\frac{c_*Z}{ys}\right)G_a(A_0,B_0)\right]
=\frac1y\mathbb E[B_0G_a(A_0,B_0)]
-\frac{c_*}{y}\mathbb E[G_{aa}(A_0,B_0)].
\tag{Pr34}
$$
Here the subscripts $N,x,y$ on $G$ are suppressed, and $\mathbb E[ZG_a(A_0,B_0)]=s\mathbb E G_{aa}(A_0,B_0)$. For each fixed finite model the full coordinate covariance stays positive definite at $c_*^2=xy$, since both independent residual variances are positive. Its density derivative is continuous in an open neighborhood of that point. The global fixed-model bounds on $G_a,G_{aa}$ justify dominated convergence on the right of (Pr34) as $c_*\uparrow\sqrt{xy}$. Hence (Pr34) equals the actual finite-array covariance derivative at that rank-one latent boundary as well.

On the common-gate path this yields, with $B_0\sim N(0,\lambda)$,
$$
\partial_{c_*}H_N(r^2\lambda,\lambda,r\lambda)
=\frac1\lambda\mathbb E[B_0(G_{N,r^2\lambda,\lambda})_a(rB_0,B_0)]
-r\,\mathbb E[(G_{N,r^2\lambda,\lambda})_{aa}(rB_0,B_0)].
\tag{Pr35}
$$
This holds also at $r=0$ by a separate symmetry argument: $G$ is even in its centered-null shift $a$, so $G_a(0,b)=0$, while the full model with zero cross covariance is invariant under simultaneous null sign reversal and has zero cross derivative. The normalization and finite-model boundary extension in (Pr34)--(Pr35) were independently cold-checked.

In particular, a critical-gate calculation for $\mathcal B_N$ must account for both terms in (Pr35), the factor $r$, the dependence of $G$ on the residual null variance $1-r^2\lambda/z^2$, and the changes in FDP amplitude and Gaussian density across the moving gate. The sign of the linear-weight canonical integral (Pr33) alone does not identify their combined next coefficient. No such coefficient for the actual BH quantity has been derived here.

There is a further finite-array obligation before any population critical-gate coefficient could refute (Pr28). A general $O(z^{-2})$ tail-ratio or scalar localization error can exceed the extremely narrow transverse critical layer as $n\to\infty$. Empirical BH count fluctuations may also smooth the gate on a larger scale than the group-mean regularization $\eta_N$. One must either construct a finite-$N$ critical tuning and prove the corresponding largest-rank and differentiated error controls, or prove that the errors in an untuned model are smaller than the actual signed integrated main term. Neither control follows from subsections 5 or 9. Thus there is presently neither a proved obstruction to the plan nor a justified passage to step 4; the unresolved analytic input is precisely a BH-specific lower bound for the integrated quantity in (Pr35), or a fully controlled finite-array sequence making it tend to minus infinity.

### 13. Actual finite-$z$ critical retuning and the empirical-count scale

This calculation concerns the exact conditional Gaussian tail, rather than a canonical smoothing model. Keep $a=\alpha/2$ and the critical $t,\lambda=\lambda_{\rm crit},u=at$ from subsection 11. At the symmetric midpoint, both label groups have the same absolute-value distribution, with means $-a/z,+a/z$ and common residual variance $1-\ell/z^2$. Its exact tail ratio is
$$
R_z(s,\ell)=\frac{\overline\Phi((zs-a/z)/\sqrt{1-\ell/z^2})+\overline\Phi((zs+a/z)/\sqrt{1-\ell/z^2})}{2\overline\Phi(zs)}.
$$
Uniformly for $s$ in a compact neighborhood of $t>0$ and $\ell$ near $\lambda$, with the derivatives through order two needed below,
$$
R_z(s,\ell)=e^{-\ell s^2/2}\cosh(as)\{1+z^{-2}J(s,\ell)+O(z^{-4})\},
\tag{Pr36}
$$
$$
J(s,\ell)=-\frac{\ell^2s^2+a^2+\ell}{2}
+(\ell as+a/s)\tanh(as).
$$
Indeed the two normal arguments expand as
$$
zs+\frac{\ell s/2\mp a}{z}
+\frac{3\ell^2s/8\mp\ell a/2}{z^3}+O(z^{-5}).
$$
The logarithm of the corresponding one-sided tail ratio is
$$
\pm as-\ell s^2/2
+z^{-2}\{-\ell^2s^2/2-a^2/2-\ell/2
\pm(\ell as+a/s)\}+O(z^{-4}).
$$
For explicit remainder control, the identity
$$
\overline\Phi(w)=\frac{\varphi(w)}{w}
\int_0^\infty e^{-v}e^{-v^2/(2w^2)}\,dv
$$
gives the Mills expansion and its required parameter derivatives by Taylor expansion under an integrable polynomial times $e^{-v}$; here $w$ is bounded below by a positive constant times $z$. Summing the two tails gives (Pr36).

Put $p=\tanh u$ and $h=\operatorname{sech}^2u$. The critical identity $\lambda t=ap$ implies
$$
J(t,\lambda)=\frac{\lambda-a^2h}{2}=-\frac{A}{2M}>0.
\tag{Pr37}
$$
Thus the exact finite-$z$ tail at the unretuned population critical point lies ABOVE $M=1/q$ by a positive term of order $z^{-2}$. There is a unique nearby local tangency $(s_z,\ell_z)$ satisfying $R_z(s_z,\ell_z)=M$ and $\partial_s R_z(s_z,\ell_z)=0$, and
$$
\ell_z=\lambda+\frac{\lambda-a^2h}{t^2z^2}+O(z^{-4}),
\qquad s_z=t+O(z^{-2}).
\tag{Pr38}
$$
To justify this assertion, at the limiting double root the derivatives of the first equation in $(\ell,s)$ are $(-Mt^2/2,0)$ and the $s$ derivative of the second equation is $A<0$. Their Jacobian is invertible. The local implicit-function theorem, (Pr36), and (Pr37) give (Pr38). This is a LOCAL conditional-tail tangency; it is not a statement about the actual random largest BH rank, global root exclusion, or an integrated covariance derivative. The expansion and retuning sign were independently checked in a read-only calculation.

At this exact conditional tangency put $p_z=2\overline\Phi(zs_z)$ and $N=2n$. Conditional on the midpoint latent shift, the count $C_z$ of coordinates below the fixed p-value threshold $p_z$ is exactly $\operatorname{Bin}(N,Mp_z)$. Consequently
$$
\operatorname{Var}\left(\frac{C_z}{Np_z}\right)
=\frac{M(1-Mp_z)}{Np_z}.
\tag{Pr39}
$$
For $z^2=2c\log N$, (Pr38) and Mills bounds give $p_z\asymp N^{-ct^2}/\sqrt{\log N}$. With $\eta_z=(z^2-\ell_z)/n$, the ratio of the standard deviation in (Pr39) to $\sqrt{\eta_z}$ is asymptotic to
$$
\sqrt{\frac{M}{2z^2p_z}}\longrightarrow\infty.
\tag{Pr40}
$$
When $ct^2<1$, both scales tend to zero, but the empirical-count scale is larger. This comparison does not treat the two fluctuations as independent: the group-mean score and the count are calculated from the same observations. It proves that a regularization calculation based only on the small group-mean eigenvalue cannot simply omit empirical gate fluctuations. A largest-rank process estimate and a signed differentiated error bound are still needed.

### Historical next execution task (superseded by Failure)

Continue step 3 with the exact finite-array quantity $\mathcal B_N$ in subsection 10. Prove the negative-part bound (Pr28), possibly by establishing $\mathcal B_N\ge0$ or another uniform lower bound, or rigorously exhibit a sequence violating it and fail this plan at its common-gate stress test. The positive part need not be bounded separately for this fixed-$q$ obligation, because (Pr24)--(Pr26) already account for its cancellation and the complete correction. Separate component-derivative convergence remains an optional stronger approach; scalar FDR convergence does not justify it. Any signed-score argument must cover the rank-one latent path, $r\downarrow0$, and the Gaussian truncation remainder. The negative-null full-cost boundedness obligation in (Pr16) is settled by (Pr17)--(Pr23); do not redo it. The regularized-simplex small-$q$ estimate also remains open. If the common-gate full-cost test survives, step 4 must still prove the arbitrary all-null trace bound and the block-atom trace budget with the stated universal coefficient; neither a bounded fixed-$q$ cost nor (Pr26) proves that sharp budget.

For the optional retuned critical gate, build on (Pr29)--(Pr35) rather than redoing the midpoint derivative: its first path derivative vanishes, the hole width is linear in $1-r$, and the leading constant-weight smoothing integral is zero. The missing next coefficient must include both regression terms, the moving gate amplitude/density, and the residual variance change, followed by finite-array score and empirical-gate control. A pointwise singularity, or only the sign in (Pr33), is insufficient to fail the plan.

## Failure

Execution closed, 2026-11-04. This proof plan fails at its mandatory step 3 because it has not established the dimension-uniform negative-part bound (Pr28) for the actual finite-array common-gate cost. The exact completion algebra, one-sided negative-null diagnostic, correction bound (Pr26), and finite-array score identities remain valid progress. They do not supply the missing BH-specific lower bound. This is an unresolved proof obstruction, not a counterexample certificate and not a claim that (Pr28), (T), or the target statement is false.

The attempted direct integration of (Pr35) does not remove the uncontrolled derivative. For fixed $b\ne0$, put $D_r(b)=(G_{N,r^2\lambda,\lambda})_a(rb,b)$. Then
$$
\frac{dD_r(b)}{dr}
=b(G_{N,r^2\lambda,\lambda})_{aa}(rb,b)
+2r\lambda(G_{N,r^2\lambda,\lambda})_{ax}(rb,b).
$$
Substitution and integration by parts give the exact finite-model identity
$$
\mathcal B_N=\mathbb E\left[
-\frac{D_1(B_0)}{B_0}
+\int_0^1\left(\frac{B_0}{\lambda}+\frac1{B_0}\right)D_r(B_0)\,dr
+\int_0^1\frac{2\lambda r^2}{B_0}
(G_{N,r^2\lambda,\lambda})_{ax}(rB_0,B_0)\,dr
\right].
\tag{Pr41}
$$
At $B_0=0$ the quotients have continuous extensions by evenness of $G$ in its first mean. For each fixed finite model, the smooth Gaussian-density derivative bounds and $1-r^2\lambda/z^2>0$ justify the operations. They give no bound uniform in $N$. In particular, the final $G_{ax}$ term describes the actual residual-variance change and cannot be dropped. At the population critical point $b=-a$, the gate derivatives are $h_a=-Mt\tanh(u)/2$ and $h_x=-Mt^2/4$, and
$$
b h_a+2\lambda h_x=0.
$$
Thus the path derivative includes a same-order cancellation involving that residual change. Bounded FDP, null sign symmetry, and the current Gaussian score norms do not control the remainder's sign.

The optional critical-gate route has not supplied a complete next coefficient for $\mathcal B_N$. A formal population calculation that includes moving amplitude, latent density and path weights can suggest a positive rather than negative singular contribution; no such suggestion is used as a proved result here. It lacks a justified reduction of actual BH FDP, including any no-population-root finite-rank contribution, and a signed uniform derivative remainder. The strictly proved finite-$z$ expansion (Pr36)--(Pr38) is separate from that unfinished population calculation. It shows that the untuned critical model already has a deterministic $z^{-2}$ gate offset. Even after local retuning, (Pr39)--(Pr40) show why a group-mean smoothing model alone is insufficient. Neither population scalar convergence nor a canonical weighted moment settles these errors or the sign of the actual integrated score.

Step 4 has an additional independent obstruction: no general all-null trace estimate or dimension-uniform block-atom energy budget with the coefficient in (T) has been constructed. The exact SVD support function and a bounded fixed-$q$ diagnostic do not prove that sharp Gaussian estimate. Continuing the listed algebraic tools would therefore leave the principal new analytic inequalities unproved; they cannot be installed as assumptions to reach the target.

A replacement proof plan would need a new finite-array signed-score or largest-rank argument that actually proves (Pr28), followed by an independently justified all-null estimate and the sharp block certificate; alternatively it would need a rigorously controlled finite-array witness that disproves the proposed certificate. Neither is provided by this attempt. All verified Progress is preserved, steps 3--5 remain unchecked, and the target asset, its statement and its draft status are unchanged. No original-conjecture counterexample or completed proof is asserted.

