---
type: theorem
title: Finite-level radial bounds for Gaussian multifactor BH
status: approved
source:
  kind: original
depends_on:
  - lei2026_conditional_fdp_bound
  - lei2026_integrated_conditional_tail_ratios
uses_definitions:
  - gaussian_multifactor_representation
  - gaussian_null_loading_coefficients
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_worst_case_bh_fdr
tags:
  - gaussian
  - multifactor
  - radial_truncation
  - finite_level
  - supporting_target
---

## Statement

Consider any [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) with positive integers $m,d$. Apply the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at level $q$ to track $s\in\{1,2\}$ of the [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md). Use the [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md) $I_0,\pi_0,r_i,\gamma_i$ for that track. The [false discovery rate](../definitions/false_discovery_rate.md) $\operatorname{FDR}_{\mathrm{BH}}^{(s)}$ uses the notation of the [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md).

For $s=1$ assume $0<q<1/2$ and set $u_1(q)=\overline\Phi^{-1}(q)$. For $s=2$ assume $0<q\leq2\overline\Phi(1)$ and set $u_2(q)=\overline\Phi^{-1}(q/2)$. In particular both conclusions are asserted on the common conservative range $0<q\leq2\overline\Phi(1)<1/2$. Let $b=b_d(q)>0$ be the upper-$q$ quantile of the $\chi_d$ distribution, namely the unique number satisfying $\mathbb P(\|Z\|>b)=q$. Define
$$
\Delta_1(d,q)=\log\frac q{\overline\Phi(b)},\qquad
\Delta_2(d,q)=\log\frac q{2\overline\Phi(b)}.
$$
Then $b\geq u_s(q)$ and $\Delta_s(d,q)\geq0$, and
$$
\operatorname{FDR}_{\mathrm{BH}}^{(s)}(q;m,\theta,\Sigma(A))
\leq\min\left\{1,\ q+q\pi_0\left(\frac12+\Delta_s(d,q)\right)
+\frac{q\,u_s(q)}{\sqrt{2\pi}}\frac1m\sum_{i\in I_0}\gamma_i\right\}.
$$
The assertion is uniform over the displayed model parameters. There is no restriction on alternative means or loading directions. For one-sided tests every mean $\theta_i\leq0$ is a true null. Coordinates with $r_i=0$ or $r_i=1$ are included. If there are no true nulls, the FDR is exactly zero.

## Scope and provenance

This is the supporting target extracted from the corrected candidate idea_ad11695134a0 and its two-sided extension idea_8aff9a0ee3ec. The proposed derivation combines the [Lei conditional leave-one-out FDP bound](./lei2026_conditional_fdp_bound.md) with the [Lei integrated conditional Gaussian tail-ratio bounds](./lei2026_integrated_conditional_tail_ratios.md) and a new radial tail-strip estimate. The terms $\Delta_s$ retain the tail-strip cost at $r_i=1$; replacing that cost by a bound proportional only to $\gamma_i$ is not asserted. This statement does not claim the unrestricted two-sided sharp constant.

## Proof

Fix a track $s$, a level $q$ in its stated range, and an admissible representation with parameters $m,d,\theta,A$. All probabilities and expectations below use this fixed model unless a scalar standard-normal experiment is specified. Write $u=u_s(q)$, and put $\phi(x)=(2\pi)^{-1/2}e^{-x^2/2}$ and $\Phi(x)=1-\overline\Phi(x)$. The one-sided range gives $u>0$ and $\overline\Phi(u)=q$; the two-sided range gives $u\geq1$ and $2\overline\Phi(u)=q$.

**The radial quantile.** The norm of a $d$-dimensional standard normal vector has a continuous distribution, with strictly positive density on $(0,\infty)$, survival probability tending to $1$ at zero and to $0$ at infinity. Hence there is a unique $b>0$ with $\mathbb P(\|Z\|>b)=q$, and $\mathbb P(\|Z\|=b)=0$. Since $\|Z\|\geq|Z_1|$,
$$
q\geq\mathbb P(|Z_1|>b)=2\overline\Phi(b).
$$
For the one-sided track this implies $\overline\Phi(b)\leq q=\overline\Phi(u)$; for the two-sided track it implies $2\overline\Phi(b)\leq q=2\overline\Phi(u)$. Strict decrease of $\overline\Phi$ gives $b\geq u$ in both cases. These same inequalities give $\Delta_s(d,q)\geq0$. In particular, the event
$$
B=\{\|Z\|\leq b\}
$$
satisfies $\mathbb P(B^c)=q$ exactly.

