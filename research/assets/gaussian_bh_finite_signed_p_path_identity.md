---
type: lemma
title: Exact finite signed conditional p-path identity for Gaussian BH
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - finite_identity
  - signed_response
  - teaching_route
---

## Statement

Use the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [one-sided Gaussian p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary BH](../definitions/benjamini_hochberg_step_up.md), and [FDR](../definitions/false_discovery_rate.md). For every finite $N\geq1$, $\theta\in\mathbb R^N$, positive semidefinite unit-diagonal covariance $\Sigma$, and $0<q<1/2$, write $T=\theta+Z$, $Z\sim\mathcal N_N(0,\Sigma)$, and $I_0=\{i:\theta_i\leq0\}$. Singular covariances are included. Set $S=\overline\Phi$ and $u=S^{-1}$.

For each $i\in I_0$, put $\rho_{ij}=\Sigma_{ij}$ and $\xi_j=Z_j-\rho_{ij}Z_i$. The vector $\xi$ is independent of the standard normal $Z_i$, including for singular $\Sigma$, and $\xi_i=0$. Conditional on $\xi$, define the full original score path, without dropping any coordinate or changing any label, by
$$
T_j^{\,i}(t)=\theta_j+\rho_{ij}\{u(t)-\theta_i\}+\xi_j,
\qquad 0<t<q.
$$
In particular, $T_i^{\,i}(t)=u(t)$. Let $R_i(t)$ be the actual largest non-strict ordinary-BH rejection count at level $q$ on this full path, let $r_i(t)=R_i(t)/N$, and set
$$
A_i(t)=\begin{cases}
\min\{t/(q r_i(t)),1\},&R_i(t)>0,\\
1,&R_i(t)=0.
\end{cases}
$$

All these residual and path objects have jointly measurable versions. A finite measurable event set $E_i(\xi)\subset(0,q)$ can be chosen to contain every solution of
$$
T_j^{\,i}(t)=u(qk/N),\qquad 1\leq j,k\leq N,
$$
for a nonconstant score path, and every clipping breakpoint $qk/N$ lying in $(0,q)$. Constant score paths, including paths identically equal to a threshold, are retained in BH's non-strict count, rather than treated as infinitely many events. On every component of $(0,q)\setminus E_i$, $R_i$ is constant and $A_i$ is affine. Let $J_i(\xi)\subseteq E_i(\xi)$ consist precisely of points with unequal one-sided limits $A_i(t^-)\ne A_i(t^+)$, the actual net jump discontinuities. Removable discrepancies at isolated point values are omitted from $J_i$. Then
$$
A_i(0+)=0,\qquad A_i(q-)=1,
$$
and, away from $E_i$,
$$
A_i'(t)=\frac{\mathbf1\{i\in\mathcal R_q(T^{\,i}(t))\}}{q r_i(t)},
$$
where the ratio is zero at rank zero. Simultaneous threshold crossings are merged; each actual net jump is counted once. Isolated point values do not affect the integrals.

Define
$$
g_i(t)=\exp\{\theta_i u(t)-\theta_i^2/2\},\qquad
F_i=\mathbb E\left[\frac{\mathbf1\{i\in\mathcal R_q(T)\}}{R_q(T)\vee1}\right].
$$
The function $g_i$ is continuous and nondecreasing on $(0,q]$, and is identically one when $\theta_i=0$. The following exact signed identity holds:
$$
F_i=\frac qN\mathbb E_\xi\left[
g_i(q)-\int_{(0,q)} A_i(t)\,dg_i(t)
+\sum_{t\in J_i(\xi)}g_i(t)\{A_i(t^-)-A_i(t^+)\}
\right].
$$
The integral is a Lebesgue-Stieltjes integral for the continuous nondecreasing $g_i$. Its baseline
$$
g_i(q)-\int_{(0,q)}A_i(t)\,dg_i(t)
$$
belongs to $[0,1]$. The finite signed jump sums are absolutely integrable over $\xi$. If $\theta_i=0$, the baseline equals one, giving
$$
F_i=\frac qN\left[1+\mathbb E_\xi\sum_{t\in J_i(\xi)}
\{A_i(t^-)-A_i(t^+)\}\right].
$$
For all original true-null means, including strictly negative ones, put
$$
B_i(\xi)=\sum_{t\in J_i(\xi)}g_i(t)
[A_i(t^-)-A_i(t^+)]_+,\qquad [a]_+=\max\{a,0\},\qquad
\pi_0=|I_0|/N.
$$
With $F=\sum_{i\in I_0}F_i$ the full original FDR, the identity implies
$$
F\leq q\pi_0+\frac qN\sum_{i\in I_0}\mathbb E B_i.
$$

