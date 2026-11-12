---
type: lemma
title: Growing-private-clone compensated variation of finite Gaussian BH
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_correlated_clone_first_variation
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_bh_compensated_private_clone_model
tags:
  - gaussian_bh
  - private_clones
  - compensated_variation
  - iterated_limit
---

## Statement

Fix any finite original [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) with $N\ge1$, arbitrary $\theta\in\mathbb R^N$, positive-definite unit-diagonal $\Sigma$, any $q\in(0,1/2)$, and any chosen $i\in[N]$ satisfying $\theta_i\ne0$. Use any finite-dimensional unit-row representation $T_j=\theta_j+v_j\cdot G$, where $G\sim\mathcal N_d(0,I_d)$, $\|v_j\|=1$ and $v_j\cdot v_k=\Sigma_{jk}$. Use the [one-sided p-values and original null labels](../definitions/gaussian_test_pvalues.md) $S(T_j)$ and $I_0=\{j:\theta_j\le0\}$, where $S=\overline\Phi$, $\phi(t)=(2\pi)^{-1/2}e^{-t^2/2}$ and $h=\phi/S$. All BH procedures below are [ordinary largest-rank BH](../definitions/benjamini_hochberg_step_up.md) with their actual labels and non-strict thresholds.

Use the [compensated private-clone construction and common population crossing](../definitions/gaussian_bh_compensated_private_clone_model.md). In particular, each group has exactly $K$ copies, all groups other than $i$ remain exact, and only group $i$ is replaced by
$$
T_{ib}^{K,\varepsilon}
=\theta_i+d_\varepsilon+\frac{v_i\cdot G+\varepsilon\xi_b}{\sqrt{1+\varepsilon^2}},\qquad
s=\frac{\varepsilon}{\sqrt{1+\varepsilon^2}},\qquad
\phi(t_s)=s,\quad t_s>0,\qquad d_\varepsilon=s(t_s+t_s^{-1}).
$$
The private variables $\xi_b$ are independent standard Gaussians independent of $G$. Take $\varepsilon$ small enough that $\theta_i+d_\varepsilon$ retains the nonzero sign of $\theta_i$, so the actual expanded true-null set is exactly $I_0\times[K]$. Write $F$ for the original [FDR](../definitions/false_discovery_rate.md), $F_{K,\varepsilon}$ for the actual expanded FDR, and $\rho_\varepsilon,H_\varepsilon,J_\varepsilon,D_\varepsilon$ for the explicitly defined common-crossing functionals in that definition.

The signed measures in the conclusion are those of [the correlated-clone finite-model identity](gaussian_bh_correlated_clone_first_variation.md), in the following explicit coordinates. Put $E_i=v_i^\perp\subset\mathbb R^d$ and choose a linear isometry $U_i:\mathbb R^{d-1}\to E_i$. Write
$$
Z=v_i\cdot G,\qquad Y=U_i^{\mathsf T}G,\qquad
\rho_{ji}=v_j\cdot v_i,\qquad
u_r=S^{-1}(qr/N),\qquad a_r=u_r-\theta_i\quad(r\in[N]).
$$
Then $Z$ and $Y$ are independent standard Gaussian vectors in dimensions $1$ and $d-1$, respectively. For $x\in\mathbb R$ and $y\in\mathbb R^{d-1}$ set
$$
t^{i,r}(x,y)_i=x,\qquad
t^{i,r}(x,y)_j=\theta_j+\rho_{ji}a_r+v_j\cdot U_i y\quad(j\ne i).
$$
For the original fixed-label FDP $f(t)=|I_0\cap\mathcal R_q(t)|/(|\mathcal R_q(t)|\vee1)$ define
$$
\Delta_{i,r}(y)=\lim_{\eta\downarrow0}
\left[f(t^{i,r}(u_r+\eta,y))-f(t^{i,r}(u_r-\eta,y))\right],
$$
$$
\mu_{i,r}(B)=\phi(a_r)\int_B\Delta_{i,r}(y)\,\gamma_{d-1}(dy),
\qquad B\subseteq\mathbb R^{d-1}\text{ Borel}.
$$
Here $\gamma_{d-1}$ is standard Gaussian probability measure, with $\gamma_0$ the point mass on the zero-dimensional space. These are the approved identity's measures pulled back by $U_i$; their total masses do not depend on the chosen isometry. In the face jump only coordinate $i$ varies, while every other coordinate is frozen at its displayed face value. Both FDPs retain the actual original largest crossing, every rank cascade, and all original null labels. In particular these are signed measures, not positive parts.

