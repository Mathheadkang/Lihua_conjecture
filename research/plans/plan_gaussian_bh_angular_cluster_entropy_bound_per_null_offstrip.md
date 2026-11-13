---
id: plan_gaussian_bh_angular_cluster_entropy_bound_per_null_offstrip
type: plan
title: >-
  Per-null Lei reduction with cluster-event split and an explicit off-strip
  constant
status: succeeded
target_asset: gaussian_bh_angular_cluster_entropy_bound
inspired_by:
  - idea_f72ff17dc310
  - idea_676ddf6ca5aa
adapts:
  - directional_entropy_one_sided_fdr_bound
proof_digest: 837469b9c3ae0bd958dbec4dbb1aaff96ae26e6a142ed126ee7bb87211039b28
statement_digest: c0f4a35d70bb8c3321136accd04202b71bb70ae9a12fd0aaa5c3d48abe6e1b98
dependency_digests:
  lei2026_conditional_fdp_bound: 44ffaa8350cce69886ffb1907cd5a32495616e8ae1bfffc50faacce9e404d689
  lei2026_integrated_conditional_tail_ratios: eaba74a3d26ad4ac1b23dbf9994b6056da3e28d3e763ef838fb82f70c8fc5867
  gaussian_multifactor_representation: e3a61244f476941be96780294a5d26af63dd415aa7462c2662601bf6aeb086fe
  gaussian_null_loading_coefficients: 09a1a87d4a0bdf55ae76e1e04ecb437e172fbf9a8038b92d07f9b37d8a7002c5
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: 837469b9c3ae0bd958dbec4dbb1aaff96ae26e6a142ed126ee7bb87211039b28
---

# Per-null Lei reduction with cluster-event split and an explicit off-strip constant

## Goal

Target: [Angular-cluster entropy bound for one-sided Gaussian BH with free truncation levels](../assets/gaussian_bh_angular_cluster_entropy_bound.md).

Prove the stated inequality, unchanged, with the explicit choice
$$
A_1(\kappa)=A^*(\kappa):=2(\kappa+1)\bigl(\kappa\Phi(\kappa)+\phi(\kappa)\bigr)+2\bigl((\kappa^2+1)\Phi(\kappa)+\kappa\phi(\kappa)\bigr).
$$
The route is the proof sketch [Per-null reduction proves the angular-cluster entropy bound with explicit A_1](../ideas/idea_f72ff17dc310.md), carried out as a modification of the approved proof of [One-sided Gaussian BH bound from oriented null directional entropy](../assets/directional_entropy_one_sided_fdr_bound.md). The difference from that proof: each null is evaluated along its own direction $Y_i=a_i^{\mathsf T}Z/r_i$, while the cluster split uses the cluster direction $W_j=v_j^{\mathsf T}Z$; the mismatch produces one off-strip integral bounded by $A^*(\kappa)$. The plan also closes the two unchecked steps in the Limitations of the search record search_gaussian_bh_angular_cluster_entropy_bound_r1_boundary_degenerate: (a) Lei's scalar integrated bound applies to $Y_i$ for any $d$ (step 3), and (b) the hazard inequality $\phi(y)\le(y+1)\overline\Phi(y)$ for $y\ge0$ gets a written proof (step 5). Library searches (Mills ratio, Gaussian tail hazard, bivariate normal conditional) found no library result to cite or adapt; nothing outside `depends_on` is needed.

## Plan

1. [x] **Setup and partial FDPs.** Write $\phi,\Phi$ for the standard normal density and CDF, $u=\overline\Phi^{-1}(q)>0$, $W_j=v_j^{\mathsf T}Z\sim\mathcal N(0,1)$, and $\operatorname{FDP}_j=|\mathcal R_q\cap C_j|/(R\vee1)$, so $0\le\operatorname{FDP}_j\le1$ and $|\mathcal R_q\cap I_*|/(R\vee1)=\sum_j\operatorname{FDP}_j$. If $I_*=\varnothing$ (then $J=0$) both sides are $0$. No independence between different $W_j$ is used. Claim: it suffices to show for each $j$
$$
\mathbb E[\operatorname{FDP}_j]\le\overline\Phi(\beta_j)+\frac qm\sum_{i\in C_j}\Bigl(\tfrac12+\tfrac{\gamma_iu}{\sqrt{2\pi}}+\log\tfrac{q}{\overline\Phi(\beta_j)}+A^*(\kappa)\Bigr),
$$
since summing over $j$ with $|C_j|/m=\pi_j$ gives the target with $\tfrac12\le\tfrac32$ (one unit of slack). Note $\log(q/\overline\Phi(\beta_j))\ge0$ because $\beta_j\ge u$.

