---
type: plan
status: failed
title: Centered folded-tail null-noise interpolation and a signed completion test
target_asset: gaussian_bh_two_sided_sharp_upper
inspired_by:
  - idea_8ccb5a5a1c27
  - idea_7d718e40cb44
  - idea_45ea077b792d
  - idea_63d2ef1d26bf
---

# Centered folded-tail null-noise interpolation and a signed completion test

## Goal

Target: [Sharp uniform upper-bound target for two-sided Gaussian BH](../assets/gaussian_bh_two_sided_sharp_upper.md).

Prove the unchanged bound, uniformly over all dimensions, means, and unit-diagonal PSD covariances. The proposed new route exploits that every two-sided null has mean exactly zero and that the labelled BH FDP is even in each statistic. These facts annihilate the transverse mixed scores that invalidated a one-sided completion recipe. They do not, by themselves, establish a dimension-uniform completion budget.

This plan first derives an explicit finite Gaussian corner matrix, then tries a fixed, falsifiable semidefinite relaxation. Its proposed bound controls that matrix against *every* correlation matrix, a stronger requirement than controlling its own generating covariance. Execution must test this stronger assertion early and fail the plan if it is obstructed; replacing it with the original conjecture is not a completion of this route. Searches for Gaussian BH two-sided bounds, Gaussian threshold interpolation, and Gaussian null-smoothing semidefinite bounds returned no library results. No library statement is cited or proof adapted.

## Plan

1. [x] **Construct a null-noise path with an exact independent-null baseline.** Fix $q<1/2$, $N$, the actual means, and initially positive-definite $\Sigma$. Put $J=\{i:\theta_i=0\}$, $A=[N]\setminus J$, $P=\operatorname{Diag}(\mathbf1_J)$, and $Q=I-P$. For independent $G\sim N(0,\Sigma)$ and $Z\sim N(0,I)$ define

   $$
   T_r=\theta+(Q+rP)G+\sqrt{1-r^2}\,PZ,\qquad 0\le r\le1,
   $$

   $$
   C_r=(Q+rP)\Sigma(Q+rP)+(1-r^2)P.
   $$

   Verify unit diagonals and positive definiteness. The $AA$ block stays fixed, null/null off-diagonals are $r^2\Sigma_{ij}$, and null/alternative entries are $r\Sigma_{ij}$. Let $f_q(x)$ be the actual ordinary-BH FDP computed from $2\overline\Phi(|x_i|)$ with the fixed labels $J$. Reprove the forced-zero identity, including largest ranks and ties, to establish

   $$
   H(0):=\mathbb E f_q(T_0)=q|J|/N.
   $$

   Alternatives may remain arbitrarily dependent. Treat $J=\varnothing$ and $N=1$ separately.

2. [x] **Enumerate the exact two-sided mixed rank stencils.** Put $t_k=\overline\Phi^{-1}(qk/(2N))$ and $\mathcal B=\{-t_k,t_k:1\le k\le N\}$. For each pair $i\ne j$ and boundaries $a,b\in\mathcal B$, compute from the four full BH runs

   $$
   \Delta_{ij}^{a,b}f(x_{-ij})
   =f(a+,b+,x_{-ij})-f(a+,b-,x_{-ij})
   -f(a-,b+,x_{-ij})+f(a-,b-,x_{-ij}).
   $$

   Derive a rank/count formula for this finite stencil using the actual remaining-coordinate bins and null counts. Check unequal boundary levels and equal levels separately; include both signs and every possible rank jump. On a negative boundary increasing the statistic decreases its absolute value, so its threshold-entry orientation is opposite to the positive boundary. Verify the formula by exact rational enumeration for $N\le4$ against the four direct BH runs. This test checks the rank algebra, not the uniform estimate below.

3. [x] **Derive the folded corner matrix without a conditioning envelope.** For $r\in[0,1]$ let $g_r^{ij}(a,b)$ be the bivariate Gaussian density of $(T_{r,i},T_{r,j})$, and set

   $$
   L_{ij}(r)=\sum_{a,b\in\mathcal B}g_r^{ij}(a,b)
   \mathbb E[\Delta_{ij}^{a,b}f(T_{r,-ij})\mid T_{r,i}=a,T_{r,j}=b].
   $$

   Write the conditional Gaussian mean and covariance by the two-coordinate Schur complement. Prove Gaussian density differentiation and integrate over the finite threshold grid to obtain

   $$
   H'(r)=\frac12\operatorname{tr}(\Sigma M(r)),\qquad
   M_{ij}(r)=c_{ij}(r)L_{ij}(r),\quad M_{ii}(r)=0,
   $$

   where $c_{ij}(r)=2r$ for two nulls, $1$ for a null/alternative pair, and $0$ for two alternatives. Define

   $$
   K=\frac12\int_0^1 M(r)\,dr.
   $$

   Prove the exact signed identity

   $$
   \operatorname{FDR}^{(2)}_{\rm BH}(q;N,\theta,\Sigma)
   =q|J|/N+\operatorname{tr}(\Sigma K).
   \tag{I}
   $$

   Integrate the signed kernels before any optimization. For positive-definite endpoints all conditional laws are nonsingular and differentiation is justified on the compact path. Do not discard favorable corners or introduce a dimension-dependent regularization remainder.

