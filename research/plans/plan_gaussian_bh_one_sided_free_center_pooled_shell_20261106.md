---
type: plan
title: One-sided free central window and a pooled extreme-factor shell bound in the independent block class, then decoupling for arbitrary covariance
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
inspired_by: [idea_dacbbb3bafb1, idea_3370404c0baa, idea_a4ba452bf4a7, idea_b4add80d09ed, idea_0d2e69e0ba3b]
adapts: [directional_entropy_one_sided_fdr_bound, lei2026_conditional_fdp_bound, lei2026_integrated_conditional_tail_ratios, lei2026_one_sided_common_factor_upper]
tags: [one_sided, block_model, shell, pivotality]
---

## Goal

Target: [Sharp uniform upper-bound target for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_sharp_upper.md). The statement is unchanged, and it is the only conclusion: for every $\varepsilon>0$ there is $q_\varepsilon$ such that for all $q<q_\varepsilon$, every finite $N$, every $\theta$ with true nulls $\{\theta_i\le0\}$, and every unit-diagonal PSD $\Sigma$ (singular allowed, all depending on $q$ arbitrarily), the ordinary largest-rank BH procedure on $p_i=\overline\Phi(T_i)$ has $\mathrm{FDR}\le(1/\sqrt\pi+\varepsilon)q\sqrt{\log(1/q)}$. No fixed-dimension, one-factor, spherical or $N\to\infty$-first substitute is a conclusion of this plan.

**Mechanism.** Split every null's contribution by its own oriented factor value $Y_i$ at $U=\overline\Phi^{-1}(q)$.

- *Central window* $Y_i\le U$. In the one-sided problem this part is free. The supremum of the conditional tail ratio over all thresholds already integrates to $\frac12+\gamma_rU/\sqrt{2\pi}$ with $\gamma_r\le1$, for every background and every curve. The two-sided factor-2 loss, which needed both signs of the factor, cannot occur.
- *Shell* $Y_i>U$. All of the remaining content sits here. Per null it is unbounded: a deterministic deficit curve with anti-loaded loading-one mates tilt-matches $u(y)=y/r$ for $y$ beyond $U$. The pre-test below confirms this numerically. Only a **pooled** statement over all nulls can hold.

So the first KEY gate is not the deterministic-curve DCL proposed for this round. That DCL is true here but vacuous: step 3 proves it in three lines. The first gate is the pooled shell bound (PSL) in the independent one-factor block class $\mathfrak B_1$. This is again a statement about extreme factor coordinates across many blocks: the obstruction parked in the sibling project and the open core 6e of `plan_two_sided_averaged_flatness_exclusion_20261105`. This plan adds three new things. (i) It reduces PSL to the regime the approved entropy bound misses, by a new radial strip refinement (step 4). (ii) It adds a deterministic carrier lemma (step 5b): tilting in the shell forces the block's anti-loaded members to be counted in the block's typical state. (iii) It adds a budget telescoping route for the pooled inequality (step 5c). Arbitrary $\Sigma$ needs a further decoupling lemma (step 7); no candidate proof of it exists, and it is stated as an explicit open KEY step.

**First KEY gate (step 5), exact inequality.** For every model in $\mathfrak B_1$ (defined in step 0) and every $q\le q_0$,
$$
\mathrm{Sh}:=\sum_{i\in I_0,\ a_i\ne0}\mathbb E\Big[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}\,\mathbf 1\{Y_i>U\}\Big]\ \le\ \eta(q)\,qU,\qquad \eta(q)\to0,
$$
with $\eta$ independent of $N$, the number of blocks $G$, the means and the loadings.

## Plan

Notation. $0<q<1/2$, $U=\overline\Phi^{-1}(q)>0$, $t_k=qk/N$, $u_k=\overline\Phi^{-1}(t_k)\ge U$ ($u_N=U$), $k(w)=N\overline\Phi(w)/q$ (the BH line in level space). For $r\in[0,1)$, $s=\sqrt{1-r^2}$, $\gamma_r=\sqrt{(1-r)/(1+r)}$ and $\theta\le0$,
$$
\rho^\theta_r(v,y)=\frac{\overline\Phi((v-\theta-ry)/s)}{\overline\Phi(v)}\le\rho_r(v,y):=\rho^0_r(v,y),\qquad \rho_1(v,y)=\frac{\mathbf 1\{y\ge v\}}{\overline\Phi(v)},\quad\rho_0\equiv1 .
$$

0. [x] **Setting and planning pre-test (done at planning; evidence only).**
   - *Class $\mathfrak B_1$.* $G\ge0$ blocks, a block map $g:[N]\to\{0,\dots,G\}$, loadings $a_j\in[-1,1]$ with $a_j=0$ when $g(j)=0$, and
     $$T_j=\theta_j+a_jZ_{g(j)}+\sqrt{1-a_j^2}\,\varepsilon_j,$$
     where $Z_1,\dots,Z_G,\varepsilon_1,\dots,\varepsilon_N$ are iid $N(0,1)$ and $Z_0:=0$. So $\Sigma_{jl}=a_ja_l\mathbf 1\{g(j)=g(l)\ge1\}+\delta_{jl}(1-a_j^2)$: unit diagonal, PSD, block diagonal, and singular as soon as two members of a block have $|a|=1$. Every $N$, $G$, mean and loading may depend on $q$.
   - For a null $i$ with $a_i\ne0$: $r_i=|a_i|$, $Y_i=\operatorname{sgn}(a_i)Z_{g(i)}$. *Oriented groups* $h=(g,\pm)$ collect the nulls of block $g$ with loading sign $\pm$. Put $\pi_h=|h|/N$ and $b_h=\overline\Phi^{-1}(q\pi_h)\ge U$.
   - *Pre-test.* Script `os1/pretest.py` in this session's scratchpad. Level space with step $0.01$ on $[U,U/r+1]$. Deterministic integer deficit curves $D^*$, nonincreasing in the level, with unit jumps. Tilt-designed anti-loaded loading-one mates, one per unit jump at $(1+r)\times$ the jump level, so that $u(z)=z/r$ exactly. Variant: $20$ extra positive-loaded mates at $\pm$ means, with the curve offset by $20$. Smallest qualifying level computed exactly per $z$; $z$-grid $0.01$. Central quantity $\Delta^{\rm c}=\int_{z\le U}\phi(z)[\rho_r(u(z),z)-\rho_r(u_f,z)]dz$, reported as a ratio to $\gamma_rU/\sqrt{2\pi}$. Curve families: finest staircase ($D=1,2,3,\dots$ per level step); $D\propto k^{\vartheta}$ with $\vartheta\in\{1,0.5,0.25,2/U^2,8/U^2\}$ (normalized $D(U)=3000$, floor $1$); plateaus of length $5$ and $25$ grid steps. Largest ratio over all families:

     | $q$ | $r=0.3$ | $r=0.5$ | analytic ceiling $1+\sqrt{2\pi}/(2\gamma_rU)$ at $r=0.3$ / $0.5$ |
     |---|---|---|---|
     | $10^{-8}$ | $1.291$ (stair) | $1.355$ (plateau 5) | $1.304$ / $1.387$ |
     | $10^{-16}$ | $1.201$ | $1.249$ | $1.207$ / $1.264$ |
     | $10^{-30}$ | $1.145$ | $1.180$ | $1.149$ / $1.190$ |

     The ratios decrease with $q$ and never exceed the ceiling of step 3. The slope of $\Delta^{\rm c}$ per unit of $U/\sqrt{2\pi}$ between $q=10^{-8}$ and $10^{-30}$ is $0.586$ at $r=0.5$, against $\gamma_{0.5}=0.577$. **Verdict: the one-sided deterministic-curve DCL is not refuted.** The excess over $1$ is the additive $\frac12$ of step 3 (it is $O(1/U)$), and the $1.15$-at-all-three-$q$ criterion is met only by sequences decreasing toward $1$, which the stop rule exempts.
   - *Shell, same script.* Extending the tilt range to $W=U/r+c$ gives a per-null shell $\int_{z>U}\phi\,[\rho_r(u(z),z)-\rho_r(u_f,z)]$, in units of $U/\sqrt{2\pi}$, of $0.103,\,0.287,\,0.575$ at $q=10^{-8}$, $r=0.5$, for $c=1,\,U/2,\,U$. The prediction $(rW-U)/(sU)$ gives $0.103,0.289,0.577$. **The per-null deterministic shell is unbounded** (compare the BSP mates-only family, shell up to $(2+r)U$). Hence the gate must be pooled.

1. [x] **(routine; re-included) Forced-zero identity.** For any p-value vector, any $i$, and $R_i$ the BH rank after setting $p_i=0$: $R_i\ge1$, $R_i$ is a function of $(p_j)_{j\ne i}$, $R_i\ge R$, and pointwise $\mathbf 1\{i\in\mathcal R_q\}/(R_q\vee1)=\mathbf 1\{p_i\le t_{R_i}\}/R_i$, including ties and $R=0$.
   - Sources: (BH0) in Progress of `plan_two_sided_baseline_subtracted_pivotal_probe_20261105`; the proof of [One-sided Gaussian BH bound from oriented null directional entropy](../assets/directional_entropy_one_sided_fdr_bound.md).
   - Unchanged for one-sided p-values: only the ordering of the $p_j$ is used.

