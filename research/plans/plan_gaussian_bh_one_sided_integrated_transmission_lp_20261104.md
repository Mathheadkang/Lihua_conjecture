---
type: plan
status: failed
title: Gaussian-integrated transmission as a finite moment linear program
target_asset: gaussian_bh_one_sided_sharp_upper
inspired_by:
  - idea_a3dc57228d9e
  - idea_1901b57ddc7f
  - idea_e982856cc8fe
  - idea_e4665976e501
  - idea_4d8d1d50b0a1
  - idea_51b5a4fb20f2
tags: [gaussian-bh, integrated-flux, finite-linear-program, truncated-gaussian-moments]
---

## Goal

Target: [Sharp uniform upper-bound target for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_sharp_upper.md).

Test a genuinely different sufficient certificate: keep the fixed cellwise Stein field and pointwise cell budget, but replace each face's pointwise normal-jump constraint by its exact Gaussian surface integral. The resulting explicit finite linear program is stronger than a bound on its total flux and may fail even when the target is true. Its first mandatory gate is the complete two-coordinate system in the PRESPECIFIED small-level range u>=u_0=10, not two selected faces. This fixed cutoff is chosen before execution because the frozen target is only a q->0 assertion; it must not be increased after a failed gate. The old u=4 model remains an informative diagnostic outside the claimed range. No conclusion about feasibility is assumed.

The fresh pack lists four failed plans and no pending plan. Its library analogues contain no applicable result. Native library searches for `Gaussian integrated transmission finite linear programming Farkas truncated moments`, `Gaussian BH signed flux active rank face`, and `Gaussian bivariate kernel rank telescoping Stein` returned no matches. No library result or unapproved idea is invoked as a black box. Local Stein and finite-duality facts below must be proved in execution. Only this new plan is written; target, definitions, approvals and loop state are unchanged.

## Explicit proposed certificate

All notation in this section is local. Fix q in (0,Q(10)], u=Q^{-1}(q)>=u_0=10, and a finite positive-definite Gaussian model with actual null set J={i:theta_i<=0}. Put t_k=qk/N, z_k=Q^{-1}(t_k), b_ik=z_k-theta_i, pi_0=|J|/N. Represent G_i=v_i^T Z with Z standard Gaussian in R^N, ||v_i||=1, and v_i^Tv_j=rho_ij=Sigma_ij. Work with the complete grid G_i=b_ik, all (N+1)^N open observation boxes C, their actual largest BH count R_C, and kappa_C=R_C vee1. No forced-zero rank is substituted for this common rank.

Define

$$
M_u(x)=\sup_{0\le a\le u}e^{ax-a^2/2},\quad
c_u=1+u/\sqrt{2\pi},\quad D_u=64\log(2+u),
$$

$$
h_b(x)=-\begin{cases}Q(b)\Phi(x)/\phi(x),&x\le b,\\ \Phi(b)Q(x)/\phi(x),&x\ge b,\end{cases}
\qquad
\psi_u(x)=\phi(x)^{-1}\int_{-\infty}^x(M_u(s)-c_u)\phi(s)\,ds.
$$

For each C choose finite alpha_Cj in R and beta_Ci in [0,1], and set

$$
\mathcal A_C(Z)=\frac1N\sum_{i\in J}v_i\left\{
\frac{h_{b_{i\kappa_C}}(G_i)}{t_{\kappa_C}}-\beta_{Ci}\psi_u(G_i)\right\}
+\sum_j\alpha_{Cj}v_j. \tag{A}
$$

Let B_k=(Nt_k)^{-1}sum_{i in J}Q(b_ik), U_u(G)=N^{-1}sum_{i in J}M_u(G_i). Retain the EXACT pointwise box budget

$$
B_{\kappa_C}-\frac{c_u}N\sum_{i\in J}\beta_{Ci}
+\sum_j\sigma_{I_{Cj}}(\alpha_{Cj})\le D_u,
\qquad \sigma_I(a)=\sup_{x\in I}ax. \tag{C}
$$

Infinite endpoints constrain alpha's sign: for I=(-infinity,r), alpha>=0 and sigma=r alpha; for I=(l,infinity), alpha<=0 and sigma=l alpha. For a bounded interval sigma=max(l alpha,r alpha). Linearize the latter with an auxiliary variable >=both endpoint values; it may be negative. Never omit an infinite-endpoint sign restriction.

For a face F=C^-|C^+ at G_j=b, orient the LATENT unit normal as n_F=v_j. Define

$$
m_F=\int_F\phi_N(Z)\,d\mathcal H^{N-1}(Z)
=\phi(b)P\{G_{-j}\in I_{F,-j}\mid G_j=b\}>0.
$$

This uses ||v_j||=1 and Gaussian coarea. A Euclidean observation-coordinate normal must not be substituted without the corresponding Jacobian. Define the normalized exact face moments

