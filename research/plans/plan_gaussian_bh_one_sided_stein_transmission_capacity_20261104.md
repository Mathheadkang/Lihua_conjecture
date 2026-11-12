---
type: plan
title: Gaussian Stein transmission with a finite location-envelope budget
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
inspired_by:
  - idea_b8a514004c9b
  - idea_c781d2dc45a5
  - idea_87b11e1b30f8
  - idea_e6e1f4c16f22
  - idea_b4d004ae71a6
  - idea_cc4ddef48cdd
  - idea_f733876e24f5
tags:
  - gaussian-bh
  - one-sided
  - stein-transmission
  - global-rank-budget
---

## Goal

Target: [Sharp uniform upper-bound target for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_sharp_upper.md).

Construct a Gaussian divergence certificate on the cells of the **complete ordinary BH rule**, with a fixed one-dimensional location-envelope budget. The proposed mechanism is transmission of signed Gaussian flux between adjacent rank cells. It retains the actual covariance Gram matrix and every actual mean. It is neither a covariance-class extremal reduction nor a separate bound on each null contribution.

The principal new obligation is the coefficient lemma (CS64) below. It is a concrete, stronger sufficient certificate with a restricted ansatz and pointwise face conditions, not an assumed estimate for FDR. It may fail even when the target is true. An exact infeasibility certificate stops this plan; passing a small-dimensional FDR comparison does not pass its first gate. No statement, approval, or loop setting is changed by this plan.

The current context has three failed plans and no pending plan for the target. Native library searches for `Gaussian`, `Gaussian BH upper bound`, `Gaussian random threshold martingale stopping`, `Gaussian heat flow stochastic localization Brownian stopping`, `Gaussian surface area coarea rank partition`, `Gaussian Stein divergence transmission obstacle supersolution`, and `Shtarkov Gaussian location normalizer` returned no results. Thus no library proof is adapted or cited as an undeclared black box. Native `show` reads of the omitted actual-null jump, simplex, harmonic-contribution, negative-mean, and Su-linking ideas were needed to check which relaxations had already failed. Their observations are warnings and test families; the required calculations are rederived here.

Only short deterministic local algebra or diagnostics are allowed by this plan. Any heavy feasibility search or certified numerical sweep belongs on UC Davis, in a new isolated directory with at most two CPU processes and preserved scripts/configurations. A previous automatic-review denial of a specific unpublished-script export cannot be bypassed by another transfer channel; the coordinating root agent must resolve any fresh required approval. A computational block leaves analytic work available and does not authorize changing that boundary.

## Proposed Gaussian transmission certificate

All definitions in this section are local proof notation, not changes to the approved model definitions. Write \(Q=\overline\Phi\), \(\phi(x)=(2\pi)^{-1/2}e^{-x^2/2}\), and \(\Phi=1-Q\). Work first with \(0<q\leq Q(1)\), \(u=Q^{-1}(q)\geq1\), a positive-definite admissible covariance, the actual null set \(J=\{i:\theta_i\leq0\}\), and \(\pi_0=|J|/N\). Choose unit Gram vectors \(v_i\in\mathbb R^N\) satisfying \(v_i^\mathsf Tv_j=\Sigma_{ij}=\rho_{ij}\), let \(Z\sim N(0,I_N)\), and put \(g_i=v_i^\mathsf TZ\), so \(T_i=\theta_i+g_i\). No independence of the \(g_i\)'s is asserted.

The fixed location envelope and its proposed budget are
$$
M_u(x)=\sup_{0\leq a\leq u}e^{ax-a^2/2}
=\begin{cases}
1,&x\leq0,\\
e^{x^2/2},&0<x<u,\\
e^{ux-u^2/2},&x\geq u,
\end{cases}
\qquad
c_u=1+\frac{u}{\sqrt{2\pi}},\qquad
D_u=64\log(2+u).
$$
Splitting the Gaussian integral at \(0,u\) should give the exact identity \(\mathbb EM_u(G)=c_u\) for \(G\sim N(0,1)\). The number 64 is a fixed candidate, not a proved constant or a value allowed to depend on \(N,\theta,\Sigma\). A failure at this value refutes this plan's CS64; it need not refute a different finite constant or the target.

Define the scalar Stein solutions
$$
h_b(x)=-\begin{cases}
Q(b)\Phi(x)/\phi(x),&x\leq b,\\
\Phi(b)Q(x)/\phi(x),&x\geq b,
\end{cases}
\qquad
\psi_u(x)=\frac{1}{\phi(x)}\int_{-\infty}^{x}\{M_u(s)-c_u\}\phi(s)\,ds.
$$
The equations to check are \(h_b'-xh_b=\mathbf1_{\{x>b\}}-Q(b)\) almost everywhere and \(\psi_u'-x\psi_u=M_u-c_u\). Both functions are continuous at their displayed joining points. The equality value of an indicator is immaterial to these equations.

