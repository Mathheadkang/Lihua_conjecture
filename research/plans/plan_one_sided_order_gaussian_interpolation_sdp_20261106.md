---
type: plan
title: Universal one-sided order through signed Gaussian boundary interpolation
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by:
  - idea_0677621e4652
  - idea_bdb4492a7046
  - idea_aefc626dda25
---

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the exact current target with finite universal constants and a universal small-level interval. Retain arbitrary finite \(N\), every mean vector, every unit-diagonal PSD covariance including singular matrices, the true-null set \(I_0=\{i:\theta_i\le0\}\), and ordinary BH's largest qualifying rank with non-strict inequalities. All model parameters and the null proportion may vary with \(q\). No constant may depend on dimension, means, covariance, rank, factor count, directions, or a regularization parameter.

This plan uses signed covariance interpolation of the actual FDP. It does not assume the global positive-flux estimate left open by the previous plan. In particular, it never substitutes a sum of all marginal critical crossings for actual maximal-rank events.

Planning-time library searches for Gaussian interpolation, Price boundary identities, and Gaussian BH bounds returned no applicable result. All interpolation, matrix, independence and limiting arguments below must be proved here; no draft result is a black box.

## Plan

1. [x] **Finite-grid FDP and an admissible interpolation.** Fix \(0<q\le\overline\Phi(1)\), set \(U=\overline\Phi^{-1}(q)\ge1\), \(u_r=\overline\Phi^{-1}(qr/N)\), and let \(f_q(t)\in[0,1]\) be the actual ordinary-BH FDP at the statistic vector \(t\), with the original fixed labels \(I_0\). Show that \(f_q\) is constant on every open cell cut out by the finitely many coordinate hyperplanes \(t_j=u_r\); sorting ties are not additional cell boundaries.

   For \(0<\eta\le1\) and \(0\le a\le1\), define
   $$
   C_{a,\eta}=\frac{a\Sigma+(1-a+\eta^2)I_N}{1+\eta^2},
   \qquad
   T_{a,\eta}\sim N_N(\theta,C_{a,\eta}),\qquad
   \mathcal F_\eta(a)=\mathbb E f_q(T_{a,\eta}).
   $$
   These covariances are positive definite with diagonal one; the means and null labels are unchanged. Prove directly by the deterministic force-zero BH argument that \(\mathcal F_\eta(0)\le q|I_0|/N\), including negative null means, \(N=1\) and empty \(I_0\).

2. [x] **Exact signed two-boundary interpolation formula.** For \(j\ne k\), thresholds \(u_r,u_s\), and the remaining coordinates \(y\), define the four open-quadrant limits of the actual FDP at \(t_j=u_r,t_k=u_s\), and the mixed jump
   $$
   \Delta_{jk}^{rs}f_q(y)
   =f_q(u_r+,u_s+,y)-f_q(u_r-,u_s+,y)
    -f_q(u_r+,u_s-,y)+f_q(u_r-,u_s-,y).
   $$
   Coordinate positions in this display are \(j,k\); all other coordinates remain at \(y\). Prove existence of the limits off the remaining grid boundaries. Every term must use the largest qualifying BH rank and the actual null labels, including complete rank cascades.

   Write \(c_{jk}=a\Sigma_{jk}/(1+\eta^2)\), and let \(\phi_{2,c}\) be the centered bivariate normal density with unit marginal variances and correlation \(c\). Define, using the actual conditional Gaussian law,
   $$
   K_{jk}(a,\eta)=
   \sum_{r,s=1}^N
   \phi_{2,c_{jk}}(u_r-\theta_j,u_s-\theta_k)
   \mathbb E\!\left[
      \Delta_{jk}^{rs}f_q(T_{-(j,k)})
      \mid T_j=u_r,T_k=u_s
   \right],
   $$
   with \(T=T_{a,\eta}\). Set \(H_{jj}=0\) and \(H_{jk}=H_{kj}=K_{jk}/2\). Derive, rather than cite without proof, the finite-grid Gaussian differentiation identity
   $$
   \mathcal F_\eta'(a)
   =\frac{1}{1+\eta^2}\operatorname{tr}(\Sigma H(a,\eta)).
   $$
   One route is to differentiate the nonsingular Gaussian density and integrate twice on the grid cells. Verify every sign, the factor \(1/2\), the zero diagonal covariance derivative, finite sums, and the treatment of cells with coincident original loading directions. Do not assume that an individual mixed jump or the matrix \(H\) has a fixed sign.

