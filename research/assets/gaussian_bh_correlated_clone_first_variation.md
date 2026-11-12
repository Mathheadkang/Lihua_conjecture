---
type: lemma
title: Correlated-clone right variation of finite positive-definite Gaussian BH
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
  - correlated_clones
  - first_variation
  - signed_fdp_jumps
---

## Statement

Fix integers $N\ge1$ and $K\ge1$, a level $q\in(0,1/2)$, and a [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) with arbitrary means $\theta\in\mathbb R^N$ and positive-definite unit-diagonal covariance $\Sigma$. Choose any finite-dimensional unit-row representation
$$
G\sim\mathcal N_d(0,I_d),\qquad T_j=\theta_j+v_j\cdot G,\qquad
\|v_j\|=1,\qquad v_j\cdot v_k=\Sigma_{jk}\quad(j,k\in[N]).
$$
Here $[m]=\{1,\ldots,m\}$, the dot and norm are Euclidean, and $I_d$ is the identity matrix. Use the [one-sided Gaussian p-values and true-null labels](../definitions/gaussian_test_pvalues.md)
$$
p_j=\overline\Phi(T_j),\qquad I_0=\{j\in[N]:\theta_j\le0\}.
$$
For a deterministic score vector $t\in\mathbb R^N$, let $\mathcal R_q(t)$ be [ordinary BH](../definitions/benjamini_hochberg_step_up.md) applied to $(\overline\Phi(t_j))_{j\in[N]}$, always with the largest qualifying rank and the non-strict threshold inequalities. Put
$$
f(t)=\frac{|I_0\cap\mathcal R_q(t)|}{|\mathcal R_q(t)|\vee1},\qquad
F=\mathbb E f(T),\qquad
u_r=\overline\Phi^{-1}(qr/N)\quad(r\in[N]).
$$
Thus $f$ uses the fixed original labels $I_0$ and $F$ is the original [false discovery rate](../definitions/false_discovery_rate.md).

Fix $i\in[N]$. Write $E_i=\{y\in\mathbb R^d:v_i\cdot y=0\}$ and
$$
Z=v_i\cdot G,\qquad Y=G-Zv_i,\qquad
\rho_{ji}=v_j\cdot v_i,\qquad v_j^\perp=v_j-\rho_{ji}v_i.
$$
Then $Z$ is standard normal, $Y$ has the standard Gaussian probability measure $\gamma_{E_i}$ on the Euclidean space $E_i$, and $Z,Y$ are independent. In dimension zero $\gamma_{E_i}$ is the point mass at zero. In particular
$$
T_j=\theta_j+\rho_{ji}Z+v_j^\perp\cdot Y.
$$
Let $w_b\in E_i$ and $c_b\in\mathbb R$ be arbitrary fixed vectors and scalars for $b\in[K]$, subject to $c_b\le0$ for every $b$ when $\theta_i=0$. For $\varepsilon\ge0$, copy every original coordinate $K$ times, obtaining $NK$ scores indexed by $(j,b)\in[N]\times[K]$, and perturb only the $i$th group:
$$
T_{jb}^{\varepsilon}=T_j\quad(j\ne i),\qquad
T_{ib}^{\varepsilon}
=\theta_i+\varepsilon c_b+
\frac{(v_i+\varepsilon w_b)\cdot G}
 {\sqrt{1+\varepsilon^2\|w_b\|^2}}
=\theta_i+\varepsilon c_b+
\frac{Z+\varepsilon w_b\cdot Y}
 {\sqrt{1+\varepsilon^2\|w_b\|^2}}.
$$
Take $\varepsilon$ sufficiently small that every $\theta_i+\varepsilon c_b$ has the same sign as $\theta_i$ when $\theta_i\ne0$. Every expanded marginal has variance one, and the expanded model is jointly Gaussian, possibly singular. Its actual one-sided true-null set is exactly the preserved label set $I_0\times[K]$. Apply ordinary BH at level $q$ to the $NK$ p-values $\overline\Phi(T_{jb}^{\varepsilon})$. Denote its rejection set by $\mathcal R^\varepsilon$, its rejection count by $R^\varepsilon$, and its FDP and FDR with these labels by $f_K^\varepsilon$ and $F_K(\varepsilon)=\mathbb E f_K^\varepsilon$.