4. [x] **Run the centered folded-tail obstruction gate before attempting a budget.** First prove $L_{ij}(0)=0$ whenever a null is involved: the null coordinate is independent, centered, and $f_q$ is even in that coordinate, so its mixed Gaussian score has zero expectation. If the target covariance already has an independent null block independent of alternatives, the whole path is constant and all relevant $L_{ij}(r)$ and $K$ vanish. This directly removes the one-sided constant-path transverse-score witness; checking only the scalar derivative would not suffice.

   Reconstruct, rather than assume, the centered two-sided analogue of the weak-null-correlation witness in [Proof note and bounded independent check of the completion obstruction](../ideas/idea_63d2ef1d26bf.md). Take $N=2n$, $z_N=\sqrt{2c\log N}$ with sufficiently small fixed $c>0$, null statistics

   $$
   T_i=\sqrt{\lambda}/z_N\,W+\sqrt{1-\lambda/z_N^2}\,\epsilon_i,
   $$

   and independent alternatives $T_j=\alpha/z_N+\epsilon_j$, where $\cosh\alpha=2/q-1$. All null means are zero. The candidate conditional population equation is

   $$
   \frac12 e^{-\lambda s^2/2}\cosh(\sqrt\lambda Ws)
   +\frac12\cosh(\alpha s)=1/q.
   $$

   Prove uniform tail ratios and localization of the largest finite-$N$ BH root before using this equation. With $D=\alpha\sinh\alpha/2$, rederive the local expansion suggested by

   $$
   e^{-\lambda s^2/2}\cosh(\sqrt\lambda Ws)
   =1+\frac\lambda2(W^2-1)s^2
   +\frac{\lambda^2}{24}(W^4-6W^2+3)s^4+O(\lambda^3),
   $$

   namely an averaged local FDP of $q/2-q\lambda^2/(4D)+o(\lambda^2)$. Justify Gaussian truncation in this expansion. Its sign contrasts with the positive first-order gain from inadmissible negative null means; it is a diagnostic calculation to prove, not a premise of the theorem.

   Also evaluate the signed matrix on independent models, arbitrary-mean two-coordinate models, and the centered singular-simplex family from [Singular Gaussian simplex forces every independent-residual representation to have a vacuous capped envelope](../ideas/idea_45ea077b792d.md), initially regularized. Test weak common-gate models if the first cases survive. Preserve unfavorable results. A verified dual witness violating the budget in step 5 stops this plan, even if its actual FDR remains small.

5. [x] **Prove or refute one precise signed semidefinite budget.** For the *integrated* matrix in step 3 define the concrete finite-dimensional cost

   $$
   \mathcal D(K)=\min\left\{\sum_i d_i:
   \operatorname{Diag}(d)-K\succeq0\right\}.
   $$

   Derive its dual

   $$
   \mathcal D(K)=\max_{\Gamma\succeq0,\ \Gamma_{ii}=1}
   \operatorname{tr}(\Gamma K),
   $$

   including strong duality via a strictly feasible scalar diagonal. This gives an explicit obstruction search over actual PSD correlation matrices, rather than an assertion about a named unknown scalar remainder. Attempt to prove universal finite constants $C,U_0$ such that for *every* $U\ge U_0$, $q=2\overline\Phi(U)$, every finite $N$, all actual means with $J=\{\theta_i=0\}$, and every positive-definite unit-diagonal $\Sigma$,

   $$
   \mathcal D(K)\le
   \frac{qU}{2\sqrt{2\pi}}+Cq\{1+\log(2+U)\}.
   \tag{D2}
   $$

   The executable construction task is to use the exact stencils from step 2 to produce explicit $d_i$ and a checkable factorization of $\operatorname{Diag}(d)-K$ as a sum or integral of PSD quadratic forms, *after* summing the two signs and the actual conditional rank gates. Integrate its trace using the ordinary Gaussian Mills inequalities, proving the displayed constants and the same remainder for all models. A numerical SDP is an obstruction probe, not this construction. Absolute row sums, a separately optimized matrix at each $r$, or independent per-null rank choices are not substitutes for (D2).

   In particular the one-sided completion counterexample is not dismissed merely because null means change: prove the symmetry cancellations in step 4 and then check that a different centered-null family does not still make $\mathcal D(K)$ diverge with $N$. If a PSD witness $\Gamma$ shows such divergence at a fixed arbitrarily small $q$, or violates every universal $C$ along $q\downarrow0$, record it as a refutation of (D2) and fail the plan. Do not replace (D2) by $\operatorname{tr}(\Sigma K)$ and call the original target proved. No general validity of this stronger completion assertion is currently known.