3. [x] **An explicit finite semidefinite charge.** For any real symmetric zero-diagonal matrix \(H\), define
   $$
   \beta(H)=
   \inf\left\{\sum_{j=1}^N d_j:
        \operatorname{diag}(d_1,\ldots,d_N)-H\succeq0\right\}.
   $$
   Prove finiteness, nonnegativity, attainment and measurability of this quantity along the interpolation. For example, a row-absolute-sum diagonal proves only finiteness; it is not the desired estimate. Prove directly, without assuming that \(H\) is PSD or a convex Hessian, that
   $$
   \operatorname{tr}(\Sigma H)\le\beta(H)
   \quad\text{whenever }\Sigma\succeq0,\ \Sigma_{jj}=1.
   $$
   This follows only after the proposed diagonal domination is established: the trace of the product of two PSD matrices is nonnegative. No symmetry or positivity claim about ordinary BH's response may be inserted without proof.

4. [ ] **First substantive gate: a signed boundary-completion budget.** Prove, or stop here, that there exists a finite universal \(A\) such that for every model, every \(0<\eta\le1\), and every \(0<q\le\overline\Phi(1)\),
   $$
   \tag{G-SDP}
   \int_0^1\beta\!\left(H(a,\eta)\right)\,da
   \le A q(1+U).
   $$
   This is an explicit stronger auxiliary statement about the finite Gaussian two-boundary kernels, not an assumed reformulation of the endpoint FDR bound. It can fail without refuting the main target.

   Begin with exact \(N=2\) checks and the rank-one cascade and inactive-critical-level models recorded in the previous plan. Then seek diagonal completions by grouping the signed mixed FDP increments by their actual rejection sets and rank cascades *before* replacing them by absolute values. Pairwise Gaussian conditional expectations must retain all the corresponding maximal-rank events. A possible analytic implementation is a sum of symmetric rank-layer matrix dominations whose diagonal traces are charged to Gaussian null tail mass; prove each domination and the summed trace estimate. Merely bounding individual boundary densities or using row absolute sums recreates an uncontrolled marginal envelope and is not a proof of this gate.

   The completion may depend on \(a,\eta,\theta,\Sigma,q\), but \(A\) may not. Neither a bound involving \(\log N\), an eigenvalue, \(\eta^{-1}\), factor dimension, direction entropy, nor a nonintegrable endpoint estimate passes this gate. An integrable endpoint singularity is acceptable only after its integral has a universal bound. Short finite-model calculations may refute a proposed completion or check factors; they cannot establish (G-SDP).

   **Failure condition:** if no valid signed completion budget is proved, or the only established completion has uncontrolled complexity or regularization dependence, mark the plan failed at (G-SDP). Save the exact matrix/kernel inequality attempted, the retained or discarded rank events, and any concrete violating auxiliary object. Do not infer a main-target counterexample from failure of this stronger SDP charge. Do not proceed to Step 5 by treating (G-SDP) as a premise.

5. [ ] **Uniform conclusion, then the singular limit.** Only after Step 4 is proved, integrate the exact derivative and obtain
   $$
   \mathcal F_\eta(1)
   \le q|I_0|/N+Aq(1+U)
   $$
   uniformly in \(\eta\) and all model parameters. Couple
   $$
   T_{1,\eta}=\theta+\frac{X+\eta\varepsilon}{\sqrt{1+\eta^2}},
   \qquad X\sim N_N(0,\Sigma),\quad \varepsilon\sim N_N(0,I_N)
   $$
   independently, and let \(\eta\downarrow0\) for each arbitrary finite model and fixed \(q\). Each marginal has unit variance, so the finite union of events \(T_j=u_r\) has probability zero even when \(\Sigma\) is singular. Prove almost-sure eventual agreement of the grid comparisons and hence convergence of the FDP; bounded convergence transfers the already uniform estimate. No uniform approximation error or interchange of a supremum with a limit is being assumed.

   Finally use \(U\le\sqrt{2\log(1/q)}\), restrict to \(q_{0,1}=\min\{\overline\Phi(1),e^{-1}\}\), and exhibit a finite permissible \(C_1\), for example \(1+(1+\sqrt2)A\). Explain why proving the estimate with constants independent of each arbitrary finite model covers models and null proportions varying with \(q\).

## Verification

The full proof requires all five steps; no derivative identity or SDP feasibility calculation alone establishes the target. A fresh verifier must reconstruct the Gaussian differentiation formula and its normalization, examine the actual signed mixed BH increments and every rank-layer matrix inequality in (G-SDP), and verify all quantifiers, negative means, ties, degenerate correlations, constants and dependencies. In particular, the verifier must reject any substitution of independent conditional residuals, Hessian positivity, a fixed-\(N\) constant, or a regularization-dependent bound.

Check the empty-null and \(N=1\) cases directly. Verify the \(a=0\) independence benchmark and the factor \(1/(1+\eta^2)\). At fixed positive \(\eta\), the interpolation is nonsingular; endpoint limits are used only after a bound uniform in \(\eta,N,\theta,\Sigma\). The finite-model limit proves a universal assertion, not a dimension-limit surrogate.