The candidate assertions are the following, for every fixed choice of the finite data above.

1. There exists $\varepsilon_0>0$ such that for each fixed $\varepsilon\in(0,\varepsilon_0)$ the inner limit exists and has the common-largest-crossing representation
$$
F_{\infty,\varepsilon}:=\lim_{K\to\infty}F_{K,\varepsilon}
=\mathbb E_G D_\varepsilon(G).
$$
In this representation $H_\varepsilon(\rho_\varepsilon(G),G)=\rho_\varepsilon(G)$ whenever $\rho_\varepsilon(G)>0$, almost surely. The finite-copy limit and this representation are conclusions to establish before using the population functional; neither is an assumption. The numerator includes the fractional chosen-copy mass $b_\varepsilon$ when $i\in I_0$, as specified by $J_\varepsilon$.

2. The compensated iterated variation exists as a finite limit and satisfies
$$
\lim_{\varepsilon\downarrow0}
\frac{F_{\infty,\varepsilon}-F}{s/t_s}
=\sum_{r=1}^{N}\log\{r h(u_r)\}\,\mu_{i,r}(\mathbb R^{d-1}),
$$
where $\log$ is the natural logarithm. The order is $K\to\infty$ first at each fixed positive $\varepsilon$, then $\varepsilon\downarrow0$. All quantities on the right belong to the original finite model and its original ranks.

## Scope and verification obligations

This is a new draft candidate, with no proof asserted. The common-largest-crossing population formula, finite-copy convergence, and the compensated expansion require native falsification, proof, and independent verification. In particular, root births, root switches, actual multirank cascades and fractional-copy FDP contributions must be retained, including models with only one true-null group and the case $N=1$ when applicable.

The contact heuristic $\phi(t_r)=s/A_r$, where $A_r=1/[r h(u_r)]$ and $t_r>0$ is the positive solution for sufficiently small $s$, is motivation only. Any use of a displacement $s(t_r+t_r^{-1})$ and its expansion must be derived. The fixed-$K$ exponentially small error in the prerequisite identity supplies no estimate uniform in $K$ and does not justify exchanging the two limits.

The chosen zero-mean case $\theta_i=0$ is excluded because the positive compensation would change its true-null label. Negative chosen means are allowed only with the sign preserved. The original covariance is positive definite; no singular-original-model extension or uniform error over models is claimed. This supporting formula asserts no inverse-Mills cost bound, near-extremizer comparison, mixed trace budget, or unrestricted one-sided or two-sided FDR bound. No external contact result is assumed.

## Proof

All constants below may depend on the fixed original model and $q$. They do not depend on $K$ in the inner-limit argument. Constants used for the outer limit are uniform only for sufficiently small $s$ in this fixed model. At fixed $\varepsilon$, suppress its subscript in the population functions $H,J,b$ and crossing $\rho$. Write $\Phi=1-S$, $c_s=\sqrt{1-s^2}$, $\ell_i=\mathbf1\{i\in I_0\}$, and
$$
m=\theta_i+d_\varepsilon+c_s(T_i-\theta_i),\qquad
u(x)=S^{-1}(qx/N),\qquad
n(x)=\sum_{j\ne i}\mathbf1\{T_j\ge u(x)\}.
$$
The definitions at $x=0$ are those in the statement. The original nonzero mean and $d_\varepsilon\to0$ give a common sign-preserving interval. Every expanded coordinate is an affine function of independent Gaussian variables, its variance is $c_s^2+s^2=1$ in the chosen group, and its mean is $\theta_i+d_\varepsilon$ there. Consequently this is exactly a jointly Gaussian model with null labels $I_0\times[K]$ throughout that interval.

### 1. Exact empirical BH and microscopic ranks

Fix a positive $s<1$ in that interval. In this part $s$ is fixed before $K$ varies. Conditional on $T$, define
$$
B_K(x)=\frac1K\sum_{b=1}^K\mathbf1\{m+s\xi_b\ge u(x)\},\qquad
b(x)=S((u(x)-m)/s),\qquad H_K(x)=n(x)+B_K(x),
$$
$$
J_K(x)=\sum_{j\in I_0\setminus\{i\}}\mathbf1\{T_j\ge u(x)\}
                  +\ell_i B_K(x).