**Scalar kernels and full-factor conditioning.** For each $i\in I_0$ with $r_i>0$, let $v_i=a_i/r_i$. If $r_i=0$, choose any deterministic unit vector $v_i\in\mathbb R^d$, which is possible because $d\geq1$. In both cases set $W_i=v_i^{\mathsf T}Z$. Then $W_i\sim\mathcal N(0,1)$, it is independent of $\varepsilon_i$, and
$$
T_i=\theta_i+r_iW_i+\sqrt{1-r_i^2}\,\varepsilon_i.
$$
The different $W_i$ need not be independent. Conditional on the full vector $Z$, however, all the $T_i$, and hence all the p-values, are independent: each is a measurable function of $Z$ and its own independent $\varepsilon_i$. This also holds when a coordinate is conditionally deterministic, because its conditional law is a point mass.

For a generic $r\in[0,1]$, use the boundary-null conditional CDFs $F^{(s)}_{r,z}(t)$ in the [Lei integrated conditional Gaussian tail-ratio bounds](./lei2026_integrated_conditional_tail_ratios.md). They are the conditional kernels obtained from $X_r=rW+\sqrt{1-r^2}\,\varepsilon$, where $W,\varepsilon$ are independent standard normals. For $0<t\leq q$, put $x_1(t)=\overline\Phi^{-1}(t)$ and $x_2(t)=\overline\Phi^{-1}(t/2)$, which are positive on the ranges used here. For $r<1$, with $\sigma=\sqrt{1-r^2}>0$, the kernels are explicitly
$$
F^{(1)}_{r,z}(t)=\overline\Phi\left(\frac{x_1(t)-rz}{\sigma}\right),\qquad
F^{(2)}_{r,z}(t)=\overline\Phi\left(\frac{x_2(t)-rz}{\sigma}\right)
+\overline\Phi\left(\frac{x_2(t)+rz}{\sigma}\right).
$$
At $r=1$ their definitions use the non-strict rejection thresholds and give
$$
F^{(1)}_{1,z}(t)=\mathbf1\{z\geq x_1(t)\},\qquad
F^{(2)}_{1,z}(t)=\mathbf1\{|z|\geq x_2(t)\}.
$$
At $r=0$ either kernel is $t$, independently of $z$.

Let $H_i(t)=\mathbb P(p_i^{(s)}\leq t\mid Z)$, taking the explicit conditional kernels supplied by the representation. If $s=2$ and $i\in I_0$, then $\theta_i=0$, so $H_i(t)=F^{(2)}_{r_i,W_i}(t)$. If $s=1$ and $i\in I_0$, then $\theta_i\leq0$. For $r_i<1$,
$$
H_i(t)=\overline\Phi\left(\frac{x_1(t)-\theta_i-r_iW_i}{\sqrt{1-r_i^2}}\right)
\leq F^{(1)}_{r_i,W_i}(t),
$$
and for $r_i=1$ the same domination follows pointwise from
$$
H_i(t)=\mathbf1\{\theta_i+W_i\geq x_1(t)\}
\leq\mathbf1\{W_i\geq x_1(t)\}.
$$
Thus $H_i(t)\leq F^{(s)}_{r_i,W_i}(t)$ simultaneously for all $0<t\leq q$ and every null, with equality for two-sided nulls. In particular the argument includes negative one-sided null means.

Define the nonnegative extended-valued function
$$
G^{(s)}_r(z)=\sup_{0<t\leq q}\frac{F^{(s)}_{r,z}(t)}t.
$$
This function is measurable. Indeed, for each fixed $z$, the conditional CDF is right-continuous in $t$, including the point-mass case $r=1$. If $t<q$, choose rational $t_n\in(t,q)$ decreasing to $t$; then $F^{(s)}_{r,z}(t_n)/t_n\to F^{(s)}_{r,z}(t)/t$. Consequently the displayed supremum equals the supremum over the countable set $(\mathbb Q\cap(0,q))\cup\{q\}$. Each of those ratios is a measurable function of $z$ by the formulas above. The same observation applies to the actual conditional kernels $H_i$.

