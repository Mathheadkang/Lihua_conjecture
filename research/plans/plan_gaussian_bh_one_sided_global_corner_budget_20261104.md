---
title: Global Gaussian BH corner matrix and a diagonal budget certificate
type: plan
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
inspired_by:
  - idea_b8a514004c9b
  - idea_07179cf4b146
  - idea_45ea077b792d
adapts: []
tags:
  - gaussian-bh
  - one-sided
  - covariance-interpolation
  - global-fdp
---

## Goal

Target: [Sharp uniform upper-bound target for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_sharp_upper.md).

Attempt the recorded global-FDP covariance-interpolation route. The new analytic candidate is a diagonal semidefinite budget for the **integrated signed corner matrix**, not a bound on individual null contributions. Its proof is an essential task of this plan; it is not an assumed lemma. The candidate is stronger than the needed scalar interpolation estimate and can fail even if the target is true. A failure of this certificate must be recorded as failure of this plan, not as a refutation of the target.

Library searches for `Gaussian`, `Gaussian covariance interpolation`, `BH FDR Gaussian`, `covariance`, and `corner` returned no matches. Thus no library proof is adapted and no undeclared library statement is used. The target's displayed relations and the current context pack list no existing pending or failed plans.

## Plan

1. [x] Fix arbitrary finite admissible $(N,\theta,\Sigma)$ and $0<q<1/2$, with the actual fixed set $I_0=\{i:\theta_i\leq0\}$. Put $a=q/N$, $z_k=\overline\Phi^{-1}(ak)$, $u=\overline\Phi^{-1}(q)$, $b_{ik}=z_k-\theta_i$, and $\delta_i=\mathbf1\{i\in I_0\}$. Use $X_t\sim N(0,\Sigma_t)$ with $\Sigma_t=(1-t)I+t\Sigma$, and let $f(x)$ be the actual BH FDP computed from $\overline\Phi(\theta_i+x_i)$ and $I_0$. Reprove the independent endpoint directly: forcing the $i$th p-value to zero gives a rank $R_i$ independent of that p-value at $t=0$, and the BH identity and $\Pr\{p_i\leq s\}\leq s$ for $\theta_i\leq0$ give $\mathbb E f(X_0)\leq q|I_0|/N$. Do not cite an undeclared leave-one-out theorem or replace a composite-null mean by zero inside $f$.

2. [x] Prove the exact mixed corner coefficients below, including rank jumps of arbitrary size. For fixed $i\ne j$ and thresholds $(k,l)$, encode every other p-value by its entry rank
   $$
   h_v=\min\bigl(\{s:p_v\leq as\}\cup\{N+1\}\bigr),\quad
   C_s=\sum_{v\ne i,j}\mathbf1\{h_v\leq s\},\quad
   W_s=\sum_{v\ne i,j}\delta_v\mathbf1\{h_v\leq s\},
   $$
   with $C_0=W_0=0$. Let $f_{ef}$ be the FDP with $h_i=k+1-e$, $h_j=l+1-f$, $e,f\in\{0,1\}$, and set $\Delta_{ij;k,l}=f_{11}-f_{10}-f_{01}+f_{00}$. These are the four one-sided cell limits, not evaluations at the equalities themselves.

   For $k<l$, put
   $$
   r=\max\bigl(\{0\}\cup\{s<k:C_s\geq s\}\bigr),
   $$
   and define the joint pivotal gate $A_{ij}^{k,l}$ by
   $$
   C_k=k-1,\quad C_l=l-2,\quad
   C_s+1<s\ (k<s\leq l),\quad
   C_s+2<s\ (l<s\leq N).
   $$
   The coefficient to prove is
   $$
   \Delta_{ij;k,l}
   =\mathbf1_{A_{ij}^{k,l}}
   \left\{\frac{W_r}{r\vee1}-\frac{W_k+\delta_i}{k}\right\}.
   $$
   On this gate the four ranks are $r,k,l,l$, respectively; the two FDP values at rank $l$ cancel exactly. Off this gate the mixed difference is zero. Obtain the $l<k$ formula by interchanging $(i,k)$ and $(j,l)$.

   For $k=l$, set $r=\max(\{0\}\cup\{s<k:C_s\geq s\})$ and let $A_{ij}^{k,k}$ be
   $$
   C_k=k-2,\qquad C_s+2<s\quad(k<s\leq N).
   $$
   Prove
   $$
   \Delta_{ij;k,k}
   =\mathbf1_{A_{ij}^{k,k}}
   \left\{\frac{W_k+\delta_i+\delta_j}{k}-\frac{W_r}{r\vee1}\right\}.
   $$
   Here the ranks are $r,r,r,k$; the gate is impossible for $k=1$. Verify both formulas for every null/alternative label, including alternative/alternative corners. A planning diagnostic checked 279932 exact-rational basis-null cases over all bins and pairs for $N=2,\ldots,5$; execution still needs the general argument.

3. [x] Establish the distributional covariance identity by integration over the finite grid cells, or by smoothing followed by a justified limit. If $\varphi_2(x,y;c)$ is the bivariate standard normal density with correlation $c$, define, for $i\ne j$,
   $$
   K_{ij}=\frac12\int_0^1\sum_{k,l=1}^N
   \varphi_2(b_{ik},b_{jl};t\Sigma_{ij})
   \mathbb E_t[\Delta_{ij;k,l}\mid X_{t,i}=b_{ik},X_{t,j}=b_{jl}]\,dt,
   \qquad K_{ii}=0.
   $$
   Show that $K$ is symmetric and each entry exists for every fixed finite model. The bound $|\Delta|\leq4$ and the integrable singularity $(1-t^2\Sigma_{ij}^2)^{-1/2}$ suffice for entrywise integrability, including $|\Sigma_{ij}|=1$. Check the factor $1/2$ against
   $$
   \mathbb E f(X_1)-\mathbb E f(X_0)=\operatorname{tr}(\Sigma K).
   $$
   This equality retains the conditional gate probabilities; replacing them by independent probabilities or omitting alternative/alternative corners is invalid.