$$
At expanded rank $l$, the number below the non-strict p-value threshold is exactly $K H_K(l/K)$. Thus the BH rank divided by $K$ is
$$
x_K=\max\bigl(\{0\}\cup\{l/K:1\le l\le NK,\ H_K(l/K)\ge l/K\}\bigr).
$$
If the count at a positive maximizing rank $l$ were $L>l$, monotonicity of the threshold would give at least $L$ qualifying coordinates at rank $L$, a contradiction. Hence the actual number of rejections is $Kx_K$, $H_K(x_K)=x_K$ for $x_K>0$, and its FDP is $J_K(x_K)/x_K$. At $x_K=0$ its FDP is zero. This count argument includes all exact ties of unchanged copies.

Here is a direct uniform conditional empirical bound. For a Bernoulli variable $X$ of any parameter, the second derivative of $\log\mathbb E e^{\lambda X}$ is the variance under an exponential tilt and is at most $1/4$. Integrating twice from zero gives
$\mathbb E e^{\lambda(X-\mathbb EX)}\le e^{\lambda^2/8}$.
Independence and optimization over $\lambda$ therefore give
$$
\mathbb P\{|K^{-1}\textstyle\sum_b X_b-\mathbb EX_1|>v\mid T\}
\le2e^{-2Kv^2}.
$$
Choose a finite probability grid $j/M$, $0\le j\le M$, with $M^{-1}<a/4$, and apply this inequality at its Gaussian quantiles, using the constant endpoint events at probabilities zero and one. The empirical and population survival functions at any other threshold are bracketed by their values at adjacent grid quantiles. If all grid errors are at most $a/2$, the error everywhere is less than $a$. A union bound proves
$$
\mathbb P\{\sup_{0\le x\le N}|B_K(x)-b(x)|>a\mid T\}
\le2(M+1)e^{-Ka^2/2}.
$$
Summability over $K$, followed by intersection over $a=1,1/2,1/3,\ldots$, proves uniform conditional almost-sure convergence. Explicitly, the probability that any such deviation occurs after index $K_0$ is bounded by the tail of this summable series, which tends to zero.

Uniform convergence does not by itself control FDP at ranks tending to zero. For this purpose choose any exponent $p$ with $1<p<1/s^2$. Integration by parts gives, for $y>0$,
$$
\frac{y\phi(y)}{1+y^2}\le S(y)\le\frac{\phi(y)}y.
$$
For the lower bound use $S(y)=\phi(y)/y-\int_y^\infty\phi(z)z^{-2}dz$ and bound the integral by $S(y)/y^2$. With $y=u(x)\to\infty$ and $x=(N/q)S(y)$ these inequalities imply
$$
\frac{S((y-m)/s)}{S(y)^p}\longrightarrow0:
$$
the logarithm of the ratio is bounded above by
$-\tfrac12(s^{-2}-p)y^2+O(y+\log y)$.
Thus, for constants $C,\delta>0$ depending on the conditioned vector and this fixed $s$,
$$
b(x)\le Cx^p\quad(0<x\le\delta).
$$
Decrease $\delta<1$ so no unchanged atom occurs there and $z=eC\delta^{p-1}<1$. For $1\le l\le\lfloor\delta K\rfloor$, the binomial count $X=K B_K(l/K)$ satisfies
$$
\mathbb P\{X\ge l\mid T\}
\le\mathbb E\binom Xl=\binom Kl b(l/K)^l
\le[eK b(l/K)/l]^l\le z^l.
$$
The middle estimate follows by counting subsets of $l$ successes. For every fixed positive integer $l$, its penultimate bound tends to zero, since $K b(l/K)/l\le C(l/K)^{p-1}$. Interpret each summand as zero when $l>\lfloor\delta K\rfloor$; summing over all $l\ge1$ and comparing with the summable geometric series $\sum_l z^l$ yields
$$
\mathbb P\{\exists\,l\in\{1,\ldots,\lfloor\delta K\rfloor\}:
                  H_K(l/K)\ge l/K\mid T\}\longrightarrow0.
$$
An empty index range contributes zero. This proves the required microscopic-rank exclusion uniformly over the entire strip.

### 2. Population regularity and the inner expectation limit

