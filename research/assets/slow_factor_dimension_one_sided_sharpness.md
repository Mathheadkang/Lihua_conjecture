---
type: theorem
title: Sharp one-sided BH constant with slowly growing factor dimension
status: approved
source:
  kind: original
depends_on:
  - multifactor_radial_fdr_bounds
  - lei2026_one_sided_fdr_lower
uses_definitions:
  - gaussian_factor_dimension_budget
  - gaussian_multifactor_representation
  - gaussian_null_loading_coefficients
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_worst_case_bh_fdr
tags:
  - gaussian
  - multifactor
  - sharp_constant
  - slow_dimension
  - one_sided
  - supporting_target
---

## Statement

Let $D$ be a [Gaussian factor dimension budget](../definitions/gaussian_factor_dimension_budget.md) with $D(q)\geq1$ and
$$
D(q)\log\log(1/q)=o\!\left(\sqrt{\log(1/q)}\right),\qquad q\downarrow0.
$$
Apply the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) to the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md). The budget-restricted worst-case [false discovery rate](../definitions/false_discovery_rate.md) satisfies
$$
\lim_{q\downarrow0}\frac{F_{1,D}(q)}{q\sqrt{\log(1/q)}}=\frac1{\sqrt\pi}.
$$
In particular, the upper bound is uniform at every level over all representations with $1\leq d\leq\lfloor D(q)\rfloor$, all finite numbers of tests, all mean vectors (including negative one-sided null means), and all loading vectors of norm at most one. Every fixed factor dimension is covered. The positive-dimension convention does not exclude models whose loadings are all zero.

## Scope and provenance

This is the asymptotic supporting target proposed in idea_ad11695134a0 and idea_c6d561038d5f. The upper assertion requires a uniform quantile estimate in the [finite-level radial bounds for Gaussian multifactor BH](./multifactor_radial_fdr_bounds.md), rather than only an expansion with fixed $d$. Its matching lower assertion uses the [Lei finite Gaussian lower bound for one-sided BH](./lei2026_one_sided_fdr_lower.md), whose common-factor constructions embed into $d=1\leq D(q)$; finite construction size and its other parameters may depend on $q$. This is a restricted factor-class statement, and does not resolve the unrestricted Gaussian upper-bound target.

## Proof

Put $\ell=\log(1/q)$ and $n=n(q)=\lfloor D(q)\rfloor$. The budget assumption gives
$$
1\leq n(q)\leq D(q),\qquad n(q)\log\ell=o(\sqrt\ell).
$$
These statements are pointwise in $q$ and require neither monotonicity nor integer values of $D$. In the upper-bound argument restrict to sufficiently small $q$ that $\ell>2$, $u=\overline\Phi^{-1}(q)\geq1$, and $0<q\leq2\overline\Phi(1)$, the common range of the [finite-level radial bounds for Gaussian multifactor BH](./multifactor_radial_fdr_bounds.md). Every estimate below holds simultaneously for all integers $1\leq d\leq n(q)$.

First obtain a quantile bound with no fixed-dimension remainder. For a standard normal random variable $X$ and $0<t<1/2$, substitution in the Gaussian integral gives
$$
\mathbb E e^{tX^2}=\frac1{\sqrt{2\pi}}\int_{\mathbb R}e^{-(1-2t)x^2/2}\,dx=(1-2t)^{-1/2}.
$$
Thus, if $Z$ has $d$ independent standard normal coordinates,
$$
\mathbb E e^{t\|Z\|^2}=(1-2t)^{-d/2}.
$$
Take $t=(1-1/\ell)/2$ and define
$$
B_d(q)=\frac{2\ell+d\log\ell}{1-1/\ell},\qquad
B(q)=\frac{2\ell+n(q)\log\ell}{1-1/\ell}.
$$
Markov's inequality yields the explicit threshold calculation
$$
\mathbb P\{\|Z\|^2>B_d(q)\}
\leq e^{-tB_d(q)}\ell^{d/2}
=\exp\!\left(-\ell-\frac d2\log\ell+\frac d2\log\ell\right)
=q.
$$
The $\chi_d$ distribution is continuous with strictly decreasing survival function on $(0,\infty)$. Consequently its upper-$q$ quantile $b_d=b_d(q)$ obeys
$$
b_d^2\leq B_d(q)\leq B(q).
$$

For completeness, write $\phi(x)=e^{-x^2/2}/\sqrt{2\pi}$. Since $\phi'(x)=-x\phi(x)$ and $\phi(y)/y\to0$ as $y\to\infty$, integration by parts gives, for $x>0$,
$$
\overline\Phi(x)=\frac{\phi(x)}x-\int_x^\infty\frac{\phi(y)}{y^2}\,dy.
$$
The integral is nonnegative and at most $\overline\Phi(x)/x^2$. Rearranging proves both Mills inequalities:
$$
\frac{x}{1+x^2}\phi(x)\leq\overline\Phi(x)\leq\frac{\phi(x)}x.
$$
The radial theorem gives $b_d\geq u\geq1$, so $\Delta_1(d,q)=\log(q/\overline\Phi(b_d))\geq0$. Applying the lower Mills inequality and using $b_d+1/b_d\leq2b_d\leq2\sqrt{B(q)}$ proves
$$
\begin{aligned}
\Delta_1(d,q)
&=-\ell-\log\overline\Phi(b_d)\\
&\leq\frac{b_d^2}{2}-\ell+\log(b_d+1/b_d)+\frac12\log(2\pi)\\
&\leq C(q):=\frac{B(q)}2-\ell+\log\bigl(2\sqrt{B(q)}\bigr)+\frac12\log(2\pi).
\end{aligned}
$$
In particular, the sign of the logarithmic level in this estimate is negative. The exact identity
$$
\frac{B(q)}2-\ell=\frac{\tfrac12 n(q)\log\ell+1}{1-1/\ell}
$$
and $n(q)\log\ell=o(\sqrt\ell)$ imply $B(q)/\ell\to2$. Hence $\log(2\sqrt{B(q)})=O(\log\ell)$, and the same identity implies
$$
\frac{C(q)}{\sqrt\ell}\longrightarrow0,\qquad
0\leq\sup_{1\leq d\leq n(q)}\Delta_1(d,q)\leq C(q).
$$
All quantities on the right depend only on $q$ and the prescribed budget.