2. [x] **Cluster split and conditional per-null bound (as in directional_entropy_one_sided_fdr_bound, leave-one-out paragraph).** On $\{W_j>\beta_j\}$ use $\operatorname{FDP}_j\le1$: cost $\overline\Phi(\beta_j)$. On $\{W_j\le\beta_j\}$, which is $Z$-measurable, reproduce the leave-one-out identity $\mathbf1\{i\in\mathcal R_q\}/(R\vee1)=\mathbf1\{p_i\le qR_i/m\}/R_i$ from [Lei conditional leave-one-out FDP bound](../assets/lei2026_conditional_fdp_bound.md) restricted to $i\in C_j$ (the approved proof writes out the deterministic BH step, including ties and $R=0$), and conditional independence of $p_i$ and $R_i$ given the full $Z$. Claim:
$$
\mathbb E[\operatorname{FDP}_j\mathbf1\{W_j\le\beta_j\}]\le\frac qm\sum_{i\in C_j}\mathbb E\bigl[G_i\,\mathbf1\{W_j\le\beta_j\}\bigr],\qquad G_i=\sup_{0<t\le q}\frac{F_{i,Z}(t)}t,
$$
where $F_{i,Z}$ is the conditional CDF of $p_i$ given $Z$. Measurability of $G_i$ as in the approved proof (supremum over rationals plus $t=q$, right-continuity).

3. [x] **Reduce each null to a scalar factor (closes limitation (a)).** For $r_i>0$ put $Y_i=a_i^{\mathsf T}Z/r_i$, a standard normal scalar (as $\|a_i/r_i\|=1$). Then $T_i=\theta_i+r_iY_i+\sqrt{1-r_i^2}\,\varepsilon_i$ with $\varepsilon_i$ independent of $Z$, so $F_{i,Z}(t)=F^{\theta_i}_{r_i,Y_i}(t)$ with $F^\theta_{r,y}$ as in the approved proof, and $G_i=M_i(Y_i)\le M^0_{r_i}(Y_i)$ by translation domination ($\theta_i\le0$). The function $y\mapsto M^0_{r}(y)$ is exactly the integrand of the one-sided part of [Lei integrated conditional Gaussian tail-ratio bounds](../assets/lei2026_integrated_conditional_tail_ratios.md); that lemma is a statement about a scalar function integrated against $\phi$, so it applies verbatim for any $d$:
$$
\int_{-\infty}^{u}\phi(y)M^0_{r_i}(y)\,dy\le\tfrac12+\tfrac{\gamma_iu}{\sqrt{2\pi}},
$$
endpoint $r_i=1$ included as stated there. For $r_i=0$: $F_{i,Z}(t)=\mathbb P(\theta_i+\varepsilon_i\ge\overline\Phi^{-1}(t))\le t$, so $G_i\le1$ and $\mathbb E[G_i\mathbf1\{W_j\le\beta_j\}]\le1\le\tfrac12+\tfrac u{\sqrt{2\pi}}+\log\tfrac q{\overline\Phi(\beta_j)}+A^*(\kappa)$ since $\gamma_i=1$ and $A^*\ge A^*(0)=\sqrt{2/\pi}+1\ge\tfrac12$; no angular condition is needed, matching the statement.