During execution save each completed substep immediately in ## Progress, with single edits below about 6k tokens. Any failed stronger claim and any auxiliary diagnostic remain clearly separated from the original order target. A successful complete asset Proof still requires a new independent native verification agent.

## Assumed definitions

Only the approved definitions already listed in the target are used: the Gaussian multiple-testing model, one-sided p-values and true-null set, ordinary BH, false discovery rate, and its worst-case envelope. All new symbols, conditional boundary kernels and matrix charges are defined above and must be justified in execution. No draft lemma, old sharp conjecture, positive-flux budget, or unpublished source result is assumed.

## Difference from failed plans

- [plan_one_sided_order_actual_mean_global_flux_20261106](plan_one_sided_order_actual_mean_global_flux_20261106.md): that attempt controlled coordinatewise positive jumps and failed when the safe marginal envelope counted inactive critical levels, with a valid quadratic-growth diagnostic. This plan instead interpolates the whole actual FDP, retains signed two-coordinate boundary increments and all maximal-rank events, and asks for a semidefinite diagonal completion using the original covariance's PSD structure. Its new first gate is (G-SDP); no dimension-uniform positive-flux estimate is reused as a premise.

## Progress

### Step 1: finite grid, admissible path, and independent baseline (proved here; not independently verified)

Fix arbitrary finite $N$, means $\theta$, and $\Sigma\succeq0$ with unit diagonal. Keep the labels $I_0=\{i:\theta_i\le0\}$ fixed. Write $S=\overline\Phi$ and $u_r=S^{-1}(qr/N)$. The comparisons $p_j\le qr/N$ are exactly $t_j\ge u_r$. Their truth values determine every qualifying BH rank, its largest member, and the rejection set. They are constant on each open cell of the finite grid $t_j=u_r$. Consequently the actual FDP $f_q$ is constant on each such cell; a sorting equality inside a cell changes none of these comparisons. At grid boundaries use the original non-strict BH rule, although these boundaries will have probability zero under every unit-variance Gaussian law used here. Always $0\le f_q\le1$.

For $0<\eta\le1$ and $a\in[0,1]$, the displayed $C_{a,\eta}$ has diagonal one and
$$
x^{\mathsf T}C_{a,\eta}x\ge \frac{\eta^2}{1+\eta^2}\|x\|^2>0\quad(x\ne0).
$$
It is therefore nonsingular throughout this fixed-$\eta$ path, without imposing a lower eigenvalue on the original $\Sigma$. Its mean is exactly $\theta$. At $a=0$ the coordinates are independent $N(\theta_i,1)$.

Here is the baseline with all ties allowed. For an arbitrary p-vector let $r$ be its largest qualifying rank. If $r>0$ and more than $r$ p-values lie at or below $qr/N$, their count $s>r$ would itself qualify, a contradiction. Thus the rejection count equals $r$. Let $R_i\ge1$ be the BH rank when $p_i$ is replaced by zero. Then
$$
\frac{\mathbf1\{i\text{ rejected}\}}{R\vee1}
=\frac{\mathbf1\{p_i\le qR_i/N\}}{R_i}.
$$
Indeed, if $i$ is originally rejected, lowering it does not change any count at the thresholds of ranks larger than $r$, since its original p-value was already below all of them, and it preserves qualification at $r$. Hence $R_i=r$. Conversely, if $p_i\le qR_i/N$, restoring its value leaves rank $R_i$ qualifying; monotonicity under lowering gives the reverse inequality, so the original rank is $R_i$ and $i$ is rejected. This proves the identity also at equalities.

At the independent endpoint $R_i$ is independent of $p_i$. For $i\in I_0$ and $0<t<1$,
$$
\Pr(p_i\le t)=S(S^{-1}(t)-\theta_i)\le t.
$$
Conditioning on $R_i$ in the identity gives a contribution at most $q/N$. Summing over $I_0$ proves $\mathcal F_\eta(0)\le q|I_0|/N$. When $I_0$ is empty both FDP and bound vanish. For $N=1$ the forced rank is one and the same argument applies directly. No null mean was changed to zero, and no equality baseline is claimed for a negative null mean.

### Step 2: exact signed finite-grid interpolation (proved here; not independently verified)