4. [ ] First test the following new, sufficient **matrix** estimate in small analytic models. There should exist a numerical constant $C$, independent of $(q,N,\theta,\Sigma)$, and real numbers $d_1,\ldots,d_N$ such that
   $$
   \operatorname{Diag}(d)-K\succeq0,
   \qquad
   \sum_{i=1}^N d_i\leq
   \frac{\varphi(u)}{\sqrt{2\pi}}
   +Cq\{1+\log(1+u)\}.
   \tag{C}
   $$
   Here $\varphi$ is the standard normal density. This is a concrete Gaussian-kernel certificate, with $K$ given entrywise in step 3. It controls $\operatorname{tr}(\Gamma K)$ for **every** PSD unit-diagonal test matrix $\Gamma$, not merely the covariance $\Sigma$ that generated $K$; hence it has independent content and may be too strong. Derive $N=2$ cases explicitly and test independent and nearly singular small Gaussian models before relying on it; also test the all-null and mixed rank-one limits, the heterogeneous-null boundary-contribution obstruction, and the singular-simplex family. Any rigorous failure of (C) ends this plan with its exact failed subclaim. The original $\Sigma$-specific signed integral then remains a separate unresolved task, and the target does not become false. Do not silently weaken the target or assume that the covariance path is monotone.

5. [ ] Attempt an actual proof of (C) by constructing $d$, rather than appealing to an unspecified interpolation lemma. Expand the two formulas in step 2 into the actual null indicators $\delta_v$ and group the rank intervals $(r,k]$ **before** taking absolute values. In particular retain the negative term $-W_r(k-r)/(rk)$ in a face jump when $r>0$, and the cancellation of the two rank-$l$ values for $k<l$. Rewrite each conditional-density integral as its full Gaussian cell integral, so all pair types use the same sampling law. Seek a positive-semidefinite decomposition of $\operatorname{Diag}(d)-K$ after this grouping; completing squares must exhibit its coefficients and their signs.

   An explicit kernel identity available for this attempt is Mehler's expansion, to be proved or derived directly from the Gaussian generating function in execution:
   $$
   \varphi_2(x,y;t\rho)
   =\varphi(x)\varphi(y)\sum_{m=0}^{\infty}
   \frac{t^m\rho^m}{m!}H_m(x)H_m(y),\qquad |t\rho|<1,
   $$
   where $H_m$ are the probabilists' Hermite polynomials. For a single boundary $c_i$ per coordinate, every channel
   $$
   \left[\varphi(c_i)H_m(c_i)\,\Sigma_{ij}^{m}\,
   \varphi(c_j)H_m(c_j)\right]_{i,j}
   $$
   is PSD: use Gram tensors to prove the Schur-power assertion. The substantive task is to show that the **rank-gate-weighted sum** needed in step 3 has the required square decomposition after telescoping. Positivity of the unweighted pair kernel does not imply positivity after conditional gating. Exhibit the extension with its exact feature functions, or report this obstruction; never substitute the unweighted kernel as if it proved (C).

6. [ ] Prove the trace budget in (C) for the constructed certificate. The proposed sharp allocation is a Gaussian-tail capacity, not a separate envelope for each null:
   $$
   \frac1{\sqrt{2\pi}}\int_0^\infty
   \min\{q,\overline\Phi(v)\}\,dv
   =\frac{\varphi(u)}{\sqrt{2\pi}}.
   $$
   Derive this capacity from the grouped rank gates and the exact boundaries $b_{ik}=z_k-\theta_i$, using $b_{ik}\geq z_k$ only where $i$ is a true null. The interval allocation must be written out: show that shared rank mass is charged once, and prove that all discarded endpoint/rank terms have total at most $Cq\{1+\log(1+u)\}$. A residual $q\log N$, a bound per null with arbitrary remaining means, or a full-factor conditional supremum does not close this step. The displayed scalar integral is elementary; the nontrivial obligation is its domination of the constructed matrix certificate's trace. It must be established, not asserted as a new lemma.

7. [ ] Deduce the finite-model bound from the certificate by PSD duality, proved directly: if $\Sigma\succeq0$ and $\operatorname{Diag}(d)-K\succeq0$, then
   $$
   \operatorname{tr}(\Sigma K)\leq
   \operatorname{tr}(\Sigma\operatorname{Diag}(d))=\sum_i d_i.
   $$
   Together with step 1, obtain
   $$
   \operatorname{FDR}_{\rm BH}^{(1)}
   \leq q+\frac{\varphi(u)}{\sqrt{2\pi}}
   +Cq\{1+\log(1+u)\}.
   $$
   Establish the singular endpoint separately: for the coupling $X_t=\sqrt t\,X_1+\sqrt{1-t}\,Z$ with independent standard $Z$, $X_t\to X_1$ almost surely. Every coordinate has variance one, so each fixed grid boundary has zero endpoint probability. Thus $f(X_t)\to f(X_1)$ almost surely and bounded convergence applies for each finite model. Do not require a uniform-in-$N$ boundary avoidance probability.