6. [ ] **Finish only after the certificate is proved.** By PSD trace pairing, (I) and (D2) imply

   $$
   \operatorname{FDR}^{(2)}_{\rm BH}
   \le q+\frac{qU}{2\sqrt{2\pi}}+Cq\{1+\log(2+U)\}.
   $$

   For any singular admissible $\Sigma$, use $(1-\delta)\Sigma+\delta I$ and a common Gaussian coupling. For each fixed model the FDP is almost surely continuous at the limit outside the finite marginal threshold events $p_i=qk/N$, each of probability zero. Bounded convergence transfers the scalar bound without requiring convergence of $K$ or of an SDP optimizer. Derive $U/\sqrt{\log(1/q)}\to\sqrt2$ by Mills inequalities, then take the supremum at each $q$. Show explicitly that the resulting $q_\varepsilon$ depends only on the universal constants, covering arbitrarily growing dimension and means and all singular ties.

## Verification

Required certificates are the four-cell rank identity, the signed interpolation formula (I), the centered-null cancellations, and an actual feasible diagonal plus PSD factorization proving (D2) with uniform numerical constants. The diagonal-budget assertion is strictly stronger than the scalar conjecture and may be false; its failure must be reported as a route obstruction. The early folded-tail calculation neither proves (D2) nor rules out all centered-null obstructions. Small-dimensional checks and failed counterexample searches cannot replace the matrix proof. If it succeeds, step 6 gives exactly the unchanged leading constant $1/(2\sqrt\pi)$ and all target quantifiers.

## Assumed definitions

Use only the approved definitions [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), [false discovery rate](../definitions/false_discovery_rate.md), and [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md).

No draft definition, unproved asset, or library result is assumed. Draft ideas provide diagnostic families and warnings only; all computations used here must be rederived. Gaussian differentiation, finite-grid integration by parts, semidefinite duality, Mills bounds, and finite-array crossing localization are internal proof obligations. No negative true-null mean is admissible in this track. The target remains draft and unchanged.

## Difference from failed plans

- **`plan_two_sided_signed_face_budget_20261104`:** replaces one-coordinate rank-tail differences and the disproved opposite-kernel ordering by a covariance path, explicit two-coordinate rank stencils, and a specified global semidefinite test. It allows positive integrated corrections of order $q/U$ in the recorded two-coordinate example. It does not claim that sign averaging alone supplies the half constant; that coefficient remains an obligation in (D2).
- **`plan_gaussian_bh_one_sided_fixed_alternative_schur_budget_20261104`:** keeps the alternative covariance fixed but uses exact centered folded tails and an optimized *signed, integrated* completion instead of the failed row-absolute/additive Gram recipe. Here the independent-null constant-path model has a zero full mixed kernel, proved by coordinatewise evenness; its one-sided transverse score was nonzero. This cancellation is specific and must be checked before budgeting.
- **`plan_gaussian_bh_one_sided_global_corner_budget_20261104`:** its positive-gain completion witness uses negative composite-null means, excluded by the two-sided definition. The centered replacement has a cosh tail ratio and a vanishing first-order Gaussian-mixing gain; step 4 requires proving its second-order sign and finite-$N$ transfer. This is a new test of the completion assertion, not a claim that every centered completion is bounded. The general warning that a dual covariance can differ from the generating covariance is retained as the explicit obstruction criterion in step 5.

## Failure

Step 5 is false for the fully diagonal completion cost actually specified in (D2). For every fixed $q\in(0,1/2)$, a positive-definite centered-null Gaussian family below satisfies $\mathcal D(K_N)\to\infty$ at least as fast as a positive constant times $\log N$. Its explicit dual witness is $\Gamma_N=\mathbf1\mathbf1^{\mathsf T}$. This disproves (D2), not the unrestricted sharp-FDR target. The target asset is unchanged; step 6 is not executed. Steps 1--4 and the refutation alternative in step 5 are established below.