4. [x] **Three-region split for $r_i>0$.** Claim:
$$
\mathbb E[M_i(Y_i)\mathbf1\{W_j\le\beta_j\}]\le\underbrace{\int_{-\infty}^u\phi M^0_{r_i}}_{\text{step 3}}+\underbrace{\int_u^{\beta_j}\frac{\phi(y)}{\overline\Phi(y)}dy}_{=\log(q/\overline\Phi(\beta_j))}+\underbrace{\int_{\beta_j}^\infty\frac{\phi(y)}{\overline\Phi(y)}\,\mathbb P(W_j\le\beta_j\mid Y_i=y)\,dy}_{\text{off-strip}}.
$$
On $\{Y_i\le u\}$ and $\{u<Y_i\le\beta_j\}$ drop the indicator of $\{W_j\le\beta_j\}$. Use the approved outer-strip envelope $M^0_r(y)\le1/\overline\Phi(y)$ (as in directional_entropy_one_sided_fdr_bound: monotonicity of $F^0_{r,y}(t)$ in $y$ and $\int\phi(z)F^0_{r,z}(t)dz=t$) and $\frac d{dy}[-\log\overline\Phi]=\phi/\overline\Phi$, with $\overline\Phi(u)=q$. For the last region, $(Y_i,W_j)$ is a standard bivariate normal pair with correlation $\rho_i=a_i^{\mathsf T}v_j/r_i\in[\tfrac12,1]$; if $\rho_i=1$ then $W_j=Y_i$ a.s. and the off-strip term is $0$; if $\rho_i<1$, with $\sigma_i=\sqrt{1-\rho_i^2}\in(0,\sqrt3/2]$, $W_j\mid Y_i=y\sim\mathcal N(\rho_iy,\sigma_i^2)$ and $\mathbb P(W_j\le\beta_j\mid Y_i=y)=\Phi((\beta_j-\rho_iy)/\sigma_i)$.

5. [x] **Hazard inequality (closes limitation (b)).** Prove $\phi(y)\le(y+1)\overline\Phi(y)$ for $y\ge0$. Put $g(y)=(y+1)\overline\Phi(y)-\phi(y)$; $g(0)=\tfrac12-\tfrac1{\sqrt{2\pi}}>0$, $g(y)\to0$ as $y\to\infty$, $g'(y)=\overline\Phi(y)-\phi(y)$. The Mills ratio $\overline\Phi/\phi$ is strictly decreasing on $[0,\infty)$ (its derivative is $y\overline\Phi/\phi-1<0$ by the Gordon bound $y\overline\Phi(y)<\phi(y)$, itself from $\overline\Phi(y)=\int_y^\infty\phi<\int_y^\infty (x/y)\phi(x)dx$ for $y>0$; at $y=0$ the derivative is $-1$), equal to $\sqrt{\pi/2}>1$ at $0$ and tending to $0$. Hence $g'$ changes sign once, from $+$ to $-$, at some $y_0$: $g$ increases on $[0,y_0]$ from $g(0)>0$ and decreases on $[y_0,\infty)$ to the limit $0$, so $g\ge0$ throughout. (Numerical check: $\max_{0\le y\le30}[\phi/\overline\Phi-(y+1)]\approx-0.20$.)

6. [x] **Off-strip constant.** For $\rho_i<1$, substitute $y=\beta_j+t$, $t\ge0$:
$$
\frac{\beta_j-\rho_iy}{\sigma_i}=\frac{\beta_j(1-\rho_i)}{\sigma_i}-\frac{\rho_it}{\sigma_i}\le\kappa-\frac{t}{2\sigma_i},
$$
using $(1-\rho_i)/\sigma_i=\sqrt{(1-\rho_i)/(1+\rho_i)}\le\sigma_i$ (equivalent to $1\le(1+\rho_i)^2$), the hypothesis $\beta_j\sigma_i\le\kappa$, and $\rho_i\ge\tfrac12$. With step 5 and $s=t/(2\sigma_i)$:
$$
\text{off-strip}\le\int_0^\infty(\beta_j+1+t)\Phi\!\Bigl(\kappa-\tfrac t{2\sigma_i}\Bigr)dt=2\sigma_i(\beta_j+1)I_0(\kappa)+4\sigma_i^2I_1(\kappa),
$$
where $I_0(\kappa)=\int_0^\infty\Phi(\kappa-s)ds=\kappa\Phi(\kappa)+\phi(\kappa)$ and $I_1(\kappa)=\int_0^\infty s\Phi(\kappa-s)ds=\tfrac12\mathbb E[(\kappa-N)^2;N\le\kappa]=\tfrac12\bigl((\kappa^2+1)\Phi(\kappa)+\kappa\phi(\kappa)\bigr)$ for $N\sim\mathcal N(0,1)$ (integration by parts; verify both closed forms). Since $\sigma_i\le1$ and $\sigma_i\beta_j\le\kappa$, this is at most $2(\kappa+1)I_0(\kappa)+4I_1(\kappa)=A^*(\kappa)$. (Numerical check over $\kappa\in\{0.01,0.5,1,3\}$, $\rho\in[0.5,0.99]$, admissible $\beta$: ratio off-strip$/A^*\le0.63$.)

