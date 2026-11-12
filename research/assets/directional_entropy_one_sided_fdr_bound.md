---
type: theorem
title: One-sided Gaussian BH bound from oriented null directional entropy
status: approved
source:
  kind: original
depends_on:
  - lei2026_conditional_fdp_bound
  - lei2026_integrated_conditional_tail_ratios
uses_definitions:
  - gaussian_multifactor_representation
  - gaussian_null_loading_coefficients
  - gaussian_oriented_null_directional_entropy
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_worst_case_bh_fdr
tags:
  - gaussian
  - multifactor
  - directional_entropy
  - one_sided
  - finite_level
  - supporting_target
---

## Statement

Consider any [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md), with any positive factor dimension $d$, and apply the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) to the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) at level $0<q<1/2$. Let $u=\overline\Phi^{-1}(q)$ and use the [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md). For any oriented null grouping with masses $\pi_h$ and [oriented null directional entropy](../definitions/gaussian_oriented_null_directional_entropy.md) $\mathcal E_0$, the [false discovery rate](../definitions/false_discovery_rate.md), with the notation of the [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md), satisfies
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;m,\theta,\Sigma(A))
\leq\min\left\{1,\ \frac32q\pi_0
+\frac{q\,u}{\sqrt{2\pi}}\frac1m\sum_{i\in I_0}\gamma_i
+q\sum_{h=1}^H\pi_h\log\frac1{\pi_h}\right\}.
$$
This includes all true-null means $\theta_i\leq0$, arbitrary alternative means and loadings, and the cases $r_i=0$ and $r_i=1$. The group projections need not be independent. If $m_0=0$, the empty-group convention makes the displayed right side zero and the FDR is exactly zero.

Consequently, for any sequence of levels $q\downarrow0$ and such models and groupings, if
$$
\mathcal E_0=o\!\left(\sqrt{\log(1/q)}\right),
$$
then
$$
\limsup_{q\downarrow0}
\frac{\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;m,\theta,\Sigma(A))}{q\sqrt{\log(1/q)}}
\leq\frac1{\sqrt\pi}.
$$
The ambient factor dimension, number of tests, and grouping may vary arbitrarily with $q$ subject to the stated entropy condition.

## Scope and provenance

This is the weighted-cutoff candidate idea_676ddf6ca5aa. Its proposed derivation uses the [Lei conditional leave-one-out FDP bound](./lei2026_conditional_fdp_bound.md) and the [Lei integrated conditional Gaussian tail-ratio bounds](./lei2026_integrated_conditional_tail_ratios.md), with a separate cutoff $b_h=\overline\Phi^{-1}(q\pi_h)$ for each nonempty group. The complementary event for group $h$ has probability $q\pi_h$, while its integrated outer-strip cost is $\log(1/\pi_h)$. The weights $\pi_h=m_{0,h}/m$ and the entropy condition above are part of this target; an entropy bound of only $o(\log(1/q))$ is not asserted.

## Proof

Write $p_i=\overline\Phi(T_i)$, $\mathcal R_q=\mathcal R_q(p)$, and $R=|\mathcal R_q|$. Let $\phi(y)=(2\pi)^{-1/2}e^{-y^2/2}$ be the standard normal density. If $m_0=0$, then $V=0$ identically, $H=0$, and $\pi_0=\mathcal E_0=m^{-1}\sum_{i\in I_0}\gamma_i=0$. Both conclusions follow, including along sequences with no true nulls at some or all levels. For the finite-level argument suppose henceforth that $m_0>0$.

Keep the given partition $G_1,\ldots,G_H$ of the actual true-null set $I_0=\{i:\theta_i\leq0\}$. By the [oriented null directional entropy](../definitions/gaussian_oriented_null_directional_entropy.md) definition, $a_i=r_i v_h$ for $i\in G_h$, and
$$
\pi_h=\frac{|G_h|}{m}>0,\qquad \sum_{h=1}^H\pi_h=\pi_0\leq1,
\qquad Y_h=v_h^{\mathsf T}Z\sim\mathcal N(0,1).
$$
Set
$$
u=\overline\Phi^{-1}(q)>0,\qquad
b_h=\overline\Phi^{-1}(q\pi_h)\geq u.
$$
These cutoffs are finite because $0<q\pi_h<1$. The variables $Y_h$ may be correlated or identical. Define the partial false discovery proportions by
$$
\operatorname{FDP}_h=
\frac{\sum_{i\in G_h}\mathbf1\{i\in\mathcal R_q\}}{R\vee1}.
$$
They obey $0\leq\operatorname{FDP}_h\leq1$ and $\operatorname{FDP}=\sum_{h=1}^H\operatorname{FDP}_h$. All other true nulls retain their original status when a partial sum is considered.

