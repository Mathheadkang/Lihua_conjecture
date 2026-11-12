---
type: lemma
title: One-sided radial strip refinement RS and its sharp-constant corollary
status: draft
source:
  kind: original
  location: "plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106, Progress, Step 4 and Corollary RS-c (source lines 219–233)"
depends_on:
  - gaussian_bh_one_sided_free_central_window
  - directional_entropy_one_sided_fdr_bound
uses_definitions:
  - gaussian_multifactor_representation
  - gaussian_null_loading_coefficients
  - gaussian_oriented_null_directional_entropy
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian
  - one_sided
  - radial_strip
  - directional_entropy
  - extracted_unverified
---

## Source notation and scope

Use the one-sided testing track, with $I_0=\{i:\theta_i\le0\}$, $\pi_0=|I_0|/N$, $\overline\gamma_0=N^{-1}\sum_{i\in I_0}\gamma_i$, and the oriented null grouping and $\mathcal E_0$ from the approved definitions. The following setup is copied from the source plan.

Notation. $0<q<1/2$, $U=\overline\Phi^{-1}(q)>0$, $t_k=qk/N$, $u_k=\overline\Phi^{-1}(t_k)\ge U$ ($u_N=U$), $k(w)=N\overline\Phi(w)/q$ (the BH line in level space). For $r\in[0,1)$, $s=\sqrt{1-r^2}$, $\gamma_r=\sqrt{(1-r)/(1+r)}$ and $\theta\le0$,

$$
\rho^\theta_r(v,y)=\frac{\overline\Phi((v-\theta-ry)/s)}{\overline\Phi(v)}\le\rho_r(v,y):=\rho^0_r(v,y),\qquad \rho_1(v,y)=\frac{\mathbf 1\{y\ge v\}}{\overline\Phi(v)},\quad\rho_0\equiv1 .
$$


Notation as in `## Plan`; $N$ tests, $0<q<1/2$, $U=\overline\Phi^{-1}(q)$, $t_k=qk/N$, $u_k=\overline\Phi^{-1}(t_k)\ge U$. All statements are for an arbitrary [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) $T_i=\theta_i+a_i^{\mathsf T}Z+s_i\varepsilon_i$, $r_i=\|a_i\|$, $s_i=\sqrt{1-r_i^2}$; $\mathfrak B_1$ is the special case of step 0.

In the proof, “steps 1–2” and “Lemma C” refer to the copied proof of [One-sided free central window lemma C](./gaussian_bh_one_sided_free_central_window.md), and “approved entropy proof” refers to [One-sided Gaussian BH bound from oriented null directional entropy](./directional_entropy_one_sided_fdr_bound.md), Proof. Its local conditional CDF, copied here to define $F$ in the source text, is

$$
F^{\theta}_{r,y}(t)=\mathbb P\!\left\{\theta+ry+\sqrt{1-r^2}\,\varepsilon\ge\overline\Phi^{-1}(t)\right\},\qquad \varepsilon\sim\mathcal N(0,1).
$$


## Statement

For any multifactor representation, any oriented null grouping $(G_h,v_h)_{h\le H}$ (as in the [oriented null directional entropy](../definitions/gaussian_oriented_null_directional_entropy.md) definition, $m_0>0$) and $0<q<1/2$, with $\pi_h=|G_h|/N$, $b_h=\overline\Phi^{-1}(q\pi_h)$,

$$
\mathrm{FDR}\le\frac32q\pi_0+\frac{qU}{\sqrt{2\pi}}\overline\gamma_0+q\,\mathcal E_{\min},\qquad \mathcal E_{\min}:=\frac1N\sum_h\sum_{i\in G_h}\min\Big\{\frac{b_h-U}{s_i\sqrt{2\pi}},\ \log\frac1{\pi_h}\Big\}
$$

(first entry $+\infty$ when $s_i=0$), and $b_h-U\le\log(1/\pi_h)/U$, so $\mathcal E_{\min}\le\frac1N\sum_h\sum_{i\in G_h}\min\{\frac{\log(1/\pi_h)}{Us_i\sqrt{2\pi}},\log\frac1{\pi_h}\}\le\frac{\mathcal E_s}{U\sqrt{2\pi}}$ with $\mathcal E_s=\frac1N\sum_h\sum_{i\in G_h}\log(1/\pi_h)/s_i$.

*Corollary RS-c.* Along any sequence $q\downarrow0$ of models and groupings with $\mathcal E_{\min}=o(\sqrt{\log(1/q)})$ — in particular whenever $\mathcal E_s=o(\log(1/q))$, or $\mathcal E_0=o(\sqrt{\log(1/q)})$ — $\limsup\mathrm{FDR}/(q\sqrt{\log(1/q)})\le1/\sqrt\pi$.

## Proof

gap: The final equal-group example in the copied source proof also omits the term $\pi_0\log(1/\pi_0)/\delta$ when masses are normalized by all tests. For $H=1$ and $0<\pi_0<1$, its displayed example bound has zero right side although $\mathcal E_s$ can be positive. This example is separate from the finite RS inequality and its stated sufficient entropy conditions; no repair is inserted here.