For the rest of this execution write $C=C_{a,\eta}$ and let $p_a(t)$ be the Lebesgue density of $N_N(\theta,C)$. Put $x=t-\theta$ and $B=C'=(\Sigma-I_N)/(1+\eta^2)$. Direct differentiation of the density gives
$$
\partial_a p_a(t)=\tfrac12\{x^{\mathsf T}C^{-1}BC^{-1}x-\operatorname{tr}(C^{-1}B)\}p_a(t),
$$
$$
\partial_{t_jt_k}p_a(t)
=\{(C^{-1}x)_j(C^{-1}x)_k-(C^{-1})_{jk}\}p_a(t).
$$
Consequently $\partial_a p_a=\frac12\sum_{j,k}B_{jk}\partial_{t_jt_k}p_a$. This uses an inverse only for $C$, which is positive definite even if the original $\Sigma$ is singular. For fixed finite $N,\theta,\Sigma,\eta>0$, its eigenvalues along $[0,1]$ are bounded below by $\eta^2/(1+\eta^2)$ and above by $N$. These formulas are dominated by a fixed integrable polynomial times a Gaussian in $x$. Since $f_q$ is bounded, differentiation under its integral is valid and gives
$$
\mathcal F_\eta'(a)=\frac{1}{2(1+\eta^2)}
\sum_{j\ne k}\Sigma_{jk}\int f_q(t)\partial_{t_jt_k}p_a(t)\,dt.
$$
The diagonal terms vanish because $B_{jj}=0$. This dominated argument yields a continuous derivative on the interval, with the one-sided interpretation at its endpoints.

Fix $j\ne k$ and remaining coordinates $y$ off their grid boundaries. There are finitely many rectangular grid cells in coordinates $j,k$. On each, $f_q$ is constant. Integrating twice on these rectangles and telescoping the boundary terms gives
$$
\int f_q(t)\partial_{t_jt_k}p_a(t)\,dt
=\sum_{r,s=1}^N\int_{\mathbb R^{N-2}}
\Delta_{jk}^{rs} f_q(y)\,
p_a(t_j=u_r,t_k=u_s,t_{-(j,k)}=y)\,dy.
$$
The two integrations each introduce a minus sign from a step jump, so the displayed mixed jump has a plus sign. The density and its first derivatives vanish at both infinite ends. The remaining-coordinate grid boundaries have Lebesgue measure zero and thus contribute nothing; the values of $f_q$ at the finite grid boundaries themselves are also irrelevant to this integral. No boundary is removed because it causes a BH cascade: each of the four $f_q$ values is computed using the full largest-rank rule.

Positive definiteness gives $|c_{jk}|<1$. The last face density factors as its positive bivariate marginal density $\phi_{2,c_{jk}}(u_r-\theta_j,u_s-\theta_k)$ times the conditional Gaussian density of the remaining coordinates. This defines the conditional version at the probability-zero face by an actual density quotient. For $N=2$ the remaining-coordinate integral is simply the four-value increment itself. Each increment is in $[-2,2]$, and the sum is finite. It follows that the integral is exactly $K_{jk}(a,\eta)$ from the plan. Interchanging $j,k$ and $r,s$ proves $K_{jk}=K_{kj}$. With $H_{jk}=K_{jk}/2$ for $j\ne k$ and $H_{jj}=0$,
$$
\mathcal F_\eta'(a)=\frac{1}{1+\eta^2}\operatorname{tr}(\Sigma H(a,\eta)).
$$
In particular, the factor $1/2$ is in $H$ and the trace includes both ordered off-diagonal pairs. When $N=1$ the sum and $H$ are zero, consistent with the constant covariance path. The same domination on faces, using the conditional density quotient or directly the full density, shows that every $K_{jk}$ and hence $H$ is continuous in $a$ for fixed positive $\eta$. None of these arguments assumes conditional independence among remaining coordinates, distinct original loading directions, or positivity of $H$.

### Step 3: the finite diagonal-completion charge (proved here; not independently verified)

Let $H$ be any real symmetric matrix with $H_{jj}=0$. Set $r_j=\sum_{k\ne j}|H_{jk}|$. For every $x\in\mathbb R^N$,
$$
x^{\mathsf T}(\operatorname{diag}(r)-H)x
=\sum_{j<k}|H_{jk}|\bigl(x_j-\operatorname{sgn}(H_{jk})x_k\bigr)^2\ge0,
$$
where a summand with $H_{jk}=0$ is zero. Thus the defining feasible set for $\beta(H)$ is nonempty and its infimum is finite. Every feasible $d$ has $d_j\ge0$, by testing the $j$th coordinate vector in $\operatorname{diag}(d)-H\succeq0$. Hence $\beta(H)\ge0$. An infimizing sequence with $\sum_jd_j\le\beta(H)+1$ lies in a compact box; a convergent subsequence has a feasible limit because the PSD cone is closed. Its trace attains $\beta(H)$.

For symmetric zero-diagonal $H,G$, if $d$ is optimal for $H$, then
$$
\operatorname{diag}(d+\|H-G\|_{\mathrm{op}}\mathbf1)-G
=[\operatorname{diag}(d)-H]+[H-G+\|H-G\|_{\mathrm{op}}I_N]\succeq0.
$$
Exchanging $H,G$ gives
$$
|\beta(H)-\beta(G)|\le N\|H-G\|_{\mathrm{op}}.
$$
Thus $\beta$ is continuous. In particular, the continuity of $H(a,\eta)$ proved in Step 2 makes $a\mapsto\beta(H(a,\eta))$ continuous and integrable on $[0,1]$ for each fixed positive $\eta$ and each fixed finite model. This is only finite-model integrability, not the uniform estimate (G-SDP).