7. [x] **Properties of $A^*$.** $A^*$ is finite and nonnegative on $[0,\infty)$, depends on $\kappa$ only, and is nondecreasing: $\frac d{d\kappa}(\kappa\Phi+\phi)=\Phi\ge0$, $\frac d{d\kappa}\bigl((\kappa^2+1)\Phi+\kappa\phi\bigr)=2(\kappa\Phi(\kappa)+\phi(\kappa))\ge0$, and $\kappa+1$, $I_0$ are positive. It is independent of $m,d,J$, the means, loadings, $v_j$, $\beta_j$ and $q$, as required.

8. [x] **Assemble.** Combine steps 2-6 into the per-cluster claim of step 1 and sum over $j$. Remark the endpoint cases: $r_i=1$ (conditionally deterministic $p_i$, handled in steps 2-4 without division by $\sqrt{1-r_i^2}$), $\rho_i=1$ (off-strip zero), $\beta_j=u$ (middle strip empty), and $\rho_i=\tfrac12$ (allowed; step 6 uses only $\rho_i\ge\tfrac12$). Alternatives affect only $R_i$, which the supremum $G_i$ dominates.

## Verification

Step 1 reduces the target to a per-cluster inequality. Steps 2-4 bound $\mathbb E[\operatorname{FDP}_j]$ by $\overline\Phi(\beta_j)$ plus $\frac qm\sum_{i\in C_j}$ of (central Lei term) + (middle strip $\log(q/\overline\Phi(\beta_j))$) + (off-strip), with zero-loading members bounded by $1$ in step 3. Steps 5-6 bound the off-strip term by $A^*(\kappa)$ and step 7 shows $A_1:=A^*$ has the required properties. Summing, $\sum_j\bigl[q\pi_j(\tfrac12+A^*+\log\tfrac q{\overline\Phi(\beta_j)})+\overline\Phi(\beta_j)\bigr]+\frac{qu}{\sqrt{2\pi}}\frac1m\sum_{i\in I_*}\gamma_i$, which is at most the stated right side because $\tfrac12\le\tfrac32$. The statement's existential $A_1$ is witnessed by $A^*$.

## Assumed definitions

None beyond approved ones: the definitions in the target's `uses_definitions` and the approved dependencies [Lei conditional leave-one-out FDP bound](../assets/lei2026_conditional_fdp_bound.md) and [Lei integrated conditional Gaussian tail-ratio bounds](../assets/lei2026_integrated_conditional_tail_ratios.md). No draft dependency is assumed.

## Adapted from

- directional_entropy_one_sided_fdr_bound ([One-sided Gaussian BH bound from oriented null directional entropy](../assets/directional_entropy_one_sided_fdr_bound.md), approved). Transfers unchanged: the partial-FDP decomposition, the leave-one-out identity with conditioning on the full $Z$, translation domination for $\theta_i\le0$, the outer-strip envelope $M^0_r(y)\le1/\overline\Phi(y)$, the use of Lei's central integral, and the treatment of $r_i\in\{0,1\}$. Its cited results (the two Lei lemmas) are both in the target's `depends_on`. Changes: (i) its loadings are exactly aligned ($a_i=r_iv_h$, so $Y_i=W_h$); here $Y_i$ and $W_j$ differ, so the split event $\{W_j\le\beta_j\}$ is not a function of $Y_i$ and the region $Y_i>\beta_j$, $W_j\le\beta_j$ survives (steps 4-6, new); (ii) its cutoff is $b_h=\overline\Phi^{-1}(q\pi_h)$, here any $\beta_j\ge u$, so the strip cost is $\log(q/\overline\Phi(\beta_j))$ and the complement costs $\overline\Phi(\beta_j)$ rather than $q\pi_h$; (iii) its groups cover all of $I_0$, here only $I_*\subseteq I_0$, and the other nulls simply do not enter the partial sums; (iv) zero-loading members are bounded by $G_i\le1$ instead of being grouped with a direction.