For each original rank $r\in[N]$, set $a_r=u_r-\theta_i$. For $y\in E_i$ and scalar $x$, define a score vector with all other statistics held fixed at their values on the face $T_i=u_r$:
$$
t^{i,r}(x,y)_i=x,\qquad
t^{i,r}(x,y)_j=\theta_j+\rho_{ji}a_r+v_j^\perp\cdot y\quad(j\ne i).
$$
Define its signed coordinate-face jump by
$$
\Delta_{i,r}(y)
=\lim_{h\downarrow0}
\left[f\bigl(t^{i,r}(u_r+h,y)\bigr)
      -f\bigl(t^{i,r}(u_r-h,y)\bigr)\right].
$$
These one-sided limits exist since the fixed-coordinate BH FDP is a step function on the finite threshold grid. The definition varies only coordinate $i$: the other coordinates are held at the displayed face values, rather than recomputed at $Z=a_r\pm h$. Both FDP values use their actual largest BH ranks and the original labels $I_0$, including every rank cascade. In particular, $\Delta_{i,r}$ is a signed difference and is never replaced by its positive part.

Let $\phi(z)=(2\pi)^{-1/2}e^{-z^2/2}$ and define a signed Borel measure on $E_i$ by
$$
\mu_{i,r}(B)=\phi(a_r)\int_B\Delta_{i,r}(y)\,\gamma_{E_i}(dy),
\qquad B\subseteq E_i\text{ Borel}.
$$
Write $|\mu_{i,r}|$ for its total variation measure, and put
$$
g(y)=\min_{b\in[K]}(w_b\cdot y+c_b).
$$
The following assertions hold for every fixed choice of the finite data above.

1. **Exact-copy invariance.** At $\varepsilon=0$ the expanded BH rejection set is exactly $\mathcal R_q(T)\times[K]$, its largest rank is $K|\mathcal R_q(T)|$, and $f_K^0=f(T)$ pointwise. Consequently $F_K(0)=F$.

2. **Finite signed face measures.** Every $\mu_{i,r}$ has finite total variation and finite first moments; more explicitly,
$$
\int_{E_i}(1+\|y\|)\,|\mu_{i,r}|(dy)
\le\phi(a_r)\int_{E_i}(1+\|y\|)\,\gamma_{E_i}(dy)<\infty.
$$
Thus every integral of $g$ against these signed measures is absolutely integrable with respect to total variation.

3. **All-or-none reduction at the fixed grid.** Define the reduced $N$-score vector by
$$
H_j^\varepsilon=T_j\quad(j\ne i),\qquad
H_i^\varepsilon=\min_{b\in[K]}T_{ib}^\varepsilon.
$$
There are constants $A,a,\varepsilon_0>0$, depending on the fixed model, representation, $i,K,q$, and perturbation marks, such that for $0<\varepsilon\le\varepsilon_0$,
$$
\mathbb P\left\{
\mathcal R^\varepsilon\ne\mathcal R_q(H^\varepsilon)\times[K]
\right\}\le A e^{-a/\varepsilon^2}.
$$
Outside that exceptional event all groups are rejected all or none, $R^\varepsilon=K|\mathcal R_q(H^\varepsilon)|$, and $f_K^\varepsilon=f(H^\varepsilon)$. In particular
$$
|F_K(\varepsilon)-\mathbb E f(H^\varepsilon)|
\le A e^{-a/\varepsilon^2}.
$$
For $K=1$ the equality of rejection sets holds pointwise and the exceptional probability is zero.

4. **Exact right derivative.** The finite right derivative exists and is
$$
\lim_{\varepsilon\downarrow0}
\frac{F_K(\varepsilon)-F_K(0)}{\varepsilon}
=\sum_{r=1}^N\int_{E_i}g(y)\,\mu_{i,r}(dy)
=\sum_{r=1}^N\phi(u_r-\theta_i)
\int_{E_i}\min_{b\in[K]}(w_b\cdot y+c_b)
\Delta_{i,r}(y)\,\gamma_{E_i}(dy).
$$
The density and signed jumps in this formula belong to the original $N$-coordinate model and its original BH ranks, rather than a free rank selector or separate blockwise optima.

## Scope and pending proof obligations