8. [ ] Check the uniform asymptotics. Prove from Mills inequalities that $u/\sqrt{2\log(1/q)}\to1$, $\varphi(u)=q\{u+O(1/u)\}$, and $\log(1+u)=o(u)$. The same constant $C$ in (C) must work for every finite admissible model, without a rank, direction-entropy, mean-size, or dimension restriction. Taking the model supremum only after this uniform finite-model inequality then yields the exact target constant $1/\sqrt\pi$. Check $I_0=\varnothing$ directly and retain all negative null means and all arbitrary positive alternative means throughout.

## Verification

The algebraic corner formulas and finite-model interpolation identity are necessary preliminary claims. They do not prove the theorem. Successful execution requires a fully displayed proof of the stronger matrix estimate (C), including its diagonal construction, the rank-gate square decomposition, and the scalar trace allocation with a universal remainder constant. An SDP solution for examples, numerical evidence, or an appeal to Gaussian covariance convexity is insufficient.

If (C) or the proposed rank-gate kernel extension fails, record the finite-model or analytic obstruction in the plan's Failure section and leave the target unresolved. In particular the three-way split into null/null, null/alternative, and alternative/alternative corners must recombine before estimating the trace. The route may not revert to false per-null uniform bounds, replacement of the actual null means by zero in the FDP, or optimized full-factor-envelope certificates.

On success, steps 1, 3, and 7 give a dimension- and mean-uniform finite-$q$ inequality. Step 8 converts it to precisely the quantified statement of the target. The candidate certificate is strictly a proof obligation in this pending plan; no dependency, statement, approval, or researcher record is changed by writing it.

## Assumed definitions

The plan uses only the approved definitions supplied in the context pack: [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), [false discovery rate](../definitions/false_discovery_rate.md), and [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md).

No draft definition or unproved asset is assumed. The cited ideas motivate the route and its constraints only; their mathematical assertions are not used as black boxes. The corner formulas, Gaussian differentiation identity, Hermite/Schur-kernel statements, matrix estimate (C), and trace allocation all require proof during execution.

## Progress

Execution checkpoint, 2026-11-04. Steps 1--3 are established below. Step 4 has small analytic formulas and finite numerical tests, but its universal certificate is not established or refuted. Steps 5--8 remain unchecked. The target asset and its statement have not been edited; this plan remains pending. The exact scalar interpolation problem, including the original covariance that generated the corner matrix, remains available independently of the stronger matrix relaxation.

### Independent endpoint: step 1

Fix the finite model and retain every actual mean and the fixed labels $\delta_i$. For deterministic p-values let $R_i$ be the BH rank after replacing only $p_i$ by zero. The largest qualifying rank is also the number rejected: if the count at its threshold exceeded the rank, that larger count would itself qualify, contradicting maximality. In particular, $R_i\geq1$.

If $i$ is rejected in the original vector, reducing its p-value to zero changes no threshold count at or above its original rank. Hence $R_i=R$. Conversely, if $p_i\leq aR_i$, the original and forced vectors have the same count at rank $R_i$, and the original vector cannot qualify above $R_i$ because the forced vector does not. Thus $R=R_i$ and $i$ is rejected. This proves the pointwise identity
$$
\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}
=\frac{\mathbf1\{p_i\leq aR_i\}}{R_i}.
$$
At $t=0$, $R_i$ depends only on the other independent coordinates. For $i\in I_0$ and $s\in(0,1)$,
$$
\Pr(p_i\leq s)
=\overline\Phi\bigl(\overline\Phi^{-1}(s)-\theta_i\bigr)\leq s.
$$
Conditioning on the other coordinates therefore bounds the expectation of the displayed ratio by $a$. Summing over the actual null set gives $\mathbb Ef(X_0)\leq a|I_0|\leq q$. No mean inside $f$ was changed.

### General mixed-corner proof: step 2

All assertions here are combinatorial statements for arbitrary fixed bins of the remaining coordinates, with arbitrary binary labels. No Gaussian probability or finite enumeration is used in the argument.

Suppose first $k<l$. At ranks $s<k$, all four threshold counts equal $C_s$. At $s=k$ the count is $C_k+e$. For $k<s<l$ it is $C_s+1$; at $s=l$ it is $C_l+1+f$; above $l$ it is $C_s+2$. Thus only the qualifications at $k$ and $l$ can differ between the four states.

If a common rank above $l$ qualifies, every state has the same largest qualifying rank and the same rejection set. The mixed difference is zero. In the absence of such a rank, changing $f$ can have an effect only if $C_l=l-2$. Indeed, $C_l\leq l-3$ makes rank $l$ fail in both states. If $C_l\geq l-1$, then $l<N$ (there are only $N-2$ other coordinates), and $C_{l+1}+2\geq l+1$: a common later rank qualifies. This latter possibility was already excluded. Consequently a nonzero mixed difference requires $C_l=l-2$, with $f=1$ producing rank $l$ in both $e$ states. At this rank the two FDPs are identical, because both $i$ and $j$ are included.

It remains to compare $e=0,1$ with $f=0$. A common qualifying rank strictly between $k$ and $l$ makes this comparison independent of $e$. If there is no such rank, an effect is possible only when $C_k=k-1$. For $C_k\leq k-2$, rank $k$ fails in both states. For $C_k\geq k$, the rank $k+1$ qualifies with the $i$th coordinate included. This is either a common rank between $k$ and $l$, or is $l$ and contradicts $C_l=l-2$. These exhaust the alternatives.