**Radial truncation of the FDP.** If $I_0$ is empty, the false-rejection count $V$ is identically zero, so the FDR is exactly zero. This already proves that case. Otherwise apply the [Lei conditional leave-one-out FDP bound](./lei2026_conditional_fdp_bound.md) conditional on the full $Z$, for which the required conditional independence was established above. Its fixed null set is $I_0$ and $q\in(0,1)$ in either track. Using the conditional CDF domination, for almost every $Z$ it gives
$$
\mathbb E(\operatorname{FDP}\mid Z)
\leq\frac qm\sum_{i\in I_0}\sup_{0<t\leq q}\frac{H_i(t)}t
\leq\frac qm\sum_{i\in I_0}G^{(s)}_{r_i}(W_i).
$$
The event $B$ is measurable with respect to $Z$. Since $0\leq\operatorname{FDP}\leq1$, the tower property and nonnegativity yield
$$
\begin{aligned}
\operatorname{FDR}_{\mathrm{BH}}^{(s)}
&=\mathbb E[\mathbf1_{B^c}\operatorname{FDP}]
+\mathbb E[\mathbf1_B\mathbb E(\operatorname{FDP}\mid Z)]\\
&\leq q+\frac qm\sum_{i\in I_0}\mathbb E[\mathbf1_B G^{(s)}_{r_i}(W_i)].
\end{aligned}
$$
All terms here are well-defined as nonnegative expectations; the bounds below also show that the truncated terms are finite.

**Tail envelopes from calibration.** We next derive a bound on $G^{(s)}_r$ for every $r\in[0,1]$. Fix $0<t\leq q$. The one-sided kernel is nondecreasing in $z$. The two-sided kernel is even in $z$ and nondecreasing for $z\geq0$: when $r<1$ its derivative there is
$$
\frac r\sigma\left[
\phi\left(\frac{x_2(t)-rz}{\sigma}\right)
-\phi\left(\frac{x_2(t)+rz}{\sigma}\right)\right]\geq0,
$$
because $(x_2(t)+rz)^2-(x_2(t)-rz)^2=4x_2(t)rz\geq0$. This also covers $r=0$, for which the derivative is zero. At $r=1$, the indicator formulas give the same monotonicity directly.

The scalar variable $X_r$ is standard normal for every $r\in[0,1]$, including both endpoints. Exact standard-normal calibration therefore gives
$$
\int_{\mathbb R}\phi(w)F^{(s)}_{r,w}(t)\,dw=t:
$$
the unconditional rejection probabilities are respectively $\overline\Phi(x_1(t))=t$ and $2\overline\Phi(x_2(t))=t$. Non-strict thresholds have the same marginal probabilities because the scalar standard-normal law is continuous. For any finite $z$, nonnegativity and monotonicity consequently give, in the one-sided track,
$$
t\geq\int_z^\infty\phi(w)F^{(1)}_{r,w}(t)\,dw
\geq\overline\Phi(z)F^{(1)}_{r,z}(t).
$$
For the two-sided track, evenness and monotonicity in absolute value give
$$
t\geq\int_{|w|\geq|z|}\phi(w)F^{(2)}_{r,w}(t)\,dw
\geq2\overline\Phi(|z|)F^{(2)}_{r,z}(t).
$$
Divide by $t>0$ and take the supremum to obtain the pointwise envelopes
$$
G^{(1)}_r(z)\leq\frac1{\overline\Phi(z)},\qquad
G^{(2)}_r(z)\leq\frac1{2\overline\Phi(|z|)}.
$$
Their denominators are positive for finite $z$, so $G^{(s)}_r$ is finite everywhere. This derivation uses no loading restriction beyond $r\in[0,1]$ and, for the two-sided monotonicity, only $x_2(t)\geq0$.

**Central integrals and the strips.** For a fixed null $i$, Cauchy--Schwarz gives $|W_i|=|v_i^{\mathsf T}Z|\leq\|Z\|$. Thus $B\subseteq\{|W_i|\leq b\}$ and, using nonnegativity and the standard-normal marginal law of $W_i$,
$$
\mathbb E[\mathbf1_B G^{(s)}_{r_i}(W_i)]
\leq\mathbb E[\mathbf1\{|W_i|\leq b\}G^{(s)}_{r_i}(W_i)]
=\int_{-b}^b\phi(z)G^{(s)}_{r_i}(z)\,dz.
$$
This step uses a deterministic event inclusion and does not require independence between $B$ and $W_i$.