2. [x] **(routine; re-included, one-sided kernel: CHANGED, recheck) Conditional formula and composite domination.**
   - (a) In any [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md), in particular in $\mathfrak B_1$, for a null $i$ with $r_i=\|a_i\|$ and $Y_i=a_i^{\mathsf T}Z/r_i$ (any unit vector if $r_i=0$):
     $$\mathbb E\Big[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}\Big|Z\Big]=\frac qN\,\mathbb E\big[\rho^{\theta_i}_{r_i}(u_{R_i},Y_i)\,\big|\,Z\big]\le\frac qN\,\mathbb E\big[\rho_{r_i}(u_{R_i},Y_i)\,\big|\,Z\big].$$
     Proof: $p_i$ and $R_i$ are conditionally independent given $Z$, and $\theta_i\le0$ translates the event.
   - (b) For any $T_{-i}$-measurable rank $R'$ independent of $Y_i$: $\mathbb E\,\rho^{\theta_i}_{r_i}(u_{R'},Y_i)=\mathbb E\,\overline\Phi(u_{R'}-\theta_i)/\overline\Phi(u_{R'})\le1$. This is the one-sided composite version of exogenous unbiasedness (A1(c) of `plan_two_sided_exogenous_pivotal_blocks_20261105`), with $\le$ in place of $=$. So the two-sided identity $\mathrm{FDR}=q\pi_0+\frac qN\sum\Delta_i$ becomes $\mathrm{FDR}\le q\pi_0+\frac qN\sum_i\Delta_i$, with equality when every null mean is $0$.
   - Source: B1 of that plan (two-sided kernel replaced by the one-sided $\rho_r$); the conditional step of the approved entropy proof.

3. [x] **(routine; the free central window; settles the deterministic DCL) Lemma C.** For $r\in[0,1)$ and all real $y$, $v\ge U$,
   $$\phi(y)\rho_r(v,y)\le\frac1{s}\,\phi\Big(\frac{(rv-y)_+}{s}\Big)\le\frac1{s\sqrt{2\pi}},\qquad \int_{-\infty}^{U}\phi(y)\sup_{v\ge U}\rho_r(v,y)\,dy\le\frac12+\frac{\gamma_rU}{\sqrt{2\pi}}.$$
   - Proof: by the density identity, $\phi(y)\overline\Phi((v-ry)/s)=\int_v^\infty\phi(x)\,s^{-1}\phi((y-rx)/s)\,dx$, and $|y-rx|\ge(rU-y)_+$ for $x\ge v\ge U$. Integrate $s^{-1}\phi((rU-y)/s)$ over $y\le rU$ (giving $\frac12$) and $1/(s\sqrt{2\pi})$ over $(rU,U]$ (giving $(1-r)U/(s\sqrt{2\pi})=\gamma_rU/\sqrt{2\pi}$). At $r=1$ the integral is $0$; at $r=0$ it is $\le1$.
   - Consequences, for every model in any multifactor representation:
     $$\mathrm{Ce}:=\sum_{i\in I_0}\mathbb E\Big[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}\mathbf 1\{Y_i\le U\}\Big]\le\frac qN\sum_{i\in I_0}\Big(\frac12+\frac{\gamma_iU}{\sqrt{2\pi}}\Big).$$
     Here $Y_i:=-\infty$ when $a_i=0$, so all nulls with $a_i=0$ fall into Ce.
   - **One-sided deterministic DCL**: for every deterministic curve, every mates family and every $r$, $\Delta^{\rm c}(D^*)\le\frac12+\gamma_rU/\sqrt{2\pi}$, with no growth or anti-concentration condition. Proof: drop the baseline ($\rho\ge0$) and use Lemma C. Fubini over a random background then gives the averaged form at no cost. This is item 1 of the requested mechanism: it holds, but it bounds only the central part.
   - The proof never uses linearity of the BH line (item 2 of the requested mechanism): Lei's one-sided Theorem 4.10 is exactly Lemma C plus a cost of $q$ per factor direction for the shell (see `## Adapted from`). The Lemmas 4.5–4.7 machinery is needed only for the two-sided reflected sign.
   - Sources: B3 of the exogenous plan (two-sided, two tails: CHANGED to one tail, recheck); the approved [Lei integrated conditional Gaussian tail-ratio bounds](../assets/lei2026_integrated_conditional_tail_ratios.md), reproved here.

4. [x] **(routine; NEW) Radial strip refinement RS.** For any multifactor representation, any oriented null grouping $(G_h,v_h)$ ([oriented null directional entropy](../definitions/gaussian_oriented_null_directional_entropy.md)) and $0<q<1/2$:
   $$\mathrm{FDR}\le\frac32q\pi_0+\frac{qU}{\sqrt{2\pi}}\,\overline\gamma_0+\frac qN\sum_h\sum_{i\in G_h}\min\Big\{\frac{b_h-U}{s_i\sqrt{2\pi}},\ \log\frac1{\pi_h}\Big\},$$
   with the first entry read as $+\infty$ when $s_i=0$.
   - Proof: the approved entropy proof, with its strip integral $\int_U^{b_h}\phi M_i$ additionally bounded by $(b_h-U)/(s_i\sqrt{2\pi})$, using the pointwise half of Lemma C.
   - Since $\overline\Phi(U+x)\le e^{-Ux}\overline\Phi(U)$, we have $b_h\le U+\log(1/\pi_h)/U$. Hence
     $$\mathrm{FDR}\le\frac{qU}{\sqrt{2\pi}}\Big(\overline\gamma_0+\frac{\mathcal E_s}{U^2}\Big)+\frac32q\pi_0,\qquad \mathcal E_s:=\frac1N\sum_h\sum_{i\in G_h}\frac{\log(1/\pi_h)}{s_i}.$$
   - Corollary RS-c: the target holds along any sequence of models with a grouping satisfying $\mathcal E_s=o(U^2)$ (equivalently $o(\log(1/q))$), or more generally $\min\{\mathcal E_s/U^2,\mathcal E_0/U\}\to0$ group by group. The approved result needs $\mathcal E_0=o(U)$. RS-c allows up to $q^{-o(1)}$ equal null groups when the loadings stay $\le1-\delta$, instead of $e^{o(\sqrt{\log(1/q)})}$.
   - In $\mathfrak B_1$ the oriented groups are the $(g,\pm)$ above.