## Scope and proof obligations

This is a draft exact identity and reduction, with no asserted quantitative bound on $B_i$. Its proof must establish measurability, finite event structure, endpoint limits, the derivative formula, change of variables under the residual conditioning, and all integrability assertions. It must cover $N=1$, singular covariance, simultaneous crossings, constant ties, rank zero, and negative true-null means without generic-position assumptions or regularization. The exact net signed sum remains available separately from its positive-part upper bound.

## Proof

Fix an admissible model and an original index $i\in I_0$. Write $\rho=(\rho_{i1},\ldots,\rho_{iN})^{\mathsf T}$. All arguments below use the original $N$ coordinates and the original true-null set.

**1. Gaussian residuals and the actual BH count.** Since $\Sigma_{ii}=1$, $Z_i$ is standard normal, $\xi_i=0$, and
$$
\operatorname{Cov}(\xi_j,Z_i)=\Sigma_{ji}-\rho_{ij}=0.
$$
The pair $(\xi,Z_i)$ is a linear image of $Z$, hence jointly Gaussian, with residual covariance $\Gamma=\Sigma-\rho\rho^{\mathsf T}$. For $a\in\mathbb R^N$ and $b\in\mathbb R$, the definition of a possibly singular Gaussian gives
$$
\mathbb E e^{\mathrm i(a^{\mathsf T}\xi+bZ_i)}
=\exp\{-\tfrac12(a^{\mathsf T}\Gamma a+b^2)\}
=\mathbb E e^{\mathrm i a^{\mathsf T}\xi}\,\mathbb E e^{\mathrm i bZ_i}.
$$
Here $\mathrm i$ denotes the imaginary unit. Uniqueness of characteristic functions identifies the joint law with the product of the two marginal laws. Thus $\xi$ and $Z_i$ are independent, without a nonsingularity hypothesis or a residual density. Residuals are measurable linear functions of $Z$. Their law is supported on the Borel hyperplane $H=\{x\in\mathbb R^N:x_i=0\}$, and we take this as their state space. The displayed score path is jointly Borel on $H\times(0,1)$; on this space its $i$th coordinate is $u(t)$.

For completeness, let $p\in[0,1]^N$ and let $K$ be its largest qualifying BH rank. If $K=0$, the rejection set is empty by definition. If $K>0$, at least $K$ coordinates are at most $qK/N$. If their number were $m>K$, then $p_{(m)}\leq qK/N\leq qm/N$, making $m$ a qualifying rank, a contradiction. Consequently the actual rejection count equals $K$, including ties. On the score path put
$$
C_k(x,t)=\sum_{j=1}^N\mathbf1\{T_j^{\,i}(t)\geq u(qk/N)\},\qquad
R_i(t)=\max\bigl(\{0\}\cup\{k:C_k(x,t)\geq k\}\bigr).
$$
The equivalence $p_{(k)}\leq qk/N\iff C_k\geq k$ proves the second formula. Each $C_k$ is jointly Borel; a maximum over finitely many Borel tests is Borel. It follows that $R_i,r_i,A_i$ and the individual rejection indicators have jointly Borel versions, using the stated separate value at rank zero. All comparisons here and below are non-strict.