The Mills bounds also control the normal quantile with an explicit remainder. Since $q=\overline\Phi(u)$ and $u\geq1$, the upper Mills inequality gives
$$
q\leq\frac{e^{-u^2/2}}{\sqrt{2\pi}\,u}\leq e^{-u^2/2},\qquad u^2\leq2\ell.
$$
The lower Mills inequality then gives
$$
0\leq\ell-\frac{u^2}{2}
\leq\log(u+1/u)+\frac12\log(2\pi)
\leq\log\bigl(2\sqrt{2\ell}\bigr)+\frac12\log(2\pi).
$$
Dividing by $\ell$ proves $u/\sqrt{2\ell}\to1$.

Now take any representation in the budget class, with any finite $m$, any mean vector $\theta$, and any loading matrix $A$ whose rows have norm at most one. With the one-sided null set $I_0=\{i:\theta_i\leq0\}$, the [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md) satisfy
$$
0\leq\overline\gamma_0=\frac1m\sum_{i\in I_0}\gamma_i\leq\pi_0=\frac{|I_0|}{m}\leq1.
$$
The [finite-level radial bounds for Gaussian multifactor BH](./multifactor_radial_fdr_bounds.md), applied with $s=1$, therefore yield
$$
\begin{aligned}
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;m,\theta,\Sigma(A))
&\leq q+q\pi_0\left(\frac12+\Delta_1(d,q)\right)
+\frac{qu}{\sqrt{2\pi}}\overline\gamma_0\\
&\leq q\left(\frac32+C(q)\right)+\frac{qu}{\sqrt{2\pi}}.
\end{aligned}
$$
Here $\Delta_1\geq0$ justifies replacing $\pi_0$ by one. The theorem applies also to negative null means, zero loadings, unit-norm loadings and singular covariance matrices; none was removed in this argument. Its zero-null case is included as well. The final bound is independent of $d,m,\theta,A$. Taking the supremum over the full budget class at this fixed level, and only then letting $q\downarrow0$, gives
$$
F_{1,D}(q)\leq q\left(\frac32+C(q)\right)+\frac{qu}{\sqrt{2\pi}},\qquad
\limsup_{q\downarrow0}\frac{F_{1,D}(q)}{q\sqrt\ell}\leq\frac1{\sqrt\pi}.
$$

For the lower bound use the approved [Lei finite Gaussian lower bound for one-sided BH](./lei2026_one_sided_fdr_lower.md), including its source proof route's assertion that the finite transfer and independent perturbation preserve the common-factor class. At each fixed $q$ choose its accuracy parameter $\delta(q)=q^2$. It supplies a finite example of size $N(q)$, with true-null means zero and alternative means positive, for which
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N(q),\theta,\Sigma)>\ell_{\leq}(q)-q^2.
$$
By the common-factor assertion this example has a representation
$$
T_i=\theta_i+a_iZ+\sqrt{1-a_i^2}\,\varepsilon_i,\qquad a_i\in[-1,1],\quad 1\leq i\leq N(q),
$$
with independent standard normal $Z,\varepsilon_1,\ldots,\varepsilon_{N(q)}$. Regard each scalar $a_i$ as a vector in $\mathbb R^1$. This is exactly the [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) with $d=1$, so $D(q)\geq1$ places this finite example in the budget class. This uses the source's common-factor preservation, rather than inferring it from positive definiteness. Thus
$$
F_{1,D}(q)\geq\ell_{\leq}(q)-q^2.
$$
The same approved lower-bound result gives
$$
\ell_{\leq}(q)=\frac{q\sqrt\ell}{\sqrt\pi}+\frac q2+o(q).
$$
As $q^2/(q\sqrt\ell)=q/\sqrt\ell\to0$, division by $q\sqrt\ell$ proves
$$
\liminf_{q\downarrow0}\frac{F_{1,D}(q)}{q\sqrt\ell}\geq\frac1{\sqrt\pi}.
$$
The finite size $N(q)$ and all construction parameters may depend arbitrarily on $q$: existence at each fixed level suffices for the displayed inequality. No supremum is asserted to be attained, and no finite-size limit is interchanged with the level limit.

Combining the two bounds proves the stated limit. For every fixed positive integer $d$, the constant budget $D(q)=d$ satisfies the hypothesis; the one-factor lower examples also admit that exact dimension by padding their loadings with zeros. Finally, an all-zero-loading model has a representation with $d=1$ and $a_i=0$ for every $i$, so the positive-dimension convention includes it. The proof assumes only the two approved dependency results and approved definitions; the Gaussian-square moment identity and Mills bounds were derived above.