### 1. Exact baseline and path

For a p-value vector, set $C_h=\#\{i:p_i\le qh/N\}$. The largest qualifying rank is $R=\max(\{0\}\cup\{h:C_h\ge h\})$. If $R>0$ and $C_R>R$, the integer $s=C_R$ would satisfy $C_s\ge C_R=s$, contradicting maximality. Thus $C_R=R$, including ties.

Replace $p_i$ by zero and denote the resulting rank by $R_i^0\ge1$. The deterministic forced-zero identity is
$$
\mathbf1\{i\in\mathcal R_q(p)\}/(R\vee1)
=\mathbf1\{p_i\le qR_i^0/N\}/R_i^0.
$$
Indeed, if $i$ is rejected at rank $R$, any larger rank qualifying after replacement would also qualify before replacement, because $p_i\le qR/N$ is already below every larger threshold. Conversely, if $p_i\le qR_i^0/N$, rank $R_i^0$ still qualifies before replacement, and no larger rank can qualify because replacement only decreases p-values. These arguments use non-strict inequalities and do not assume distinct p-values.

At $r=0$ every null p-value is exactly uniform and independent of all the other p-values. Conditional on them, $R_i^0$ is fixed, so the displayed expectation is $q/N$. Summation gives $H(0)=q|J|/N$, with arbitrary dependence among alternatives. If $J$ is empty, FDP is identically zero. If $N=1$, its FDR is $q$ for a null and zero otherwise, and $K=0$.

The covariance path has unit diagonals and the blocks in step 1. At $r=0$ it is $I_{JJ}\oplus\Sigma_{AA}$ and is positive definite. At $r>0$, $Q+rP$ is invertible, so its congruence of $\Sigma$ is positive definite; adding $(1-r^2)P$ preserves this. Continuity on $[0,1]$ gives a positive minimum eigenvalue for this fixed finite model.

### 2. Four-cell rank formula and exact check

For each remaining coordinate $h$, let its bin be $b_h=\min\{v:p_h\le qv/N\}$, or $N+1$ if none qualifies. At levels $v=1,\ldots,N$, put
$$
n_v=\#\{h\ne i,j:b_h\le v\},\qquad
w_v=\#\{h\in J\setminus\{i,j\}:b_h\le v\}.
$$
Consider boundaries at levels $k,l$. An entry indicator $u\in\{0,1\}$ for coordinate $i$ means bin $k+1-u$; $v\in\{0,1\}$ for coordinate $j$ means bin $l+1-v$. To avoid confusing this indicator with a rank, write the rank argument as $h$ and define
$$
e_i(h;u)=\mathbf1\{h\ge k+1\}+u\mathbf1\{h=k\},\qquad
e_j(h;v)=\mathbf1\{h\ge l+1\}+v\mathbf1\{h=l\}.
$$
All qualifying ranks except $k,l$ are independent of $u,v$. Put
$$
r_* =\max\left(\{0\}\cup
\{h\notin\{k,l\}:n_h+\mathbf1\{h\ge k+1\}+\mathbf1\{h\ge l+1\}\ge h\}\right).
$$
For $k<l$, $r_{uv}$ is the maximum of $r_*$, level $k$ if $n_k+u\ge k$, and level $l$ if $n_l+1+v\ge l$. For $k>l$, interchange $(i,k,u)$ and $(j,l,v)$. For $k=l$, the only extra candidate is $k$ if $n_k+u+v\ge k$. These formulas cover jumps to any value of $r_*$ and every combination of equal or unequal boundary levels. With $\ell_i=\mathbf1\{i\in J\}$, define $F_{uv}=0$ if $r_{uv}=0$, and otherwise
$$
F_{uv}=\frac{w_{r_{uv}}+\ell_i e_i(r_{uv};u)+\ell_j e_j(r_{uv};v)}{r_{uv}}.
$$
For $a=\sigma t_k$, $b=\tau t_l$, $\sigma,\tau\in\{-1,1\}$, the exact stencil is
$$
\Delta_{ij}^{a,b}f=\sigma\tau(F_{11}-F_{10}-F_{01}+F_{00}).
$$
The sign follows because increasing a positive boundary enters its tail, whereas increasing a negative boundary exits it. Other coordinates exactly on boundaries can be assigned their non-strict bins; these exceptional values have probability zero in subsequent conditional Gaussian integrals.