Finally, if $\Sigma\succeq0$ has unit diagonal and $d$ is any feasible diagonal, then
$$
0\le\operatorname{tr}\bigl(\Sigma^{1/2}[\operatorname{diag}(d)-H]\Sigma^{1/2}\bigr)
=\sum_jd_j-\operatorname{tr}(\Sigma H).
$$
Using an optimal diagonal proves $\operatorname{tr}(\Sigma H)\le\beta(H)$. This also applies to singular $\Sigma$ because a PSD square root exists and no inverse of $\Sigma$ occurs. For $N=1$, $H=0$ and $\beta(H)=0$. More generally any correlation matrix $Q$ supplies the certified lower bound $\beta(H)\ge\operatorname{tr}(QH)$; such a lower bound can test (G-SDP), without assuming an unproved SDP duality theorem. The row-absolute-sum construction above supplies feasibility only and has not been used to claim a universal trace budget.

### Step 4(a): exact bounded checks, $N\le2$ (supporting calculation only)

The following check was suggested independently by `adversarial_sdp_interpolation_budget` and reconstructed here. It does not settle arbitrary $N$. For $N=2$, put $A=u_1=S^{-1}(q/2)$ and $U=u_2=S^{-1}(q)$. If only coordinate 1 is a true null, the actual FDP is exactly
$$
f_q(t)=\mathbf1\{t_1\ge A\}
-\mathbf1\{t_1\ge A,t_2\ge U\}
+\tfrac12\mathbf1\{t_1\ge U,t_2\ge U\}.
$$
Indeed, a rejection of the null alone has $p_1\le q/2,p_2>q$, and two rejections have both p-values at most $q$. If both coordinates are true nulls, the FDP is the indicator of any rejection, and its pointwise expansion is
$$
f_q(t)=\mathbf1\{t_1\ge A\}+\mathbf1\{t_2\ge A\}
+\mathbf1\{t_1\ge U,t_2\ge U\}
-\mathbf1\{t_1\ge A,t_2\ge U\}
-\mathbf1\{t_1\ge U,t_2\ge A\}.
$$
These formulas use the original non-strict comparisons and are also valid at ties. Therefore, with $c=a\Sigma_{12}/(1+\eta^2)$, the one-null mixed kernel is
$$
K_{12}=\tfrac12\phi_{2,c}(U-\theta_1,U-\theta_2)
-\phi_{2,c}(A-\theta_1,U-\theta_2),
$$
and the two-null kernel is
$$
K_{12}=\phi_{2,c}(U-\theta_1,U-\theta_2)
-\phi_{2,c}(A-\theta_1,U-\theta_2)
-\phi_{2,c}(U-\theta_1,A-\theta_2).
$$
For a symmetric $2\times2$ zero-diagonal $H$ with $H_{12}=K_{12}/2$, feasibility requires $d_1,d_2\ge0$ and $d_1d_2\ge K_{12}^2/4$. The arithmetic-geometric mean inequality proves $\beta(H)=|K_{12}|$, attained at $d_1=d_2=|K_{12}|/2$.

Each density term above has at least one true-null coordinate at a threshold $x\ge U$ after centering, since its corresponding $\theta_j\le0$. For arbitrary other centered threshold $y$,
$$
\phi_{2,c}(x,y)\le \frac{\phi(x)}{\sqrt{2\pi}\sqrt{1-c^2}}
\le\frac{\phi(U)}{\sqrt{2\pi}\sqrt{1-c^2}}.
$$
Let $r=|\Sigma_{12}|/(1+\eta^2)\le1$. The elementary substitution gives
$$
\int_0^1\frac{da}{\sqrt{1-a^2r^2}}
=\begin{cases}\arcsin(r)/r,&r>0,\\1,&r=0,\end{cases}
\le\pi/2.
$$
Thus each such bivariate density integrates to at most $\pi\phi(U)/(2\sqrt{2\pi})<\phi(U)$, uniformly in both means, covariance, and $\eta>0$. Finally integration by parts gives
$$
S(U)=\frac{\phi(U)}U-\int_U^\infty\frac{\phi(x)}{x^2}\,dx
\ge\frac{\phi(U)}U-\frac{S(U)}{U^2},
$$
so $\phi(U)\le q(U+1/U)\le q(1+U)$ because $U\ge1$. Taking absolute values of only the explicit at most three terms therefore proves
$$
\int_0^1\beta(H(a,\eta))\,da\le3q(1+U)\qquad(N\le2).
$$
An empty true-null set gives zero, and the one-null case with coordinate 2 instead is symmetric. This verifies a bounded check of (G-SDP), including negative null means; it supplies no bound for arbitrary $N$.