This is a draft finite-model identity extracted from the current project specification. No proof or approved prerequisite for the clone variation is supplied here. Its native falsification, proof execution, and independent verification remain necessary.

The proof must establish exact-copy invariance for all deterministic ties using the largest-rank convention. For the all-or-none estimate, it must use the positive spacing of the fixed expanded threshold grid $\overline\Phi^{-1}(q\ell/(NK))$, $\ell\in[NK]$, to show that partial rejection of the perturbed group forces a nonvanishing clone-score spread, then control that event by Gaussian tails. Normalization terms of order $\varepsilon^2 Z$ must also be controlled.

The derivative proof must retain the signed FDP jumps and justify the limit near intersections of coordinate threshold faces. Positive definiteness of the original covariance supplies nondegenerate two-coordinate Gaussian laws: intersections $T_i=u_r$, $T_j=u_s$ for $j\ne i$ are codimension two in the original Gaussian space, but their probability zero alone does not justify a first-order limit. A valid argument must control their shrinking neighborhoods relative to $\varepsilon$, with a justified truncation or domination for the unbounded Gaussian marks $g(Y)$, and show that they contribute no extra first-order term. It must also justify replacing the normalized minimum score by $\theta_i+Z+\varepsilon g(Y)$ in the derivative.

All constants and remainder assertions are for a fixed finite model and fixed grid. The statement asserts no uniform error rate in dimension, rank, $K$, covariance, means, or $q$; no attained extremizer, conditional convex order, inverse-Mills payment, extension to a singular original covariance, or universal FDR upper bound is included. Singularity of the explicitly expanded copy model is already allowed and does not constitute an extension of the original-model hypothesis.

## Proof

All labels in this proof are the fixed original labels $I_0$ and their copies. Every constant below is allowed to depend on all the fixed finite data in the statement. A constant denoted by $C$ may increase between inequalities. Write $\Phi=1-\overline\Phi$ for the standard normal distribution function.

**1. Largest ranks, copies, and labels.** For an arbitrary vector of $m$ p-values let $k>0$ be its largest qualifying BH rank. At least $k$ p-values are at most $qk/m$. If their number were $h>k$, then $p_{(h)}\le qk/m\le qh/m$, contradicting maximality. Thus the rejection count is $k$. Rank zero gives the empty set by definition. This reasoning includes every deterministic tie.

For exact $K$-fold copies of an $N$-vector, the expanded order statistic at rank $\ell$ is $p_{(\lceil\ell/K\rceil)}$. If $\ell$ qualifies and $r=\lceil\ell/K\rceil$, then
$$
p_{(r)}\le \frac{q\ell}{NK}\le\frac{qr}{N},
$$
so $r$ qualifies originally. Conversely, an original qualifying $r$ makes $Kr$ qualify in the expanded vector. Therefore the expanded largest rank is exactly $K$ times the original largest rank, also when neither has a positive qualifying rank. At their final thresholds, the rejection sets are exactly copies of one another. Both numerator and positive denominator in the FDP are multiplied by $K$, and both FDPs are zero at rank zero. This proves assertion 1 pointwise.

Since $w_b\cdot v_i=0$, the variance of $(v_i+\varepsilon w_b)\cdot G$ is $1+\varepsilon^2\|w_b\|^2$. The normalizations therefore give unit marginal variances, and all scores remain affine functions of $G$. When $\theta_i=0$, the restrictions $c_b\le0$ make every perturbed mean nonpositive. When $\theta_i\ne0$, finiteness of the marks permits a common positive upper bound on $\varepsilon$ preserving its sign. All other means are unchanged. Hence the actual expanded true-null labels are indeed $I_0\times[K]$ throughout the local argument.

**2. Signed jumps and measures.** With all but coordinate $i$ fixed, the entire BH rejection set is determined by the finitely many comparisons of each score with each $u_r$. As the $i$th score increases, its comparison vector changes only at the distinct points $u_r$, and at each point it agrees with its value immediately to the right because the inequalities are non-strict. Consequently its FDP is a right-continuous step function, bounded between zero and one, whose signed jumps have absolute value at most one. Each jump can be evaluated by taking a fixed sufficiently small positive displacement on either side of that grid point. The evaluations use finite Borel comparisons of the other scores, so $\Delta_{i,r}(y)$ is Borel measurable and $|\Delta_{i,r}(y)|\le1$ for every $y$.