Put \(t_k=qk/N\), \(z_k=Q^{-1}(t_k)\), and \(b_{ik}=z_k-\theta_i\). Partition the observation coordinates \(g\in\mathbb R^N\) by every grid hyperplane \(g_i=b_{ik}\). For each open rectangular cell \(C\), compute the **full** BH rejection count \(R_C\) and set \(\kappa_C=R_C\vee1\). In particular, zero-rejection cells use \(\kappa_C=1\), rather than a zero vector field. Define
$$
B_k=\frac1{Nt_k}\sum_{i\in J}Q(b_{ik}),
\qquad
U_u(g)=\frac1N\sum_{i\in J}M_u(g_i).
$$
Every actual negative null mean remains in \(b_{ik}\) and \(B_k\). Only the marginal inequality \(Q(z_k-\theta_i)\leq t_k\) is used, giving \(0\leq B_k\leq\pi_0\).

The allowed correction is deliberately fixed. For each cell choose finite real coefficients \(\alpha_{Cj}\), \(j\in[N]\), and \(0\leq\beta_{Ci}\leq1\), \(i\in J\), and form the vector field
$$
\mathcal A_C(Z)=\frac1N\sum_{i\in J}v_i\left\{
\frac{h_{b_{i\kappa_C}}(g_i)}{t_{\kappa_C}}
-\beta_{Ci}\psi_u(g_i)\right\}
+\sum_{j=1}^N\alpha_{Cj}v_j.
\tag{A}
$$
Coefficients can depend on the displayed model and cell, but not on an unknown FDR value. Enlarging this ansatz after a counterexample requires a new plan.

**Coefficient lemma CS64 (unproved).** For every positive-definite admissible model and \(0<q\leq Q(1)\), coefficients in (A) exist satisfying both of the following explicit conditions.

* Cell budget: for every cell \(C\),
$$
B_{\kappa_C}-\frac{c_u}{N}\sum_{i\in J}\beta_{Ci}
+\sup_{g\in C}\sum_{j=1}^N\alpha_{Cj}g_j
\leq D_u.
\tag{C}
$$
The supremum is the sum of one-dimensional endpoint suprema on the rectangular intervals. A nonzero coefficient pointing toward an infinite endpoint is prohibited by (C), rather than silently discarded.

* Transmission: on every adjacent face \(F=C^-\mid C^+\) in coordinate \(j\), oriented from smaller to larger \(g_j\), the normal jump is nonnegative everywhere on the finite part of the face:
$$
\frac1N\sum_{i\in J}\rho_{ji}
\left\{
\frac{h_{b_{i\kappa_+}}(g_i)}{t_{\kappa_+}}
-\frac{h_{b_{i\kappa_-}}(g_i)}{t_{\kappa_-}}
-(\beta_{C^+i}-\beta_{C^-i})\psi_u(g_i)
\right\}
+\sum_{\ell=1}^N\rho_{j\ell}(\alpha_{C^+\ell}-\alpha_{C^-\ell})
\geq0.
\tag{T}
$$
Here \(\kappa_\pm=\kappa_{C^\pm}\) and \(g_j\) equals the face threshold. Because the covariance is positive definite, all other observation coordinates can vary freely and separately over their cell intervals when testing this pointwise condition. Its infimum is therefore a sum of explicit one-variable infima, with the \(i=j\) term evaluated at the threshold. No conditional-independence approximation or replacement of \(\rho\) by another PSD matrix is allowed. Opposite signs of correlations must use the appropriate infimum, not a common upper bound.

The Gaussian structure enters through the actual unit Gram normals, the Stein drift, and the exact marginal integral of \(M_u\). The main proposed mechanism is to allocate the bounded coefficients \(\beta\) across the cell graph so that harmful rank-face flux is transported to favorable faces, while (C) limits the price of the constant vector corrections. Unlike an unconstrained matrix completion, these coefficients must satisfy every face of the same BH grid simultaneously.

## Plan

1. [x] **Establish the exact full-rank cell identity before testing CS64.** Prove deterministically that the count at the largest qualifying rank equals that rank, including tied p-values. On each open cell verify
$$
\frac1{Nt_{\kappa_C}}\sum_{i\in J}\mathbf1_{\{g_i>b_{i\kappa_C}\}}
=\frac{\operatorname{FDP}_C}{q}.
$$
For \(R_C=0\), prove that all p-values exceed \(q/N\), so the left side is zero despite \(\kappa_C=1\). Derive the Gaussian divergence, with \(\operatorname{div}_\gamma A=\operatorname{div}A-Z^\mathsf TA\), of (A) in a cell:
$$
\operatorname{div}_\gamma\mathcal A_C
=\frac{\operatorname{FDP}_C}{q}-B_{\kappa_C}
-\frac1N\sum_{i\in J}\beta_{Ci}\{M_u(g_i)-c_u\}
-\sum_j\alpha_{Cj}g_j.
\tag{I}
$$
Check the sign in (T) using integration over two adjacent cells: a positive jump contributes a positive singular measure to the distributional divergence, so the sum of **interior** divergence integrals is nonpositive after the exterior boundary vanishes. Do not reverse this sign. Reprove the scalar Stein equations and \(\mathbb EM_u=c_u\), rather than citing an unlisted dependency.