A short deterministic rational check used $q=1/5$, all null labelings, every remaining-coordinate bin, all $k,l$, and all four sign pairs for $N=2,3,4$. Direct sorted-p-value BH runs were compared with the formula, using within-bin rational p-values and the two adjacent sides of each boundary. All 26,816 four-cell values and 26,816 signed stencil checks passed. There is no mixed pair for $N=1$. Since bin representatives exhaust all changes in this finite rank algebra, the check covers ties of p-values within bins as well as all rank jumps. It is not evidence for (D2).

### 3. Signed finite Gaussian interpolation

For $B=\{i,j\}$ and $E=[N]\setminus B$, write $C=C_r$ and $y_B=(a,b)^{\mathsf T}$. The conditional law used in $L_{ij}$ has mean and covariance
$$
\theta_E+C_{EB}C_{BB}^{-1}(y_B-\theta_B),\qquad
C_{EE}-C_{EB}C_{BB}^{-1}C_{BE}.
$$
The covariance is positive definite by the Schur complement (with the empty conditional law interpreted directly when $N=2$).

For the full Gaussian density $\varphi_C(x-\theta)$, direct differentiation gives
$$
\frac{d}{dr}\varphi_C
=\frac{\varphi_C}{2}\left[(x-\theta)^{\mathsf T}C^{-1}C'C^{-1}(x-\theta)-\operatorname{tr}(C^{-1}C')\right]
=\frac12\sum_{i,j}C'_{ij}\partial_{ij}\varphi_C.
$$
The fixed-model eigenvalue bound and compactness of the path dominate these derivatives by an integrable Gaussian times a polynomial. Thus differentiation under the bounded-FDP integral is valid. The FDP is constant on the finite rectangular grid cut out by all $\pm t_k$. Twice integrating by parts on its cells gives, for $i\ne j$,
$$
\int f_q\partial_{ij}\varphi_C
=\sum_{a,b\in\mathcal B}\int\Delta_{ij}^{a,b}f(x_E)\varphi_C(a,b,x_E)\,dx_E
=L_{ij}(r).
$$
All corner signs are retained. The diagonal derivative of $C$ is zero, and $C'_{ij}=\Sigma_{ij}c_{ij}(r)$ with exactly the coefficients in step 3. Therefore
$$
H'(r)=\tfrac12\operatorname{tr}(\Sigma M(r)),\qquad
H(1)-q|J|/N=\operatorname{tr}(\Sigma K),\quad
K=\tfrac12\int_0^1M(r)\,dr.
$$
This is (I) for every finite positive-definite model, with symmetric $K$ and $K_{ii}=0$. No absolute values or separate optimizations in $r$ have been introduced.

### 4. Centered cancellations and elementary test matrices

At $r=0$, a null coordinate $i$ is independent centered standard normal. In the mixed-density score $\partial_{ij}\varphi_C/\varphi_C$, its factor is $x_i$ times a score depending only on the other coordinates. Coordinatewise evenness of $f_q$ makes its integral zero. Hence $L_{ij}(0)=0$ for every pair involving a null. If $\Sigma_{JJ}=I$ and $\Sigma_{JA}=0$, every null remains independent of every other coordinate throughout the constant path. The same argument gives every relevant $L_{ij}(r)=0$ and $K=0$, even when the alternatives are dependent.

Here are exact evaluations of the other prescribed elementary tests. For $N=2$, put $u=\overline\Phi^{-1}(q/2)$, $v=\overline\Phi^{-1}(q/4)$, and $J_{ab}=\Pr(|T_1|\ge a,|T_2|\ge b)$. With coordinate 1 null and coordinate 2 of any nonzero mean,
$$
H=q/2+\tfrac12J_{uu}-J_{vu}.
$$
This follows by splitting null rejection into $|T_1|\ge v,|T_2|<u$ (FDP one) and both absolute values at least $u$ (FDP one half). With both means zero,
$$
H=q+J_{uu}-J_{vu}-J_{uv}.
$$
If their correlation is $\rho\ne0$, the unique off-diagonal entry is $k=(H-q|J|/2)/(2\rho)$ and $\mathcal D(K)=2|k|$. At $\rho=0$, $K=0$ by the centered cancellation. If both means are nonzero, FDP and $K$ vanish. These exhaust arbitrary two-coordinate means and labels; they do not establish a uniform budget.

For the centered regularized simplex, all means are zero and $\rho_\delta=-(1-\delta)/(N-1)$, $0<\delta<1$, off the diagonal. Exchangeability gives a common off-diagonal entry
$$
k_\delta=\frac{H_\delta-q}{N(N-1)\rho_\delta}.
$$
The exact dual value is $N(N-1)k_\delta$ if $k_\delta\ge0$, and $-Nk_\delta$ otherwise: writing a correlation matrix as a Gram matrix shows $0\le\mathbf1^{\mathsf T}\Gamma\mathbf1\le N^2$, with the extrema achieved by the simplex correlation matrix and by $\mathbf1\mathbf1^{\mathsf T}$. This evaluates the finite signed matrix without claiming any unproved rate for $H_\delta-q$. The common-gate family below supplies the decisive obstruction without requiring such a rate.