The remaining conditions are precisely $A_{ij}^{k,l}$. They give ranks $r,k,l,l$ in states $00,10,01,11$. The two rank-$l$ FDPs cancel and the remaining values are $W_r/(r\vee1)$ and $(W_k+\delta_i)/k$. This proves the asserted unequal-threshold formula and proves zero off its gate. Interchanging $(i,k)$ and $(j,l)$ gives the formula for $l<k$.

For $k=l$, only rank $k$ has a state-dependent count, namely $C_k+e+f$. Every rank below it has count $C_s$; every rank above it has count $C_s+2$. If a common rank above $k$ qualifies, all rejection sets agree. Otherwise $C_k\geq k-1$ is impossible: it would force a common qualification at $k+1$; when $k=N$ it is impossible because $C_N\leq N-2$. If $C_k\leq k-3$, no state qualifies at $k$. The only remaining case is $C_k=k-2$, when only state $11$ qualifies. The four ranks are $r,r,r,k$, giving exactly the displayed equal-threshold formula. For $k=1$ its condition would read $C_1=-1$, so it is impossible.

The proofs use no restriction on the labels. In particular alternative/alternative corners are retained. They can be nonzero because the denominator and the rejection of other nulls can change. Two exact examples also show why individual corner signs cannot supply a positive-kernel argument:

- $N=4$, $i=1$, $j=2$, $(k,l)=(3,4)$, remaining bins $(h_3,h_4)=(1,3)$, and labels $(1,0,1,0)$ give $r=1$ and $\Delta=1-2/3=1/3$ at an unequal null/alternative corner.
- With $(k,l)=(3,3)$, remaining bins $(1,5)$, and labels $(0,0,1,0)$, the equal alternative/alternative corner has $\Delta=1/3-1=-2/3$.

These are algebraic counterexamples to a sign shortcut, not failures of (C).

### Finite-model Gaussian interpolation: step 3

For $0\leq t<1$, $\Sigma_t$ is positive definite and has smooth density $g_t$. Direct differentiation of its Gaussian Fourier transform, or of the density, gives
$$
\partial_tg_t=\frac12\sum_{i,j}(\Sigma-I)_{ij}\partial_i\partial_jg_t.
$$
On any compact subinterval of $[0,1)$, the density derivatives have integrable polynomial-times-Gaussian bounds. Since $0\leq f\leq1$, differentiation under the integral is justified there. The diagonal coefficients vanish. Integrating the remaining mixed derivatives over each of the finitely many grid cells telescopes at its two finite coordinate faces. The coefficient at $(x_i,x_j)=(b_{ik},b_{jl})$ is the four-cell mixed difference proved above. Gaussian decay removes the faces at infinity. With the remaining coordinates integrated out this yields
$$
\frac d{dt}\mathbb Ef(X_t)
=\frac12\sum_{i\ne j}\Sigma_{ij}
\sum_{k,l=1}^N\varphi_2(b_{ik},b_{jl};t\Sigma_{ij})
\mathbb E_t[\Delta_{ij;k,l}\mid X_{t,i}=b_{ik},X_{t,j}=b_{jl}].
$$
The sign is positive: increasing $x_i$ through $b_{ik}$ changes its bin from $k+1$ to $k$, and likewise for $j$. The two one-dimensional integration-by-parts signs multiply to a positive sign.

For every fixed pair and fixed finite model,
$$
\varphi_2(b_{ik},b_{jl};t\Sigma_{ij})
\leq\frac1{2\pi\sqrt{1-t^2\Sigma_{ij}^2}},\qquad |\Delta_{ij;k,l}|\leq4.
$$
The right-hand side is integrable on $[0,1)$, even at $|\Sigma_{ij}|=1$. Thus each entry of the specified $K$ exists absolutely; symmetry follows by interchanging the two coordinates and thresholds.

To pass to the endpoint, couple $X_t=\sqrt t\,X_1+\sqrt{1-t}\,Z$ with independent $Z\sim N(0,I)$. Then $X_t\to X_1$ almost surely. Every coordinate of $X_1$ has a continuous variance-one marginal, so the finite union of fixed grid boundaries has zero probability, even for singular $\Sigma$. Off that union $f$ is locally constant. Bounded convergence therefore gives $\mathbb Ef(X_t)\to\mathbb Ef(X_1)$. Integrating the previous derivative formula and taking this limit proves
$$
\mathbb Ef(X_1)-\mathbb Ef(X_0)=\operatorname{tr}(\Sigma K).
$$
The factor $1/2$ inside $K$ is required because the trace sums both ordered pairs. This proof does not assert any monotonicity in $t$ and needs no boundary-avoidance estimate uniform in dimension. It also establishes the singular-endpoint portion of step 7, but does not settle that whole checklist item.

### An exact full-cell form for the remaining analysis

Put $b_{v0}=+\infty$, $b_{v,N+1}=-\infty$, and, for the other-bin vector $h$, set
$$
D_{ij}(h)=\prod_{v\ne i,j}(b_{v,h_v},b_{v,h_v-1}),\qquad
B_t^{ij}(k,l,h)=\int_{D_{ij}(h)}g_t(x_i=b_{ik},x_j=b_{jl},x_{-ij})\,dx_{-ij}.
$$
Boundary inclusions have zero measure for $t<1$. The exact matrix is
$$
K_{ij}=\frac12\int_0^1\sum_{k,l,h}\Delta_{ij;k,l}(h)B_t^{ij}(k,l,h)\,dt.
$$
Every $B$ here uses the same full density $g_t$, including its genuine remaining-coordinate dependence. This representation is available for regrouping terms; it does not replace conditional gate probabilities by independent ones.