gap: The source does not specify the value of $\log(1/\pi_h)/s_i$ in $\mathcal E_s$ when $\pi_h=1$ and $s_i=0$ (the undefined expression $0/0$). No convention is added in this extraction. The source does explicitly set the first entry of $\mathcal E_{\min}$ to $+\infty$ when $s_i=0$.

Copied verbatim from [the source plan](../plans/plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106.md), Progress, “Step 4 (RS, radial strip refinement; written out in full; settles checklist item 4)”, source lines 225–232. The extraction carries no independent verification verdict.

*Proof.* Put $M_i(y)=\sup_{v\ge U}\rho^{\theta_i}_{r_i}(v,y)$; this is the function $\sup_{0<t\le q}F^{\theta_i}_{r_i,y}(t)/t$ of the approved entropy proof (substitute $t=\overline\Phi(v)$, a bijection of $(0,q]$ onto $[U,\infty)$). For $i\in G_h$ with $r_i>0$, $Y_i=Y_h=v_h^{\mathsf T}Z$; for $r_i=0$, $M_i$ is constant. By steps 1–2, $\mathbb E[\mathrm{FDP}_h\mid Z]\le\frac qN\sum_{i\in G_h}M_i(Y_h)$, with $\mathrm{FDP}_h=\sum_{i\in G_h}\mathbf 1\{i\in\mathcal R_q\}/(R\vee1)\le1$. Split each $\mathrm{FDP}_h$ at $\{Y_h\le b_h\}$ (a $Z$-measurable event):
- $\mathbb E[\mathrm{FDP}_h\mathbf 1\{Y_h>b_h\}]\le\overline\Phi(b_h)=q\pi_h$.
- $\mathbb E[\mathrm{FDP}_h\mathbf 1\{Y_h\le U\}]\le\frac qN\sum_{i\in G_h}\int_{-\infty}^U\phi M_i\le\frac qN\sum_{i\in G_h}(\frac12+\frac{\gamma_iU}{\sqrt{2\pi}})$: by $M_i\le\sup_{v\ge U}\rho_{r_i}(v,\cdot)$ (step 2) and Lemma C; for $r_i=0$, $\int_{-\infty}^U\phi M_i\le\Phi(U)=1-q$, and $1-q\le\frac12+\frac U{\sqrt{2\pi}}$ since $\Phi(U)-\frac12=\int_0^U\phi\le U\phi(0)$.
- $\mathbb E[\mathrm{FDP}_h\mathbf 1\{U<Y_h\le b_h\}]\le\frac qN\sum_{i\in G_h}\int_U^{b_h}\phi M_i$, and for each $i$ this integral is at most both $\log(1/\pi_h)$ (approved entropy proof: $M_i(y)\le1/\overline\Phi(y)$ and $\int_U^{b_h}\phi/\overline\Phi=\log(\overline\Phi(U)/\overline\Phi(b_h))$) and, when $s_i>0$, $(b_h-U)/(s_i\sqrt{2\pi})$, by the pointwise half of Lemma C, $\phi(y)\rho_{r_i}(v,y)\le1/(s_i\sqrt{2\pi})$ for every $v$ ($r_i=0$ included, $s_i=1$).

Summing the three bounds over $i$ and $h$ (with $\sum_h|G_h|/N=\pi_0$) gives $\mathrm{FDR}\le q\pi_0+\frac q2\pi_0+\frac{qU}{\sqrt{2\pi}}\overline\gamma_0+q\mathcal E_{\min}$. Finally $\overline\Phi(U+x)=\int_U^\infty\phi(t+x)dt=\int_U^\infty\phi(t)e^{-tx-x^2/2}dt\le e^{-Ux-x^2/2}\overline\Phi(U)$ for $x\ge0$; at $x=\log(1/\pi_h)/U$ this is $\le q\pi_h=\overline\Phi(b_h)$, so $b_h\le U+\log(1/\pi_h)/U$. $\square$

*Corollary RS-c, Proof:* $\overline\gamma_0\le\pi_0\le1$, $U\le\sqrt{2\log(1/q)}$ (Markov, as in the approved entropy proof), so $\mathrm{FDR}/(q\sqrt L)\le\frac3{2\sqrt L}+\frac1{\sqrt\pi}+\frac{\mathcal E_{\min}}{\sqrt L}$, $L=\log(1/q)$; and $\mathcal E_{\min}\le\mathcal E_s/(U\sqrt{2\pi})$ with $U\to\infty$, $U\ge\sqrt{\log(1/q)}$ for small $q$ (since $\overline\Phi(x)\ge\phi(x)x/(1+x^2)$). Example: $H$ equal groups with $s_i\ge\delta$ give $\mathcal E_s\le\pi_0\log H/\delta$, so $H=q^{-o(1)}$ suffices for fixed $\delta$.