### Step 4(b): a dimension-free Gaussian scalar charge (supporting lemma; reconstructed from a root proposal)

This scalar lemma is not a matrix domination of $H$. Let $0<\nu\le1$, $r=\sqrt{1-\nu}$, and $X\sim N_N(0,\Sigma)$ for any unit-diagonal PSD $\Sigma$, including singular matrices. Define, conditional on $X$,
$$
p_i(v\mid X)=S\!\left(\frac{v-\theta_i-rX_i}{\sqrt\nu}\right),\qquad
d_j(w\mid X)=\frac1{\sqrt\nu}\phi\!\left(\frac{w-\theta_j-rX_j}{\sqrt\nu}\right).
$$
For $i\in I_0$, $v\ge U\ge1$, and arbitrary $j,w,\theta_j$, the claim is
$$
\tag{SC}
\mathbb E[p_i(v\mid X)d_j(w\mid X)^2]
\le \sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}
\le\frac{q(1+U)}{\sqrt\nu},\qquad q=S(U).
$$
The indices $i,j$ may coincide. To prove this, add three independent standard-normal residual copies, independent of $X$, and put
$$
Y_i=\theta_i+rX_i+\sqrt\nu\,\varepsilon^0,
\quad Y_j^1=\theta_j+rX_j+\sqrt\nu\,\varepsilon^1,
\quad Y_j^2=\theta_j+rX_j+\sqrt\nu\,\varepsilon^2.
$$
Even if $i=j$ these residual copies are distinct. The left side of (SC) is the joint density at $Y_j^1=Y_j^2=w$ together with the event $Y_i\ge v$. Set $A=(Y_j^1+Y_j^2)/2$ and $D=(Y_j^1-Y_j^2)/2$. Then
$$
\mathbb E A=\theta_j,\quad \sigma_A^2=\operatorname{Var}(A)=1-\nu/2,\quad
\operatorname{Var}(D)=\nu/2,
$$
and $D$ is independent of $(A,Y_i)$, by joint Gaussianity and zero covariances. The change of variables $(A,D)\mapsto(Y_j^1,Y_j^2)$ has absolute Jacobian 2. Thus the left side is exactly
$$
\frac{1}{2\sqrt{\pi\nu}\,\sigma_A}\,
\phi(z)\Pr\{Z_i\ge b\mid Z_A=z\},
\qquad z=\frac{w-\theta_j}{\sigma_A},\quad b=v-\theta_i\ge U,
$$
where $Z_i=Y_i-\theta_i$ and $Z_A=(A-\theta_j)/\sigma_A$ are standard normal. Their correlation is $\rho=r^2\Sigma_{ij}/\sigma_A$, whose absolute value is strictly less than one for $\nu>0$.

Here is the required elementary bivariate bound. For any $b\ge1$ and $|\rho|<1$, write $s=\sqrt{1-\rho^2}$ and use the bivariate density identity
$$
\phi(z)\Pr(Z_i\ge b\mid Z_A=z)
=\int_b^\infty \phi(x)\frac1s\phi\!\left(\frac{z-\rho x}{s}\right)dx.
$$
If $|\rho|\ge1/2$, monotonicity of $\phi$ on $[b,\infty)$ bounds this by $\phi(b)/|\rho|\le2\phi(b)$: extending the last Gaussian kernel integral to all $x$ gives $1/|\rho|$. If $|\rho|<1/2$, then $s>\sqrt3/2$ and the bound is $S(b)/(s\sqrt{2\pi})\le\phi(b)$, using $S(b)\le\phi(b)/b$ and $b\ge1$. Hence it is always at most $2\phi(b)$. This also has the evident degenerate extension at $\rho=\pm1$, where the conditional tail is an indicator; the application above already has strict inequality.

Substitution and $\sigma_A\ge1/\sqrt2$ yield
$$
\mathbb E[p_i d_j^2]\le\frac{\phi(b)}{\sqrt{\pi\nu}\,\sigma_A}
\le\sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}.
$$
The last inequality in (SC) follows from the Mills integration-by-parts bound proved in Step 4(a), since $\sqrt{2/\pi}<1$. This proof uses only the two unit marginal variances and their Gaussian joint law; it is uniform in factor dimension, all means allowed above, every correlation including original singularity, and all $N$.