For a fixed finite original vector, $b$ is continuous on $(0,N]$, lies strictly between zero and one, and $b(x)/x\to0$ at zero. The unchanged count $n$ has finitely many upward jumps, taking its right value at each atom. It is upper semicontinuous: at a jump its value is the larger of its two one-sided limits. Thus $H=n+b$ is upper semicontinuous away from zero. There are no crossings sufficiently close to zero. Every nonempty positive crossing set is therefore closed in a compact interval bounded away from zero and has a maximum $\rho$. If $H(\rho)>\rho$, right continuity supplies a larger crossing, unless $\rho=N$; the latter is impossible since $H(N)\le N-1+b(N)<N$. Hence
$$
H(\rho)=\rho\quad\hbox{if }\rho>0.
$$
In particular $\rho$ is not an integer, because $H(x)=n(x)+b(x)$ is never an integer for positive $x$.

We prove the needed almost-sure regularity, including at random atoms. Condition now on $W=(T_j)_{j\ne i}$. The Schur complement of the positive-definite original covariance gives a strictly positive conditional variance for $T_i\mid W$. Since $c_s>0$, $m\mid W$ has a density. On any atom-free interval where $n=k$, an equality $H(x)=x$ requires $x=k+\nu$, $0<\nu<1$, and
$$
m=g_{k,s}(\nu):=u(k+\nu)-s S^{-1}(\nu),\qquad 0\le k\le N-1.
$$
This function is real analytic on $(0,1)$ and is not constant, since it tends to $+\infty$ as $\nu\uparrow1$. Its derivative has only isolated zeros in $(0,1)$: otherwise the power-series identity principle would force the derivative to vanish identically. Such a discrete set is countable, by covering $(0,1)$ with countably many compact subintervals. The associated critical values of $m$ are a conditional null set.

At each of the finitely many atom locations $a=N S(T_j)/q$ in $(0,N]$, let $k_-$ and $k_+$ be the left and right unchanged counts. For each of these two counts, an endpoint equality can occur only if $0<a-k_\pm<1$, and then only at the single value
$$
m=u(a)-s S^{-1}(a-k_\pm).
$$
Exclude these finitely many additional conditional null values. This excludes both equality at the non-strict atom value and equality in its left limit. Conditioning on the empty $W$ gives exactly the same argument when $N=1$.

At every remaining vector, a positive largest root lies inside an atom-free interval and is simple. Indeed, writing $\nu=b(x)$ at a root gives
$$
g'_{k,s}(\nu)=\frac{s}{\phi(S^{-1}(\nu))}-A(x),\qquad
A(x)=-u'(x)=\frac{q}{N\phi(u(x))},
$$
so $g'=0$ is equivalent to $H'(x)-1=0$. At the largest root this nonzero derivative of $H-x$ is negative; a positive derivative would give later crossings. There are consequently strict positive and negative signs immediately to its left and right. For any $a>\rho$, upper semicontinuity on $[a,N]$ implies that $H(x)-x$ attains a strictly negative maximum there. If $\rho=0$, this negative-gap assertion holds on every $[a,N]$ with $a>0$.

On these regular vectors, $\rho$ is also the supremum of zero and the rational points where $H(x)>x$: a positive largest root has strict crossings immediately to its left, and if $\rho=0$ there are none. This gives a measurable version of $\rho$ and hence of its displayed bounded fractional FDP, agreeing almost surely with the functionals in the statement.

At a regular vector with $\rho>0$, choose atom-free bracketing points arbitrarily close to $\rho$ with these strict signs. A small interval to the left has a strictly positive gap and contains a lattice point $l/K$ for all sufficiently large $K$. Uniform conditional convergence of $H_K$ to $H$ supplies an empirical crossing there. The compact negative gap excludes all empirical crossings at distance at least any fixed positive amount above $\rho$. Therefore $x_K\to\rho$ conditionally almost surely. The unchanged selected set is eventually constant, since $\rho$ is not an atom, and
$$
B_K(x_K)\longrightarrow b(\rho),\qquad
\frac{J_K(x_K)}{x_K}\longrightarrow\frac{J(\rho)}\rho.
$$
If $\rho=0$, use the microscopic strip just proved and the compact negative gap on $[\delta,N]$. These together give $\mathbb P\{x_K>0\mid T\}\to0$, so its bounded FDP converges conditionally in probability and in mean to zero. In both cases conditional mean FDP converges to $D_\varepsilon$. Since it lies in $[0,1]$, integration over $T$ proves
$$
\lim_{K\to\infty}F_{K,\varepsilon}=\mathbb E D_\varepsilon.
$$
This establishes the first assertion for each fixed positive $\varepsilon$ in the sign-preserving interval; its regular null set may depend on $\varepsilon$. No small-noise asymptotic or fixed-$K$ perturbation estimate has been used in this inner limit.