**2. A finite measurable event decomposition.** For each $j$ with $\rho_{ij}\ne0$ and $1\leq k\leq N$, solving the threshold equation gives its unique possible solution
$$
e_{jk}(x)=S\!\left(\theta_i+\frac{u(qk/N)-\theta_j-x_j}{\rho_{ij}}\right).
$$
This is Borel and is retained only if it belongs to $(0,q)$. The path is strictly monotone when $\rho_{ij}\ne0$, since $u$ is strictly decreasing, so these are all its threshold solutions. When $\rho_{ij}=0$, the comparison is the fixed Borel test $\theta_j+x_j\geq u(qk/N)$; it contributes no event, even when equality persists for all $t$. Include the fixed clipping points $qk/N$, $1\leq k<N$.

Here is an explicit measurable enumeration, including all possible coincidences. Make a list of length
$$
M=N^2+N-1
$$
with one slot for each $(j,k)$ and each clipping point. Use the value $q$ in a slot whose correlation is zero or whose candidate is invalid. Denote this Borel list by $b_1,\ldots,b_M$ and set $e_0=0$. Recursively, for $1\leq \ell\leq M$, let $e_\ell$ be the minimum of $q$ and the $b_h$ satisfying $e_{\ell-1}<b_h<q$. This operation is Borel: replace a failing candidate by $q$ and take a finite minimum. Thus the values below $q$ are strictly increasing, each distinct valid candidate occurs once, and after they are exhausted all remaining entries equal $q$. The integer
$$
m(x)=\sum_{\ell=1}^M\mathbf1\{e_\ell(x)<q\}
$$
is Borel. Set $E_i(x)=\{e_1(x),\ldots,e_{m(x)}(x)\}$. In particular its graph is a finite union of Borel graphs restricted to Borel sets. On each Borel stratum $\{m=n\}$, use the endpoints $e_0=0<e_1<\cdots<e_n<e_{n+1}=q$.

On each open segment $(e_h,e_{h+1})$, every nonconstant threshold comparison has no zero and keeps its sign, and each constant comparison keeps its stipulated value. Hence $R_i$ has a constant value $k_h$. It is a Borel function of $x$, obtained by evaluating $R_i$ at the Borel midpoint $(e_h+e_{h+1})/2$. Define on $[0,q]$
$$
H_0(t)=1,\qquad H_k(t)=\min\{Nt/(qk),1\}\quad(1\leq k\leq N).
$$
Then $A_i(t)=H_{k_h}(t)$ on this segment. The clipping points included in $E_i$ ensure that this function is affine there. At an interior event $e_\ell$ its left and right traces are respectively $H_{k_{\ell-1}}(e_\ell)$ and $H_{k_\ell}(e_\ell)$. These formulas prove that both traces are Borel functions of $x$. Selecting precisely those events where the two traces differ gives a finite Borel enumeration of $J_i$. Thus a simultaneous crossing is processed once, with its actual net change; an actual point value different from two equal traces does not create a member of $J_i$.

**3. Endpoints, derivatives and finite variation.** The original coordinate $i$ has p-value $t$. If $0<t<q/N$, it forces the first rank to qualify, so $R_i(t)\geq1$ and
$$
0\leq A_i(t)\leq Nt/q.
$$
This proves $A_i(0+)=0$. If $q(N-1)/N<t<q$ and $R_i(t)<N$, either its rank is zero and $A_i=1$, or $t>qR_i(t)/N$ and again $A_i=1$. If its rank is $N$, then $A_i=t/q$. Both cases imply $A_i(q-)=1$. These statements also apply when $N=1$.

On a segment with rank $k>0$, $H_k$ has derivative $N/(qk)$ below $qk/N$ and zero above it. The original coordinate is rejected exactly when $t\leq qk/N$, because the actual rejection count is $k$. Equality cannot occur off $E_i$ if $k<N$, and if $k=N$ it would require $t=q$, outside the path. On a rank-zero segment both the derivative and the rejection indicator are zero. Therefore off $E_i$,
$$
A_i'(t)=\frac{\mathbf1\{i\in\mathcal R_q(T^{\,i}(t))\}}{q r_i(t)},\qquad
0\leq A_i'(t)\leq N/q,
$$
with the ratio defined to be zero at rank zero. Also $0\leq A_i\leq1$ everywhere. Define its derivative to be zero at $E_i$ when using it as a Lebesgue integrand. This is a jointly Borel version, obtained by multiplying the Borel ratio above by the indicator of the complement of the Borel event graph.