It follows directly from its density that
$$
|\mu_{i,r}|(dy)=\phi(a_r)|\Delta_{i,r}(y)|\,\gamma_{E_i}(dy).
$$
Since a finite-dimensional standard Gaussian has a finite first norm moment, this gives exactly
$$
\int_{E_i}(1+\|y\|)\,|\mu_{i,r}|(dy)
\le\phi(a_r)\int_{E_i}(1+\|y\|)\,\gamma_{E_i}(dy)<\infty.
$$
Also
$$
|g(y)|\le\max_b|c_b|+\bigl(\max_b\|w_b\|\bigr)\|y\|.
$$
Thus every stated signed integral is absolutely integrable with respect to total variation. These arguments also apply to the point mass when $\dim E_i=0$, and prove assertion 2 without changing any signed jump to its positive part.

**3. A deterministic grid gap.** Suppose first $K>1$. Put $M=NK$ and
$$
b_\ell=\overline\Phi^{-1}(q\ell/M),\qquad \ell\in[M].
$$
This is a strictly decreasing finite grid. Each unchanged group has identical scores and hence is rejected whole or not at all at the final expanded threshold. If the $i$th group is partial, let $m\in\{1,\ldots,K-1\}$ be its rejected count and let $h$ be the number of rejected unchanged groups. By step 1 the expanded largest rank equals its rejection count $\ell=Kh+m$. In particular $L=K(h+1)\le M$ and $L>\ell$. Some $i$-clone has score at least $b_\ell$. If the spread of this group's scores were less than $b_\ell-b_L$, every $i$-clone would be strictly above $b_L$. The $h$ rejected unchanged groups already have scores at least $b_\ell>b_L$. Thus at least $L$ expanded scores would be at least $b_L$, making $L$ qualify, a contradiction. Therefore partial rejection forces spread at least
$$
\delta=\min_{\substack{1\le\ell\le M\\K\nmid\ell}}
\bigl(b_\ell-b_{K\lceil\ell/K\rceil}\bigr)>0.
$$
The finite set in this minimum is nonempty when $K>1$. The argument permits equality at any BH threshold.

Now suppose every group is whole and write the expanded largest rank as $Kh$, where $h$ is the number of rejected groups. If $h>0$, each of those groups has its minimum score at least $b_{Kh}=u_h$, so $h$ qualifies for BH on $H^\varepsilon$. Every reduced qualifying rank $r$, conversely, supplies at least $r$ groups whose minima are at least $u_r=b_{Kr}$, so $Kr$ qualifies in the expanded problem. The two largest ranks must therefore be $h$ and $Kh$. If $h=0$, a positive reduced qualifying rank would contradict the same converse implication, so both ranks are zero. At a positive final rank the unchanged groups have precisely their original scores and the $i$th group is either whole above the threshold or whole below it. Membership thus agrees exactly with the reduced minimum-score membership. Hence
$$
\mathcal R^\varepsilon=\mathcal R_q(H^\varepsilon)\times[K]
$$
whenever the $i$th group is not partial. For $K=1$, the expanded vector itself is $H^\varepsilon$, so this equality holds pointwise without a gap argument.

**4. Gaussian control of the exceptional event.** Define
$$
D_b(\varepsilon)=\sqrt{1+\varepsilon^2\|w_b\|^2}.
$$
The elementary inequality $0\le1-(1+x)^{-1/2}\le x/2$ for $x\ge0$ gives, for $0<\varepsilon\le1$,
$$
|T_{ib}^\varepsilon-T_i|
\le\varepsilon(|c_b|+|w_b\cdot Y|)
   +\tfrac12\varepsilon^2\|w_b\|^2|Z|.
$$
Here the coefficient of $w_b\cdot Y$ was bounded by $\varepsilon$ using $D_b\ge1$. Since $|Z|,\|Y\|\le\|G\|$ and there are finitely many marks, the spread is at most $C\varepsilon(1+\|G\|)$ for a fixed finite $C$. If the spread is identically zero, partial rejection is impossible. Otherwise we can choose $C>0$ and then restrict $\varepsilon\le\delta/(2C)$. Spread at least $\delta$ implies $\|G\|\ge\delta/(2C\varepsilon)$.