Weighted Cauchy--Schwarz gives the further bound, for arbitrary $j,k,w,z$,
$$
\tag{SC2}
\mathbb E[p_i(v\mid X)d_j(w\mid X)d_k(z\mid X)]
\le\sqrt{\mathbb E[p_i d_j(w)^2]\mathbb E[p_i d_k(z)^2]}
\le\sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}.
$$
For the covariance path in this plan,
$$
\nu_a=\frac{1-a+\eta^2}{1+\eta^2},\qquad r_a^2=\frac a{1+\eta^2},\qquad
T_{a,\eta}=\theta+r_aX+\sqrt{\nu_a}\,\varepsilon
$$
with independent standard residual coordinates. The exact integral is
$$
\int_0^1\nu_a^{-1/2}da
=2\sqrt{1+\eta^2}\bigl(\sqrt{1+\eta^2}-\eta\bigr)
=\frac{2\sqrt{1+\eta^2}}{\sqrt{1+\eta^2}+\eta}\le2.
$$
Thus the scalar charges have an integrable endpoint bound uniform in $\eta$. They do not bound $\beta(H)$ unless a valid matrix aggregation removes the number of faces and indices; no such aggregation is asserted here.

### Step 4(c): a valid but nonuniform matrix benchmark and the missing aggregation

The deterministic levels in (SC) and (SC2) cannot be chosen after seeing $X$ without a new argument. Nevertheless they do control every fixed face in the finite sum. Here is the explicit resulting bound, which is insufficient for (G-SDP).

Let $m_0=|I_0|$, $m_1=N-m_0$, $n_1=m_1(m_1-1)$, and $n_0=N(N-1)-n_1$. Thus $n_0$ counts ordered distinct pairs with at least one true-null label, and $n_1$ counts the two-alternative pairs. At a given path parameter write $\nu=\nu_a$ and condition on $X$ in the independent-residual representation in Step 4(b).

If a face pair $j,k$ contains a true null, say $j$, its density at $(u_r,u_s)$ is at most
$$
\frac{\phi(u_r-\theta_j)}{\sqrt{2\pi\nu}}
\le\frac{\phi(U)}{\sqrt{2\pi\nu}}.
$$
Indeed, conditional on $T_j$, coordinate $T_k$ retains its independent residual $\sqrt\nu\,\varepsilon_k$, so its conditional variance is at least $\nu$. With $|\Delta f_q|\le2$ and $H_{jk}=K_{jk}/2$, summing the $N^2$ threshold pairs yields
$$
|H_{jk}|\le \frac{N^2\phi(U)}{\sqrt{2\pi\nu}}.
$$
If $j,k$ are both alternatives, the mixed FDP increment is zero whenever all remaining true-null statistics are below $U$: no null can then be rejected in any of the four configurations. Therefore
$$
|\Delta_{jk}^{rs}f_q(y)|\le2\sum_{i\in I_0}\mathbf1\{y_i\ge U\}.
$$
Each such $i$ differs from $j,k$. Conditional residual independence in the actual path gives the exact joint face-density/tail expression
$$
\int\mathbf1\{t_i\ge U\}p_a(t_j=u_r,t_k=u_s,t_{-(j,k)})\,dt_{-(j,k)}
=\mathbb E[p_i(U\mid X)d_j(u_r\mid X)d_k(u_s\mid X)].
$$
Applying (SC2) separately at these deterministic levels proves
$$
|H_{jk}|\le N^2m_0\sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}.
$$
The row-absolute-sum diagonal from Step 3 is thus a valid completion with
$$
\beta(H(a,\eta))\le
N^2\left\{\frac{n_0}{\sqrt{2\pi}}+m_0n_1\sqrt{\frac2\pi}\right\}
\frac{\phi(U)}{\sqrt{\nu_a}}.
$$
Integration and the proved scalar endpoint estimate give
$$
\tag{PB}
\int_0^1\beta(H(a,\eta))\,da
\le2N^2\left\{\frac{n_0}{\sqrt{2\pi}}+m_0n_1\sqrt{\frac2\pi}\right\}
q(1+U).
$$
This is uniform in $\eta$, the covariance and the means, but its polynomial dependence on $N$ is uncontrolled. It is only a failed benchmark for the desired universal constant. The scalar helper has removed the apparent nonintegrable smoothing loss; it has not removed the face and index multiplicity.

Two exact finite checks explain why the omitted information cannot simply be ignored. First, an alternative--alternative mixed jump need not be zero. For $N=3$, $I_0=\{1\}$, fix $p_1<q/3$ and let $p_2,p_3$ approach $q$ from either side while their lower-side values remain above $2q/3$. When both are below $q$, rank 3 qualifies and FDP is $1/3$. In each other quadrant only rank 1 qualifies and FDP is 1. Thus $\Delta_{23}^{33}f_q=-2/3$. A null-tail factor for such a face must come from the conditional remaining-null event, rather than a null label on one of its two boundary coordinates.