2. [ ] **First substantive gate: test the fixed ansatz, not the FDR bound.** Enumerate the full grid and all adjacent faces for \(N=2,3\), keeping the common \(R_C\). Derive the exact convex feasibility problem (C),(T), with a certified one-variable separation oracle for each face. Begin with \(q=1/64\), all-null \(\theta=0\), \(\Sigma_{ij}=-1/10\) for \(i\ne j\), then the three-coordinate mixed-mean rank-one families from the negative-null example, regularized by \(\Sigma_\eta=(1-\eta)ss^\mathsf T+\eta I\) with \(\eta>0\), and all label patterns in \(N=2\). Treat negative means as actual parameters. Provide either explicit coefficients and certified extrema covering every face and cell, or an exact dual/separation obstruction at a concrete admissible parameter value. A grid of collocation points is a discovery aid only. Establish the required quantile and one-dimensional extremum enclosures with directed bounds. Feasibility of the zero-mean independent model is a normalization check, not evidence of universal feasibility. The existing \(N=3\) FDR gap and the fact that \(H_3q\) is already below the envelope budget at \(q=1/64\) supply **no** certificate for this gate. If CS64 is infeasible, stop without changing the target or silently increasing 64.

3. [ ] **Check dimension growth before relying on the finite gate.** Derive symbolic feasible coefficients or a symbolic dual obstruction for the following growing families, uniformly in the indicated singular regularization before its limit: centered iid nulls; the singular all-null simplex \(\Sigma_{ij}=-1/(N-1)\); the one-boundary-null harmonic staircase with conservative cloned nulls from [the checked harmonic obstruction](../ideas/idea_f733876e24f5.md), including \(K=\lceil e^{1/q}\rceil\); and the fixed-alternative/common-alternative-block examples in the failed plans. These test both actual negative-null attenuation and collective allocation. Track the minimum required cell budget, not just actual FDR. Prove it remains at most \(64\log(2+u)\), or exhibit a certified lower bound forcing failure. In particular, show explicitly where the harmonic sum in ranks cancels or is charged to \(\beta\in[0,1]\). No term \(c\log N\), hidden number of cells, \(\log(1/\eta)\), or unbounded mean range may be put in the remainder. A divergent necessary budget refutes this certificate, even if every model's actual FDR is small.

4. [ ] **Construct coefficients for arbitrary \(N,\theta,\Sigma\succ0\), or fail at a precise obstruction.** Obtain an explicit construction or constructive dual proof of CS64. Use (T)'s separability to write the exact semi-infinite convex system, including all endpoint sign restrictions from (C). For a finite separator set, derive its linear/convex separation dual; justify passage to all face points using analytic endpoint bounds, not unchecked sampling. A viable dual proof must identify the cell-graph circulations that cancel the \(\alpha\) variables and the bounded resources from \(0\leq\beta\leq1\). Give the actual signed rank/covariance telescoping identity and the inequality that bounds each surviving class of terms by the total \(64\log(2+u)\) budget. Any use of Gram positivity must display its vectors or its quadratic form at the **generating** covariance. Derive the needed finite-dimensional separation result within the proof if no dependency is available. Do not replace this task by an assertion that a divergence solution exists, a restatement of an FDR bound, a numerical optimizer, an unrestricted PSD support bound, or per-null square-root-log inequalities. If the proposed local face resources cannot be made compatible around a cycle, record that exact cycle as the obstruction and stop.