For $G\sim\mathcal N_d(0,I_d)$, independence of its coordinates and the elementary Gaussian integral give $\mathbb E\exp(\|G\|^2/4)=2^{d/2}$. Markov's inequality therefore yields
$$
\mathbb P\{\|G\|\ge t\}\le2^{d/2}e^{-t^2/4}.
$$
Together with step 3, this bounds the rejection-set discrepancy by $A\exp(-a/\varepsilon^2)$ for some fixed positive $A,a,\varepsilon_0$. Empty exceptional events, including $K=1$, also satisfy such a bound. On its complement, ranks and labels give $R^\varepsilon=K|\mathcal R_q(H^\varepsilon)|$ and $f_K^\varepsilon=f(H^\varepsilon)$. Both FDPs lie in $[0,1]$, so their expectations differ by at most that probability. This proves assertion 3, including its set-valued assertion and its FDR estimate.

**5. A normal coordinate that fixes the background.** Positive definiteness of $\Sigma$ implies linear independence of $v_1,\ldots,v_N$, because the squared norm of any linear combination of the rows is the associated covariance quadratic form. Let $U=\operatorname{span}\{v_j:j\ne i\}$, let $r_i=v_i-P_Uv_i\ne0$ be the orthogonal residual, and set
$$
\ell=\frac{r_i}{\|r_i\|},\qquad
\sigma=v_i\cdot\ell=\|r_i\|>0,\qquad
L=\ell^\perp.
$$
Here $P_U$ and $P_L$ denote Euclidean orthogonal projections onto the indicated subspaces, with $P_U=0$ if $U=\{0\}$. Since $v_i$ and $\ell$ are unit vectors, $0<\sigma\le1$. Decompose
$$
G=\ell S+B,\qquad S=\ell\cdot G,\qquad B=P_LG.
$$
Orthogonal Gaussian coordinates give independent $S\sim\mathcal N(0,1)$ and $B$ with standard Gaussian measure $\gamma_L$ on $L$. For every $j\ne i$, $v_j\cdot\ell=0$, so $T_j=\theta_j+v_j\cdot B$ is fixed when $B$ is fixed.

For such a fixed $B$, let $f_B(x)$ be the original $f$ with these unchanged scores and with $x$ in coordinate $i$. By step 2 it has the exact finite expansion
$$
f_B(x)=f_B(-\infty)+\sum_{r=1}^N D_r(B)\,1_{\{x\ge u_r\}},
\qquad |D_r(B)|\le1.
$$
The first term denotes its constant value below $u_N$, and $D_r(B)$ is its signed right-minus-left jump at $u_r$. This telescopes across the ordered grid, including its non-strict threshold values. Every $D_r$ is Borel measurable. In particular both sides of each jump use the actual largest BH ranks; there is no fixed-rank replacement in this expansion.

**6. Exact roots and their remainders.** Put $\alpha_b=w_b\cdot\ell$ and
$$
s_r(B)=\frac{a_r-v_i\cdot B}{\sigma},\qquad
G_r(B)=B+\ell s_r(B),\qquad
y_r(B)=G_r(B)-v_i a_r.
$$
Then $v_i\cdot G_r(B)=a_r$, so $y_r(B)\in E_i$, and $|s_r(B)|+\|y_r(B)\|\le C(1+\|B\|)$ uniformly in the finite set of $r$. Decrease $\varepsilon_0$ so that $\sigma+\varepsilon\alpha_b\ge\sigma/2$ for every $b$. As a function of $S$, each clone is then strictly increasing. Solving its exact crossing equation gives
$$
s_{b,r}^\varepsilon(B)=
\frac{D_b(\varepsilon)(a_r-\varepsilon c_b)-v_i\cdot B-\varepsilon w_b\cdot B}
{\sigma+\varepsilon\alpha_b}.
$$
It follows pointwise that
$$
H_i^\varepsilon\ge u_r
\quad\Longleftrightarrow\quad
S\ge s_r^\varepsilon(B),\qquad
s_r^\varepsilon(B)=\max_b s_{b,r}^\varepsilon(B).
$$
To check the first variation with its normalization retained, write
$$
h_{b,r}(B)=c_b+w_b\cdot B+\alpha_b s_r(B)
          =c_b+w_b\cdot y_r(B).