### 5. Uniform folded tails and largest-rank finite-array transfer

Fix any $q\in(0,1/2)$ and set $\alpha=\operatorname{arcosh}(2/q-1)>0$, $D=\alpha\sinh\alpha/2$, and $c=1/100$. For even $N=2n$, put $z=\sqrt{2c\log N}$. For $b\in\{0,1\}$ define, with independent standard Gaussian $W,\epsilon_1,\ldots,\epsilon_N$,
$$
T_i=\frac{\sqrt\lambda}{z}W+\sqrt{1-\lambda/z^2}\,\epsilon_i\quad(i\le n),
$$
$$
T_j=\frac\alpha z+\frac{b\sqrt\lambda}{z}W+\sqrt{1-b^2\lambda/z^2}\,\epsilon_j\quad(j>n).
$$
For all sufficiently large $N$, these have unit marginal variance and positive-definite covariance, because all independent residual variances are positive. Their true-null set is exactly the first $n$ coordinates. The case $b=0$ is the centered independent-alternative diagnostic requested in step 4; $b=1$ is the additional weak common-gate test.

Write $a=\sqrt\lambda W$ and $U=\overline\Phi^{-1}(q/2)>0$. Conditional on $W$, a group member has distribution $m/z+\sqrt{1-v/z^2}\epsilon$, with $(m,v)=(a,\lambda)$ or $(\alpha+ba,b^2\lambda)$. Uniformly for $|a|\le\varepsilon$, $0\le\lambda\le\lambda_0$ and $U\le x\le3z/2$, ordinary Mills inequalities give
$$
\frac{\Pr(|m/z+\sqrt{1-v/z^2}\epsilon|\ge x)}{2\overline\Phi(x)}
=e^{-vs^2/2}\cosh(ms)+o_N(1),\qquad s=x/z.
$$
For completeness, the two normal arguments are $y_\pm=x\mp m/z+vx/(2z^2)+O(z^{-3})$, with $y_\pm-x=O(z^{-1})$ on this range. Integrating $u<\varphi(u)/\overline\Phi(u)<u+1/u$ between $x$ and $y_\pm$ gives
$$
\log\frac{\overline\Phi(y_\pm)}{\overline\Phi(x)}
=\pm ms-vs^2/2+O(z^{-1}).
$$
All constants may depend on this fixed $q,\varepsilon,\lambda_0$; uniformity in $q$ is unnecessary for the fixed-$q$ obstruction. Summing the two signs proves the asserted uniform ratio down to $x=U$.

Consequently the conditional mixture CDF divided by its p-value threshold $t=2\overline\Phi(x)$ converges uniformly on $[t_{\min},q]$, $t_{\min}=2\overline\Phi(3z/2)$, to
$$
h_b(s,a,\lambda)=\tfrac12e^{-\lambda s^2/2}\cosh(as)
+\tfrac12e^{-b^2\lambda s^2/2}\cosh((\alpha+ba)s).
$$
At $(a,\lambda)=(0,0)$ it is $(1+\cosh(\alpha s))/2$, equals $1/q$ at $s=1$, and has derivative $D>0$ there. On $0\le s\le3/2$ its second derivative at the base is at least $\alpha^2/2>0$. Compactness and the implicit-function theorem therefore give fixed small $\varepsilon,\lambda_0>0$ and a smooth root $S_b(a,\lambda)\in(.9,1.1)$, with strictly positive second derivative on this interval of $s$ after reducing the parameter neighborhood if needed. Since $h_b(0,a,\lambda)=1<1/q$, strict convexity shows there is no earlier root. For every sufficiently small fixed $\delta>0$, uniformly on this parameter neighborhood, $h_b$ is bounded strictly below $1/q$ for $0\le s\le S_b-\delta$, and is strictly above it at $S_b+\delta$. These facts use only $s\le3/2$; no assertion about larger $s$ is needed.