In particular define the unequal-corner face increment
$$
J_{i;r,k}=\frac{W_k+\delta_i}{k}-\frac{W_r}{r\vee1}.
$$
For $r>0$ its exact interval decomposition is
$$
J_{i;r,k}=\frac{W_k-W_r+\delta_i}{k}-\frac{W_r(k-r)}{rk}.
$$
For $r=0$ it is $(W_k+\delta_i)/k$. Unequal corners contribute $-J_{i;r,k}$ on their gates. Equal corners have the same formula with $\delta_i+\delta_j$ in place of $\delta_i$. The second term for $r>0$ is the retained old-null dilution term. Either sign is possible, as the two exact examples above demonstrate.

### Small analytic and numerical tests of step 4

For $N=2$ the only possibly nonzero coefficients are
$$
\Delta_{12;1,2}=-\delta_1,\qquad
\Delta_{12;2,1}=-\delta_2,\qquad
\Delta_{12;2,2}=(\delta_1+\delta_2)/2.
$$
Writing $\rho=\Sigma_{12}$, this gives the explicit one-dimensional integral
$$
K_{12}=\frac12\int_0^1\left\{
-\delta_1\varphi_2(b_{11},b_{22};t\rho)
-\delta_2\varphi_2(b_{12},b_{21};t\rho)
+\frac{\delta_1+\delta_2}{2}\varphi_2(b_{12},b_{22};t\rho)
\right\}\,dt.
$$
For a symmetric $2$ by $2$ zero-diagonal matrix with off-diagonal entry $h$, the smallest feasible diagonal trace is exactly $2|h|$. Necessity follows from $d_1,d_2\geq0$, $d_1d_2\geq h^2$; equality is attained by $d_1=d_2=|h|$. This provides a direct exact test of the relaxation in two dimensions, not a proof of its uniform budget.

Reproducible script: `research-local/verification_gaussian_bh_corner_budget_20261104.py`. Captured output: `research-local/verification_gaussian_bh_corner_budget_20261104.jsonl`. Run it with `python3` and no extra packages. It performs 39,280 exact-rational comparisons of the two formulas with direct BH over all labels/bins/pairs for $N=2,3,4$. These passed and serve as independent algebra diagnostics, not the general proof above.

It also evaluates 33 small $N=2,3$ Gaussian models at $q=0.05,0.001,10^{-6}$: independent mixed means, nearly singular positive correlation, all-null rank-one, heterogeneous-null and mixed rank-one, antagonistic rank-one in two dimensions, and the singular three-dimensional simplex. Bivariate boundary densities are integrated in $t=\sin\alpha$; for $N=3$ the remaining conditional bin probabilities are univariate Gaussian probabilities. Two midpoint resolutions are reported. The $N=3$ dual test optimizes explicitly over $x\in[-1,1]$ the expression $2\{K_{12}x+\sqrt{K_{13}^2+K_{23}^2+2K_{13}K_{23}x}\}$; it supplies a feasible-correlation lower bound on any diagonal trace.

The script additionally tests the $K=2$, $N=4$ representative of the boundary-null obstruction in the inspired risk, at $q=0.05,0.001$, retaining its positive/negative rank-one signs and actual heterogeneous null means. For this test it conditions the one-factor representation on the two boundary coordinates and integrates the remaining scalar factor before enumerating the two remaining bins. The two resolutions give row-certificate traces approximately $0.0112358$ and $0.000223366$, versus leading budgets $0.0411452$ and $0.00134327$. None of these finite diagnostics refutes (C). They do not test either exponentially growing obstruction family uniformly, do not provide rigorous quadrature error bounds, and do not establish a universal remainder constant. Tiny residuals in the homogeneous all-null rank-one zero matrix are quadrature error, not evidence of a nonzero exact matrix.

### A genuine PSD construction, and the budget it loses

For the actual integrated $K$, let $d_i^{\rm row}=\sum_{j\ne i}|K_{ij}|$. This always gives a certificate, since, with $e_i$ the coordinate basis vectors,
$$
\operatorname{Diag}(d^{\rm row})-K
=\sum_{i<j}|K_{ij}|(e_i-\operatorname{sgn}(K_{ij})e_j)
(e_i-\operatorname{sgn}(K_{ij})e_j)^{\mathsf T}\succeq0.
$$
The sign at a zero coefficient is irrelevant. Its trace is $\sum_{i\ne j}|K_{ij}|$. This construction is valid; the required trace bound for it is not proved. The available entrywise integrability bound gives only $|K_{ij}|\leq N^2/2$ and trace at most $N^3(N-1)/2$, which has neither the needed $q$ factor nor dimension uniformity. Taking absolute values inside the full-cell sum is even weaker: it charges the old-null dilution terms and the newly admitted rank-interval terms separately, and cannot use the exact cancellations already present in $J_{i;r,k}$. Thus this attempt loses control at the trace-allocation step. No counterexample to a sharper bound for the row construction has been proved.