$$
The last equality uses $w_b\cdot v_i=0$. Direct subtraction of the roots yields the exact identity
$$
s_{b,r}^\varepsilon(B)-s_r(B)
=\frac{-\varepsilon h_{b,r}(B)
 +(D_b(\varepsilon)-1)(a_r-\varepsilon c_b)}
 {\sigma+\varepsilon\alpha_b}.
$$
Now $|h_{b,r}(B)|\le C(1+\|B\|)$, $D_b-1\le\varepsilon^2\|w_b\|^2/2$, and the denominator is at least $\sigma/2$. Moreover,
$$
\left|\frac1{\sigma+\varepsilon\alpha_b}-\frac1\sigma\right|
\le\frac{2\varepsilon|\alpha_b|}{\sigma^2}.
$$
Thus, uniformly in $b,r,B$ and sufficiently small positive $\varepsilon$,
$$
\left|s_{b,r}^\varepsilon(B)-s_r(B)
       +\frac{\varepsilon}{\sigma}h_{b,r}(B)\right|
\le C\varepsilon^2(1+\|B\|).
$$
Taking a maximum of a finite family changes a uniform remainder by at most its bound. Since $\varepsilon>0$, its first-order maximum is the negative of the minimum mark. Consequently
$$
s_r^\varepsilon(B)=s_r(B)
 -\frac{\varepsilon}{\sigma}g(y_r(B))
 +e_r^\varepsilon(B),\qquad
|e_r^\varepsilon(B)|\le C\varepsilon^2(1+\|B\|),
$$
and $|s_r^\varepsilon(B)-s_r(B)|/\varepsilon\le C(1+\|B\|)$ globally in $B$.

For completeness define $\widetilde H_j^\varepsilon=T_j$ for $j\ne i$ and $\widetilde H_i^\varepsilon=\theta_i+Z+\varepsilon g(Y)$. This last score is the minimum of $\theta_i+\varepsilon c_b+(v_i+\varepsilon w_b)\cdot G$. Its individual crossing roots $\widetilde s_{b,r}^\varepsilon$ are obtained from the displayed exact roots by replacing $D_b$ in their numerators by $1$. Therefore
$$
|s_{b,r}^\varepsilon-\widetilde s_{b,r}^\varepsilon|
=\left|\frac{(D_b-1)(a_r-\varepsilon c_b)}
 {\sigma+\varepsilon\alpha_b}\right|
\le C\varepsilon^2.
$$
Their maximum roots have the same bound. The step expansion and $\sup\phi\le(2\pi)^{-1/2}$ now give, after conditional normal integration,
$$
|\mathbb E f(H^\varepsilon)-\mathbb E f(\widetilde H^\varepsilon)|
\le C\varepsilon^2.
$$
Thus replacing the normalized minimum by that first-order score costs $o(\varepsilon)$. We will in fact use the exact normalized roots in the derivative.

**7. Conditional transport and all backgrounds.** For every fixed background $B$, step 5 and the crossing equivalences give the exact identity
$$
\mathbb E[f(H^\varepsilon)-f(T)\mid B]
=\sum_{r=1}^N D_r(B)
 [\Phi(s_r(B))-\Phi(s_r^\varepsilon(B))].
$$
One may read this as the integral over $S$ for each deterministic $B$; all its thresholds are finite and have zero mass under this one-dimensional normal law. The mean-value bound and step 6 imply that the absolute value of its difference quotient is at most $C(1+\|B\|)$, an integrable function under $\gamma_L$. For each $B$ the quotient tends to
$$
\sum_{r=1}^N D_r(B)\phi(s_r(B))
                 \frac{g(y_r(B))}{\sigma}.
$$
Dominated convergence therefore proves
$$
\lim_{\varepsilon\downarrow0}
\frac{\mathbb E f(H^\varepsilon)-F}{\varepsilon}
=\sum_{r=1}^N\int_L D_r(B)\phi(s_r(B))
              \frac{g(y_r(B))}{\sigma}\,\gamma_L(dB).
$$
This argument includes backgrounds at which other scores meet any of their threshold faces. For each $B$, all unchanged scores and all signed jumps $D_r(B)$ stay fixed during the exact normal integration. Their possible discontinuities as functions of $B$ are never differentiated or shifted. The same integrable bound holds on every background and hence on shrinking neighborhoods of any such discontinuities. Thus the conditional identity and dominated convergence account for face intersections directly; no inference from their unconditional probability zero is used to discard a first-order contribution.