We first reproduce the leave-one-out argument of the [Lei conditional leave-one-out FDP bound](./lei2026_conditional_fdp_bound.md) with its sum restricted to $G_h$. For a fixed p-value vector, the BH rejection count equals its largest qualifying rank: if more coordinates than that rank lay below its rejection threshold, their count would itself be a larger qualifying rank. Let $R_i$ be the rejection count after replacing $p_i$ by zero. Then $1\leq R_i\leq m$, $R_i$ depends only on $(p_j)_{j\ne i}$, and lowering one p-value gives $R_i\geq R$.

If $i\in\mathcal R_q$, then $R\geq1$ and $p_i\leq qR/m$. We claim $R_i=R$. Otherwise, with $k=R_i>R$, the modified vector has at least $k$ coordinates at most $qk/m$. Restoring $p_i$ preserves this fact because $p_i\leq qR/m\leq qk/m$, so $k$ would qualify for the original vector, a contradiction. Conversely, if $p_i\leq qR_i/m$, restoring $p_i$ in the modified vector preserves at least $R_i$ values at most $qR_i/m$. Hence $R\geq R_i$ and therefore $R=R_i\geq1$, with $i\in\mathcal R_q$. This proves the pointwise identity, including all threshold equalities,
$$
\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}
=\frac{\mathbf1\{p_i\leq qR_i/m\}}{R_i}.
$$
When $R=0$, the converse just proved shows that the indicator on the right is also zero.

For $r\in[0,1]$, $y,\theta\in\mathbb R$, and $0<t<1$, define the local conditional CDF
$$
F^{\theta}_{r,y}(t)=
\mathbb P\!\left\{\theta+ry+\sqrt{1-r^2}\,\varepsilon
\geq\overline\Phi^{-1}(t)\right\},
\qquad \varepsilon\sim\mathcal N(0,1).
$$
For $i\in G_h$, this is the conditional CDF of $p_i$ given the full vector $Z$, evaluated at $r=r_i$, $y=Y_h$, and $\theta=\theta_i$. Define
$$
M_i(y)=\sup_{0<t\leq q}\frac{F^{\theta_i}_{r_i,y}(t)}{t},
\qquad
M^0_r(y)=\sup_{0<t\leq q}\frac{F^0_{r,y}(t)}{t}.
$$
These are measurable: for each fixed $y$, a CDF is right-continuous in $t$, so either supremum equals the supremum over $(\mathbb Q\cap(0,q))\cup\{q\}$. Each function in this countable supremum is measurable in $y$. This also covers the deterministic conditional CDF at $r=1$.

The [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) makes all p-values independent conditional on the full $Z$. In particular $p_i$ and $R_i$ are conditionally independent even when $r_i=1$ and $p_i$ is conditionally deterministic. Thus, for $i\in G_h$, the identity above gives almost surely
$$
\begin{aligned}
\mathbb E\!\left(\left.
\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}\right|Z\right)
&=\mathbb E\!\left(\left.
\frac{F^{\theta_i}_{r_i,Y_h}(qR_i/m)}{R_i}\right|Z\right)\\
&=\frac qm\mathbb E\!\left(\left.
\frac{F^{\theta_i}_{r_i,Y_h}(qR_i/m)}{qR_i/m}\right|Z\right)
\leq\frac qm M_i(Y_h).
\end{aligned}
$$
Summing only over $i\in G_h$ yields
$$
\mathbb E(\operatorname{FDP}_h\mid Z)
\leq\frac qm\sum_{i\in G_h}M_i(Y_h).
$$
This argument conditions on $Z$ throughout; it does not require conditional independence given only $Y_h$. Since $\theta_i\leq0$, translating the Gaussian variable in the event defining the CDF shows directly that
$$
F^{\theta_i}_{r_i,y}(t)\leq F^0_{r_i,y}(t),
\qquad M_i(y)\leq M^0_{r_i}(y).
$$
The inclusion of events proving this domination remains valid at both loading endpoints.

We next bound the outer strip. For every fixed $r\in[0,1]$ and $0<t\leq q$, $F^0_{r,y}(t)$ is nondecreasing in $y$, since $r\geq0$. If $Y$ and $\varepsilon$ are independent standard normal variables, then $rY+\sqrt{1-r^2}\,\varepsilon$ is standard normal, including at $r=0$ and $r=1$. Consequently
$$
\int_{-\infty}^{\infty}\phi(z)F^0_{r,z}(t)\,dz=t.
$$
For every finite $y$, monotonicity and nonnegativity therefore give
$$
\overline\Phi(y)F^0_{r,y}(t)
\leq\int_y^{\infty}\phi(z)F^0_{r,z}(t)\,dz
\leq t,
\qquad
M^0_r(y)\leq\frac1{\overline\Phi(y)}.
$$
In particular these suprema are finite for finite $y$. Because
$\frac{d}{dy}[-\log\overline\Phi(y)]=\phi(y)/\overline\Phi(y)$, each $i\in G_h$ satisfies
$$
\begin{aligned}
\int_u^{b_h}\phi(y)M_i(y)\,dy
&\leq\int_u^{b_h}\frac{\phi(y)}{\overline\Phi(y)}\,dy\\
&=\log\frac{\overline\Phi(u)}{\overline\Phi(b_h)}
=\log\frac1{\pi_h}.
\end{aligned}
$$
If $\pi_h=1$, then $b_h=u$ and both integrals are zero. At $r=1$ the CDF is the indicator $\mathbf1\{\overline\Phi(y)\leq t\}$; its non-strict endpoint is included in the pointwise argument and changes no Gaussian integral.