$$
H_{Fi}^{k}=E\left[\frac{h_{b_{ik}}(G_i)}{t_k}\ \middle|\ G_j=b,\ G_{-j}\in I_{F,-j}\right],
\qquad
P_{Fi}=E[\psi_u(G_i)\mid G_j=b,\ G_{-j}\in I_{F,-j}],
$$

$$
K_F=\frac1N\sum_{i\in J}\rho_{ji}(H_{Fi}^{\kappa_+}-H_{Fi}^{\kappa_-}).
$$

The proposed integrated transmission constraint is

$$
K_F+\sum_l\rho_{jl}(\alpha_{C^+l}-\alpha_{C^-l})
-\frac1N\sum_{i\in J}\rho_{ji}P_{Fi}(\beta_{C^+i}-\beta_{C^-i})\ge0. \tag{IT}
$$

Multiplication by m_F recovers exactly integral_F <n_F,A_plus-A_minus> phi_N dH>=0. Dividing by the strictly positive m_F changes neither that constraint nor the actual conditional measure inside H,P; it is NOT pointwise replacement by a favorable face point. All signs of rho, all actual means, all full-grid cells, and all truncated moments remain present.

**Candidate IT64 lemma (unproved):** for every displayed positive-definite model, finite coefficients satisfy (C),(IT). Failure of any fixed admissible full system with u>=10 stops this plan; failures at diagnostic u<10 do not contradict this prespecified lemma. Neither IT64 nor its dual formulation below is a known theorem.

## Concrete finite dual to derive and test

Introduce lambda_C>=0 for (C), mu_F>=0 for (IT), and the incidence epsilon_CF=+1 for C=C^+, -1 for C=C^- (zero otherwise). Put

$$
w_{Cl}=\sum_F\epsilon_{CF}\mu_F\rho_{j(F)l},\qquad
s_{Ci}=\frac1N\left\{-c_u\lambda_C+
\sum_F\epsilon_{CF}\mu_F\rho_{j(F)i}P_{Fi}\right\}. \tag{D1}
$$

Elimination of alpha via the interval support functions requires the cell-moment cone conditions

$$
\begin{cases}
\lambda_C l\le w_{Cl}\le\lambda_C r,&I_{Cl}=(l,r),\\
w_{Cl}\le\lambda_C r,&I_{Cl}=(-\infty,r),\\
w_{Cl}\ge\lambda_C l,&I_{Cl}=(l,\infty).
\end{cases} \tag{D2}
$$

These formulas INCLUDE lambda_C=0; in an unbounded interval w may then be a recession direction rather than zero. Eliminating beta in [0,1] yields min(0,s_Ci). Thus the explicit candidate Farkas test for feasibility at D_u is

$$
\sum_C\lambda_C(B_{\kappa_C}-D_u)
-\sum_F\mu_F K_F
+\sum_{C,i\in J}\min(0,s_{Ci})\le0 \tag{DB}
$$

for every nonnegative lambda,mu obeying (D2). Execution MUST derive the signs and the exact necessary-and-sufficient Farkas statement rather than trust this displayed candidate. In particular include infeasibility rays with sum lambda=0; normalizing sum lambda=1 alone would miss them. A convenient compact normalization for a nonzero ray is sum lambda+sum mu=1 after the beta-box multipliers have been handled.

The new mathematical obligation is a Gaussian TRUNCATED-MOMENT/CELL-MOMENT estimate proving (DB) for all such dual weights at the GENERATING covariance. It cannot be replaced by existence of an unspecified Gaussian flow, a bound on unweighted/absolute negative flux, an unrestricted PSD support supremum, or the target FDR itself. If no usable signed rank/Gram cancellation is established, execution must report failure or a genuine partial checkpoint rather than call (DB) proved.

## Plan

1. [x] **Derive the identities and the exact finite LP before a feasibility claim.** Prove R equals the largest qualifying rank including ties, with kappa=1 in R=0 cells; derive div_gamma A_C=FDP_C/q-B_kappa-N^{-1}sum beta(M_u-c_u)-sum alpha G. Verify h_b'-xh_b=1{x>b}-Q(b), psi_u'-xpsi_u=M_u-c_u, and E M_u=c_u. Derive m_F and (IT) with the unit normal v_j. Show all fixed-model face moments finite and all cells/faces finite. Write every LP row including endpoint signs and beta bounds, then derive (D1)--(DB) from finite-dimensional separation/Farkas, proving the elementary separation statement if it is not an allowed dependency. No source result absent from target dependencies is used as a black box.