For comparison, the unweighted Schur-channel assertion itself is elementary. If $\Sigma_{ij}=\langle v_i,v_j\rangle$ is a Gram representation, then for integer $m\geq0$ and arbitrary real $a_i$ the matrix $[a_i\Sigma_{ij}^ma_j]$ is the Gram matrix of $a_iv_i^{\otimes m}$, using scalar $1$ at $m=0$. In particular this applies to $a_i=\varphi(c_i)H_m(c_i)$ for a single boundary per coordinate. In the full-cell representation above, however, the weights $B_t^{ij}(k,l,h)$ and $J_{i;r,k}$ depend jointly on the pair and the other bins; they have not been factored into such coordinate features. The two signed-corner examples also rule out simply declaring all rank-channel coefficients nonnegative. Consequently neither the Schur assertion nor this row construction proves the needed rank-gated square decomposition.

### Elementary final deductions that are conditional on the missing budget

If a diagonal satisfying (C) is constructed, the PSD trace implication follows directly by writing $\Sigma=\sum_\alpha\lambda_\alpha v_\alpha v_\alpha^{\mathsf T}$ with $\lambda_\alpha\geq0$: for $A=\operatorname{Diag}(d)-K\succeq0$, $\operatorname{tr}(\Sigma A)=\sum_\alpha\lambda_\alpha v_\alpha^{\mathsf T}Av_\alpha\geq0$. The unit diagonal then gives $\operatorname{tr}(\Sigma K)\leq\sum_i d_i$. Along with step 1 and the interpolation identity, this would yield the finite-model inequality in step 7.

The scalar capacity integral is exactly
$$
\int_0^\infty\min\{q,\overline\Phi(v)\}\,dv
=qu+\int_u^\infty\overline\Phi(v)\,dv
=qu+\varphi(u)-uq=\varphi(u).
$$
Integration by parts gives, for $u>0$, $\varphi(u)u/(u^2+1)\leq q\leq\varphi(u)/u$. Hence $\varphi(u)=q\{u+O(1/u)\}$ and $\log(1/q)=u^2/2+\log u+\tfrac12\log(2\pi)+O(u^{-2})$. It follows that $u/\sqrt{2\log(1/q)}\to1$ and $\log(1+u)=o(u)$. These elementary facts do not identify a matrix trace with the capacity integral. If $I_0$ is empty, $f$, every corner, and $K$ are identically zero.

### Exact next executable task

Resume here rather than redoing steps 1--3. The unresolved task is to prove or refute (C) for the explicitly defined integrated matrix, with a single constant valid for all finite $q$-dependent models. Start from the full-cell formula and the signed interval identity for $J$ above. Keep the two terms in that identity together while aggregating equal and unequal corners over their actual rank gates. A successful construction must specify real $d_i$ and an explicit sum or integral of square features equal to $\operatorname{Diag}(d)-K$, with nonnegative coefficients, and then assign its trace to the single capacity $\varphi(u)/\sqrt{2\pi}$ plus a proved $Cq\{1+\log(1+u)\}$ remainder. One concrete branch is to test whether the already explicit row certificate admits this trace bound without moving absolute values inside its integrated corner sum; another is to improve it by a rank-interval square decomposition that preserves the negative dilution term.

Before claiming such a decomposition, test it on the two signed corners displayed above, on the saved $N=2$ exact integral, and on both growing obstruction families specified by the inspired ideas. If a proposed uniform diagonal budget fails, exhibit a feasible unit-diagonal PSD test matrix $\Gamma$ and a family with $\operatorname{tr}(\Gamma K)$ exceeding its budget by an unbounded multiple of $q\{1+\log(1+u)\}$; this would rigorously fail the stronger plan. Numerical optimization alone is insufficient. If the matrix relaxation fails, retain the exact original-covariance signed integral $\operatorname{tr}(\Sigma K)$ as the separate remaining upper-bound task. The target has not been proved or refuted by this checkpoint, and no additional global-budget assumption is introduced.

## Failure

Continuation, 2026-11-04. Step 4's matrix estimate (C) is false. The analytic family below has an admissible PSD unit-diagonal test matrix $\Gamma_N$ for which $\operatorname{tr}(\Gamma_NK_N)$ grows at least as a positive constant times $\log N$, at a fixed testing level. Therefore no diagonal completion, including one obtained by rank-gate squares, can have the proposed dimension-uniform trace budget. The earlier Progress is retained verbatim as a historical checkpoint; this Failure supersedes its pending-status and next-task sentences. The target asset and its statement are unchanged.

### An admissible family and an exact dual identity

Fix $q=1/4$ and even $N$, and put
$$
\beta=10,\qquad
\eta=\frac{e^{-10}}8,\qquad
\alpha=\log(8-e^{-10}),\qquad
c=\frac1{16},\qquad
L_N=\sqrt{2c\log N}.
$$
The first $N/2$ coordinates are true nulls of mean $-\beta/L_N$; the other $N/2$ are alternatives of mean $\alpha/L_N>0$. Let $\lambda>0$ be a sufficiently small fixed number, chosen below, and define
$$
\rho_N=\frac{\lambda}{L_N^2},\qquad
\Gamma_N=I_{N/2}\oplus J_{N/2},\qquad
\Sigma_N=(1-\rho_N)I_N+\rho_N\Gamma_N,
$$
where $J_m$ is the $m$ by $m$ all-ones matrix. For all sufficiently large $N$, both matrices are PSD with unit diagonal. Thus nulls are mutually independent and independent of all alternatives; only the alternatives have common correlation $\rho_N$. All mean signs, labels, and unit marginal variances are the actual admissible ones.