### 3. High roots and all below-birth roots

We now take $s\downarrow0$, always after the inner limit. Put $\alpha_s=s/t_s$. Since $q<1/2$, $u(x)>0$ for $0<x\le N$, and differentiation gives
$$
A(x)=\frac1{x h(u(x))},\qquad A'(x)=-u(x)A(x)^2<0.
$$
For $r\in[N]$ put $k=r-1$. Parametrize $\nu=\Phi(t)$, so
$$
g_{k,s}(\Phi(t))=u(k+\Phi(t))+st,\qquad
Q_k(t)=A(k+\Phi(t))\phi(t).
$$
Here $Q_k$ is the plan's saddle function $B_k(t)$; the different letter distinguishes it from empirical masses. For $t\ge0$,
$$
(\log Q_k)'=-t-u(k+\Phi(t))Q_k(t)<0.
$$
Its value at zero is positive and it tends to zero as $t\to\infty$. Hence, for all sufficiently small $s$, there is exactly one $t_{c,r}>0$ with $Q_k(t_{c,r})=s$. The derivative of $g_{k,s}(\Phi(t))$ is $s-Q_k(t)$, so on $t\ge0$ it decreases to a unique minimum
$$
M_r=u(k+\Phi(t_{c,r}))+s t_{c,r}
$$
and then increases strictly to infinity. For each $m\ge M_r$ let $t_+(m)\ge t_{c,r}$ denote this upper root and set
$$
\nu_r(m)=\Phi(t_+(m)),\qquad
\delta_r(m)=1-\nu_r(m),\qquad x_r(m)=r-1+\nu_r(m).
$$
The exact saddle equation implies
$$
t_{c,r}^2=t_s^2+2\log A(k+\Phi(t_{c,r})).
$$
On $k+\Phi(t)\in[r-1/2,r]$, $A$ is bounded above and below by positive constants. Consequently, uniformly over the finitely many $r$,
$$
t_{c,r}=t_s+O(t_s^{-1}),\qquad
0\le\delta_r(m)\le S(t_{c,r})\le C\alpha_s,\qquad M_r\longrightarrow u_r.
$$

For $N\ge2$ choose a fixed $D>0$ smaller than half of every gap $u(k+1/2)-u(k+1)$, $1\le k\le N-1$, and set $\eta_s=S(D/s)$. For $N=1$ choose any fixed $D>0$ and the same definition; there are then no lower-root strips to consider. The tail bound above gives $\eta_s\le C e^{-c/s^2}$ for some $c>0$. If $k\ge1$ and $\eta_s\le\nu\le1/2$, then
$$
g_{k,s}(\nu)\ge u(k+1/2)-D>M_{k+1}
$$
for sufficiently small $s$. For $\nu\ge1/2$ its minimum is exactly $M_{k+1}$. Therefore any equality root in the cell $(k,k+1)$ below this birth level has $0<\nu<\eta_s$.

For the first cell, if $0<\nu\le1/2$, then $S^{-1}(\nu)\ge0$ and $u(\nu)\ge S^{-1}(\nu)$, whence
$$
g_{0,s}(\nu)\ge(1-s)u(\nu)\ge(1-s)u(1/2)>M_1
$$
for small $s$, because $u(1/2)>u(1)$. Along with the minimum on $\nu\ge1/2$, this proves there is no below-birth equality root in the first cell.

When $m\ge M_{k+1}$, the upper root is the largest equality root of $g_{k,s}(\nu)=m$ in this cell: roots in $\nu<1/2$ precede it, and the just-established decrease/increase on the upper half excludes later ones. If an actual equality root $x=k+\nu$ has unchanged count $k$, this upper root $x_{k+1}$ is at least $x$. Monotonicity of $n$ then gives $H(x_{k+1})\ge k+\nu_{k+1}=x_{k+1}$, so it is feasible even if atoms occur between the roots. In particular an actual largest crossing in this cell must be the upper root. Combining these facts, every positive actual largest crossing is either an upper root $x_r(m)$ with $m\ge M_r$, or a root $k+\nu$ with $k\ge1$, $m<M_{k+1}$, and $0<\nu<\eta_s$. This classification concerns the actual global maximum and retains all atom switches.