Conditional on $W$, each group consists of $n$ iid continuous p-values. A grid of $M_N=\lceil N^{1/4}\rceil$ true-CDF quantiles, Chebyshev at each quantile with error $N^{-1/4}$, and monotonicity give
$$
\Pr\left(\sup_t|\widehat F_h(t)-F_h(t)|>3N^{-1/4}\mid W\right)=O(N^{-1/4})
$$
for each group $h$, with constants independent of $W$. Indeed each grid failure is $O(N^{-1/2})$, there are $O(N^{1/4})$ grid points, and between grid points the true CDF changes by at most $1/M_N$. Mills bounds give $t_{\min}\asymp N^{-9c/4}/\sqrt{\log N}$. Since $9c/4<1/4$, both $N^{-1/4}/t_{\min}$ and $(q/N)/t_{\min}$ tend to zero.

Thus the empirical mixture CDF divided by $t$ converges to $h_b$ uniformly over the full interval $[t_{\min},q]$, uniformly in $|a|\le\varepsilon$. Every BH grid value $t=qk/N\ge2\overline\Phi((S_b-\delta)z)$ fails the BH inequality, by the strict below-line margin. A grid value within $q/N$ of $2\overline\Phi((S_b+\delta)z)$ satisfies it, by the above-line margin and the negligible relative grid spacing. Its scaled normal score changes by $o(1)$ under this rounding, as follows either by integrating the Mills hazard or by the derivative of the inverse tail. This value is above $t_{\min}$ and yields polynomially many rejections. Therefore the LARGEST BH threshold, not merely a selected local root, has scaled normal score converging in conditional probability to $S_b(a,\lambda)$.

At the selected threshold $t_N=qR/N$, the identity $R=Nt_N/q$ and the null empirical CDF give convergence of the actual FDP to
$$
g_b(a,\lambda)=\frac q2e^{-\lambda S_b(a,\lambda)^2/2}\cosh(aS_b(a,\lambda)).
$$
The relative empirical error is negligible because $t_N\ge t_{\min}$ with probability tending to one. At the root, $0\le g_b\le1$ because the other group contribution to $h_b=1/q$ is nonnegative. For $E_\lambda=\{|\sqrt\lambda W|\le\varepsilon\}$, boundedness now yields
$$
L_b(\lambda):=\mathbb E[\mathbf1_{E_\lambda}g_b(\sqrt\lambda W,\lambda)]
\le\liminf_N H_{N,b}(\lambda)
\le\limsup_N H_{N,b}(\lambda)
\le L_b(\lambda)+\Pr(E_\lambda^c).
$$
Here limits are along even $N$. This sandwich requires neither a population approximation outside $E_\lambda$ nor existence of a full limiting FDR there.

### 6. Local expansion, including the negative diagnostic

All following derivatives of $S_b$ are at $(a,\lambda)=(0,0)$, where $S_b=1$. Implicit differentiation gives
$$
(S_b)_a=-b/\alpha,\qquad
(S_b)_{aa}=\frac{b^2\sinh\alpha/\alpha-1/2}{D}.
$$
Indeed $h_s=D$, $h_a=b\sinh\alpha/2$, $h_{aa}=(1+b^2\cosh\alpha)/2$, $h_{sa}=b(\sinh\alpha+\alpha\cosh\alpha)/2$, and $h_{ss}=\alpha^2\cosh\alpha/2$ at the base, which give the displayed derivatives by $h_sS_{aa}+h_{aa}+2h_{sa}S_a+h_{ss}S_a^2=0$.

For a smooth bounded root on this neighborhood, expansion of the null folded factor by weighted degree, with $a$ of degree one and $\lambda$ of degree two, gives
$$
e^{-\lambda S_b^2/2}\cosh(aS_b)
=1+\frac{a^2-\lambda}{2}
\left[1+2S_a a+(S_a^2+S_{aa})a^2+2S_\lambda\lambda\right]
+\frac{a^4-6\lambda a^2+3\lambda^2}{24}+R(a,\lambda).
$$
For fixed sufficiently small neighborhood the remainder is bounded by a constant times $|a|^5+\lambda|a|^3+\lambda^2|a|+\lambda^3$. Substituting $a=\sqrt\lambda W$ gives expected remainder $O(\lambda^{5/2})+O(\lambda^3)=o(\lambda^2)$. Gaussian truncation causes errors smaller than every power of $\lambda$: $\Pr(E_\lambda^c)\le2e^{-\varepsilon^2/(2\lambda)}$, and the same holds for each fixed polynomial moment on $E_\lambda^c$ up to a polynomial prefactor. Symmetry and $\mathbb EW^2=1$, $\mathbb EW^4=3$ then give
$$
L_b(\lambda)=\frac q2+
\frac q2\lambda^2\left(S_a^2+S_{aa}\right)+o(\lambda^2)
=\frac q2+\frac q2\lambda^2
\left[\frac{3b^2}{\alpha^2}-\frac1{\alpha\sinh\alpha}\right]+o(\lambda^2).
$$
For $b=0$, this is exactly $q/2-q\lambda^2/(4D)+o(\lambda^2)$. The finite-array sandwich and exponentially small omitted probability prove the same sequential second-order expansion for both $\liminf_N H_{N,0}$ and $\limsup_N H_{N,0}$ as $\lambda\downarrow0$. Thus the centered independent-alternative diagnostic has the proposed negative sign, with its finite-array and truncation obligations established.