Write $K_N$ for the integrated matrix of step 3 generated by this model, and write $B_N(\Omega)$ for its actual BH FDR when only its covariance is changed to $\Omega$. Since $\operatorname{tr}K_N=0$, the already established exact interpolation identity gives
$$
\rho_N\operatorname{tr}(\Gamma_NK_N)
=\operatorname{tr}(\Sigma_NK_N)
=B_N(\Sigma_N)-B_N(I_N).
\tag{F1}
$$
No corner signs or conditional gates have been discarded. We prove that the right-hand side has a strictly positive lower limit for a suitable fixed $\lambda$. The division by $\rho_N$ will then force the dual trace to diverge.

### Conditional population root, with a finite-sample justification

Represent the alternatives, conditional on a standard normal $Z$, as independent coordinates with distribution
$$
N\left(\frac{A}{L_N},1-\frac{\lambda}{L_N^2}\right),
\qquad A=\alpha+\sqrt\lambda Z.
$$
The null coordinates remain independent $N(-\beta/L_N,1)$, independent of $Z$. For a threshold $p=\overline\Phi(v)$, set $s=v/L_N$. If $v\geq u=\overline\Phi^{-1}(q)>0$ and $0\leq s\leq S=3/2$, the two conditional p-value CDFs satisfy, uniformly for $A$ in a compact neighborhood of $\alpha$,
$$
\frac{\overline\Phi(v+\beta/L_N)}{\overline\Phi(v)}
=e^{-\beta s}+o(1),
$$
$$
\frac{\overline\Phi\left((v-A/L_N)/\sqrt{1-\lambda/L_N^2}\right)}{\overline\Phi(v)}
=e^{As-\lambda s^2/2}+o(1).
\tag{F2}
$$
These uniform statements include $s\to0$. Indeed the normal hazard $H(v)=\varphi(v)/\overline\Phi(v)$ obeys $H(v)=v+O(1)$ on $v\geq u/2$, by Mills inequalities and a bound on the remaining compact interval. Integrate this hazard over the null shift $\beta/L_N$ and over the alternative shift
$$
\frac{v-A/L_N}{\sqrt{1-\lambda/L_N^2}}-v
=\frac{\lambda s/2-A}{L_N}+O(L_N^{-3}).
$$
The errors are uniform on the displayed compact sets, and yield (F2) directly.

Consequently, at a BH threshold $p=qk/N$, the conditional expected threshold count divided by $k$ converges uniformly on this range to
$$
Q(s;A,\lambda)
=\frac q2\left\{e^{-\beta s}+e^{As-\lambda s^2/2}\right\}.
$$
At $(A,\lambda)=(\alpha,0)$, one has $Q(1;\alpha,0)=1$ and
$$
\partial_sQ(1;\alpha,0)=D,
\qquad D=\alpha(1-\eta)-\beta\eta>0.
$$
Also $Q(0;A,\lambda)=q<1$. Choose fixed $\varepsilon>0$ and $\lambda_0>0$ small enough that, for $|A-\alpha|\leq\varepsilon$ and $0\leq\lambda\leq\lambda_0$, the first crossing $s_*(A,\lambda)$ is smooth, lies in $(1/2,3/2)$, and has positive derivative in $s$. There is no earlier crossing: on $[0,S]$ the null exponential is strictly convex, and the alternative exponential has second derivative
$$
\left\{(A-\lambda s)^2-\lambda\right\}e^{As-\lambda s^2/2}>0
$$
after decreasing this neighborhood. Strict convexity, the value below one at zero, and the local upward crossing imply $Q(s)<1$ for every $s<s_*$ and $Q(s)>1$ just after $s_*$. A possible crossing beyond $S$ cannot produce a larger BH rank.

Here is why the random BH threshold selects this first root. For each small fixed $d>0$ with $s_*\pm d\in(0,S)$, the grid ranks corresponding to thresholds $\overline\Phi((s_*\pm d)L_N)$ are
$$
k_{N,\pm}=\frac Nq\overline\Phi((s_*\pm d)L_N)+O(1)
=N^{1-c(s_*\pm d)^2+o(1)}.
$$
They grow polynomially, uniformly on a smaller compact neighborhood, since $cS^2=9/64<1$. At $k_{N,+}$ the expected count exceeds its rank by a fixed positive fraction. At every grid rank at least $k_{N,-}$, (F2) and the strict pre-crossing gap bound the expected count below its rank by a fixed positive fraction. The count is a sum of conditionally independent Bernoulli variables. For completeness, its exponential moment obeys
$$
\mathbb E e^{t(C-\mathbb EC)}
\leq\exp\{\mathbb EC(e^t-1-t)\}.
$$
Markov's inequality with a fixed small positive or negative $t$ therefore bounds either fixed-fraction error by $e^{-\kappa k}$ for some $\kappa>0$. A union bound over at most $N$ ranks costs at most $N e^{-N^{\kappa'}}\to0$, with another positive $\kappa'$. Hence the BH rank $R_N$ satisfies
$$
\frac{\overline\Phi^{-1}(qR_N/N)}{L_N}
\ \longrightarrow\ s_*(A,\lambda)
\quad\text{in conditional probability}.
$$
The distinction between a threshold count and the BH rejection count causes no error: as proved in step 1, at the largest qualifying rank that count equals the rank.