### 4. Exact compensated saddles and integrated upper-root deficit

Two integrations by parts give, for $t>0$,
$$
S(t)=\phi(t)(t^{-1}-t^{-3})+R(t),\qquad
0\le R(t)=3\int_t^\infty\phi(z)z^{-4}dz\le3\phi(t)t^{-5}.
$$
Write $A_r=A(r)$ and $\delta_c=S(t_{c,r})=O(\alpha_s)$. Smoothness near $r$ and the exact saddle equation yield
$$
\log A(r-\delta_c)=\log A_r+O(\alpha_s),\qquad
t_{c,r}=t_s+\frac{\log A_r}{t_s}
       +O(t_s^{-3}+s/t_s^2).
$$
The second estimate follows by taking the positive square root of
$t_s^2+2\log A_r+O(\alpha_s)$.
The Mills estimate and $\phi(t_{c,r})=s/A(r-\delta_c)$ also give
$$
A_r\delta_c=\frac{s}{t_{c,r}}
                 +O(s/t_s^3+s\delta_c/t_s),\qquad
u(r-\delta_c)=u_r+A_r\delta_c+O(\delta_c^2).
$$
Substitution in $M_r=u(r-\delta_c)+st_{c,r}$ proves
$$
M_r=u_r+s(t_s+t_s^{-1})+\alpha_s\log A_r
           +O(s/t_s^3+s^2).
$$
These bounds also apply to $r=1$, since $r-\delta_c$ stays near the positive number one. Converting the inequality $m\ge M_r$ to a threshold in the original $T_i$ gives
$$
\beta_r=\theta_i+\frac{M_r-\theta_i-d_\varepsilon}{c_s}
       =u_r+\alpha_s\log A_r+O(s/t_s^3+s^2).
$$
Here $c_s^{-1}=1+O(s^2)$ and $M_r-\theta_i-d_\varepsilon$ stays bounded. The finitely many original threshold gaps are positive, so $\beta_1>\cdots>\beta_N$ for small $s$.

The marginal variable $m$ is normal with variance $c_s^2$; its density is bounded by a common constant for small $s$. On the increasing branch, the substitution $m=u(k+\Phi(t))+st$ has derivative $s-Q_k(t)\ge0$. Thus
$$
\begin{aligned}
\mathbb E[\delta_r(m)\mathbf1\{m\ge M_r\}]
&\le C\int_{t_{c,r}}^\infty S(t)(s-Q_k(t))dt\\
&\le Cs\int_{t_{c,r}}^\infty S(t)dt
 = Cs[\phi(t_{c,r})-t_{c,r}S(t_{c,r})]
 =O(\alpha_s^2).
\end{aligned}
$$
The integral identity follows by interchanging the nonnegative integrals defining $S$; the final bound follows from the displayed Mills remainder and $\phi(t_{c,r})=O(s)$. The estimate is only for the upper branch and for all ranks, including one.

### 5. Global comparison with the actual largest crossing

Define $n_r=n(r)$ and $B_r=\mathbf1\{T_i\ge\beta_r\}=\mathbf1\{m\ge M_r\}$, and set
$$
R^*=\max\bigl(\{0\}\cup\{r\in[N]:n_r+B_r\ge r\}\bigr).
$$
Both $n_r$ and $B_r$ are nondecreasing in $r$. At a positive maximum $r$, one has $n_r+B_r=r$: if the count were at least $r+1$, rank $r+1$ would qualify, unless $r=N$, where a count above $N$ is impossible. Define $f_s^*$ to select the unchanged coordinates with $T_j\ge u_r$ and the chosen label precisely when $B_r=1$, using their original labels; put $f_s^*=0$ if $R^*=0$. This auxiliary functional therefore always selects exactly $R^*$ labels.

Let $E_H$ be the union over $r\in[N]$ and $j\ne i$ of
$$
\{m\ge M_r,\quad u_r\le T_j\le u(x_r(m))\}.
$$
Its interval length is at most $C\delta_r(m)$ because $x_r\in[r-C\alpha_s,r]$. Original positive definiteness implies that $T_j\mid T_i$ has variance $1-\Sigma_{ji}^2>0$ and a density bounded independently of $T_i$. Conditioning on $T_i$, and then using the integrated deficit just proved, gives
$$
\mathbb P(E_H)\le C\sum_r\mathbb E[\delta_r(m)\mathbf1\{m\ge M_r\}]
                =O(\alpha_s^2).