**8. The Gaussian face density.** For fixed $r$, the affine map from $E_i$ to $L$ is
$$
\Psi_r(y)=P_L(v_i a_r+y).
$$
It is a bijection with inverse $B\mapsto y_r(B)$. Indeed, starting with $y\in E_i$ and $x=v_i a_r+y$, write $x=B+\ell s$ with $B=P_Lx$. Since $v_i\cdot x=a_r$, one obtains $s=(a_r-v_i\cdot B)/\sigma=s_r(B)$ and thus $y=y_r(B)$. Conversely, the construction of $G_r(B)$ gives $P_LG_r(B)=B$ and $v_i\cdot G_r(B)=a_r$, establishing the other composition.

The absolute Euclidean Jacobian of $P_L|_{E_i}$ is $\sigma$. To see this explicitly when $d\ge2$ and $\sigma<1$, let
$$
\eta=\frac{\ell-\sigma v_i}{\sqrt{1-\sigma^2}}\in E_i.
$$
The common subspace $E_i\cap L$ has dimension $d-2$, is perpendicular to $\eta$, and is fixed by $P_L$. Its image is perpendicular to $P_L\eta$. Since $\eta\cdot\ell=\sqrt{1-\sigma^2}$,
$$
\|P_L\eta\|^2=1-(\eta\cdot\ell)^2=\sigma^2.
$$
An orthonormal basis of the common subspace completed by $\eta$ therefore shows the volume factor $\sigma$. When $\sigma=1$, $\ell=v_i$, the two hyperplanes coincide and the restricted projection is the identity, again with Jacobian $1=\sigma$.

On corresponding points, orthogonality gives
$$
\|B\|^2+s_r(B)^2=\|G_r(B)\|^2
=\|y\|^2+a_r^2.
$$
Writing both standard Gaussian measures by their Euclidean densities in dimension $d-1$ and using $dB=\sigma\,dy$ consequently proves
$$
\frac{\phi(s_r(B))}{\sigma}\,\gamma_L(dB)
=\phi(a_r)\,\gamma_{E_i}(dy)
$$
under this change of variables. When $d=1$, linear independence forces $N=1$, $\ell=v_i$, $\sigma=1$, and $L=E_i=\{0\}$. Here $s_r(0)=a_r$, $y_r(0)=0$, and both Gaussian background measures are point masses. The same formula follows directly with the zero-dimensional Jacobian $1$, so no negative-dimensional common-subspace argument is needed.

For $j\ne i$, $v_j\cdot\ell=0$ and on this face
$$
\theta_j+v_j\cdot B
=\theta_j+v_j\cdot G_r(B)
=\theta_j+\rho_{ji}a_r+v_j^\perp\cdot y.
$$
These are exactly the unchanged scores in $t^{i,r}(x,y)$. The fixed labels and full BH rule are identical as well. Hence $D_r(B)=\Delta_{i,r}(y)$ for corresponding points, including any background ties and any cascade of the largest rank. Substitution into step 7 gives
$$
\lim_{\varepsilon\downarrow0}
\frac{\mathbb E f(H^\varepsilon)-F}{\varepsilon}
=\sum_{r=1}^N\phi(a_r)\int_{E_i}
       g(y)\Delta_{i,r}(y)\,\gamma_{E_i}(dy)
=\sum_{r=1}^N\int_{E_i}g\,d\mu_{i,r}.
$$

**9. Transfer to the expanded model.** Assertion 1 gives $F_K(0)=F$. Step 4 gives
$$
\frac{|F_K(\varepsilon)-\mathbb E f(H^\varepsilon)|}{\varepsilon}
\le A\varepsilon^{-1}e^{-a/\varepsilon^2}\longrightarrow0.
$$
Together with step 8, this proves exactly assertion 4, with its signed jumps, original grid, and actual original ranks. Its value is finite by step 2. All restrictions on $\varepsilon$ made above can be imposed simultaneously because there are finitely many marks and ranks and $\sigma>0$ is fixed. They include the local sign restrictions, and the arguments explicitly cover $K=1$ and zero-dimensional Gaussian backgrounds. All constants and remainders are for this fixed finite positive-definite original model. This completes all four assertions.