5. [ ] **Prove that a CS64 certificate implies the finite-level scalar bound, with explicit exterior boundary conditions.** From (I), \(0\leq\beta\leq1\), and (C), derive pointwise in every cell
$$
\frac{\operatorname{FDP}_C}{q}
\leq \operatorname{div}_\gamma\mathcal A_C+U_u(g)+D_u.
\tag{S}
$$
For each fixed finite positive-definite model, prove that the finitely many coefficients are finite, the \(h_b\)'s are bounded, and \(\psi_u\) satisfies \(|\psi_u(x)|\leq C_u(1+e^{u|x|})\) for a finite constant \(C_u\) depending only on \(u\). Integrate over a smooth radius cutoff in \(Z\), pass its radius to infinity using Gaussian integrability of \(1+\sum_i e^{u|g_i|}\), and verify that all exterior cutoff terms tend to zero. Prove that face traces are integrable under their induced Gaussian surface measure; no absolute-sum bound uniform in \(N\) is needed for this fixed-model integration. Codimension-two intersections have zero surface measure for positive-definite covariance. Use (T) only after summing the exact interior and face terms. Obtain
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)
\leq q\left\{\pi_0\left(1+\frac{u}{\sqrt{2\pi}}\right)
+64\log(2+u)\right\}.
\tag{F}
$$
This is an aggregate null allocation; no conclusion about an individual null contribution follows.

6. [ ] **Pass to all singular PSD matrices without a coefficient-limit assumption.** For fixed \(N,\theta,q\), use \(\Sigma_\eta=(1-\eta)\Sigma+\eta I\succ0\), preserving unit diagonal, actual means and labels. Prove weak convergence of these Gaussian laws, and show that FDP discontinuities lie in the finite union \(\{T_i=z_k\}\). Each marginal remains a nondegenerate \(N(\theta_i,1)\), so this union has probability zero even when several hyperplanes coincide on the singular support. Boundedness of FDP gives convergence of expectations and hence (F) at \(\eta=0\), since its right side does not depend on \(\eta\). No convergence or uniform boundedness of the individual certificate coefficients is asserted or required. The stress tests in step 3 must still check that the proposed uniform budget exists for positive \(\eta\).

7. [ ] **Verify the exact uniform asymptotic quantifiers.** From the elementary Gaussian Mills inequalities prove \(u/\sqrt{2\log(1/q)}\to1\) and \(\log(2+u)=o(\sqrt{\log(1/q)})\). Bound \(\pi_0\leq1\) in (F); its explicit remainder is \(q\{1+64\log(2+u)\}\), uniformly in every model parameter. Choose a single \(q_\varepsilon\) from this scalar bound, independent of \(N,\theta,\Sigma\), and deduce exactly the target. If any preceding coefficient or tail estimate contains an unbounded model-dependent constant in (F), this step cannot proceed.

## Verification

The first gate concerns a finite-coefficient, pointwise transmission problem and can fail independently of the target. Its success is only an entry condition for the full-dimensional construction, not a proof of it. Steps 3--4 must supply the global Gaussian mechanism: cancellation around rank-cell cycles using the same covariance, with a total price logarithmic in \(u\) and no harmonic residue in \(N\).

If CS64 is proved, (I) and (C) yield (S). Nonnegative normal jumps in (T) and zero exterior flux imply \(\mathbb E\operatorname{div}_\gamma^{\rm interior}\mathcal A\leq0\). Each centered null projection has exactly the standard normal marginal, so \(\mathbb E U_u=\pi_0c_u\); this gives (F). Positive-definite approximation then covers every singular covariance. The explicit uniform remainder in (F) proves the exact epsilon statement and leading constant \(1/\sqrt\pi\).

Actual negative means enter the full grid, the Stein kernels and the cell budgets. Their marginal superuniformity is used only in \(B_k\leq\pi_0\). Neither setting all null means to zero nor local monotonicity of total FDR is used. All alternative means and their complete covariance geometry remain in the common rank cells and transmission constraints. There is no null-only FDR-linking reduction and no independent-residual conditional supremum. No result is established merely by writing this plan.

## Assumed definitions

The five model/procedure definitions in the target's approved context are used as definitions: [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary BH step-up](../definitions/benjamini_hochberg_step_up.md), [false discovery rate](../definitions/false_discovery_rate.md), and [uniform worst-case Gaussian BH FDR](../definitions/gaussian_worst_case_bh_fdr.md). No draft definition, unproved asset, or library result is assumed as a theorem. CS64, the scalar Stein formulas, transmission integration, finite-dimensional separation, singular convergence, and Mills asymptotics are explicit proof obligations. The related draft ideas specify obstructions or test families whose relevant algebra must be checked again; they are not black-box dependencies.

## Difference from failed plans