$$
Let $E_L$ be the union over $1\le k\le N-1$ and $j\ne i$ of
$\{u(k+\eta_s)\le T_j\le u(k)\}$.
Bounded marginal Gaussian densities and bounded $u'$ near the positive integers give $\mathbb P(E_L)=O(\eta_s)$. Empty unions have probability zero. All endpoints may be included. In particular off $E_L$,
$$
n(k+\nu)=n(k)\quad(0\le\nu\le\eta_s),
$$
and the same unchanged labels occur, for every $1\le k\le N-1$.

We now give an exhaustive routing argument outside these two events, at a regular original vector. The classification in part 3 applies to any actual positive largest crossing $\rho$. If it is an upper root $x_l$, then $n(x_l)=l-1$, so $n_l\ge l-1$ and $B_l=1$, implying that surrogate rank $l$ qualifies. If it is a microscopic root $k+\nu$, then $k\ge1$ and, off $E_L$, $n_k=n(k+\nu)=k$, so surrogate rank $k$ qualifies. These implications use no independence assumptions.

If $R^*=0$, either kind of positive actual maximum would therefore contradict the definition of $R^*$. Thus $\rho=0$ and both FDPs vanish.

Suppose $R^*=r$ and $B_r=1$. Then $n_r=r-1$. The high root $x_r$ exists. Off $E_H$, every one of these $r-1$ unchanged selected scores survives at the raised threshold $u(x_r)$, and no additional score can appear, since $u(x_r)>u_r$. Hence $n(x_r)=r-1$, its unchanged selected labels are exactly the surrogate's, and $H(x_r)=x_r$. Thus $\rho\ge x_r>r-1+1/2$. If the actual maximum is a high root $x_l$, the preceding qualification implication gives $l\le r$, so $\rho\le x_r$ (for $l<r$, $x_l<l\le r-1<x_r$). If it is microscopic, its integer part $k$ satisfies $k\le r$ by the other qualification implication. For $k<r$, $k+\nu\le r-1+\eta_s<x_r$; for $k=r$, off $E_L$ it would require $n_r=k=r$, contradicting $n_r=r-1$. Hence the actual maximum is exactly $x_r$ and has exactly the surrogate's unchanged selected labels.

Suppose instead $R^*=r>0$ and $B_r=0$. Then $n_r=r$, so $r\le N-1$ and $H(r)=r+b(r)>r$. In particular $\rho>r$. A high actual maximum $x_l$ would have $l\ge r+1$ and qualify surrogate rank $l$, impossible. A microscopic actual maximum has $k\ge r$; $k>r$ is excluded by qualification of rank $k$. Consequently
$$
r<\rho=r+\nu\le r+\eta_s.
$$
Off $E_L$ its unchanged selected set is precisely the same $r$ labels as the surrogate, and its chosen mass is $b(\rho)=\nu\le\eta_s$. The endpoint $r=N$ cannot arise in this case; in the high case $x_N<N$ already treats the top endpoint. This exhausts all routing possibilities, including background-only crossings and global changes of selected rank.

In the high case let $v$ be the number of unchanged true nulls selected. For $r\ge2$ the two FDPs are
$$
D_\varepsilon=\frac{v+\ell_i\nu_r}{r-1+\nu_r},\qquad
f_s^*=\frac{v+\ell_i}r,
$$
whose difference is at most $C\delta_r(m)$. For $r=1$, $v=0$ and both are exactly $\ell_i$, regardless of the positive fraction $\nu_1$. In the background case the two FDPs are $(v+\ell_i\nu)/(r+\nu)$ and $v/r$, with difference at most $C\eta_s$. On $E_H\cup E_L$ the difference is at most one. Integration, using part 4 for all possible high ranks, proves the global bound
$$
\mathbb E|D_\varepsilon-f_s^*|\le C(\alpha_s^2+\eta_s).
$$
This bound includes fractional null-copy mass, atom clipping, root births and switches, and the actual largest crossing. It has been derived from the routing cases rather than inferred from the local saddle.

### 6. Signed original faces and assembly