Apply the same exponential-moment bound to the null threshold counts, uniformly over the polynomially large ranks just localized. Their expected count divided by $k$ is $\frac q2e^{-\beta s}+o(1)$, bounded away from zero on the compact interval. Thus
$$
\operatorname{FDP}_N\longrightarrow
F(A,\lambda):=\frac q2e^{-\beta s_*(A,\lambda)}
\quad\text{in conditional probability}.
\tag{F3}
$$
Since FDP lies in $[0,1]$, its conditional expectation converges to the same value. In particular, the independent baseline, given by $A=\alpha$ and $\lambda=0$, obeys
$$
B_N(I_N)\longrightarrow F(\alpha,0)=\eta.
\tag{F4}
$$
This proves the required expectation limits from actual threshold counts; no derivative limit in dimension and no unproved population approximation is used.

### A positive Gaussian-mixing gain

Put $r=1-\eta$. All derivatives in this paragraph are evaluated at $(A,\lambda)=(\alpha,0)$, where $s_*=1$. Implicit differentiation of $Q(s_*;A,\lambda)=1$ gives
$$
s_{*,A}=-\frac rD,\qquad s_{*,\lambda}=\frac r{2D},
\qquad
F_A=\frac{\beta\eta r}{D},\qquad
2F_\lambda=-F_A.
$$
Differentiating once more, using $Q_{ss}=\beta^2\eta+\alpha^2r$, $Q_{sA}=r(1+\alpha)$ and $Q_{AA}=r$, yields the exact expression
$$
G:=F_{AA}+2F_\lambda
=\frac{\beta\eta r^2}{D^3}
\left\{r\alpha(\beta-\alpha-2)+2\beta\eta(1+\alpha)\right\}>0.
\tag{F5}
$$
Positivity follows from $0<\alpha<\log8<3$, $\beta=10$, and $D>0$. For example $\eta<1/8000$, $\alpha>\log7>1$, so $D>1-11/8000>0$. The variance correction $-\lambda s^2/2$ in (F2) is retained in the term $2F_\lambda$; omitting it would give a different, invalid calculation.

Taylor expansion of the smooth local function $F$, with $A=\alpha+\sqrt\lambda Z$, now gives
$$
\mathbb E\left[
\mathbf1\{|\sqrt\lambda Z|\leq\varepsilon\}
F(\alpha+\sqrt\lambda Z,\lambda)\right]
=\eta+\frac\lambda2G+o(\lambda).
\tag{F6}
$$
To justify this expansion on the local domain, retain terms through $F_{AA}(A-\alpha)^2/2+F_\lambda\lambda$ and bound the integrated remainder by a constant times $\mathbb E|\sqrt\lambda Z|^3+\lambda\mathbb E|\sqrt\lambda Z|+\lambda^2=O(\lambda^{3/2})$. The truncated odd term is zero by symmetry; truncation changes the constant and quadratic terms by an exponentially small amount, because $\Pr(|\sqrt\lambda Z|>\varepsilon)\leq2e^{-\varepsilon^2/(2\lambda)}$. No assertion about the population root outside this local event is needed.

Conditional FDP is nonnegative outside the local event. On the event, (F3) and bounded convergence apply. Choose one sufficiently small fixed $\lambda\in(0,\lambda_0)$ so that the right-hand side of (F6) is at least $\eta+\lambda G/4$. Together with (F4), this proves
$$
\liminf_{N\to\infty\atop N\ \mathrm{even}}
\{B_N(\Sigma_N)-B_N(I_N)\}
\geq\frac{\lambda G}{4}>0.
\tag{F7}
$$

### Contradiction to (C), and the remaining original-covariance task

Combining (F1), (F7), and $L_N^2=2c\log N$ gives
$$
\liminf_{N\to\infty\atop N\ \mathrm{even}}
\frac{\operatorname{tr}(\Gamma_NK_N)}{\log N}
\geq\frac{cG}{2}>0.
\tag{F8}
$$
For every proposed completion $\operatorname{Diag}(d)-K_N\succeq0$, PSD trace duality with the explicit $\Gamma_N$ implies $\sum_i d_i\geq\operatorname{tr}(\Gamma_NK_N)$. At the fixed $q=1/4$, the right-hand budget in (C) is finite and independent of $N$, for every fixed numerical $C$. Equation (F8) contradicts it. This refutes the uniform trace allocation itself, not only the row completion or a proposed kernel factorization. In particular no regrouping of the actual rank gates can produce a diagonal with the claimed budget.

The obstruction is not confined to a moderate testing level. For any fixed $q\in(0,1/2)$, take $\eta=(q/2)e^{-\beta}$ and $\alpha=\log(2/q-e^{-\beta})$. Choose $\beta$ sufficiently large that $D>0$ and $\beta>\alpha+2$. All the preceding arguments hold with these fixed constants, and (F5) remains positive. Thus a version of (C) restricted to all sufficiently small levels is also false.

For the covariance that generated $K_N$, (F1) instead gives $\operatorname{tr}(\Sigma_NK_N)=\rho_N\operatorname{tr}(\Gamma_NK_N)$, which remains a bounded FDR increment. Indeed, each null here is independent of all the other coordinates, even though the alternatives are dependent. The leave-one-out identity in step 1 therefore applies to every null in this family and gives $B_N(\Sigma_N)\leq q/2$. Consequently this family supplies no refutation of the target upper bound.

Steps 5--8 cannot complete this plan because their required premise (C) has been refuted. What remains for the original target is a dimension- and mean-uniform upper bound on the signed scalar $\operatorname{tr}(\Sigma K)$ for its own generating covariance; the stronger support over all PSD unit-diagonal $\Gamma$ cannot be used. No such general scalar estimate is proved here. No asset, approval record, loop state, settings, or existing verification script/output was changed by this continuation; only this plan was edited.