- `plan_gaussian_bh_one_sided_global_corner_budget_20261104`: its dimension-uniform diagonal completion against every PSD correlation matrix is false. This plan introduces a piecewise first-order Gaussian Stein field with fixed scalar basis and pointwise transmission constraints on the actual BH cell graph. It never supports a corner matrix against a second covariance. Any constant-vector correction must pay its box endpoint cost in (C).
- `plan_gaussian_bh_one_sided_fixed_alternative_schur_budget_20261104`: its row and alternative-Gram additive recipe is false, and the later null-block obstruction also prevents treating its general completion as settled. Here the complete model is fixed while Gaussian divergence is integrated; null/alternative and null/null effects share the same coupled face constraints. The old common-block and conservative-null families are mandatory budget stress tests. There is no absolute row allocation or Schur certificate hidden in CS64.
- `plan_gaussian_bh_one_sided_joint_extremum_factor_reduction_20261104`: the exact finite-factor extremality principle was refuted by the fully optimized \(N=3,q=1/64\) comparison recorded in [the audited finite-sample obstruction](../ideas/idea_87b11e1b30f8.md). This plan makes no finite or asymptotic factor replacement. Its one-dimensional function \(M_u\) is a marginal Gaussian budget density, not a claim that the joint covariance has one factor. The negative triangle is a first transmission-feasibility test, and growing-dimensional tests prevent a small-\(N\) budget from being mistaken for a uniform theorem. A failure of CS64 changes neither that audited obstruction nor the original asymptotic conjecture.

## Progress

Execution checkpoint before the gate refutation, 2026-11-04. Checklist item 1 is established below. The subsequent Failure supersedes this checkpoint's open-gate status: CS64 is refuted at item 2. The target asset is unchanged.

### Exact BH count and the zero-rejection cell