The scalar experiment defining these kernels satisfies every hypothesis of the [Lei integrated conditional Gaussian tail-ratio bounds](./lei2026_integrated_conditional_tail_ratios.md): its two noises are independent standard normals, its mean is the boundary-null value zero, and its loading is $r_i\in[0,1]$. The track-specific $q$ ranges are exactly those of that lemma. Since $\gamma_{r_i}=\sqrt{(1-r_i)/(1+r_i)}=\gamma_i$, the lemma gives
$$
\int_{-\infty}^u\phi(z)G^{(1)}_{r_i}(z)\,dz
\leq\frac12+\frac{\gamma_i u}{\sqrt{2\pi}}
$$
in the one-sided track, and
$$
\int_{-u}^u\phi(z)G^{(2)}_{r_i}(z)\,dz
\leq\frac12+\frac{\gamma_i u}{\sqrt{2\pi}}
$$
in the two-sided track. For the latter, its more precise estimate for $r_i<1$ has first term $\Phi(u/\gamma_i)-1/2\leq1/2$. At $r_i=1$ use the lemma's separate endpoint assertion: the central integrals vanish, since the respective indicator kernels are zero in the interior of the central region for every $t\leq q$. Values at $u$ or $\pm u$ have Gaussian measure zero. Thus no division by $\gamma_i=0$ is used. At $r_i=0$ the kernels equal $t$ and $G^{(s)}_0=1$, and the same central estimates apply by the lemma's $r=0$ case.

For the one-sided track, $b\geq u$ and nonnegativity allow the portion $[-b,u]$ to be enlarged to $(-\infty,u]$. The remaining strip is bounded by the one-sided envelope, and its integral is
$$
\int_u^b\frac{\phi(z)}{\overline\Phi(z)}\,dz
=\log\frac{\overline\Phi(u)}{\overline\Phi(b)}
=\log\frac q{\overline\Phi(b)}=\Delta_1(d,q).
$$
Here the equality follows by integrating $-(\log\overline\Phi)'=\phi/\overline\Phi$. For the two-sided track, keep the central interval $[-u,u]$ and use the two-sided envelope on both strips. Symmetry gives
$$
\begin{aligned}
\int_{u<|z|\leq b}\frac{\phi(z)}{2\overline\Phi(|z|)}\,dz
&=\int_u^b\frac{\phi(z)}{\overline\Phi(z)}\,dz\\
&=\log\frac{\overline\Phi(u)}{\overline\Phi(b)}
=\log\frac q{2\overline\Phi(b)}=\Delta_2(d,q).
\end{aligned}
$$
Thus the factor $2$ from the symmetric strips cancels the $2$ in their envelope. When $b=u$, each strip is empty up to endpoints and has integral zero, as does its logarithmic expression. Combining the central and strip estimates proves, in either track and for every null including $r_i=0,1$,
$$
\mathbb E[\mathbf1_B G^{(s)}_{r_i}(W_i)]
\leq\frac12+\Delta_s(d,q)+\frac{\gamma_i u_s(q)}{\sqrt{2\pi}}.
$$
In particular the strip allowance was retained at $r_i=1$, even though its central contribution vanishes.

**Summation.** Insert this last estimate into the radially truncated FDP bound. Since $|I_0|/m=\pi_0$, this yields
$$
\operatorname{FDR}_{\mathrm{BH}}^{(s)}(q;m,\theta,\Sigma(A))
\leq q+q\pi_0\left(\frac12+\Delta_s(d,q)\right)
+\frac{q\,u_s(q)}{\sqrt{2\pi}}\frac1m\sum_{i\in I_0}\gamma_i.
$$
Intersecting with $\operatorname{FDR}\leq1$ proves the displayed bound. The empty-null case has already given the stronger exact value zero; its empty sums and $\pi_0=0$ are consistent with this inequality. The one-sided argument used the entire composite null $\theta_i\leq0$. No step restricted alternative means or the deterministic loading directions, and all dependence arguments conditioned on the full $Z$. The constants are the displayed universal constants, so the conclusion holds uniformly over the model parameters. Both track-specific ranges, including the two-sided endpoint $u=1$, were retained; since $2\overline\Phi(1)<1/2$, their common conservative range is the one stated. $\square$