For the central integral, the one-sided statement of the approved [Lei integrated conditional Gaussian tail-ratio bounds](./lei2026_integrated_conditional_tail_ratios.md), together with CDF domination, yields
$$
\int_{-\infty}^u\phi(y)M_i(y)\,dy
\leq\int_{-\infty}^u\phi(y)M^0_{r_i}(y)\,dy
\leq\frac12+\frac{\gamma_i u}{\sqrt{2\pi}}.
$$
Its hypotheses hold because $0<q<1/2$, $r_i\in[0,1]$, and the scalar boundary-null variable used above has exactly that lemma's form. At $r_i=0$, $F^0_{0,y}(t)=t$, $M^0_0(y)=1$, and $\gamma_i=1$. At $r_i=1$, $M^0_1(y)=0$ for $y<u$, so the central integral is zero, in accord with the lemma's stated endpoint and $\gamma_i=0$. No division by $\gamma_i$ or $\sqrt{1-r_i^2}$ is used at an endpoint.

The event $\{Y_h\leq b_h\}$ is measurable with respect to the full $Z$. Multiply the conditional partial-FDP bound by its indicator, integrate, and use only the standard normal marginal of $Y_h$. The central and strip estimates give
$$
\begin{aligned}
\mathbb E[\operatorname{FDP}_h\mathbf1\{Y_h\leq b_h\}]
&\leq\frac qm\sum_{i\in G_h}
\int_{-\infty}^{b_h}\phi(y)M_i(y)\,dy\\
&\leq\frac qm\sum_{i\in G_h}
\left(\frac12+\frac{\gamma_i u}{\sqrt{2\pi}}
+\log\frac1{\pi_h}\right).
\end{aligned}
$$
Separately, $\operatorname{FDP}_h\leq1$ gives
$$
\mathbb E[\operatorname{FDP}_h\mathbf1\{Y_h>b_h\}]
\leq\mathbb P(Y_h>b_h)=\overline\Phi(b_h)=q\pi_h.
$$
Each partial FDP has thus been split using its own group event. Adding these two bounds for each $h$ and summing over the partition, with $|G_h|/m=\pi_h$, proves
$$
\begin{aligned}
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;m,\theta,\Sigma(A))
&\leq\sum_{h=1}^H\left[
q\pi_h+\frac q2\pi_h
+\frac{qu}{m\sqrt{2\pi}}\sum_{i\in G_h}\gamma_i
+q\pi_h\log\frac1{\pi_h}\right]\\
&=\frac32q\pi_0
+\frac{qu}{\sqrt{2\pi}}\frac1m\sum_{i\in I_0}\gamma_i
+q\mathcal E_0.
\end{aligned}
$$
Since $\operatorname{FDP}\leq1$, this gives the claimed minimum with $1$. The group masses have throughout been normalized by $m$, so the complements cost $q\pi_0$ and the strips cost exactly $q\mathcal E_0$. The proof imposes no condition on alternative means or loadings beyond the given representation, or on dependence between the group projections, $d$, $m$, or $H$. In particular it covers all-zero null loadings and any mixture of zero and unit loadings with the given grouping.

Finally put $L=\log(1/q)$. For a standard normal variable $G$, completing the square gives
$$
\mathbb E e^{\lambda G}
=\frac1{\sqrt{2\pi}}\int_{-\infty}^{\infty}
e^{\lambda x-x^2/2}\,dx
=e^{\lambda^2/2}.
$$
Markov's inequality with $\lambda=u>0$ gives
$q=\mathbb P(G\geq u)\leq e^{-u^2}\mathbb E e^{uG}=e^{-u^2/2}$, hence $u\leq\sqrt{2L}$. By the [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md),
$$
0\leq\frac1m\sum_{i\in I_0}\gamma_i\leq\pi_0\leq1.
$$
Dividing the finite-level bound by $q\sqrt L$ therefore yields, at every level and for every allowed model and grouping,
$$
\frac{\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;m,\theta,\Sigma(A))}
{q\sqrt L}
\leq\frac{3}{2\sqrt L}+\frac1{\sqrt\pi}
+\frac{\mathcal E_0}{\sqrt L}.
$$
This inequality also holds at levels with $m_0=0$, where its left side is zero. Under $\mathcal E_0=o(\sqrt L)$ its upper limit is at most $1/\sqrt\pi$. Since this is a level-by-level deterministic bound, all model parameters and the grouping may vary with $q$ as stated; no interchange of a limit and a model-dependent expectation or supremum is required.