The sum of the variations along the open affine segments is at most $(N/q)q=N$. A representative taking, for example, the right trace at each event has additional variation at most $m\leq M$. With the actual value at an event restored, its passage from left trace to point value to right trace has variation at most $2$, since all three values lie in $[0,1]$. Consequently the actual function, extended by its endpoint limits, has variation at most $N+2M$. Its isolated values need not agree with a chosen one-sided representative.

**4. Conditional change of variables and the null weight.** Under the product law just proved, put $t=S(\theta_i+Z_i)$. The inverse change is $Z_i=u(t)-\theta_i$, and $u'(t)=-1/\phi(u(t))$, where $\phi(s)=(2\pi)^{-1/2}e^{-s^2/2}$. Thus, for each residual value, the scalar conditional density on $(0,1)$ is
$$
\phi(u(t)-\theta_i)|u'(t)|
=\frac{\phi(u(t)-\theta_i)}{\phi(u(t))}
=\exp\{\theta_i u(t)-\theta_i^2/2\}=g_i(t).
$$
Every original score is reconstructed by $Z_j=\rho_{ij}Z_i+\xi_j$, exactly as on the full path. The same formula can be used on $(0,1)$ for this change of variables. If $t>q$, coordinate $i$ cannot be rejected, since every BH threshold is at most $q$. The scalar event $t=q$ has probability zero. Nonnegative product integration therefore gives
$$
F_i=\mathbb E_\xi\int_0^q g_i(t)
\frac{\mathbf1\{i\in\mathcal R_q(T^{\,i}(t))\}}{R_i(t)\vee1}\,dt
=\frac qN\mathbb E_\xi\int_0^q g_i(t)A_i'(t)\,dt.
$$
For the second equality, off the finite event set and at rank $k>0$ the derivative formula gives $(q/N)A_i'=\mathbf1\{i\in\mathcal R_q\}/k$; both sides vanish at rank zero. A finite event set has zero scalar measure for every residual value, so it does not change this equality of integrals.

For $\theta_i<0$, the decrease of $u$ makes $g_i$ nondecreasing, and $u(t)\to+\infty$ as $t\downarrow0$ gives a continuous extension with $g_i(0)=0$. For $\theta_i=0$ the extension is identically one, including at zero. In both cases $g_i$ is continuous on $[0,q]$. Since $q<1/2$, $u(t)\geq u(q)>0$ on $(0,q]$; hence $\theta_i u(t)-\theta_i^2/2\leq0$, and
$$
0\leq g_i(t)\leq1,\qquad
\operatorname{Var}_{[0,q]}(g_i)=g_i(q)-g_i(0)\leq1.
$$
In particular the finite positive Lebesgue-Stieltjes measure $dg_i$ is atomless.

**5. Signed integration on the actual segments.** Fix a residual value and write its distinct events as above. On a segment $(a,b)=(e_h,e_{h+1})$, let $H=H_{k_h}$. It is affine on that segment and extends continuously to its endpoints. On compact subintervals of $(a,b)$, ordinary integration by parts, using the smooth function $g_i$ on $(0,q)$, gives the formula below. Letting the subinterval endpoints approach $a,b$ gives
$$
\int_a^b g_i(t)H'(t)\,dt
=g_i(b)H(b)-g_i(a)H(a)-\int_{(a,b)}H(t)\,dg_i(t).
$$
Indeed the endpoint products converge by continuity of $g_i,H$, the left integrals converge by the bound $|g_iH'|\leq N/q$, and the Stieltjes integrals converge because $0\leq H\leq1$, $dg_i$ is finite and atomless. This also justifies the two outer segments touching $0$ or $q$.