For an unchanged score vector $w=(w_j)_{j\ne i}$ define the signed jump
$$
\lambda_r(w)=f(u_r+,w)-f(u_r-,w),
$$
where only the chosen coordinate varies in this notation. Both values use the original fixed labels and their full largest-rank rule, so $|\lambda_r(w)|\le1$. Write $d_r=\beta_r-u_r$. For small $s$ the bands between $u_r$ and $\beta_r$ are pairwise disjoint and lie inside disjoint neighborhoods of the original thresholds. Outside these bands, every qualification $B_l$ agrees with $\mathbf1\{T_i\ge u_l\}$, so $f_s^*=f(T)$. Within the $r$th band, only qualification $r$ differs. The two qualification vectors are exactly those of the original chosen score just above and just below $u_r$, with all other scores frozen. The largest-rank definition of $R^*$ and its exact selected-count identity therefore imply a change of $-\lambda_r(w)$ if $\beta_r>u_r$, and $+\lambda_r(w)$ if $\beta_r<u_r$. This accounts for any resulting cascade in the final selected rank, without assigning a sign to the jump.

For completeness the required regularity of its conditional integral follows directly from the Gaussian density. If $N\ge2$, $W\mid T_i=t$ has mean $\theta_{-i}+a(t-\theta_i)$, $a=\Sigma_{-i,i}$, and positive-definite covariance $C=\Sigma_{-i,-i}-aa^{\mathsf T}$ independent of $t$. Its density $p_t$ satisfies
$$
\partial_t p_t(w)=p_t(w)\,a^{\mathsf T}C^{-1}
                  (w-\theta_{-i}-a(t-\theta_i)),\qquad
\int|\partial_t p_t(w)|dw\le\sqrt{a^{\mathsf T}C^{-1}a}.
$$
Thus the bounded jump's conditional integral is Lipschitz in $t$. The same statement is immediate for the empty vector when $N=1$. In particular
$$
L_r(t)=\phi(t-\theta_i)\,\mathbb E[\lambda_r(W)\mid T_i=t]
$$
is Lipschitz near $u_r$. Integrating the exact band identity with an oriented integral gives
$$
\mathbb E f_s^*-F
 =-\sum_{r=1}^N\int_{u_r}^{\beta_r}L_r(t)dt
 =-\sum_{r=1}^N d_r L_r(u_r)+O\left(\sum_r d_r^2\right).
$$
Conditioning on $T_i=u_r$ is conditioning on $Z=a_r$ in the statement's orthogonal representation. The unchanged scores are then exactly
$\theta_j+\rho_{ji}a_r+v_j\cdot U_iY$, with $Y\sim\gamma_{d-1}$ independent of $Z$. Therefore
$$
L_r(u_r)=\phi(a_r)\int\Delta_{i,r}(y)\gamma_{d-1}(dy)
        =\mu_{i,r}(\mathbb R^{d-1}).
$$
Only the chosen coordinate moves inside this jump; the other coordinates are frozen at their face values. All signed original-face masses are finite because $|\Delta_{i,r}|\le1$.

Since $d_r=\alpha_s\log A_r+O(s/t_s^3+s^2)$ and $d_r=O(\alpha_s)$, the inner limit, the global comparison, and this face calculation imply
$$
F_{\infty,\varepsilon}-F
 =-\alpha_s\sum_{r=1}^N\log A_r\,
           \mu_{i,r}(\mathbb R^{d-1})
       +O(\alpha_s^2+s/t_s^3+s^2+\eta_s).
$$
Each remainder is $o(\alpha_s)$: their ratios are respectively $\alpha_s$, $t_s^{-2}$, $s t_s$, and $\eta_s t_s/s$, all tending to zero. Finally $-\log A_r=\log\{r h(u_r)\}$ gives the stated coefficient and its sign.

The argument used $\ell_i$ as the actual fixed null label throughout. It therefore includes a negative chosen mean with its sign preserved. If $I_0$ is empty all FDPs and signed masses vanish. If $N=1$, a positive chosen mean has this empty-null case; for a negative chosen mean both positive fractional FDP and the surrogate FDP equal one, the first-cell result gives $D_\varepsilon=\mathbf1\{T_i\ge\beta_1\}$ up to a null event, and the same signed-band calculation applies with $\Delta_{i,1}=1$. No draft definition or additional unproved result is assumed. The asset remains draft pending independent verification.