2. [ ] **First substantive gate: solve ALL nine cells and twelve faces of N=2.** Use theta=(0,1), rho_12=-9/10, q=Q(4) only as an out-of-range diagnostic; the mandatory first gate is q=Q(10), followed by the same family q=Q(u) as u tends to infinity. Also test r=r(u)->1, rather than allowing a fixed-r asymptotic to hide a nonuniform singular-correlation obstruction. Keep u_0=10 fixed. Compute each cell's TRUE BH rank and every face's one-dimensional conditional truncated Gaussian integrals, including the unbounded faces. Provide either actual alpha,beta with certified moment inequalities for the complete system or a certified finite dual obstruction violating the derived Farkas test. Short deterministic floating-point LPs are discovery aids only; rational/analytic enclosures or verified strict margins must support the conclusion. At a zero-slack equality give exact algebra rather than an ambiguous interval crossing zero. Do not conflate success on two faces with feasibility of the full twelve-face system.

   As a diagnostic that must itself be checked, the old three-cell endpoint obstruction no longer directly applies. Write v=Q^{-1}(q/2), U=u-1, and on the middle face G_2=U, G_1 in (u,v) set d(x)=h_u(x)/q-h_v(x)/(q/2)>=0. Its integrated beta capacity uses E[d(X)]/E[-psi_u(X)], where X~N(-rU,1-r^2) truncated to (u,v). For fixed r in (0,1), y=u(X-u) ranges asymptotically over (0,log2), with truncated density proportional to exp[-a y], a=1/(1-r). The candidate ratio limit is 2[1-I_a/I_{a-1}], I_c=int_0^{log2} exp(-cy)dy (I_0=log2), which is <1; r=.9 gives approximately .198. This is only a two-face capacity check and supplies no coefficients for the other faces. As another diagnostic, with x/y intervals A=(-infinity,u or U), B=(u or U,v or V), C=(v or V,infinity), the complete rank matrix is kappa=(1,1,1;1,2,2;1,2,2). With alpha=0, beta zero except beta_BA=r_B and beta_CA=max(r_B,r_C) satisfies all twelve integrated faces provided the two exact middle/high tail ratios r_B,r_C lie in [0,1]. Here r_B uses X in (u,v), and r_C uses X in (v,infinity), both conditional on G_2=U. This sufficiency must be rechecked in execution, not assumed. A short uncertified standard-library quadrature diagnostic gave r_B approximately .2383 and r_C approximately 1.0378 at u=4,r=.9, so the proposed beta-only choice does NOT settle the first finite gate; alpha corrections or a genuine full-LP obstruction remain necessary. The high-tail ratio has candidate limit (a-1)/a=r<1 as u tends to infinity: the numerator integrates exp(-a y), while the denominator integrates exp[-(a-1)y] because the Stein denominator carries the reciprocal-Gaussian-density factor. This asymptotic must be proved, and alone is not a certificate for finite u. If the full LP fails at any u>=10, stop and record which integrated cycle forces it; keep 64, u_0=10 and the field class fixed. A u=4 failure is recorded as an out-of-range diagnostic, not as failure of the asymptotic certificate.

3. [ ] **Test dimension and singular-boundary obstructions before a general lemma.** Derive symbolic feasible coefficients or certified dual failures for N=3 at q=Q(10) and smaller levels with centered negative-triangle covariance and all label patterns needed for the mixed-mean family (q=1/64 can be kept only as an out-of-range comparison); centered iid nulls; positive-definite regularizations of the all-null simplex; the exact one-null harmonic staircase with conservative clones; and the failed fixed-alternative/common-alternative-block constructions. Include any newly verified critical one-factor example with large opposing fluxes. Every computation retains the full masks and signed moments; the sum of negative-rho fluxes is NOT assumed O(u). Check limits as N grows and regularization eta tends to0. A required budget growing faster than log(2+u), including a hidden logN, rejects IT64 even if actual FDR is small. Heavy numerical work, if needed and authorized, belongs on UC Davis in an isolated directory with at most two CPU processes; do not bypass any prior export approval denial.