## Outcome

Succeeded. The complete proof is under `## Proof` in [Angular-cluster entropy bound for one-sided Gaussian BH with free truncation levels](../assets/gaussian_bh_angular_cluster_entropy_bound.md) (statement unchanged, status draft), with the explicit witness $A_1=A^*(\kappa)=2(\kappa+1)(\kappa\Phi(\kappa)+\phi(\kappa))+2((\kappa^2+1)\Phi(\kappa)+\kappa\phi(\kappa))$. All eight plan steps were carried out as written; the leave-one-out identity, translation domination and outer-strip envelope from directional_entropy_one_sided_fdr_bound are reproved in full. Limitation (a) is closed by identifying $F^0_{r,y}$ with the scalar conditional CDF of Lei's one-sided integrated bound; limitation (b) by a written proof of $\phi(y)\le(y+1)\overline\Phi(y)$ via Gordon's bound and monotonicity of the Mills ratio. The closed forms of the plan's $I_0,I_1$ (renamed $K_0,K_1$ in the proof, since $I_0$ denotes the true-null set) are verified by differentiation and limits at $-\infty$. Assumed: only the approved dependencies lei2026_conditional_fdp_bound and lei2026_integrated_conditional_tail_ratios and approved definitions; no draft definition.

## Verdict

confirmed

Checked step by step against the statement. Step 1: the sum of (1) over $j$ gives the stated bound with $\frac12$ in place of $\frac32$, and $J=0$ when $I_*=\varnothing$. Step 2: the leave-one-out identity is re-derived inline, ties and $R=0$ included. $R_i\ge1$ because $p_i=0\le q/m$. $p_i$ is a function of $(Z,\varepsilon_i)$ and $R_i$ of $(Z,\varepsilon_{-i})$, so the two are conditionally independent given $Z$, as the multifactor definition and Lei's lemma require. Step 3: $F_{i,Z}=F^{\theta_i}_{r_i,Y_i}$ along each null's own direction $Y_i=a_i^{\mathsf T}Z/r_i\sim\mathcal N(0,1)$. The composite-null domination $F^{\theta}\le F^{0}$ holds for $\theta\le0$. The hypotheses of the one-sided tail-ratio lemma ($0<q<1/2$, $r\in[0,1]$, $r=1$ included) hold, and it is a scalar statement, so $d$ plays no role. For $r_i=0$, $G_i\le1<A^*(0)$. Step 4: the envelope $M^0_r(y)\le1/\overline\Phi(y)$ follows from monotonicity in $y$ and $\int\phi F^0_{r,z}(t)\,dz=t$. The middle strip integrates to $\log(q/\overline\Phi(\beta_j))$. The off-strip conditioning uses $\operatorname{Cov}(Y_i,W_j)=\rho_i$ and the fact that $W_j-\rho_iY_i$ is independent of $Y_i$. This is correct, and $\rho_i=1$ is handled without dividing by $\sigma_i$. Step 5: $\mu'=y\mu-1$ and $g'=\phi(\mu-1)$ are correct, $g(0)>0$ and $g\to0$, so $\phi\le(y+1)\overline\Phi$ on $[0,\infty)$. Step 6: $(1-\rho)/\sigma\le\sigma$ holds iff $(1+\rho)^2\ge1$; this, with $\beta_j>0$, $\rho_i\ge\frac12$ and $\sigma_i\le1$, gives the bound. The substitution $t=2\sigma_is$ and the closed forms $K_0=\kappa\Phi+\phi$ and $K_1=\frac12((\kappa^2+1)\Phi+\kappa\phi)$ were checked by differentiation and their limits at $-\infty$. $K_1(0)=\frac14$ agrees with $\int_0^\infty s\overline\Phi(s)\,ds=\frac14$. Step 7: $A^*$ is nonnegative, depends only on $\kappa$, and is nondecreasing; $A^*(0)=1+\sqrt{2/\pi}$. Singular covariance and the endpoint loadings $r_i\in\{0,1\}$ are covered, since only scalar Gaussian projections were used. No gaps needed closing.