5. [ ] **(KEY 1, the first gate) Pooled shell lemma PSL in $\mathfrak B_1$.** The exact inequality of `## Goal`: $\mathrm{Sh}\le\eta(q)qU$, uniformly over $\mathfrak B_1$. The cap is free: $\sum_h\mathbb E[\mathrm{FDP}_h\mathbf 1\{Y_h>b_h\}]\le\sum_h\overline\Phi(b_h)=q\pi_0$, where $\mathrm{FDP}_h\le1$ is the partial FDP of group $h$. So PSL is equivalent to the strip form
   $$\mathrm{St}:=\frac qN\sum_{i\in I_0,a_i\ne0}\mathbb E\big[\rho_{r_i}(u_{R_i},Y_i)\,\mathbf 1\{U<Y_i\le b_{h(i)}\}\big]\le\eta(q)qU.$$
   By step 4, St already satisfies this whenever $\mathcal E_s=o(U^2)$. The open regime is therefore: the null mass sits in groups with $\pi_h\le q^{c}$ for a fixed $c>0$ ($b_h-U\ge cU/2$), or with loadings $s_i\to0$.

   - 5a. [ ] **(falsification probe, run first; evidence only)** Design family $\mathfrak D(q,r,H,n_0)$.
     - $H$ identical independent blocks. Each has $n_0$ nulls with $\theta=0$ and loading $r$, anti-loaded loading-one tilt mates (one per unit jump of a deficit curve, at $(1+r)\times$ the jump level, covering the strip $(U,b]$), and optional positive carriers (loading-one and loading $<1$).
     - An independent $a=0$ background in the continuum limit, with counts designed so that its deficit equals the staircase.
     - Evaluate St exactly in level space. Use the top-$200$ order statistics of the $Z_g$ plus the exact mean count of the remaining blocks, as in the evaluator of step 5a of `plan_two_sided_baseline_subtracted_pivotal_probe_20261105`.
     - Grid: $H=\lceil q^{-a}\rceil$ with $a\in\{0.25,0.5,r^2,1,1.5\}$; $r\in\{0.5,0.9,0.95\}$; $q\in\{10^{-8},10^{-16},10^{-30}\}$; then a $(1+12)$-ES over carrier positions and $n_0$.
     - Why this design is the dangerous one: a heuristic that ignores the typical-state anti mates predicts $\mathrm{FDR}/(qU/\sqrt{2\pi})\approx(\sqrt{1+r^2}-r)/\sqrt{1-r^2}$ at $a=r^2$. That exceeds $1$ for $r^2>4/5$ (it is $1.375$ at $r=0.95$). The budget of 5b–5c predicts that this gain is cut back to $o(U)$. The probe decides which.
     - *Stop rule.* (i) Best $\mathrm{St}/(qU/\sqrt{2\pi})\ge0.15$ at all three $q$, not decreasing: PSL is false, and the plan fails at 5. (ii) Moreover, if the full $\mathrm{FDR}/(qU/\sqrt{2\pi})\ge1.15$ at all three $q$, not decreasing: record a refutation candidate of the target and verify it as an exact finite model. The candidate goes to the falsification stage. This plan does not weaken the target.
     - *Pass:* $\le0.05$ at $q=10^{-30}$ and decreasing.
   - 5b. [x] **(routine; deterministic carrier lemma CB, NEW)**
     - Setting. Block $g$, null $i$ oriented so that $a_i=r>0$, $Y=Z_g$. Fix the background, so the deficit curve $D(u_k):=D^*(k)$ is deterministic and nonincreasing in the level. Fix the private noises of the members of $B_g$. Write $v(y)$ for the threshold level $u_{R_i}$ as a function of $y$.
     - Split $B_g\setminus\{i\}$ for $\alpha\in(0,1]$: $\mathcal P_\alpha$ = same-sign members with $|a_j|\ge\alpha$ (this includes the block's other nulls when $r\ge\alpha$); $\mathcal A$ = opposite-sign members; $\mathcal W_\alpha$ = same-sign members with $0\le|a_j|<\alpha$. $P_\alpha(w;y)$, $A(w;y)$, $W_\alpha(w;y)$ are their counts at level $w$.
     - **Claim.** If $y_1<y_2$, $\Delta=y_2-y_1$, $v_1=v(y_1)$ and $v(y_2)>v_1+\alpha\Delta$, put $w'''=\max\{u_k:u_k\le v_1+\alpha\Delta\}$. Then
       $$A(v_1;y_1)+W_\alpha(v_1;y_1)>D(v_1)-D(w'''),$$
       and $A(v_1;y')\ge A(v_1;y_1)$ for every $y'\le y_1$.
     - Proof (to be written out): $v_1$ qualifies at $y_1$, and $w'''<v(y_2)$ does not qualify at $y_2$ (curve reduction, step 5c(i)). For $j\in\mathcal P_\alpha$, $|a_j|\Delta\ge w'''-v_1$ gives $P_\alpha(w''';y_2)\ge P_\alpha(v_1;y_1)$ pointwise in the noises. Subtract.
     - Meaning: wherever the threshold rises faster than slope $\alpha$ (tilt matching has slope $1/r>1$), the block's opposite-sign members are counted at the lower level in every typical state $y'\le y_1$, in number more than the deficit drop over a level window of width $\approx\alpha\Delta$. This is the one-sided, mixed-loading form of R4 in `plan_two_sided_central_deficit_curve_lei_20261105`. It is exactly the information that the flat-staircase counterexample of that plan exploits two-sidedly. One-sidedly the typical state is $y'\le y_1$, not $-y_1$, and anti-loaded members are counted *more* there.
   - 5c. [ ] **(KEY) Pooled budget.** Prove $\mathrm{St}\le\eta(q)qU$ in the open regime by chaining the following items.
     - (i) *(routine; re-included, unchanged) Curve reduction.* $R_i=\max\{k:M_y(k)\ge D^*(k)\}$ and $R^\flat_i=\max\{k:D^*(k)\le0\}$, where $D^*(k)=\min_{j\ge k}(j-1-\beta(j))$, $\beta$ is the background count outside $B_g$, independent of $(Z_g,\varepsilon_{B_g})$, and $M_y$ counts $B_g\setminus\{i\}$. $D^*$ is integer, nondecreasing, has increments in $\{0,1\}$ and satisfies $D^*\le k-1$. $R_i$ is a plateau right end. Source: step 3 and R1 of `plan_two_sided_central_deficit_curve_lei_20261105`. The proof uses only counts, so it holds verbatim for one-sided p-values.
     - (ii) *(routine with check) Tilt localization T.* For $0<r<1$, $U\ge2$ and $y,v\ge U$:
       $$\phi(y)\rho_r(v,y)\le\frac{1+v}{s}\max\Big\{e^{-r^2(v-y/r)^2/(2s^2)},\ e^{-s^2y^2/2}\Big\}.$$
       Checked numerically at planning for $r\in\{0.05,\dots,0.99\}$, $U\in\{2,\dots,20\}$, $y\le5U$, $v\le8U/r$: worst log-ratio $-0.76$. The analytic proof is owed (Mills bounds on both regimes $v\gtrless ry$). Consequence: up to $O(q\pi_0)$, St is at most $\frac qN\sum_i\frac{1}{s_i\sqrt{2\pi}}\,\mathbb E\,|\mathcal T_i|$, where $\mathcal T_i=\{y\in(U,b_{h(i)}]:|v(y)-y/r_i|\le K_qs_i/r_i\}$ is the tilt set, with $K_q=\sqrt{4\log U}$ and polynomial factors absorbed (to be made exact).
     - (iii) *(routine) Tilt slope.* If $y_1<y_2$ both lie in $\mathcal T_i$ and $\Delta\ge4K_qs/(1-r)$, then $v(y_2)-v(y_1)\ge\Delta/r-2K_qs/r>\alpha\Delta$ for every $\alpha\le1$. So 5b applies along every tilt set, with $\alpha=\alpha_0:=\kappa/U$; members with $|a_j|<\kappa/U$ are weak.
     - (iv) *(KEY) Weak members.* $W_{\alpha_0}(v_1;y_1)\le W_{\alpha_0}(v_1;y')+$ (small) in expectation over their noises, for $y'\le y_1\le b$: their counts change by a factor at most $e^{\kappa(b-U)v/U}$. Here this needs $b-U=O(U)$ and a concentration bound for the weak count, uniform in its size.
     - (v) *(KEY) Budget telescoping.* While block $g$ is in its strip, all other blocks $g'$ are, with probability $1-O(Hq\cdot\mathrm{poly}(U))$ when $Hq\le U^{-3}$ (the sparse-extreme regime), in typical states. By 5b and (iv), each $g'$ that tilts at level $w$ on a positive-probability set of its own backgrounds contributes at least $\delta_{g'}(w)$ to $\beta_g(w)$, the essential supremum of its deficit drops. Since $\beta_g(w)\le k(w)-1-D^*_g(w)$ at plateau levels, summing over $g'$ and telescoping in level windows of width $\alpha_0\Delta$ should give $D_g(w)\lesssim\sum_{j\ge0}k(w+j\alpha_0\Delta)/H_{\rm eff}(w)$. Here $H_{\rm eff}(w)$ is the number of blocks that tilt at $w$.
     - (vi) *(routine) Self-count.* If $v(y)=v$, every level $w'<v$ fails, so $D^*(w')>\#\{\text{nulls of }B_g\text{ counted at }w'\}$. Given $Z_g=y$ this count is $\mathrm{Bin}(n_{0,g},\overline\Phi((w'-ry)/s))$. At $w'=v-K_qs/r$ near the tilt its mean is $\ge n_{0,g}\overline\Phi(sy/r+O(K_q))$. A Chernoff bound gives $D^*(w')\ge\frac12n_{0,g}\overline\Phi(\cdot)$ except on an event of probability $e^{-c\,n_{0,g}\overline\Phi(\cdot)}$.
     - (vii) *(KEY) Combination.* (v) and (vi) give $\pi_h\lesssim e^{-(y^2-U^2)/2}\,\mathrm{poly}(U)/(s\,H_{\rm eff})$ for any $y$ in a tilt set of a group of mass $\pi_h$. So, off an event of probability $o(1/U)$ per null, $\mathcal T_i\subset(U,U+L_q/U]$ with $L_q=O(\log U+\log(1/s_i)+\log(1+b_h-U))$. On $(U,U+L_q/U]$ use $\phi(y)\rho_r(v,y)\le\min\{1/(s\sqrt{2\pi}),\ \phi(y)/\overline\Phi(v)\}\le\min\{1/(s\sqrt{2\pi}),\,2+U+L_q/U\}$ (Lemma C, and Mills with $v\ge U$). Hence
       $$\mathrm{St}\le\frac qN\sum_i\frac{L_q}{U}\min\Big\{\frac1{s_i\sqrt{2\pi}},\,3U\Big\}+O(q\pi_0)\le O(q\pi_0L_q)=o(qU).$$
       Two points must be settled here. First, the window $K_q$ of (ii) must be enlarged to $K_{q,i}=\sqrt{2\log(U^2(1+b_h-U)/s_i)}$ so that the off-tilt integral over the whole strip is $O(1)$ per null. Second, for $s_i<1/U$ the two branches of (ii) merge: the tilt set is then $\{v(y)\in[r_iy-K_q/U,\ y/r_i+K_qs_i/r_i]\}$, and at $r=1$ it is $\{v(y)\in[y-K_q/U,y]\}$, since $\rho_1$ is an indicator. The same chain (v)–(vii) must be run on this set.
     - (viii) *(KEY) Dense-extreme regime* $Hq>U^{-3}$. Many blocks are simultaneously in their strips and the threshold is a single level. Show $\mathbb E\sup_v\sum_h\pi_h\rho_{r_h}(v,Y_h)\mathbf 1\{U<Y_h\le b_h\}\le\pi_0(1+o(1))\cdot O(1)$ by a chaining or bracketing bound for this empirical process of independent nonnegative terms of mean $\le\pi_h$ over the level grid, using the caps $\pi_h\rho\le1/q$ and $\pi_h\le\pi_0/H\cdot O(1)$ after grouping. Groups of unequal mass are handled by dyadic mass classes, each class in one regime.

6. [ ] **(routine) Block-class theorem.**
   - In $\mathfrak B_1$: $\mathrm{FDR}=\mathrm{Ce}+\mathrm{Sh}\le\frac q2\pi_0+\frac{qU}{\sqrt{2\pi}}\overline\gamma_0+\eta(q)qU$ (steps 3 and 5). Use $U\le\sqrt{2\log(1/q)}$ (Markov with $\mathbb Ee^{UG}=e^{U^2/2}$, as in the approved entropy proof) and $\overline\gamma_0\le\pi_0\le1$. Then $\mathrm{FDR}\le(1/\sqrt\pi+\varepsilon)q\sqrt{\log(1/q)}$ for $q<q_\varepsilon$, uniformly in $N,G,\theta$, loadings and signs.
   - This step covers, with no further work:
     - B6′, exponentially many null blocks: PSL has no restriction on $G$. Steps 4 and RS-c show which part is already free.
     - Multiplicities: any number of nulls per block, mixed loadings and both signs. These fall into the oriented groups $(g,\pm)$; at most one sign of a block is in its shell.
     - Composite nulls: $\rho^\theta\le\rho$.
     - Nulls with $a_i=0$: they lie in Ce with $\gamma_i=1$.
   - This is an intermediate theorem, not a conclusion of the plan.

7. [ ] **(KEY 2; C3, arbitrary $\Sigma$; missing lemma, no candidate proof)** **Shell decoupling SD.**
   - *Missing inequality.* For every admissible $(N,\theta,\Sigma)$ and $q\le q_0$ there are a multifactor representation $\Sigma=AA^{\mathsf T}+\operatorname{diag}(1-\|a_i\|^2)$ and an oriented null grouping such that $\mathrm{Sh}_{\rm rep}:=\sum_{i\in I_0}\mathbb E[\mathbf 1\{i\in\mathcal R_q\}/(R_q\vee1)\,\mathbf 1\{Y_i>U\}]\le\eta(q)qU$, uniformly in $N$. Step 3 holds for every representation, so SD plus step 3 gives the target directly.
   - *What is plainly missing.*
     - (a) The canonical representation $A=\Sigma^{1/2}$ has $r_i=1$ for all $i$, hence $\mathrm{Ce}=0$ and $\mathrm{Sh}=\mathrm{FDR}$: useless. Exact duplicates force $r_i=1$; they are removed by duplication invariance (A1(f) of `plan_two_sided_exogenous_pivotal_blocks_20261105`). Near-duplicates at correlation $1-\delta$ force $s_i\le\sqrt{2\delta}$, and no invariance removes them.
     - (b) For dense $\Sigma$ every coordinate is a mover of every null, so the baseline-subtracted identity is vacuous. The background in 5c(i) is no longer independent of $Y_h$: by A1(a) of the exogenous plan it is $c_hY_h+W_h$ with $W_h\perp Y_h$. The carrier lemma 5b survives, because it uses only per-member monotonicity in $y$, and the members are now all coordinates with loadings $c_{hj}$.
     - (c) The budget step 5c(v) does **not** survive: it needs "while $h$ is extreme, the other groups are typical", that is, independence of the group factors. With correlated directions, conditionally on $Y_h=y>U$ a group $h'$ has $Y_{h'}\sim N(\rho_{hh'}y,1-\rho_{hh'}^2)$ and can sit in its own tilt region.
   - *Exact gap.* A conditional budget inequality replacing 5c(v): for every Gram matrix of oriented directions, the deficit drops of groups that are conditionally in their tilt states sum to at most $k(w)$ up to $o(k(w))$ on the relevant levels, with an error $o(qU)$ in St uniform in $N$. Alternatively, a comparison lemma reducing an arbitrary $\Sigma$ to a mixture of $\mathfrak B_1$ models with error $o(qU)$ uniform in $N$.
   - Every comparison route tried for this target has failed: the covariance-interpolation certificates of the first three failed plans, and the joint-extremum factor reduction, which is false at $N=3$. Per-null conditioning on $T_{-i}$ is not duplication-robust (idea_0d2e69e0ba3b). Execute step 7 only after step 5 succeeds. Its first task is to state the conditional budget precisely and test it on the near-duplicate family: Lei's equicorrelated nulls, each replaced by a cluster at correlation $1-U^{-4}$.

8. [ ] **(routine) Assembly.** For every admissible model, take the representation of step 7. Then $\mathrm{FDR}=\mathrm{Ce}+\mathrm{Sh}_{\rm rep}\le\frac q2+\frac{qU}{\sqrt{2\pi}}+\eta(q)qU\le(1/\sqrt\pi+\varepsilon)q\sqrt{\log(1/q)}$ for $q<q_\varepsilon$. This is exactly the target statement.

**Failure condition (first unprovable KEY step; no after-the-fact weakening).**
- *At 5a:* the stop rule above. Record the configuration $(q,r,H,n_0$, carrier positions$)$ and the St and FDR ratios.
- *At 5c:* the exact inequality $\mathrm{St}\le\eta(q)qU$ uniformly over $\mathfrak B_1$ is not proved. State which item fails: (iv) weak members, (v) budget telescoping, (vii) combination, or (viii) the dense-extreme empirical process. Name the parameter that breaks uniformity: $Hq$ near $U^{-3}$, $s_i\to0$, the size of the weak-member set, or unequal group masses. If a violating $\mathfrak B_1$ model is found, give it with its hypotheses checked: finite $N$, block-diagonal unit-diagonal PSD (possibly singular) $\Sigma$, nulls $\theta_i\le0$, largest-rank BH, every $q\le q_0$.
- *At 7:* SD is not proved. Report the exact conditional budget that fails and the correlation structure that breaks it.
- Restricting loadings to $\le1-\delta$, the number of blocks to $\le q^{-1}$, or $\Sigma$ to block form are separate ideas and not repairs. A failed plan is not a falsification.

## Verification

**Chain.** Steps 1–2 give, for every null in any multifactor representation, $\mathbb E[\mathbf 1\{i\in\mathcal R\}/(R\vee1)\mid Z]\le\frac qN\mathbb E[\rho_{r_i}(u_{R_i},Y_i)\mid Z]$. Splitting at $Y_i=U$ gives $\mathrm{FDR}=\mathrm{Ce}+\mathrm{Sh}$ exactly. Step 3 bounds Ce by $\frac qN\sum(\frac12+\gamma_iU/\sqrt{2\pi})$ for every model, every background and every curve, which also settles the deterministic DCL. Then:
- Step 5 bounds Sh by $\eta(q)qU$ in $\mathfrak B_1$, which gives step 6.
- Step 7 supplies, for every $\Sigma$, a representation with $\mathrm{Sh}_{\rm rep}\le\eta(q)qU$.
- Step 8 is then the exact target: every $\varepsilon$, every $q<q_\varepsilon$, every finite $N$, every $\theta$ with nulls $\theta_i\le0$, every unit-diagonal PSD (singular) $\Sigma$, the constant $1/\sqrt\pi$, and largest-rank BH. Uniformity holds because no constant in steps 3, 5 and 7 may depend on $N$, $G$, means, loadings or $\Sigma$.

**For a fresh referee, check:**
- (1) the one-tail density identity and the two integrals of Lemma C ($\frac12$ and $(1-r)U/(s\sqrt{2\pi})=\gamma_rU/\sqrt{2\pi}$), including the endpoints $r\in\{0,1\}$;
- (2) $b_h\le U+\log(1/\pi_h)/U$, from $\overline\Phi(U+x)\le e^{-Ux-x^2/2}\overline\Phi(U)$;
- (3) the monotonicity step of 5b, $|a_j|\Delta\ge w'''-v_1$ for $j\in\mathcal P_\alpha$, and that $w'''<v(y_2)$ makes $w'''$ non-qualifying (smallest qualifying level, plateau right ends);
- (4) the analytic proof of T in 5c(ii) on both regimes $v\gtrless ry$;
- (5) in 5c(v), that "other blocks typical" is used only on the sparse-extreme event, whose complement costs $O(Hq\,\mathrm{poly}(U))$;
- (6) that 5c(viii) is a genuine uniform empirical-process bound, not a per-$v$ expectation;
- (7) in step 7, that the representation is chosen per model and that Lemma C is applied in that representation.

**Numerics are evidence only:** the step 0 table, the T check, and 5a.

## Assumed definitions

- All definitions used are approved: [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary BH step-up](../definitions/benjamini_hochberg_step_up.md), [false discovery rate](../definitions/false_discovery_rate.md), [uniform worst-case Gaussian BH FDR](../definitions/gaussian_worst_case_bh_fdr.md), [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md), [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md), and [oriented null directional entropy](../definitions/gaussian_oriented_null_directional_entropy.md).
- The block class $\mathfrak B_1$, Sh, St, Ce, tilt sets and the deficit curve are defined inside this plan. They are not definition nodes.
- The target has empty `depends_on`, so no result is cited as a black box. Every borrowed step is reproved (see `## Adapted from`).
- No unproved dependency is assumed. The draft [Lei one-sided common-factor bound](../assets/lei2026_one_sided_common_factor_upper.md) is adapted only for its proof structure. Sibling-project files are read-only references, and their approval does not transfer.

## Adapted from

- **[One-sided Gaussian BH bound from oriented null directional entropy](../assets/directional_entropy_one_sided_fdr_bound.md)** (approved).
  - Its hypotheses hold verbatim in any multifactor representation with $0<q<1/2$; $\mathfrak B_1$ is one.
  - Reused, reproved in steps 1–4: the forced-zero identity, conditional independence given $Z$, composite domination $F^{\theta}\le F^0$, the central integral, the strip $\int_U^{b_h}\phi M_i\le\log(1/\pi_h)$, and the group cap $\overline\Phi(b_h)=q\pi_h$.
  - Changed: the strip is additionally bounded by $(b_h-U)/(s_i\sqrt{2\pi})$ (step 4). Its strip and cap are kept only as the cap of step 5; the open part of the strip is replaced by PSL.
- **[Lei conditional leave-one-out FDP bound](../assets/lei2026_conditional_fdp_bound.md)** (approved): the forced-zero identity of step 1, unchanged for one-sided p-values.
- **[Lei integrated conditional Gaussian tail-ratio bounds](../assets/lei2026_integrated_conditional_tail_ratios.md)** (approved): its one-sided central integral, reproved in step 3 by the one-tail density identity. Change: the pointwise form $\phi\rho\le1/(s\sqrt{2\pi})$ is also extracted and used in steps 4 and 5c.
- **[Lei one-sided common-factor bound](../assets/lei2026_one_sided_common_factor_upper.md)** (draft; source Theorem 4.10, Section 4.3).
  - Its proof structure: central sup form, plus $\mathbb P(Y>U)=q$ per factor direction. It uses no line-specific lemma.
  - With one direction the shell costs $q$. With many directions, that per-direction cost is exactly what fails; this plan replaces it by steps 4–5.
- Reused proved steps from plans of the two-sided target, reproved here with their Progress sources:
  - (BH0) and BSP (`plan_two_sided_baseline_subtracted_pivotal_probe_20261105`, step 3);
  - A1(a),(c),(f) and B1, B3 (`plan_two_sided_exogenous_pivotal_blocks_20261105`), with the one-sided kernel substituted and flagged for recheck in steps 2–3;
  - the curve reduction and R1, R4 (`plan_two_sided_central_deficit_curve_lei_20261105`, step 3 and 6a), unchanged in step 5c(i) and generalized in 5b.
  - The averaged-flatness plan's MLR rigidity (`plan_two_sided_averaged_flatness_exclusion_20261105`, 6b–6c; idea_a4ba452bf4a7) is a fallback tool for 5c(viii) if the background must be shown not to hug the line.
- Sibling (read-only, cited by path; approval does not transfer):
  - `/Users/xiaosheng/Desktop/Research/Lihua_conjecture_claude/BH_FDR_Claude_Independent/research/assets/onesided_direction_entropy_upper.md` (the analogue of the approved entropy bound);
  - `.../onesided_block_factor_sharp_upper.md` (the block statement that step 6 targets, parked there);
  - `.../block_carrier_excess_lemma.md` (its pooled level-sum bound $(\Sigma^{**})$).
  - This plan differs from $(\Sigma^{**})$ in two ways: it localizes the shell gain to tilt sets (5c(ii)), and it converts tilting into typical-state counts by the explicit lemma 5b rather than by rank-share sums.

## Difference from failed plans

- **plan_gaussian_bh_one_sided_fixed_alternative_schur_budget_20261104:** that plan interpolated the covariance with a Schur-complement certificate (R), refuted by an all-null equicorrelation family and an alternative Gram family. This plan uses no covariance interpolation. It splits each null by its own factor value, so the central part is bounded for every covariance, and the whole difficulty is isolated in the shell.
- **plan_gaussian_bh_one_sided_global_corner_budget_20261104:** that plan used a diagonal SDP budget for the integrated corner matrix, refuted with growth like $\log N$ at a fixed level. No PSD-completion or trace certificate is used here. The bounds are scalar and conditional on factors, so no supremum over test matrices $\Gamma$ appears.
- **plan_gaussian_bh_one_sided_integrated_transmission_lp_20261104:** that plan built a finite Stein-flux LP (IT64), refuted at $u=10$ by a two-coordinate model. This plan has no divergence field or face constraints. Its first gate is a probabilistic pooled bound, tested numerically on the adversarial block family before any proof is attempted.
- **plan_gaussian_bh_one_sided_stein_transmission_capacity_20261104:** that plan used a Stein transmission certificate with a location-envelope budget (CS64), refuted by a three-cell analytic separation. This plan uses no transmission ansatz. The only deterministic lemma (5b) is a monotone counting inequality checked directly from the BH rule.
- **plan_gaussian_bh_one_sided_joint_extremum_factor_reduction_20261104:** that plan relied on a joint extremal reduction to one signed factor (E), false at $N=3$. This plan makes no extremal or least-favourable reduction. The block class is treated directly with any number of blocks, and the passage to arbitrary $\Sigma$ is stated as the explicit open lemma SD (step 7), with its exact gap named.

## Progress

Execution started 2026-11-06 (worker exec7). Order fixed by the driver: step 5a probe first, then steps 1–4, then 5b–5c, 6–8.

- 5a done (no refutation candidate; section below). Steps 1–4 and 5b proved (sections below). 5c(v) not proved: the plan stops at step 5 (see `## Failure`). Steps 6–8 not reached.

### Steps 1–3 (written out in full; settle checklist items 1, 2, 3)

Notation as in `## Plan`; $N$ tests, $0<q<1/2$, $U=\overline\Phi^{-1}(q)$, $t_k=qk/N$, $u_k=\overline\Phi^{-1}(t_k)\ge U$. All statements are for an arbitrary [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) $T_i=\theta_i+a_i^{\mathsf T}Z+s_i\varepsilon_i$, $r_i=\|a_i\|$, $s_i=\sqrt{1-r_i^2}$; $\mathfrak B_1$ is the special case of step 0.

**Step 1 (forced-zero identity).** Fix $p\in[0,1]^N$ and $i$. For any vector $p'$ write $R(p')=\widehat k_q(p')$ (BH definition). *Claim 0:* $R(p')=|\{j:p'_j\le qR(p')/N\}|$. Indeed, if $k=R(p')\ge1$ then $p'_{(k)}\le qk/N$ so at least $k$ coordinates are $\le qk/N$; if $c>k$ coordinates were $\le qk/N$, then $p'_{(c)}\le qk/N\le qc/N$ and $c$ would qualify, contradicting maximality; for $k=0$ the rejection set is empty by definition. Let $p^{(i)}$ be $p$ with $p_i$ replaced by $0$ and $R_i=R(p^{(i)})$. Then $p^{(i)}_{(1)}=0\le q/N$, so $R_i\ge1$; $R_i$ is a function of $(p_j)_{j\ne i}$; and $R_i\ge R:=R(p)$, because lowering a coordinate does not increase any order statistic, so every rank qualifying for $p$ qualifies for $p^{(i)}$. *Identity:* $\mathbf 1\{i\in\mathcal R_q\}/(R\vee1)=\mathbf 1\{p_i\le t_{R_i}\}/R_i$. If $i\in\mathcal R_q$ then $R\ge1$ and $p_i\le t_R$; with $k=R_i$, $p^{(i)}$ has at least $k$ coordinates $\le t_k$ (Claim 0), and restoring $p_i\le t_R\le t_k$ keeps them $\le t_k$, so $k$ qualifies for $p$, $k\le R$, hence $R_i=R$ and both sides equal $1/R$. If $i\notin\mathcal R_q$ but $p_i\le t_{R_i}$, restoring $p_i$ keeps at least $R_i$ coordinates $\le t_{R_i}$, so $R\ge R_i$, $R=R_i\ge1$ and $p_i\le t_R$, i.e. $i\in\mathcal R_q$, a contradiction. So both sides vanish. This covers ties, threshold equalities and $R=0$. $\square$

**Step 2 (conditional formula; one-sided composite domination).** (a) For $s>0$ put $\rho^\theta_r(v,y)=\overline\Phi((v-\theta-ry)/s)/\overline\Phi(v)$; for $r=1$, $\rho^\theta_1(v,y)=\mathbf 1\{\theta+y\ge v\}/\overline\Phi(v)$. Let $Y_i=a_i^{\mathsf T}Z/r_i$ if $r_i>0$ (any fixed unit-vector projection if $r_i=0$). Given $Z$ the coordinates are independent, so $p_i=\overline\Phi(T_i)$ and $R_i$ (a function of $(p_j)_{j\ne i}$) are conditionally independent. Since $\overline\Phi$ is a continuous strictly decreasing bijection $\mathbb R\to(0,1)$, $\{p_i\le t\}=\{T_i\ge\overline\Phi^{-1}(t)\}$, whose conditional probability given $Z$ is $\overline\Phi((\overline\Phi^{-1}(t)-\theta_i-r_iY_i)/s_i)$ ($s_i>0$) or $\mathbf 1\{\theta_i+Y_i\ge\overline\Phi^{-1}(t)\}$ ($s_i=0$). Taking $t=t_{R_i}=\overline\Phi(u_{R_i})$ in step 1 and conditioning first on $(Z,(\varepsilon_j)_{j\ne i})$:
$$\mathbb E\Big[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}\Big|Z\Big]=\mathbb E\Big[\frac{\overline\Phi(u_{R_i})\rho^{\theta_i}_{r_i}(u_{R_i},Y_i)}{R_i}\Big|Z\Big]=\frac qN\mathbb E\big[\rho^{\theta_i}_{r_i}(u_{R_i},Y_i)\big|Z\big],$$
using $\overline\Phi(u_k)/k=q/N$. *Domination:* $\theta_i\le0$ gives $(v-\theta_i-ry)/s\ge(v-ry)/s$, and $\overline\Phi$ is decreasing, so $\rho^{\theta_i}_r\le\rho_r:=\rho^0_r$; at $r=1$, $\{\theta_i+y\ge v\}\subset\{y\ge v\}$. (b) If $R'$ is a random rank independent of $Y_i$ and of $\varepsilon_i$, then conditioning on $R'$ and using $r_iY_i+s_i\varepsilon_i\sim N(0,1)$, $\mathbb E[\rho^{\theta_i}_{r_i}(u_{R'},Y_i)\mid R']=\overline\Phi(u_{R'}-\theta_i)/\overline\Phi(u_{R'})\le1$ (equality iff $\theta_i=0$). $\square$
Consequence used below: with $\mathrm{Ce}=\sum_{i\in I_0}\mathbb E[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}\mathbf 1\{Y_i\le U\}]$ and $\mathrm{Sh}$ the same with $\mathbf 1\{Y_i>U\}$ (for $r_i=0$ we put $Y_i:=-\infty$, so these nulls are in Ce), $\mathrm{FDR}=\mathrm{Ce}+\mathrm{Sh}$ exactly, and since $Y_i$ is $Z$-measurable, $\mathrm{Ce}\le\frac qN\sum_{i\in I_0}\mathbb E[\rho_{r_i}(u_{R_i},Y_i)\mathbf 1\{Y_i\le U\}]$, likewise for Sh.

**Step 3 (Lemma C).** *Claim.* For $r\in[0,1)$, $s=\sqrt{1-r^2}$, all real $y$ and all $v\ge U$:
$$\phi(y)\rho_r(v,y)\le\frac1s\phi\Big(\frac{(rv-y)_+}{s}\Big)\le\frac1{s\sqrt{2\pi}},\qquad\int_{-\infty}^U\phi(y)\sup_{v\ge U}\rho_r(v,y)\,dy\le\frac12+\frac{\gamma_rU}{\sqrt{2\pi}} .$$
*Proof.* The standard bivariate normal density with correlation $r$ factors both ways, $\phi(x)s^{-1}\phi((y-rx)/s)=\phi(y)s^{-1}\phi((x-ry)/s)$; integrating over $x\ge v$ gives $\phi(y)\overline\Phi((v-ry)/s)=\int_v^\infty\phi(x)s^{-1}\phi((y-rx)/s)dx$. For $x\ge v$, $|y-rx|\ge(rx-y)_+\ge(rv-y)_+$ ($r\ge0$), and $\phi$ is decreasing in $|\cdot|$, so the integral is $\le s^{-1}\phi((rv-y)_+/s)\overline\Phi(v)$; divide by $\overline\Phi(v)$. For $v\ge U$, $(rv-y)_+\ge(rU-y)_+$, so $\sup_{v\ge U}\phi(y)\rho_r(v,y)\le s^{-1}\phi((rU-y)_+/s)$ (the supremum is measurable: $\rho_r(\cdot,y)$ is continuous, take rational $v$). Then $\int_{-\infty}^{rU}s^{-1}\phi((rU-y)/s)dy=\frac12$ and $\int_{rU}^U s^{-1}(2\pi)^{-1/2}dy=\frac{(1-r)U}{s\sqrt{2\pi}}=\frac{\gamma_rU}{\sqrt{2\pi}}$, since $(1-r)/\sqrt{1-r^2}=\sqrt{(1-r)/(1+r)}$. This includes $r=0$ ($s=1$). At $r=1$, $\rho_1(v,y)=0$ for $y<U\le v$, so the integral is $0$. $\square$
*Consequences.* (i) For $0<q\le1/10$ and every multifactor model, $\mathrm{Ce}\le\frac qN\sum_{i\in I_0}(\frac12+\frac{\gamma_iU}{\sqrt{2\pi}})$: for $r_i>0$ bound $\rho_{r_i}(u_{R_i},Y_i)\mathbf 1\{Y_i\le U\}\le\sup_{v\ge U}\rho_{r_i}(v,Y_i)\mathbf 1\{Y_i\le U\}$ (as $u_{R_i}\ge U$) and integrate against the standard normal law of $Y_i$; for $r_i=0$, $\rho_0\equiv1$ and $1\le\frac12+\frac U{\sqrt{2\pi}}$ because $q\le1/10<\overline\Phi(\sqrt{\pi/2})$. (ii) One-sided deterministic DCL: for any (random or deterministic) threshold map, $\int_{y\le U}\phi(y)[\rho_r(u(y),y)-\rho_r(u_f,y)]dy\le\frac12+\frac{\gamma_rU}{\sqrt{2\pi}}$, dropping the nonnegative baseline. Linearity of the BH line is never used.
- [x] Step 1 proved above. [x] Step 2 proved above (recheck of the one-sided kernel done: only the one-tail event $\{T_i\ge u\}$ enters). [x] Step 3 proved above.

### Step 4 (RS, radial strip refinement; written out in full; settles checklist item 4)

*Claim.* For any multifactor representation, any oriented null grouping $(G_h,v_h)_{h\le H}$ (as in the [oriented null directional entropy](../definitions/gaussian_oriented_null_directional_entropy.md) definition, $m_0>0$) and $0<q<1/2$, with $\pi_h=|G_h|/N$, $b_h=\overline\Phi^{-1}(q\pi_h)$,
$$\mathrm{FDR}\le\frac32q\pi_0+\frac{qU}{\sqrt{2\pi}}\overline\gamma_0+q\,\mathcal E_{\min},\qquad \mathcal E_{\min}:=\frac1N\sum_h\sum_{i\in G_h}\min\Big\{\frac{b_h-U}{s_i\sqrt{2\pi}},\ \log\frac1{\pi_h}\Big\}$$
(first entry $+\infty$ when $s_i=0$), and $b_h-U\le\log(1/\pi_h)/U$, so $\mathcal E_{\min}\le\frac1N\sum_h\sum_{i\in G_h}\min\{\frac{\log(1/\pi_h)}{Us_i\sqrt{2\pi}},\log\frac1{\pi_h}\}\le\frac{\mathcal E_s}{U\sqrt{2\pi}}$ with $\mathcal E_s=\frac1N\sum_h\sum_{i\in G_h}\log(1/\pi_h)/s_i$.

*Proof.* Put $M_i(y)=\sup_{v\ge U}\rho^{\theta_i}_{r_i}(v,y)$; this is the function $\sup_{0<t\le q}F^{\theta_i}_{r_i,y}(t)/t$ of the approved entropy proof (substitute $t=\overline\Phi(v)$, a bijection of $(0,q]$ onto $[U,\infty)$). For $i\in G_h$ with $r_i>0$, $Y_i=Y_h=v_h^{\mathsf T}Z$; for $r_i=0$, $M_i$ is constant. By steps 1–2, $\mathbb E[\mathrm{FDP}_h\mid Z]\le\frac qN\sum_{i\in G_h}M_i(Y_h)$, with $\mathrm{FDP}_h=\sum_{i\in G_h}\mathbf 1\{i\in\mathcal R_q\}/(R\vee1)\le1$. Split each $\mathrm{FDP}_h$ at $\{Y_h\le b_h\}$ (a $Z$-measurable event):
- $\mathbb E[\mathrm{FDP}_h\mathbf 1\{Y_h>b_h\}]\le\overline\Phi(b_h)=q\pi_h$.
- $\mathbb E[\mathrm{FDP}_h\mathbf 1\{Y_h\le U\}]\le\frac qN\sum_{i\in G_h}\int_{-\infty}^U\phi M_i\le\frac qN\sum_{i\in G_h}(\frac12+\frac{\gamma_iU}{\sqrt{2\pi}})$: by $M_i\le\sup_{v\ge U}\rho_{r_i}(v,\cdot)$ (step 2) and Lemma C; for $r_i=0$, $\int_{-\infty}^U\phi M_i\le\Phi(U)=1-q$, and $1-q\le\frac12+\frac U{\sqrt{2\pi}}$ since $\Phi(U)-\frac12=\int_0^U\phi\le U\phi(0)$.
- $\mathbb E[\mathrm{FDP}_h\mathbf 1\{U<Y_h\le b_h\}]\le\frac qN\sum_{i\in G_h}\int_U^{b_h}\phi M_i$, and for each $i$ this integral is at most both $\log(1/\pi_h)$ (approved entropy proof: $M_i(y)\le1/\overline\Phi(y)$ and $\int_U^{b_h}\phi/\overline\Phi=\log(\overline\Phi(U)/\overline\Phi(b_h))$) and, when $s_i>0$, $(b_h-U)/(s_i\sqrt{2\pi})$, by the pointwise half of Lemma C, $\phi(y)\rho_{r_i}(v,y)\le1/(s_i\sqrt{2\pi})$ for every $v$ ($r_i=0$ included, $s_i=1$).

Summing the three bounds over $i$ and $h$ (with $\sum_h|G_h|/N=\pi_0$) gives $\mathrm{FDR}\le q\pi_0+\frac q2\pi_0+\frac{qU}{\sqrt{2\pi}}\overline\gamma_0+q\mathcal E_{\min}$. Finally $\overline\Phi(U+x)=\int_U^\infty\phi(t+x)dt=\int_U^\infty\phi(t)e^{-tx-x^2/2}dt\le e^{-Ux-x^2/2}\overline\Phi(U)$ for $x\ge0$; at $x=\log(1/\pi_h)/U$ this is $\le q\pi_h=\overline\Phi(b_h)$, so $b_h\le U+\log(1/\pi_h)/U$. $\square$

*Corollary RS-c.* Along any sequence $q\downarrow0$ of models and groupings with $\mathcal E_{\min}=o(\sqrt{\log(1/q)})$ — in particular whenever $\mathcal E_s=o(\log(1/q))$, or $\mathcal E_0=o(\sqrt{\log(1/q)})$ — $\limsup\mathrm{FDR}/(q\sqrt{\log(1/q)})\le1/\sqrt\pi$. Proof: $\overline\gamma_0\le\pi_0\le1$, $U\le\sqrt{2\log(1/q)}$ (Markov, as in the approved entropy proof), so $\mathrm{FDR}/(q\sqrt L)\le\frac3{2\sqrt L}+\frac1{\sqrt\pi}+\frac{\mathcal E_{\min}}{\sqrt L}$, $L=\log(1/q)$; and $\mathcal E_{\min}\le\mathcal E_s/(U\sqrt{2\pi})$ with $U\to\infty$, $U\ge\sqrt{\log(1/q)}$ for small $q$ (since $\overline\Phi(x)\ge\phi(x)x/(1+x^2)$). Example: $H$ equal groups with $s_i\ge\delta$ give $\mathcal E_s\le\pi_0\log H/\delta$, so $H=q^{-o(1)}$ suffices for fixed $\delta$.
- [x] Step 4 proved above.

### Step 5a (falsification probe; evidence only)

*Model actually evaluated* (family $\mathfrak D$ of 5a, in its most adversary-friendly continuum form). $H=\lceil q^{-a}\rceil$ iid blocks; block $g$ = $n_0$ nulls ($\theta=0$, loading $r$ on $Z_g$) plus anti-loaded loading-one mates $T_j=\mu_j-Z_g$, one per unit jump of a deficit curve $D$ at $\mu_j=(1+r)\times$(jump level), so that a block in state $y$ counts exactly $D(y/r)$ mates at level $y/r$ (tilt matching $v(y)=y/r$). Counts are scaled by $M\to\infty$ inside blocks (fractions of $N$, $k(w)/N=\overline\Phi(w)/q$). The other $H-1$ blocks enter through their typical-state mean count $(H-1)\mathbb E\,D((w+Z)/(1+r))+\pi_0\overline\Phi(w)$ (LLN; fluctuations ignored, which favours the adversary). The background is a **perfect deterministic count** $G(w)=k(w)-\mathrm{others}(w)-D(w)-\epsilon$ on the designed level window $[w_a,v_{\max}]$ (not realizable by any Gaussian model — it is a noise-free loading-one block frozen at $Z_b=0$; it favours the adversary), with $\overline\Phi(w_a)=q(1-\pi_0)$ fixing the null fraction $\pi_0$. Feasibility forces $G\ge0$ (and $G$ nonincreasing, checked). FDR is computed by the exact formula of step 2(a): $\mathrm{FDR}/q=\pi_0\int\phi(y)\rho_r(v(y),y)\,dy$, $v(y)$ the smallest qualifying level on a grid of step $10^{-3}$, $y$-grid $3\cdot10^{-3}$. Scripts: `exec7/probe5a2.py` (uniform jump density) and `exec7/probe5a3.py` (curves $D(x)=\min\{B,A e^{-\beta(x^2-v_{\max}^2)/2}\}$, $A=\lambda(\pi_0/H)\overline\Phi(v_{\max}s)$, $B$ = $0.9\times$ largest feasible) in this session's scratchpad.

*Mechanism found (why the planner's heuristic fails; heuristic derivation, not a proof).* For block $g$ in state $y$ to have threshold $v=v(y)$ (all lower levels failing), (i) its own nulls must not qualify a level $w<v$: near $w=v^-$ this needs $D(v^-)\gtrsim(\pi_0/H)\overline\Phi((v-ry)/s)$; (ii) the anti mates that fill $D(v)$ in state $y$ have $\mu_j\ge v+y$, so in every typical state ($Z_{g'}=O(1)$) each other block counts at least $D(v)$ of its own copies at every level $w<v$; since no level below $v$ may qualify, $(H-1)D(v)<k(v)$ (the background is $\ge0$). Combining, $\pi_0\frac{H-1}{H}\overline\Phi((v-ry)/s)\lesssim\overline\Phi(v)/q$. On the tilt line $v=y/r$ this reads $\pi_0\overline\Phi(ys/r)\lesssim\overline\Phi(y/r)/q$, i.e. $e^{y^2/2}\lesssim s/(q\pi_0)\cdot\mathrm{poly}$, i.e. $y\le U+O(\log(U/(s\pi_0))/U)$: **the shell tilt is killed for every $H\ge2$, independently of $a$**. The heuristic $(\sqrt{1+r^2}-r)/\sqrt{1-r^2}$ assumed the tilt continues to $b=U\sqrt{1+a}$; that ignores (ii) (typical-state counting of the other blocks' copies). In the central window the same budget leaves only a short tilt interval (for $v_{\max}=tU$, tilt only for $v\in(\max\{w_a,U\sqrt{t^2-1}/s\},tU]$), so even the central gain is far below $\gamma_r U/\sqrt{2\pi}$.

*Numbers* (`exec7/probe5a3.py`, output `exec7/probe5a3_out.txt`; best design over $t=v_{\max}/U\in\{1.1,1.25,\sqrt{2-r^2},1/r,\sqrt{1+a}/r\}$, $\beta\in\{s^2,1\}$, $\lambda=3$, $\pi_0=0.9$; the results are identical for $a\in\{0.25,r^2,1.5\}$, i.e. $H=q^{-a}$ drops out, as the mechanism predicts). Columns: full $\mathrm{FDR}/(q\sqrt{\log(1/q)}/\sqrt\pi)$; $\mathrm{St}/(qU/\sqrt{2\pi})$ (non-baseline-subtracted, as in the stop rule); shell gain over the fixed-threshold baseline, in units of $qU/\sqrt{2\pi}$; tilt interval in $y/U$.

| $q$ | $r$ | FDR / target | St$/(qU/\sqrt{2\pi})$ | shell gain | tilt $y/U$ |
|---|---|---|---|---|---|
| $10^{-8}$ | 0.5 | 0.398 | 0.000 | 0.0000 | [0.519, 0.688] |
| $10^{-8}$ | 0.75 | 0.385 | 0.028 | 0.0000 | [0.788, 0.886] |
| $10^{-8}$ | 0.9 | 0.372 | 0.176 | 0.0009 | [0.953, 1.010] |
| $10^{-8}$ | 0.95 | 0.372 | 0.303 | 0.0001 | [1.008, 1.022] |
| $10^{-16}$ | 0.5 | 0.290 | 0.000 | 0.0000 | [0.506, 0.632] |
| $10^{-16}$ | 0.75 | 0.268 | 0.001 | 0.0000 | [0.766, 0.824] |
| $10^{-16}$ | 0.9 | 0.263 | 0.040 | 0.0000 | [0.923, 0.936] |
| $10^{-16}$ | 0.95 | 0.263 | 0.122 | 0.0005 | [0.977, 0.986] |
| $10^{-30}$ | 0.5 | 0.237 | 0.000 | 0.0000 | [0.501, 0.629] |
| $10^{-30}$ | 0.75 | 0.209 | 0.000 | 0.0000 | [0.757, 0.827] |
| $10^{-30}$ | 0.9 | 0.192 | 0.004 | 0.0000 | [0.911, 0.920] |
| $10^{-30}$ | 0.95 | 0.192 | 0.034 | 0.0000 | [0.963, 0.970] |

The nonzero St values at $r\ge0.9$ are the fixed-threshold baseline $\int_{y>U}\phi\rho_r(w_a,y)$, which is $O(1)$ in units of $q$ and decreases like $1/U$ ($0.303\to0.122\to0.034$ at $r=0.95$). The uniform-density curves of `probe5a2.py` give no tilt at all (FDR$/q=\pi_0$ to 3 digits; e.g. $q=10^{-8}$, $r=0.95$: FDR/target $0.372$). Feasibility: all three $q$ are feasible in this continuum form (exact conditional formula, deterministic given the design; cost a few seconds per design at $q=10^{-8}$, about a minute at $q=10^{-30}$); an exact finite-$N$ Monte Carlo of the same family is not feasible at these $q$ and was not attempted.

*Verdict.* Stop rule (i) not met: no St ratio $\ge0.15$ at all three $q$ without decreasing (best $0.303\to0.122\to0.034$). Stop rule (ii) not met: full FDR$/$target $\le0.40$ everywhere and decreasing. Pass criterion of 5a: St $\le0.05$ at $q=10^{-30}$ and decreasing — met (best $0.034$). **No refutation candidate.** The heuristic $(\sqrt{1+r^2}-r)/\sqrt{1-r^2}>1$ fails because of typical-state counting of the other blocks' copies (mechanism above); the evaluator keeps every hypothesis that matters for this conclusion (unit variances, $\theta=0$ nulls, largest-rank BH) and relaxes only realizability of the background, in the adversary's favour.

### Step 5b (carrier lemma CB; written out in full; settles checklist item 5b)

*Setting.* $\mathfrak B_1$, block $g$, null $i\in B_g$ with $a_i=r>0$ (the case $a_i<0$ is the same after replacing $Z_g$ by $-Z_g$), $y$ = value of $Z_g$. Condition on all variables except $Z_g$: the other blocks' factors, all private noises (including those of $B_g$). Then $\beta(w):=\#\{j\notin B_g:T_j\ge w\}$ is fixed, and for $j\in B_g$, $T_j(y)=\theta_j+a_jy+s_j\varepsilon_j$ is a deterministic affine function of $y$. Let $M_y(w)=\#\{j\in B_g\setminus\{i\}:T_j(y)\ge w\}$. By step 1 (with $p_i$ forced to $0$) the forced-zero rank is $R_i(y)=\max\{k\le N:\beta(u_k)+M_y(u_k)+1\ge k\}$ (the forced coordinate is counted at every level; Claim 0 of step 1 identifies the BH rank with the largest $k$ having at least $k$ coordinates at levels $\ge u_k$). Put $v(y)=u_{R_i(y)}$ and the raw deficit $D(k)=k-1-\beta(u_k)$. Split $B_g\setminus\{i\}$, for $\alpha\in(0,1]$, into $\mathcal P_\alpha=\{a_j\ge\alpha\}$, $\mathcal A=\{a_j<0\}$, $\mathcal W_\alpha=\{0\le a_j<\alpha\}$, with counts $P_\alpha(w;y),A(w;y),W_\alpha(w;y)$.

*Claim.* Let $y_1<y_2$, $\Delta=y_2-y_1$, $k_1=R_i(y_1)$, $v_1=u_{k_1}$, and suppose $v(y_2)>v_1+\alpha\Delta$. Let $k'''=\min\{k:u_k\le v_1+\alpha\Delta\}$ and $w'''=u_{k'''}$. Then
$$A(v_1;y_1)+W_\alpha(v_1;y_1)>D(k_1)-D(k''')=(k_1-k''')-(\beta(v_1)-\beta(w''')),$$
and $A(v_1;y')\ge A(v_1;y_1)$ for every $y'\le y_1$.

*Proof.* $k'''\le k_1$ since $u_{k_1}=v_1\le v_1+\alpha\Delta$. As $u_{R_i(y_2)}=v(y_2)>v_1+\alpha\Delta\ge w'''=u_{k'''}$ and $u$ is decreasing in the rank, $R_i(y_2)<k'''$, so $k'''$ does not qualify at $y_2$ (it is larger than the largest qualifying rank): $\beta(w''')+M_{y_2}(w''')+1<k'''$. Rank $k_1$ qualifies at $y_1$: $\beta(v_1)+M_{y_1}(v_1)+1\ge k_1$. Subtracting, $M_{y_1}(v_1)-M_{y_2}(w''')>D(k_1)-D(k''')$. For $j\in\mathcal P_\alpha$ with $T_j(y_1)\ge v_1$: $T_j(y_2)=T_j(y_1)+a_j\Delta\ge v_1+\alpha\Delta\ge w'''$, so $M_{y_2}(w''')\ge P_\alpha(w''';y_2)\ge P_\alpha(v_1;y_1)$. Hence $A(v_1;y_1)+W_\alpha(v_1;y_1)=M_{y_1}(v_1)-P_\alpha(v_1;y_1)\ge M_{y_1}(v_1)-M_{y_2}(w''')>D(k_1)-D(k''')$. Finally for $j\in\mathcal A$ and $y'\le y_1$, $T_j(y')=T_j(y_1)+a_j(y'-y_1)\ge T_j(y_1)$. $\square$
(The statement is pointwise in the conditioning variables; nothing about their law is used.)

### Step 5c(ii) (tilt localization T; analytic proof, replacing the planner's numerical check)

*Claim.* For $r\in(0,1)$, $v\ge0$ and real $y$: if $v\ge ry$, $\phi(y)\rho_r(v,y)\le\frac{1+v}{2}e^{-(y-rv)^2/(2s^2)}$; if $v<ry$ (so $y>0$), $\phi(y)\rho_r(v,y)\le(1+v)e^{-s^2y^2/2}$. Together with Lemma C ($\phi(y)\rho_r(v,y)\le s^{-1}\phi((rv-y)/s)$ when $rv\ge y$) this localizes the shell integrand to the tilt set $|y-rv|\lesssim s\sqrt{2\log(1+v)}$ up to $(1+v)e^{-s^2U^2/2}$.
*Proof.* Two Mills facts for $x\ge0$: $\overline\Phi(x)\le\sqrt{\pi/2}\,\phi(x)$ ($\overline\Phi/\phi$ is decreasing and equals $\sqrt{\pi/2}$ at $0$), and $\phi(x)/\overline\Phi(x)\le(x+\sqrt{x^2+4})/2\le1+x$. Algebra: $y^2+(v-ry)^2/s^2-v^2=(y-rv)^2/s^2$, so $\phi(y)\phi((v-ry)/s)/\phi(v)=\phi((y-rv)/s)$. If $v\ge ry$: $\phi(y)\rho_r\le\phi(y)\sqrt{\pi/2}\phi((v-ry)/s)(1+v)/\phi(v)=\sqrt{\pi/2}(1+v)\phi((y-rv)/s)$, and $\sqrt{\pi/2}/\sqrt{2\pi}=\frac12$. If $v<ry$: $\overline\Phi(\cdot)\le1$ and $\phi(y)/\overline\Phi(v)\le(1+v)e^{-(y^2-v^2)/2}\le(1+v)e^{-(1-r^2)y^2/2}$ since $v^2<r^2y^2$. $\square$

### Step 5c (KEY; attempted, not completed)

- (i) curve reduction: holds verbatim (only counts are used); not needed separately once 5b is stated with the raw deficit $D(k)=k-1-\beta(u_k)$ as above.
- (ii) proved above (T).
- (iii) tilt slope: immediate from (ii) as stated in the plan (if $y_1<y_2$ both satisfy $|v(y)-y/r|\le Ks/r$ and $\Delta\ge4Ks/(1-r)$, then $v(y_2)-v(y_1)\ge\Delta/r-2Ks/r>\Delta\ge\alpha\Delta$).
- (v) budget telescoping: **not proved; this is where the chain breaks** (details in `## Failure`). Items (iv), (vii), (viii) were not reached in proved form.

## Failure

The plan stops at its first KEY gate, **step 5 (PSL)**, by its own stop rule. Step 5a did **not** trigger the stop rule (no refutation candidate; numbers in `## Progress`), so the failure is a missing proof, not a falsification.

**Exact inequality not proved.** For every model in $\mathfrak B_1$ and every $q\le q_0$,
$$\mathrm{St}=\frac qN\sum_{i\in I_0,\,a_i\ne0}\mathbb E\big[\rho_{r_i}(u_{R_i},Y_i)\,\mathbf 1\{U<Y_i\le b_{h(i)}\}\big]\le\eta(q)\,qU,\qquad\eta(q)\to0,$$
with $\eta$ independent of $N$, $G$, means and loadings (equivalently $\mathrm{Sh}\le\eta(q)qU$, since the cap part is $\le q\pi_0$).

**Failing sub-item: 5c(v), budget telescoping** (and hence 5c(vii), which consumes it). What was proved: the pointwise carrier lemma 5b and the tilt localization T. What (v) needs and why it cannot be completed from them:
1. *Circularity of the lower bound.* 5b bounds the anti count of another block $g'$ (in its typical state) from below by its own deficit drop $D_{g'}(k_1)-D_{g'}(k''')$, and only on the event that $g'$ *would* have its threshold rise faster than slope $\alpha$ between two of its own factor values. Both the deficit $D_{g'}$ and that event are computed in the background of $g'$, which contains block $g$. When $g$ is in its strip, $g$'s own count is exactly the quantity that sits in the window $[k(v)-n_g,k(v))$; so the drop of $D_{g'}$ is not controlled independently of the state of $g$, and "$g'$ would tilt" is a counterfactual about $Z_{g'}$, not an event that occurs. The plan's $\delta_{g'}(w)$ (essential supremum of the deficit drops of $g'$) is not a lower bound for the anti count of $g'$ in the particular background realization in which $g$ is extreme.
2. *Heterogeneous blocks escape the chain.* If only a few blocks carry anti members (the others carry none), the budget in (v) is empty, and the tilt of $g$ is limited only by how likely the background is to hug the BH line within $n_g$ just below the tilt level. That is an anti-concentration statement about the background count process (the fallback MLR rigidity of `plan_two_sided_averaged_flatness_exclusion_20261105` / idea_a4ba452bf4a7), which is not in the chain and has no proof here. Heuristically it is small (an expected count is always $\sum_j\overline\Phi(w-\mu_j)$, and $\overline\Phi(w-\mu)/\overline\Phi(w)$ is increasing in $w$ for $\mu>0$, so no smooth background follows $k(w)$ over long level ranges), but no uniform inequality was established.
3. *Small blocks.* When $n_{0,g}\overline\Phi(\cdot)<1$ the self-count 5c(vi) is vacuous (its Chernoff bound gives nothing); the probe shows that integrality of the deficit ($D\ge1$) must then replace it. The plan's chain has no such branch.

**Parameter breaking uniformity.** Heterogeneity of the blocks (which blocks carry anti members, at which levels they tilt); secondarily the weak-member set size in (iv) (members with $|a_j|<\kappa/U$, whose count is not monotone in $y$ and whose concentration is not uniform in their number), $s_i\to0$ (the two branches of T merge), and the dense-extreme regime $Hq\ge U^{-3}$ of (viii). None of (iv), (vii), (viii) was proved.

**Violating configuration.** None found. In the adversary-friendly continuum version of the 5a family (perfect deterministic background, LLN other blocks), the tilt never extends beyond $y\le1.022\,U$, the shell gain is $\le0.001\cdot qU/\sqrt{2\pi}$, and the full FDR is at most $0.40$ of the target scale at $q=10^{-8}$, decreasing in $q$ (table in `## Progress`).

**What was established (reusable; checked in full in `## Progress`).**
- Steps 1–3: the forced-zero identity; the one-sided conditional formula $\mathbb E[\mathbf 1\{i\in\mathcal R\}/(R\vee1)\mid Z]=\frac qN\mathbb E[\rho^{\theta_i}_{r_i}(u_{R_i},Y_i)\mid Z]\le\frac qN\mathbb E[\rho_{r_i}(u_{R_i},Y_i)\mid Z]$ with composite domination; and **Lemma C** (proved): for $r\in[0,1)$, $v\ge U$, $\phi(y)\rho_r(v,y)\le s^{-1}\phi((rv-y)_+/s)\le1/(s\sqrt{2\pi})$ and $\int_{-\infty}^U\phi(y)\sup_{v\ge U}\rho_r(v,y)dy\le\frac12+\gamma_rU/\sqrt{2\pi}$; consequently $\mathrm{Ce}\le\frac qN\sum_{i\in I_0}(\frac12+\gamma_iU/\sqrt{2\pi})$ for every multifactor model and $0<q\le1/10$ (the central window is free). Possible separate draft asset.
- Step 4: **RS** (proved): for any multifactor representation, oriented null grouping and $0<q<1/2$, $\mathrm{FDR}\le\frac32q\pi_0+\frac{qU}{\sqrt{2\pi}}\overline\gamma_0+\frac qN\sum_h\sum_{i\in G_h}\min\{\frac{b_h-U}{s_i\sqrt{2\pi}},\log\frac1{\pi_h}\}$, with $b_h\le U+\log(1/\pi_h)/U$; corollary: the target holds along sequences with $\mathcal E_s=\frac1N\sum_h\sum_{i\in G_h}\log(1/\pi_h)/s_i=o(\log(1/q))$ (e.g. $q^{-o(1)}$ equal groups with loadings $\le1-\delta$), extending the approved entropy bound ($\mathcal E_0=o(\sqrt{\log(1/q)})$). Possible separate draft asset.
- Step 5b (carrier lemma, pointwise) and 5c(ii) (tilt localization T, analytic).
- Not reached: steps 6, 7 (SD), 8. Step 6 would in any case be a block-class theorem, not the target.

**What would be needed.** A pooled inequality that does not go through counterfactual tilts of other blocks: e.g. a direct bound on $\sum_g\mathbb P(\text{the count of all blocks other than }g\text{ lies in }[k(w)-n_g,k(w))\text{ at the tilt level of }g)$ weighted by $\pi_g$, uniform in heterogeneous designs, combining the copy budget (for blocks with anti members), integrality, the self-count, and an anti-concentration bound for the remaining background. The exchangeable-block case looks provable along the lines recorded in idea_cd01eda5d536; it would be an intermediate result only.