Summing the finitely many segment formulas, the contribution at an interior event $e$ is exactly
$$
g_i(e)\{A_i(e^-)-A_i(e^+)\}.
$$
The outer contributions are $g_i(q)A_i(q-)=g_i(q)$ and $-g_i(0)A_i(0+)=0$. Every event occurs once in the increasing enumeration. Equal traces contribute zero, so the interior sum reduces precisely to $J_i$. Since the event set is finite and $dg_i$ is atomless, the actual point values at events affect neither integral. We have therefore proved the pathwise equality with its signed net jumps:
$$
\int_0^q g_i(t)A_i'(t)\,dt
=g_i(q)-\int_{(0,q)}A_i(t)\,dg_i(t)
+\sum_{e\in J_i}g_i(e)\{A_i(e^-)-A_i(e^+)\}.
$$

**6. Measurability, integrability and the baseline.** The enumeration and trace formulas in step 2 make each summand, the signed sum and $B_i$ Borel functions of the residual; this can be checked separately on the finitely many strata $\{m=n\}$ and then combined. The bounded jointly Borel function $A_i(x,t)$ integrated against the fixed finite measure $dg_i(t)$ gives a measurable function of $x$. Likewise the derivative version in step 3 is jointly Borel, so its nonnegative Lebesgue integral against $g_i$ is measurable. Independently of the residual,
$$
\sum_{e\in J_i}\left|g_i(e)\{A_i(e^-)-A_i(e^+)\}\right|\leq M,
\qquad 0\leq B_i\leq M,
\qquad 0\leq\int_0^q g_i A_i'\,dt\leq N.
$$
These follow respectively from $|J_i|\leq M$, $0\leq g_i,A_i\leq1$, and $A_i'\leq N/q$. They establish absolute integrability of the finite signed sum as well as of all terms in the pathwise identity. Moreover
$$
0\leq\int_{(0,q)}A_i\,dg_i\leq g_i(q)-g_i(0),
$$
so its baseline lies in $[g_i(0),g_i(q)]\subset[0,1]$. Taking expectations in step 5 and substituting step 4 proves exactly
$$
F_i=\frac qN\mathbb E_\xi\left[g_i(q)-\int_{(0,q)}A_i\,dg_i
+\sum_{e\in J_i}g_i(e)\{A_i(e^-)-A_i(e^+)\}\right].
$$
For $\theta_i=0$, $dg_i=0$ and $g_i(q)=1$; the same equality is the stated zero-mean specialization, with baseline exactly one. The bounds $M,N$ above are solely finite-$N$ bounds used to make integration legitimate.

**7. Original FDR and boundary cases.** Only now use $g_i(e)\geq0$ to bound the signed sum above by $B_i$, and the baseline by $1$. This gives $F_i\leq(q/N)(1+\mathbb E B_i)$ for every original $i\in I_0$, including $\theta_i<0$. For the original rejection set, pointwise
$$
\frac{|\mathcal R_q(T)\cap I_0|}{R_q(T)\vee1}
=\sum_{i\in I_0}\frac{\mathbf1\{i\in\mathcal R_q(T)\}}{R_q(T)\vee1}.
$$
Taking expectations and summing the finite family yields
$$
F=\sum_{i\in I_0}F_i
\leq\frac qN|I_0|+\frac qN\sum_{i\in I_0}\mathbb E B_i
=q\pi_0+\frac qN\sum_{i\in I_0}\mathbb E B_i.
$$
If $I_0$ is empty, both sums and the FDR are zero.

When $N=1$, the only score on this path is $u(t)$, its p-value satisfies $t<q$, $R_i=1$ and $A_i=t/q$ throughout; there are no interior threshold or clipping events and the argument applies verbatim. Rank-zero segments in larger dimensions use $H_0=1$ and a zero derivative and rejection contribution. Correlations $0$ are treated by fixed comparisons, and correlations $1$ or $-1$ still have the unique candidate formula; the characteristic-function argument already covers all covariance degeneracies. Persistent threshold ties remain in the non-strict counts; duplicate and simultaneous events are merged before taking traces. If a point value differs from equal traces, both atomless integrals ignore it and its net jump is zero. A crossing occurring only at $q$ is not an interior event, and the established left endpoint trace at $q$ is still one. Strictly negative means use their actual density $g_i$ throughout. Thus none of these cases requires a generic-position assumption, smoothing, a removed coordinate or changed label. No positive-jump estimate uniform in dimension, or OU bridge, has been used. $\square$