For $b=1$, however, put
$$
B=\frac3{\alpha^2}-\frac1{\alpha\sinh\alpha}>0.
$$
Positivity follows from $\sinh\alpha>\alpha>0$. Choose a fixed sufficiently small $\lambda>0$, depending only on this fixed $q$, so that
$$
\liminf_N\bigl(H_{N,1}(\lambda)-q/2\bigr)\ge qB\lambda^2/4>0.
$$
This uses the lower sandwich alone; no behavior outside $E_\lambda$ is assumed. A bounded deterministic quadrature check at $q=0.1$ corroborated the coefficients for $b=0,1$ as $\lambda$ decreased, but the proof is the Taylor expansion and finite-array argument above, not that check.

### 7. Duality and the explicit divergent witness

For fixed symmetric zero-diagonal $K$, the Lagrangian of the diagonal-majorant program with PSD multiplier $\Gamma$ is
$$
\sum_i d_i-\operatorname{tr}(\Gamma(\operatorname{Diag}(d)-K))
=\sum_i(1-\Gamma_{ii})d_i+\operatorname{tr}(\Gamma K).
$$
Its infimum over unrestricted $d$ is finite exactly when $\Gamma_{ii}=1$. A scalar $d_i=t>\|K\|_{\rm op}$ is strictly feasible; the primal is bounded below because each $d_i\ge K_{ii}=0$, and is attained by compactness of a nonempty objective sublevel set. Finite-dimensional semidefinite Slater duality, applicable by this strict feasibility, therefore gives
$$
\mathcal D(K)=\max_{\Gamma\succeq0,\ \Gamma_{ii}=1}\operatorname{tr}(\Gamma K).
$$
The dual maximum is attained since its correlation-matrix domain is compact. In particular, its weak-duality inequality also follows directly by pairing $\operatorname{Diag}(d)-K\succeq0$ with any such $\Gamma$; this inequality by itself suffices for the obstruction.

For the $b=1$ family above, its endpoint covariance is
$$
\Sigma_N=(1-\rho_N)I+\rho_N\mathbf1\mathbf1^{\mathsf T},\qquad
\rho_N=\lambda/z_N^2\in(0,1).
$$
It is positive definite. Along the specified null-noise path its alternative block stays fixed, while the independent-null starting law has FDR exactly $q/2$. The finite signed identity in section 3, with $K_{ii}=0$, therefore gives the exact equality
$$
H_{N,1}(\lambda)-q/2
=\operatorname{tr}(\Sigma_N K_N)
=\rho_N\operatorname{tr}(\mathbf1\mathbf1^{\mathsf T}K_N).
$$
The matrix $\Gamma_N=\mathbf1\mathbf1^{\mathsf T}$ is PSD with unit diagonal. Hence
$$
\liminf_{N\to\infty}\frac{\mathcal D(K_N)}{\log N}
\ge\frac{2c}{\lambda}\liminf_N(H_{N,1}(\lambda)-q/2)
\ge c qB\lambda/2>0.
$$
For this fixed $q$, $U=\overline\Phi^{-1}(q/2)$ is fixed, so the right side of (D2) is a finite constant independent of $N$, for every finite proposed $C$. The displayed divergence contradicts (D2). Since the construction works for every fixed $q\in(0,1/2)$, it also defeats any proposed universal lower cutoff $U_0$ by first choosing $q$ sufficiently small and then $N$ sufficiently large.

Scope of the obstruction: the dual in this plan permits every unit-diagonal PSD $\Gamma$, including $\Gamma_N$ whose alternative block differs from the fixed generating alternative block. This witness refutes the fully diagonal relaxation (D2). It does not refute a different completion class imposing $\Gamma_{AA}=\Sigma_{AA}$, and no conclusion about that different class is asserted. The finite-$q$ FDR gain above $q/2$ also does not violate the target asymptotic bound of order $q\sqrt{\log(1/q)}$. A new route would need a genuinely weaker certificate respecting generating-covariance constraints, or a direct scalar estimate; it cannot complete this plan by asserting (D2).