Let \(k\) be the largest qualifying rank. If \(k>0\), the count \(d=\#\{i:p_i\leq qk/N\}\) is at least \(k\). If \(d>k\), then \(p_{(d)}\leq qk/N\leq qd/N\), making \(d\) a larger qualifying rank, a contradiction. Thus \(d=k=R\), including multiplicities and weak inequalities. If \(k=0\), \(p_{(1)}>q/N\), so every coordinate exceeds the first grid threshold. Consequently, on every open cell, with \(\kappa=R\vee1\),
$$
\frac1{Nt_\kappa}\sum_{i\in J}\mathbf1_{\{g_i>b_{i\kappa}\}}
=\frac{V}{q\kappa}=\frac{\operatorname{FDP}}q.
\tag{P1}
$$
The first equality also holds when \(R=0\), because both sums are zero. No individual null's forced-zero rank or surrogate p-value has been used.

### Scalar Stein formulas and the exact normalizer

The maximizing location in \(M_u(x)\) is \(0\), \(x\), or \(u\), according as \(x\leq0\), \(0<x<u\), or \(x\geq u\), by completing the square in \(ax-a^2/2\). Hence
$$
\int_{\mathbb R}M_u(x)\phi(x)\,dx
=\frac12+\phi(0)u+\int_u^\infty\phi(x-u)\,dx
=1+\phi(0)u=c_u.
\tag{P2}
$$
For \(x<b\), \((\Phi/\phi)'=1+x\Phi/\phi\), giving \(h_b'-xh_b=-Q(b)\). For \(x>b\), \((Q/\phi)'=-1+xQ/\phi\), giving \(h_b'-xh_b=\Phi(b)=1-Q(b)\). The two values at \(x=b\) agree. Thus \(h_b\) is continuous and locally absolutely continuous, with the stated Stein equation almost everywhere.

The defining numerator of \(\psi_u\) is continuously differentiable. Differentiating it and \(1/\phi\) proves \(\psi_u'-x\psi_u=M_u-c_u\). For later exact evaluation, integration of \(M_u\phi\) gives
$$
\psi_u(x)=\begin{cases}
(1-c_u)\Phi(x)/\phi(x),&x\leq0,\\
\{1/2+\phi(0)x-c_u\Phi(x)\}/\phi(x),&0\leq x\leq u,\\
\{c_uQ(x)-Q(x-u)\}/\phi(x),&x\geq u.
\end{cases}
\tag{P3}
$$
The formulas agree at \(0,u\) by \(c_u=1+\phi(0)u\). These are identities, not numerical approximations.

### Interior divergence and the orientation of transmission

Each \(v_i\) has norm one and \(\nabla_Z g_i=v_i\). Thus
$$
\operatorname{div}_\gamma\{v_i f(g_i)\}
=f'(g_i)-g_if(g_i).
$$
For a constant vector \(\sum_j\alpha_{Cj}v_j\), the Gaussian divergence is \(-\sum_j\alpha_{Cj}g_j\). Substitution of the two scalar Stein equations and (P1) proves (I) exactly on each cell. Since every \(\theta_i\leq0\) for \(i\in J\), \(b_{ik}\geq z_k\); decreasingness of \(Q\) gives \(0\leq B_k\leq |J|/N\), without moving any mean.

For a face in coordinate \(j\), the latent hyperplane has unit normal \(v_j\), oriented from \(C^-\) to \(C^+\). Taking \((\mathcal A_{C^+}-\mathcal A_{C^-})^\mathsf Tv_j\) yields exactly the left side of (T), since \(v_i^\mathsf Tv_j=\rho_{ji}\). Write this normal jump as \(a_F\). With any smooth compactly supported cutoff \(\chi\), cellwise Gaussian integration by parts gives
$$
\sum_C\int_C\chi\,\operatorname{div}_\gamma\mathcal A_C\,d\gamma_N
=-\int \mathcal A^\mathsf T\nabla\chi\,d\gamma_N
-\sum_F\int_F\chi\,a_F\,\phi_N\,d\mathcal H^{N-1}.
\tag{P4}
$$
On an internal face, the two outward normals are \(v_j,-v_j\); their sum is \((\mathcal A_{C^-}-\mathcal A_{C^+})^\mathsf Tv_j=-a_F\), proving the sign. The positive-definite Gram representation is invertible, so distinct coordinate faces meet in codimension at least two and contribute no further surface term. Thus (T) makes the face term on the right of (P4) nonpositive. Removing the cutoff requires the integrability estimates in item 5; no unproved exterior-boundary limit is used here.

### Independent verification of the one-coordinate normalization

For \(N=1\), \(\kappa_C=1\) on both grid cells, regardless of whether \(R_C=0\) or \(1\). If \(\theta_1\leq0\), take \(\alpha=\beta=0\) on both cells. Their fields are identical, so the single normal jump is zero. The budget is \(B_1=Q(u-\theta_1)/q\leq1<64\log(2+u)\) for \(u\geq1\). For a centered null it is exactly \(B_1=1\). If \(\theta_1>0\), \(J\) is empty and the zero field with zero budget works. This proves feasibility in \(N=1\) and rules out an alleged one-coordinate obstruction for the present basis; it does not settle the required \(N=2,3\) gate.

## Failure

Execution on 2026-11-04 refutes CS64 at checklist item 2. The obstruction below uses an admissible positive-definite two-coordinate model, three cells, two face inequalities, and the cell budgets. It proves that every certificate in the fixed ansatz would require a budget
$$
D>\frac{2159}{16}=134.9375,
$$
whereas CS64 prescribes \(D=64\log6<128\). This is an analytic separation certificate, not a numerical FDR comparison or an infeasible-grid inference. The target statement and asset are untouched. The original asymptotic FDR conjecture is not refuted. Items 3--7 cannot complete this plan because their required coefficient lemma is false.

### Admissible model and the three actual BH cells

Take
$$
N=2,\qquad \theta=(0,1),\qquad
\Sigma=\begin{pmatrix}1&-r\\-r&1\end{pmatrix},
\qquad r=\frac9{10},\qquad q=Q(4).
\tag{F1}
$$
The covariance has eigenvalues \(1-r=1/10\) and \(1+r=19/10\), so is positive definite and has unit diagonal. The actual null set is \(J=\{1\}\). Put
$$
u=4,\quad v=Q^{-1}(q/2),\quad U=u-1=3,\quad V=v-1,\quad
c=1+4\phi(0).
$$
The grid thresholds in \(g_1\) are \(u,v\) and in \(g_2\) are \(U,V\). Consider precisely the three cells
$$
C_{AB}=(-\infty,u)\times(U,V),\qquad
C_{BA}=(u,v)\times(-\infty,U),\qquad
C_{BB}=(u,v)\times(U,V).
\tag{F2}
$$
In \(C_{AB}\), the first p-value is above \(q\) and the second is strictly between \(q/2\) and \(q\); hence no rank qualifies. The same holds with the coordinates interchanged in \(C_{BA}\). Thus both cells have \(R=0,\ \kappa=1\). In \(C_{BB}\), both p-values are between \(q/2\) and \(q\), so \(R=\kappa=2\). This uses the complete BH rule, rather than testing a single candidate rank. Since the only null is centered,
$$
B_1=B_2=\frac12.
\tag{F3}
$$

Denote the constant-vector coefficients in these three cells by \(a,b,d\in\mathbb R^2\), respectively, and the corresponding null coefficients by \(\beta_a,\beta_b,\beta_d\in[0,1]\). A finite cell budget forces
$$
a_1\geq0,\qquad b_2\geq0,
\tag{F4}
$$
because otherwise \(\sup a_1g_1\) or \(\sup b_2g_2\) is infinite at the negative unbounded endpoint. The cell budget, evaluated at finite boundary limits \((0,V)\), \((v,0)\), and \((u,U)\), gives
$$
Va_2\leq D-\tfrac12+\tfrac c2\beta_a,\qquad
vb_1\leq D-\tfrac12+\tfrac c2\beta_b,\qquad
ud_1+Ud_2\leq D-\tfrac12+\tfrac c2\beta_d.
\tag{F5}
$$
Here \(0<u\) and \(0<U\), so the zero coordinates are inside the relevant lower intervals; the other coordinates are obtained by limits from the open cells. These inequalities do not assume that any right-hand side is positive.

Write
$$
w_1(x)=x_1-rx_2,\qquad w_2(x)=x_2-rx_1,\qquad
P_u=-\psi_u(u),\quad P_v=-\psi_u(v),\quad
d_v=\frac1{2\phi(v)}.
$$
From (F4)--(F5), since \(r,V,v>0\),
$$
w_1(a)\geq-\frac rV\left(D-\tfrac12+\tfrac c2\beta_a\right),
\qquad
w_2(b)\geq-\frac rv\left(D-\tfrac12+\tfrac c2\beta_b\right).
\tag{F6}
$$

### Exact face orientation and elimination of the constant vectors

The \(g_1=u\) face is oriented from \(C_{AB}\) to \(C_{BB}\). The centered null's own normalized Stein terms coincide there:
$$
\frac{h_u(u)}q=\frac{h_v(u)}{q/2}
=-\frac{\Phi(u)}{\phi(u)}.
$$
Thus (T), including its factor \(1/N=1/2\), is exactly
$$
w_1(d)\geq w_1(a)-\frac{P_u}{2}(\beta_d-\beta_a).
\tag{F7}
$$
The \(g_2=U\) face is oriented from \(C_{BA}\) to \(C_{BB}\). Taking \(g_1\uparrow v\) on that face,
$$
\frac{h_u(v)}q-\frac{h_v(v)}{q/2}
=\frac{\Phi(v)-\Phi(u)/2}{\phi(v)}
=\frac1{2\phi(v)}=d_v.
$$
All scalar functions are continuous, so a transmission inequality valid on the open face remains valid in this finite endpoint limit. Its normal correlation with the null is \(\rho_{21}=-r\), giving
$$
w_2(d)\geq w_2(b)+\frac r2d_v
+\frac{rP_v}{2}(\beta_d-\beta_b).
\tag{F8}
$$
In particular, the sign of the \(rP_v\) term is positive on the right of (F8); this is the harmful negative-correlation face.

Choose the positive rational multipliers
$$
\lambda=\frac{670}{19},\qquad \eta=\frac{660}{19}.
$$
They satisfy \(\lambda-r\eta=u=4\) and \(\eta-r\lambda=U=3\), whence
$$
\lambda w_1(d)+\eta w_2(d)=ud_1+Ud_2.
$$
Multiply (F7),(F8) by \(\lambda,\eta\), substitute (F6), and use the last inequality in (F5). With
$$
A=1+\frac{\lambda r}V+\frac{\eta r}v,
$$
the resulting necessary condition is
$$
A(D-\tfrac12)\geq
\frac{\eta r}{2}d_v
-C_{BB}\beta_d-C_{AB}\beta_a-C_{BA}\beta_b,
\tag{F9}
$$
where
$$
C_{BB}=\frac{c+\lambda P_u-\eta rP_v}{2},\qquad
C_{AB}=\frac{\lambda(rc/V-P_u)}{2},\qquad
C_{BA}=\frac{\eta r(c/v+P_v)}{2}.
\tag{F10}
$$
This derivation permits all three vectors and all three coefficients to be otherwise arbitrary. The remaining cells cannot repair a violation of this necessary subsystem.

### Elementary rigorous bounds on the quantile and scalar coefficients

For \(x>0\), integration by parts gives the strict Mills bounds
$$
\frac{x}{1+x^2}\phi(x)<Q(x)<\frac{\phi(x)}x.
\tag{F11}
$$
For the upper bound integrate \(t\phi(t)/x\) on \([x,\infty)\). For the lower bound, use \(Q(x)=\phi(x)/x-\int_x^\infty\phi(t)/t^2\,dt>\phi(x)/x-Q(x)/x^2\).

The rational exponential bounds \(e^{81/200}<3/2\) and \(e^{41/50}>9/4\), justified below, imply
$$
\frac{Q(41/10)}{Q(4)}
>\frac{1640}{1781}e^{-81/200}
>\frac{3280}{5343}>\frac12,
$$
$$
\frac{Q(21/5)}{Q(4)}
<\frac{85}{84}e^{-41/50}
<\frac{85}{189}<\frac12.
$$
Therefore
$$
\frac{41}{10}<v<\frac{21}{5},\qquad
\frac1{10}<v-u<\frac15,\qquad V>\frac{31}{10}.
\tag{F12}
$$
Only the elementary bounds \(3<\pi<4\) are needed below. They imply \(1/3<\phi(0)<5/12\), and hence \(c<3\). The bound \(e^8>2500\) gives
$$
\phi(4)=\phi(0)e^{-8}<\frac1{6000},
\qquad 0<q<\frac1{24000}.
\tag{F13}
$$
Also \(\phi(1/5)>(1/3)e^{-1/50}>(1/3)(49/50)>3/10\). With \(w=v-u\in(1/10,1/5)\),
$$
Q(w)>\frac12-\frac15\phi(0)>\frac5{12}.
$$
Formula (P3) at \(u\) and \(v>u\) gives the exact expressions
$$
P_u=\frac{1/2-cq}{\phi(4)},\qquad
P_v=\frac{Q(w)-cq/2}{\phi(v)}.
\tag{F14}
$$
Since \(cq<1/8000\), these imply
$$
\frac{49}{100\phi(4)}<P_u<\frac1{2\phi(4)},\qquad
P_v>\frac{39}{100\phi(v)}>0.
\tag{F15}
$$
Furthermore,
$$
\frac{\phi(4)}{\phi(v)}
=e^{(v^2-16)/2}>e^{81/200}>\frac{149}{100}.
\tag{F16}
$$
Using \(\eta r>31,\ \lambda<36\), (F15)--(F16) give
$$
\eta rP_v-\lambda P_u
>\frac{31(39/100)(149/100)-18}{\phi(4)}
=\frac{141}{10000\phi(4)}
>\frac{423}{5}>c.
$$
Consequently \(C_{BB}<0\). Also \(rc/V<1\), whereas \(P_u>2940\), so \(C_{AB}<0\). Finally \(C_{BA}>0\).

The same formulas yield a lower bound without subtracting two large approximate values:
$$
d_v-P_v
=\frac{1/2-Q(w)+cq/2}{\phi(v)}
>\frac{\int_0^w\phi(s)\,ds}{\phi(v)}
>\frac{(1/10)(3/10)}{\phi(v)}
>180.
\tag{F17}
$$
Here \(\phi(v)<\phi(4)<1/6000\). Moreover \(c/v<3/4\), \(\eta r/2>15\), and
$$
0<A<1+\frac{320}{31}+\frac{320}{41}
=\frac{24311}{1271}<20.
\tag{F18}
$$
The bounds on \(A\) use \(\lambda r=603/19<32,\ \eta r=594/19<32\).

For completeness, every exponential estimate used here has a finite rational Taylor certificate. Write \(S_m(t)=\sum_{k=0}^m t^k/k!\). For \(t=81/200\), the positive tail after \(S_5(t)\) is at most \(t^6/[6!(1-t/7)]\), by bounding successive term ratios by \(t/7\). Exact arithmetic gives
$$
S_5(t)+\frac{t^6}{6!(1-t/7)}
=\frac{50626048038633209}{33766400000000000}<\frac32,\qquad
S_3(t)=\frac{23969347}{16000000}>\frac{149}{100}.
$$
Likewise
$$
S_4(41/50)=\frac{340039961}{150000000}>\frac94,\qquad
S_{11}(8)=\frac{412782941}{155925}>2500.
$$
Thus (F12)--(F18) use rigorous analytic bounds. A short local standard-library rational-arithmetic check reproduced these displayed fractions and comparisons; no floating-point quadrature, simulation, or optimization supplies the proof.

### Contradiction to CS64 and exact scope of failure

In (F9), use \(C_{BB}<0,\ C_{AB}<0,\ C_{BA}>0\) and \(0\leq\beta_a,\beta_b,\beta_d\leq1\). The right side is at least
$$
\frac{\eta r}{2}d_v-C_{BA}
=\frac{\eta r}{2}(d_v-P_v-c/v).
$$
Together with (F17)--(F18), this forces
$$
D\geq\frac12+\frac{\eta r}{2A}(d_v-P_v-c/v)
>\frac12+\frac34(180-\tfrac34)
=\frac{2159}{16}>128.
\tag{F19}
$$
But CS64 at \(u=4\) requires \(D=64\log(2+u)=64\log6<128\): the latter follows from \(e^2>S_3(2)=19/3>6\). This contradiction already occurs in the positive-definite model (F1), so no singular endpoint, mean compactification, or dimension-growth argument is involved.

The obstruction is specifically the simultaneous pointwise transmission and box-budget conditions of the fixed Stein ansatz. Its underlying scalar Stein identities, normalizer, full-rank identity, and face orientation remain valid as proved in Progress. No conclusion about the truth of the original FDR statement follows. The finite result here also does not assert that every possible constant in front of \(\log(2+u)\) is impossible; only the prescribed CS64 has been refuted. The plan's instruction to stop at an exact low-dimensional infeasibility certificate therefore applies.

For follow-up planning, the separately recorded draft observation [Two-coordinate Gaussian cells require exponentially large pointwise Stein budgets](../ideas/idea_e982856cc8fe.md) contains a stronger asymptotic obstruction for this same ansatz. That strengthening is not used in the finite proof above. A replacement plan must inspect that record before proposing merely to change 64.