Second, there is no general $O(N)$ pointwise charge for the raw rank-layer coefficient matrix. Take all labels to be null and fix every remaining p-value in the band $(q(N-1)/N,q)$. At the top-level face $u_N=U$ for coordinates $j,k$, each of their lower-p limits can also be chosen in that band. All $N$ p-values are at most $q$ only in the $++$ statistic quadrant, where the largest rank is $N$ and FDP is 1. In any other quadrant rank $N$ fails and every lower rank fails because all p-values exceed $q(N-1)/N$. Hence $\Delta_{jk}^{NN}f_q=1$ for every pair. The raw symmetric coefficient matrix is $J_N-I_N$, whose completion charge is exactly $N(N-1)$: the correlation matrix $J_N$ gives this lower bound in Step 3, and the row-sum diagonal $(N-1)I_N$ attains it. This is a statement about unweighted coefficients at legitimate active configurations, not a lower bound on the Gaussian-averaged $H$. For example, under independent centered nulls the band event has very small probability. It does not refute (G-SDP) or the main FDR target; it shows that the missing Gaussian-weighted, rank-sensitive aggregation cannot be replaced by this pointwise combinatorial bound.

### Independent read-only checks received during execution

- `audit_signed_interpolation_partial_fresh`, a fresh agent uninvolved in derivation, confirmed the partial finite-grid, independent-baseline and signed density-interpolation arguments in its then-current Steps 1--2 excerpt. Its exact excerpt SHA256 was `623bfe160f3fbd0a022b11d0d4f4f84aee91799d3caabd316a911aec774c8f7d`. It did not audit Step 3, the completion budget or the main target.
- `audit_replica_tail_density_fresh`, another fresh agent uninvolved in derivation, confirmed the entire Step 4(b) scalar proof, including the replica Jacobian, $i=j$, $\nu=1$, singular original covariance, deterministic-level scope, weighted Cauchy--Schwarz and the integral at most 2. Its exact section SHA256 was `a9ad5b1b3045180220ddaab352a887edde75833a5c714863d919d437758eec39`. It did not certify any random-level extension or matrix aggregation.
- These are scoped read-only proof checks, not native approval of an asset or confirmation of the full theorem. The polynomial matrix benchmark and the raw coefficient diagnostic in Step 4(c) are saved for a separate independent check; neither is asserted to falsify (G-SDP).

## Failure

The plan stops at its first substantive gate, Step 4 / (G-SDP). The exact interpolation, the finite SDP charge and the dimension-free scalar charge have been derived, but no dimension-free Gaussian-weighted diagonal completion of the full signed BH boundary matrix has been established.

More precisely, the established completion is the row-absolute-sum one with trace bounded by (PB). Its coefficient
$$
2N^2\left\{n_0/\sqrt{2\pi}+m_0n_1\sqrt{2/\pi}\right\}
$$
grows with $N$. The scalar charge and its $\nu_a^{-1/2}$ integral are already uniform in the regularization parameter: the obstruction here is not an unresolved smoothing singularity. What remains is a new Gaussian-weighted, rank-sensitive signed/PSD aggregation that removes the face and label multiplicity while retaining all maximal-BH-rank events. Neither the raw pointwise coefficient matrix nor individual density bounds provide that aggregation. The active top-rank coefficient example has quadratic completion charge before Gaussian averaging, so an $O(N)$ pointwise combinatorial replacement is unavailable.

No random or maximizing threshold is substituted into (SC) or (SC2); those estimates were proved only for deterministic levels. A pointwise sum-of-weights bound alone does not justify replacing an expectation of a random selected level by the largest of its fixed-level expectations. No such interchange is used to hide the factors in (PB).

The arbitrary-$N$ budget (G-SDP) remains unproved, not refuted. The $N\le2$ check and the conditional scalar lemma are supporting results only. Step 5 has not been used, the target asset is untouched, and neither the one-sided universal order theorem nor a counterexample to it is claimed.

### Post-attempt independent checks

The following fresh read-only checks were received after the failed attempt; they preserve and supplement the earlier record rather than changing any proof claim or status.

- `audit_sdp_basics_and_n2_fresh` confirmed Step 3 and Step 4(a), its exact lines 174--249, SHA256 `38136e1811eedd44a8a4d2c8c02a30475a47ae4c1c394a663fdaa1c3900c9be3`. This covers the finite diagonal-completion properties and the bounded $N\le2$ calculation only.
- `audit_replica_tail_density_fresh` confirmed Step 4(b), SHA256 `a9ad5b1b3045180220ddaab352a887edde75833a5c714863d919d437758eec39`, for deterministic levels only. No random-level selection or supremum interchange is certified.
- `audit_sdp_polynomial_benchmark_fresh` confirmed Step 4(c), its exact lines 318--363, SHA256 `6306d6da489ea089417f9d14bbcd5eacd2532e5a1342235add2976742733484d`. This checks the polynomial factor counts in (PB), the nonzero alternative--alternative increment, and the quadratic raw-coefficient diagnostic. It does not establish or refute (G-SDP) or the main target.

None of these scoped checks is a whole-target proof or native asset approval. The plan remains failed at the arbitrary-$N$ completion budget, and the target statement and asset remain untouched.