4. [ ] **Establish an explicit signed Gaussian moment/Gram identity or stop.** First reprove the concrete normal-tube counting tool in the draft observation [the low-count Gaussian perimeter bound](../ideas/idea_51b5a4fb20f2.md): for unit normals n_j and offsets b_j<=B, the Gaussian reduced-boundary area of {x:#{j:n_j dot x>b_j}<=k} is at most (k+1)phi(B)/Q(B). Give the complete ray argument: for y in L normal tubes choose the smallest positive source distance t_j; each other source gives the strict violation t_i-t_j(n_i dot n_j)>0 at its source, so L<=k+1. Integrate over the whole space, allowing rays to reenter the nonconvex set, and handle ties/degenerate coincident hyperplanes. This is a noncircular geometric lemma but is NOT an approved dependency and must be reproved here. For alternatives at a fixed threshold z_s their offsets z_s-theta_j<=z_s permit its application. Actual negative-mean null offsets do not obey that bound; do not erase those coordinates or condition on them without recomputing norms and offsets. Then, for dual weights satisfying (D2), rewrite -sum mu K+sum min(0,s) using the actual Gaussian conditional box integrals and the active-face count structure. Explicitly determine whether the moment-cone restrictions yield a WEIGHTED normal-tube multiplicity inequality charging arbitrary mu_F to lambda_C. An unweighted fixed-rank perimeter bound cannot be summed over all s: a surviving logN or missing cross-rank multiplicity is an obstruction, not a proof. Prove, rather than assume, a rank/covariance telescoping formula that charges its positive part to D_u sum lambda minus sum lambda B. The one-active-face identity may reduce redundant rank transitions, but the other coordinates remain integrated over the actual box. For centered nulls verify the useful exact kernel H_s(x)-H_r(x)=[Q(x)/phi(x)]int_{t_r}^{t_s}1{Q(x)<t}dt/t^2 with H_k=h_{z_k}/t_k and r=R_0 vee1; use it only where theta_i=0. Actual negative null means must remain in h_{b_ik} and B_k throughout the proof; no zero-mean least-favorable reduction is available. If using Gram positivity, display the vectors/quadratic form at this Sigma and show the coefficients have the needed signs. A model-dependent or dimension-dependent hidden constant does not prove (DB). A failure here is a failed certificate plan, not a refutation of the target.

5. [ ] **Deduce the scalar bound from a proved IT64 lemma, with full integrability.** From (C), beta in [0,1] and M_u>=0, derive FDP/q<=div_gamma A_C+D_u+U_u pointwise inside each cell. Integrate with a smooth compactly supported cutoff and then remove it. For each fixed finite model the finite h_b/t terms, the constant coefficients, and psi_u=O_u(1+exp(u|x|)) are Gaussian integrable, so exterior cutoff terms vanish. The exact sum of interior divergence integrals is minus the sum of the Gaussian face integrals. Apply (IT) only AFTER integration; never strengthen it to a pointwise face claim. Obtain FDR<=q[pi_0(1+u/sqrt(2pi))+64log(2+u)]. No proof step may use an unknown FDR value to select coefficients.

6. [ ] **Pass to all PSD models and the uniform sharp limit.** For each fixed finite singular covariance use Sigma_eta=(1-eta)Sigma+eta I, preserving actual means/labels and diagonal1. Each marginal is continuous, and FDP discontinuities lie in the finite union T_i=z_k, so weak convergence gives convergence of FDR. The scalar bound is uniform in eta and therefore passes to the limit without any convergence of alpha,beta. Derive u/sqrt(2log(1/q))->1 from Mills bounds and log(2+u)=o(sqrt(log(1/q))); pi_0<=1 then gives exactly the frozen uniform target, with q_epsilon independent of every model parameter.

## Progress

Execution on 2026-11-04 establishes checklist item 1 and an analytic infeasibility certificate at item 2. No target proof is claimed. The argument below uses no simulated FDR, numerical quadrature, floating-point feasibility verdict, or external theorem as an unproved dependency.

### Exact Stein and BH identities

Write \(\phi_0=\phi(0)\). Splitting the integral at \(0,u\), the three contributions to \(\mathbb E M_u(G)\) are \(1/2,u\phi_0,1/2\); hence \(\mathbb E M_u=c_u\). Direct integration gives
$$
\psi_u(x)=
\begin{cases}
(1-c_u)\Phi(x)/\phi(x),&x\le0,\\
\{1/2+x\phi_0-c_u\Phi(x)\}/\phi(x),&0\le x\le u,\\
\{c_uQ(x)-Q(x-u)\}/\phi(x),&x\ge u.
\end{cases}
\tag{P1}
$$
The joining values agree. Differentiating, using \(\phi'=-x\phi\), proves \(\psi_u'-x\psi_u=M_u-c_u\). The same differentiation of the two defining branches proves \(h_b'-xh_b=\mathbf1_{\{x>b\}}-Q(b)\), with equal traces at \(b\). For each fixed \(b\), \(h_b\) is bounded: its continuous branches tend to zero at their respective infinite endpoints by the elementary Mills bounds. Formula (P1) gives \(|\psi_u(x)|\le C_u(1+e^{u|x|})\) for fixed \(u\). On the positive tail use \(Q(x-u)/\phi(x)\le e^{ux-u^2/2}/(x-u)\) for \(x\ge u+1\), and use continuity on the remaining bounded interval.

Let \(K\) be the largest qualifying BH rank. If \(K>0\) but \(r>K\) p-values were at most \(qK/N\), then \(p_{(r)}\le qK/N\le qr/N\), contradicting maximality. Thus the rejection count is exactly \(K\), including ties. If \(R=0\), every p-value exceeds \(q/N\), since otherwise rank one qualifies. Consequently, in every open grid cell, including zero-rejection cells with \(\kappa=1\),
$$
\frac1{Nt_\kappa}\sum_{i\in J}\mathbf1_{\{G_i>b_{i\kappa}\}}
=\frac{\operatorname{FDP}_C}{q}.
\tag{P2}
$$
Since \(\|v_i\|=1\), the Gaussian divergence of \(v_if(G_i)\) is \(f'(G_i)-G_if(G_i)\), and the divergence of \(\sum_j\alpha_jv_j\) is \(-\sum_j\alpha_jG_j\). Combining these facts proves exactly the divergence identity in item 1.

For positive-definite \(\Sigma\), the observation-coordinate grid has finitely many nonempty boxes and faces, and the \(j\)-th latent face normal is the UNIT vector \(v_j\). Disintegration in this unit direction gives \(m_F=\phi(b)\mathbb P(G_{-j}\in I_{F,-j}\mid G_j=b)>0\). All face moments are finite: \(h_b\) is bounded and the exponential growth in (P1) is integrable under every fixed conditional Gaussian law; restricting to a positive-probability box and dividing by that probability preserves finiteness. Integrating the exact normal jump, then dividing by \(m_F\), proves (IT) with precisely its stated signs and conditional moments.

### Finite LP and its exact dual

For every cell and bounded coordinate interval \((l,r)\), introduce a real epigraph variable \(z_{Cj}\) and the two rows \(z_{Cj}\ge l\alpha_{Cj}\), \(z_{Cj}\ge r\alpha_{Cj}\). For an upper-unbounded interval impose \(\alpha_{Cj}\le0\) and put \(z_{Cj}=l\alpha_{Cj}\); for a lower-unbounded interval impose \(\alpha_{Cj}\ge0\) and put \(z_{Cj}=r\alpha_{Cj}\). Add the cell row \(B_\kappa-c_u\sum_i\beta_{Ci}/N+\sum_jz_{Cj}\le D\), every row (IT), and both bounds on every beta. These are all the rows of a finite linear feasibility problem. The epigraph formulation is equivalent to the support-function budget, because at feasibility each epigraph variable may be reduced to its endpoint maximum.

With nonnegative cell multipliers \(\lambda_C\) and face multipliers \(\mu_F\), its Lagrangian before eliminating alpha and beta is
$$
\sum_C\lambda_C(B_\kappa-D)-\sum_F\mu_FK_F
+\sum_{C,j}\{\lambda_C\sigma_{I_{Cj}}(\alpha_{Cj})-w_{Cj}\alpha_{Cj}\}
+\sum_{C,i}s_{Ci}\beta_{Ci},
\tag{P3}
$$
where \(w,s\) are exactly (D1). Minimization over alpha, retaining its required endpoint sign domain even when \(\lambda_C=0\), is finite precisely under (D2); the minimum is then zero. For example, in \((-\infty,r)\) it is \(\inf_{\alpha\ge0}(\lambda_Cr-w)\alpha\), finite exactly when \(w\le\lambda_Cr\). In a bounded interval it is finite exactly for \(\lambda_Cl\le w\le\lambda_Cr\). The lower-bounded case is analogous. Minimization over each beta in \([0,1]\) gives \(\min(0,s_{Ci})\). Thus (DB) is necessary.

It is also sufficient. Here is the finite alternative needed for that conclusion. Eliminate one real variable from finitely many linear inequalities by splitting its coefficients into positive, negative and zero classes, retaining zero-coefficient rows and combining each positive/negative pair with nonnegative multipliers to cancel that variable. The resulting lower-versus-upper-bound comparisons describe the projection exactly; if either class is empty there is no bound in the missing direction. Repeating eliminates every variable. Infeasibility is equivalent to one final false scalar inequality, and tracing its construction gives a nonnegative combination of original rows with zero variable coefficients and a false scalar right side. Conversely any such combination contradicts feasibility. Applying this elimination alternative to the explicit epigraph LP gives its separating multipliers. Eliminating its endpoint and beta-bound multipliers by the minimizations in (P3) gives exactly (D2),(DB). Hence infeasibility produces a STRICT violation of (DB); no rays with \(\sum_C\lambda_C=0\) are omitted. This proves the proposed dual signs rather than assuming them.

## Failure

IT64 is false already in its prespecified core range at checklist item 2. A fixed positive-definite TWO-coordinate model forces \(D>284\), whereas the prescribed budget is \(D=64\log12<192\). The contradiction below uses a subsystem of the COMPLETE nine-cell/twelve-face LP; therefore adding its remaining rows cannot repair it. The target statement and asset are unchanged, and the original Gaussian BH conjecture is not refuted.

### Model and complete grid

Take
$$
u=10,\quad q=Q(10),\quad
r=\frac{999999}{1000000},\quad
\theta=(0,1),\quad
\Sigma=\begin{pmatrix}1&-r\\-r&1\end{pmatrix}.
\tag{F1}
$$
Its eigenvalues \(1-r,1+r\) are strictly positive. The actual null set is \(J=\{1\}\). Put \(v=Q^{-1}(q/2)\), \(U=u-1=9\), \(V=v-1\), \(c=c_u\). For the null coordinate the intervals \(A,B,C\) are \((-\infty,u),(u,v),(v,\infty)\), and for the alternative coordinate they are \((-\infty,U),(U,V),(V,\infty)\). The COMPLETE matrices of actual \(R\) and \(\kappa=R\vee1\), with null intervals indexing rows, are
$$
R=\begin{pmatrix}0&0&1\\0&2&2\\1&2&2\end{pmatrix},
\qquad
\kappa=\begin{pmatrix}1&1&1\\1&2&2\\1&2&2\end{pmatrix}.
\tag{F2}
$$
These follow directly by testing BOTH candidate ranks of ordinary BH. For every cell \(B_\kappa=1/2\).

Write \(P(x)=-\psi_u(x)\), \(P_u=P(u)\), \(P_v=P(v)\), and \(H_k=h_{z_k}/t_k\). On \(x\ge v\),
$$
d(x):=H_2(x)-H_1(x)=\frac{Q(x)}{q\phi(x)},\qquad
d(v)=d_v:=\frac1{2\phi(v)}.
\tag{F3}
$$
On \(u<x<v\), the same jump is \((1-Q(x)/q)/\phi(x)\), and \(d(u)=0\). Thus all six null-coordinate faces have ZERO baseline jump: at \(x=u\) the only changing-rank faces have \(d(u)=0\), and at \(x=v\) the kappas on both sides agree. Among the six alternative-coordinate faces, only \(y=U\) in the null intervals \(B,C\) has a nonzero baseline jump. Each of the twelve rows is exactly (IT): the null-coordinate rows use the fixed moment \(P(u)\) or \(P(v)\), and the alternative-coordinate rows use \(P(X)\) averaged under \(X\sim N(-ry,1-r^2)\) restricted to its indicated null interval. All faces, including the unbounded ones, are retained; only three of these rows are needed below.

Let
$$
d_C=\mathbb E[d(X)\mid X>v],\qquad
P_C=\mathbb E[P(X)\mid X>v],
\quad X\sim N(-rU,1-r^2).
\tag{F4}
$$
These are the EXACT normalized Gaussian moments of the unbounded face \(y=U,x>v\). No endpoint replacement is made in (F4).

### A finite-r separating combination that permits arbitrary coefficients

For any constant coefficient vector \(a\), write
$$
n_1(a)=a_1-ra_2,\qquad n_2(a)=-ra_1+a_2.
$$
Denote the cell alpha vectors by \(a^{AB},a^{BB},a^{CB},a^{CA}\), and their betas by \(\beta_{AB},\beta_{BB},\beta_{CB},\beta_{CA}\). The three required integrated face rows are
$$
n_1(a^{BB})-n_1(a^{AB})
+\frac{P_u}{2}(\beta_{BB}-\beta_{AB})\ge0,
\tag{F5}
$$
$$
n_1(a^{CB})-n_1(a^{BB})
+\frac{P_v}{2}(\beta_{CB}-\beta_{BB})\ge0,
\tag{F6}
$$
$$
n_2(a^{CB})-n_2(a^{CA})
-\frac r2\{d_C+P_C(\beta_{CB}-\beta_{CA})\}\ge0.
\tag{F7}
$$
These correspond respectively to \(AB\to BB\) at \(x=u\), \(BB\to CB\) at \(x=v\), and \(CA\to CB\) at \(y=U\). They use the plan's increasing-coordinate orientations and its factor \(1/N=1/2\).

The AB lower-unbounded null interval requires \(a^{AB}_1\ge0\). Its cell budget, evaluated at the finite corner limit \((u,V)\), gives
$$
ua^{AB}_1+Va^{AB}_2\le D-\tfrac12+\tfrac c2\beta_{AB},
\qquad
n_1(a^{AB})\ge
-\frac rV(D-\tfrac12+\tfrac c2\beta_{AB}).
\tag{F8}
$$
The CB upper-unbounded null interval requires \(a^{CB}_1\le0\), hence
$$
n_1(a^{CB})+rn_2(a^{CB})
=(1-r^2)a^{CB}_1\le0.
\tag{F9}
$$
In CA the null interval is upper-unbounded and the alternative interval lower-unbounded, so \(a^{CA}_1\le0,a^{CA}_2\ge0\), and
$$
n_2(a^{CA})\ge0.
\tag{F10}
$$

The elementary bounds proved below give \(P_v>P_u>rc/V\) and \(P_C>0\). Adding (F5),(F6), then using (F8), makes the coefficients of \(\beta_{AB}\) and \(\beta_{BB}\) nonnegative on the right, so
$$
n_1(a^{CB})+\frac{P_v}{2}\beta_{CB}
\ge-\frac rV(D-\tfrac12).
\tag{F11}
$$
From (F7),(F10) and \(\beta_{CA}\le1\),
$$
n_2(a^{CB})\ge\frac r2(d_C-P_C+P_C\beta_{CB}).
\tag{F12}
$$
Combine (F9),(F11),(F12), and minimize over \(0\le\beta_{CB}\le1\). Every feasible FULL LP necessarily satisfies
$$
\boxed{\quad
D\ge\frac12+\frac V{2r}
\{r^2d_C-\max(r^2P_C,P_v)\}.
\quad}
\tag{F13}
$$
Equivalently one may add the three face rows with positive weights \(1,1,r\), then use their endpoint-sign, AB-budget and beta-bound rows. This is a finite nonnegative separating combination, not an assumption about any coefficient limit. In particular alpha coefficients growing like \(1/(1-r)\) cannot evade (F9).

### Rigorous scalar and truncated-tail moment bounds

For \(x>0\), integration by parts gives
$$
\frac{x}{1+x^2}\phi(x)<Q(x)<\frac{\phi(x)}x.
\tag{F14}
$$
The upper bound follows by integrating \(t\phi(t)/x\); for the lower bound use
\(Q(x)=\phi(x)/x-\int_x^\infty\phi(t)/t^2\,dt
>\phi(x)/x-Q(x)/x^2\).
The elementary constants \(3<\pi<4\) and \(8/3<e<3\) suffice below. The latter follow from the positive exponential series and its factorial geometric upper bound.

The Mills ratios imply
$$
\frac{Q(251/25)}{Q(10)}
>\frac{10(251/25)}{1+(251/25)^2}e^{-501/1250}
>\frac34\frac23=\frac12,
$$
where \(501/1250<81/200\) and \(e^{81/200}<3/2\). Also
$$
\frac{Q(101/10)}{Q(10)}
<\frac{101}{101}e^{-201/200}<\frac12.
$$
Thus
$$
10+\frac1{25}<v<10+\frac1{10},\qquad V>9.
\tag{F15}
$$
The one exponential upper bound just used has a finite rational certificate. For \(t=81/200\), bound the series remainder after degree five by \(t^6/[6!(1-t/7)]\); then
$$
\sum_{j=0}^5\frac{t^j}{j!}
+\frac{t^6}{6!(1-t/7)}
=\frac{50626048038633209}{33766400000000000}
<\frac32.
$$
Since \(\phi(0)<5/12\) and \(e^8>(8/3)^8>2500\),
$$
\phi(v)<\phi(10)<\phi(4)<1/6000,\qquad
q<1/60000,\qquad c<6.
\tag{F16}
$$
Also \(\phi(1/10)>(1/3)e^{-1/200}>3/10\). Put \(\delta=v-u\). The bounds in (F15) give
$$
\frac9{20}<Q(\delta)
<\frac12-\frac1{25}\frac3{10}
=\frac{61}{125}.
\tag{F17}
$$
Formula (P1) yields
$$
P_u=\frac{1/2-cq}{\phi(u)},\qquad
P_v=\frac{Q(\delta)-cq/2}{\phi(v)}.
\tag{F18}
$$
It follows that \(P_u>2940>rc/V\), since \(cq<1/10000\), \(rc/V<6/9<1\). Furthermore
$$
\frac{P_v}{P_u}
>\frac{(44/100)}{1/2}\frac{\phi(u)}{\phi(v)}
>\frac{88}{100}(1+2/5)>1,
\tag{F19}
$$
where \(\phi(u)/\phi(v)=e^{u\delta+\delta^2/2}>e^{2/5}>1+2/5\).
For \(x\ge v\), \(P(x)>0\): the tail likelihood-ratio identity gives
\(Q(x-u)\ge e^{ux-u^2/2}Q(x)>cQ(x)\), since \(e^{u^2/2}>c\).

Now write \(s^2=1-r^2\), \(m=-rU\), and condition \(X>v\). The overshoot \(Y=X-v\) has density proportional to
$$
\exp\{-ay-y^2/(2s^2)\},\quad y>0,
\qquad
a=\frac{v+rU}{s^2}.
\tag{F20}
$$
Our EXPLICIT rational \(r\) satisfies
$$
0<s^2<2\cdot10^{-6},\quad r^2>999/1000,\quad
v+rU>18,\quad a>9\,000\,000.
\tag{F21}
$$
For every \(y\ge0\), shifting the numerator of the survival integral in (F20) proves \(\mathbb P(Y>y)\le e^{-ay}\). Thus \(\mathbb EY\le1/a\). If \(R(x)=Q(x)/\phi(x)\), then \(R'(x)=xR(x)-1\ge-1\). Consequently, by (F3),(F14),
$$
d_C\ge d_v-\frac{\mathbb EY}{q}
\ge d_v\left\{1-\frac{v+v^{-1}}a\right\}
>\frac{999}{1000}d_v,
\tag{F22}
$$
since \(v+v^{-1}<11\) and \(11/(9\,000\,000)<1/1000\). This lower bound integrates the ENTIRE unbounded face.

For its Stein moment, (P1) and monotonicity of \(Q\) give, for all \(y\ge0\),
$$
P(v+y)\le P_v\,
\frac{Q(\delta)}{Q(\delta)-cq/2}\,
e^{vy+y^2/2}
<P_v\frac{9000}{8999}e^{vy+y^2/2}.
\tag{F23}
$$
Indeed \(cq/2<1/20000\), while \(Q(\delta)>9/20\).
The normalizing integral in (F20) is at least
\(a^{-1}\{1-(s^2a^2)^{-1}\}\), by \(e^{-t}\ge1-t\) and the exact second exponential moment integral. The corresponding numerator for \(\mathbb E e^{vY+Y^2/2}\) is at most \(1/(a-v)\), since \(s^2<1\). Hence
$$
\mathbb E e^{vY+Y^2/2}
\le\frac{a}{a-v}\,
\frac1{1-(s^2a^2)^{-1}}
<\left(\frac{100001}{100000}\right)^2.
\tag{F24}
$$
For clarity the second factor is controlled by the EXACT identity
\(s^2a^2=(v+rU)^2/s^2>18^2/(2\cdot10^{-6})>10^8\);
it does not follow by separately multiplying upper and lower estimates on \(s^2,a\).
The first factor uses \(v<101/10,a>9\,000\,000\).
Both rational comparisons in (F24) are strict. Combining with (F23),
$$
0<P_C<
\frac{9000}{8999}\left(\frac{100001}{100000}\right)^2P_v
=\frac{90001800009}{89990000000}P_v
<\frac{1001}{1000}P_v.
\tag{F25}
$$

### Contradiction at the fixed positive-definite model

By (F21),(F22),
\(r^2d_C>(998/1000)d_v\). By (F17),(F18),(F25),
\(\max(r^2P_C,P_v)<(1001/1000)P_v
<(1001/1000)(61/125)/\phi(v)\).
Therefore
$$
r^2d_C-\max(r^2P_C,P_v)
>\frac{(998/1000)/2-(1001/1000)(61/125)}{\phi(v)}
=\frac{657}{62500\phi(v)}
>63.
\tag{F26}
$$
Insert (F26) into the necessary condition (F13), using \(V>9\), \(r<1\):
$$
D>\frac12+\frac92\,63=284.
\tag{F27}
$$
But IT64 at \(u=10\) prescribes \(D=64\log12<192\), because
\(e^3>(8/3)^3>12\). This is the required strict contradiction at an explicitly specified admissible positive-definite model INSIDE the prespecified core range.

All finite rational comparisons, including the exponential-series upper bound, (F21),(F24)--(F26), were additionally checked by a short standard-library Fraction calculation. That calculation is an arithmetic replay only; the analytic inequalities above supply the proof. No numerical Gaussian probability or optimizer supplies a premise.

This failure is specific to demanding a nonnegative integrated jump on EVERY face while retaining the restricted field and pointwise cell budget. Although integration removes the old middle-face endpoint obstruction, the additional unbounded face and endpoint signs create this different separating combination. The argument does not prove or disprove any FDR asymptotic claim. The original target asset is untouched; items 3--6 cannot establish IT64 because its mandatory first gate has failed. No coefficient, constant, cutoff, covariance, mean, label, or approval has been changed to avoid the obstruction.

## Verification

The finite LP is a concrete model-input certificate with a fixed field and per-face integrated inequalities; it is not a relabeling of mean FDR. Its dual (DB) is an explicit proposed finite-algebraic sufficient obligation whose Gaussian coefficients and complete constraints are written above. Nonetheless its uniform feasibility is presently unproved. A finite gate or a new dual/Gram identity is required before any target claim. Satisfying only the old selected faces, numerical LP feasibility, or bounded actual FDR does not establish this certificate.

All comparisons must use complete BH largest rank. Preserve q-dependent N, arbitrary actual means, every correlation sign and all positive-definite regularizations. If any mandatory gate with u>=10 refutes IT64, leave the target untouched and record failure under this plan. Out-of-range u<10 diagnostics carry no claimed feasibility and cannot refute the prespecified small-level lemma. No constant or ansatz may be silently enlarged.

## Assumed definitions

All model/BH/FDR definitions are the approved definitions already named by the target. No draft definition, unproved asset, source theorem, finite LP feasibility claim, or Gaussian moment estimate is assumed. M_u,h_b,psi_u, the grid, moment coefficients, interval cones and dual weights are local notation whose required identities are rederived. Referenced ideas supply tests and warnings only.

## Difference from failed plans

- `plan_gaussian_bh_one_sided_global_corner_budget_20261104`: no unrestricted diagonal-majorant/support bound and no optimizing a trace against a new PSD matrix. All dual moment coefficients retain the generating Sigma, actual full-cell masks and signed contributions.
- `plan_gaussian_bh_one_sided_fixed_alternative_schur_budget_20261104`: no row-absolute null cost or enlarged alternative Gram support. The mechanism is exact Gaussian face integration plus a finite cell-moment dual; the alternative covariance is never replaced.
- `plan_gaussian_bh_one_sided_joint_extremum_factor_reduction_20261104`: no finite or asymptotic one-factor extremal replacement. Negative triangles and all admissible PSD matrices remain in the model class.
- `plan_gaussian_bh_one_sided_stein_transmission_capacity_20261104`: the field and D64 pointwise CELL budget remain fixed, but pointwise face transmission is removed entirely and replaced by exact Gaussian face INTEGRALS. The old exponential endpoint obstruction is not reused as an integrated contradiction. All twelve N2 faces, including unbounded faces, must be checked in the new LP.
