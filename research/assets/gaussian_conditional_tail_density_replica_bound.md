---
type: lemma
title: Gaussian conditional tail-density replica bound at deterministic levels
status: approved
source:
  kind: original
  location: >-
    plan_one_sided_order_gaussian_interpolation_sdp_20261106, Progress, Step
    4(b)
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
tags:
  - gaussian_dependence
  - conditional_density
  - replica_bound
  - universal_order_support
---

## Statement

Let $N$ be any positive integer, let $\Sigma$ be any positive-semidefinite $N\times N$ matrix with unit diagonal, and let $X\sim\mathcal N_N(0,\Sigma)$. Singular $\Sigma$ is allowed, as in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md). Let $\theta\in\mathbb R^N$, and write $I_0=\{i\in[N]:\theta_i\le0\}$ for the one-sided true-null set in [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md). Define $\phi(x)=(2\pi)^{-1/2}\exp(-x^2/2)$ and $S(x)=\overline\Phi(x)=\int_x^\infty\phi(y)\,dy$.

Fix $0<\nu\le1$ and put $r=\sqrt{1-\nu}$. For deterministic real levels $v,w$ and indices $i,j\in[N]$, define
$$
p_i(v\mid X)=S\!\left(\frac{v-\theta_i-rX_i}{\sqrt\nu}\right),\qquad
d_j(w\mid X)=\frac1{\sqrt\nu}\phi\!\left(\frac{w-\theta_j-rX_j}{\sqrt\nu}\right).
$$
For every $i\in I_0$, every deterministic $v\ge U\ge1$, every $j\in[N]$ and every deterministic $w\in\mathbb R$, with $q=S(U)$,
$$
\mathbb E[p_i(v\mid X)d_j(w\mid X)^2]
\le \sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}
\le\frac{q(1+U)}{\sqrt\nu}.
$$
The indices $i,j$ may coincide. For any further index $k\in[N]$ and deterministic $z\in\mathbb R$,
$$
\mathbb E[p_i(v\mid X)d_j(w\mid X)d_k(z\mid X)]
\le\sqrt{\mathbb E[p_i(v\mid X)d_j(w\mid X)^2]\mathbb E[p_i(v\mid X)d_k(z\mid X)^2]}
\le\sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}.
$$
All expectations are over $X$. The bounds are uniform in $N$, $\theta$, $\Sigma$ and the displayed deterministic levels subject to these assumptions.

For every $\eta>0$, the interpolation residual variance and shared coefficient
$$
\nu_a=\frac{1-a+\eta^2}{1+\eta^2},\qquad r_a^2=\frac a{1+\eta^2},\qquad 0\le a\le1,
$$
give $T_{a,\eta}=\theta+r_aX+\sqrt{\nu_a}\,\varepsilon$, where $\varepsilon\sim\mathcal N_N(0,I_N)$ has independent standard-normal coordinates and is independent of $X$, and satisfy
$$
\int_0^1\nu_a^{-1/2}\,da
=2\sqrt{1+\eta^2}\bigl(\sqrt{1+\eta^2}-\eta\bigr)
=\frac{2\sqrt{1+\eta^2}}{\sqrt{1+\eta^2}+\eta}\le2.
$$
Thus the displayed scalar bounds have an integrable interpolation endpoint bound uniform in $\eta$. The statement concerns deterministic levels only.

## Provenance and scope

Extracted from [the Gaussian interpolation SDP proof plan](../plans/plan_one_sided_order_gaussian_interpolation_sdp_20261106.md), `Progress`, Step 4(b), reconstructed there by the executing agent from a root proposal. That plan failed at its separate uniform matrix-aggregation gate; its failure is retained. The exact source section, with one terminal newline, has SHA256 `a9ad5b1b3045180220ddaab352a887edde75833a5c714863d919d437758eec39`.

A fresh, uninvolved agent previously checked this section read-only. That scoped check is not native verification or approval of this new draft. The candidate proof below is copied verbatim from the source section, including its reference to the Mills integration-by-parts bound proved in that plan's Step 4(a). Its scope caveats use $H$ for the source plan's signed BH boundary matrix and $\beta(H)$ for its diagonal positive-semidefinite completion charge; neither is a quantity bounded by this lemma. This supporting asset asserts neither a random-level extension nor a full BH matrix budget or a main FDR order bound.

## Extracted proof awaiting native execution

### Step 4(b): a dimension-free Gaussian scalar charge (supporting lemma; reconstructed from a root proposal)

This scalar lemma is not a matrix domination of $H$. Let $0<\nu\le1$, $r=\sqrt{1-\nu}$, and $X\sim N_N(0,\Sigma)$ for any unit-diagonal PSD $\Sigma$, including singular matrices. Define, conditional on $X$,
$$
p_i(v\mid X)=S\!\left(\frac{v-\theta_i-rX_i}{\sqrt\nu}\right),\qquad
d_j(w\mid X)=\frac1{\sqrt\nu}\phi\!\left(\frac{w-\theta_j-rX_j}{\sqrt\nu}\right).
$$
For $i\in I_0$, $v\ge U\ge1$, and arbitrary $j,w,\theta_j$, the claim is
$$
\tag{SC}
\mathbb E[p_i(v\mid X)d_j(w\mid X)^2]
\le \sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}
\le\frac{q(1+U)}{\sqrt\nu},\qquad q=S(U).
$$
The indices $i,j$ may coincide. To prove this, add three independent standard-normal residual copies, independent of $X$, and put
$$
Y_i=\theta_i+rX_i+\sqrt\nu\,\varepsilon^0,
\quad Y_j^1=\theta_j+rX_j+\sqrt\nu\,\varepsilon^1,
\quad Y_j^2=\theta_j+rX_j+\sqrt\nu\,\varepsilon^2.
$$
Even if $i=j$ these residual copies are distinct. The left side of (SC) is the joint density at $Y_j^1=Y_j^2=w$ together with the event $Y_i\ge v$. Set $A=(Y_j^1+Y_j^2)/2$ and $D=(Y_j^1-Y_j^2)/2$. Then
$$
\mathbb E A=\theta_j,\quad \sigma_A^2=\operatorname{Var}(A)=1-\nu/2,\quad
\operatorname{Var}(D)=\nu/2,
$$
and $D$ is independent of $(A,Y_i)$, by joint Gaussianity and zero covariances. The change of variables $(A,D)\mapsto(Y_j^1,Y_j^2)$ has absolute Jacobian 2. Thus the left side is exactly
$$
\frac{1}{2\sqrt{\pi\nu}\,\sigma_A}\,
\phi(z)\Pr\{Z_i\ge b\mid Z_A=z\},
\qquad z=\frac{w-\theta_j}{\sigma_A},\quad b=v-\theta_i\ge U,
$$
where $Z_i=Y_i-\theta_i$ and $Z_A=(A-\theta_j)/\sigma_A$ are standard normal. Their correlation is $\rho=r^2\Sigma_{ij}/\sigma_A$, whose absolute value is strictly less than one for $\nu>0$.

Here is the required elementary bivariate bound. For any $b\ge1$ and $|\rho|<1$, write $s=\sqrt{1-\rho^2}$ and use the bivariate density identity
$$
\phi(z)\Pr(Z_i\ge b\mid Z_A=z)
=\int_b^\infty \phi(x)\frac1s\phi\!\left(\frac{z-\rho x}{s}\right)dx.
$$
If $|\rho|\ge1/2$, monotonicity of $\phi$ on $[b,\infty)$ bounds this by $\phi(b)/|\rho|\le2\phi(b)$: extending the last Gaussian kernel integral to all $x$ gives $1/|\rho|$. If $|\rho|<1/2$, then $s>\sqrt3/2$ and the bound is $S(b)/(s\sqrt{2\pi})\le\phi(b)$, using $S(b)\le\phi(b)/b$ and $b\ge1$. Hence it is always at most $2\phi(b)$. This also has the evident degenerate extension at $\rho=\pm1$, where the conditional tail is an indicator; the application above already has strict inequality.

Substitution and $\sigma_A\ge1/\sqrt2$ yield
$$
\mathbb E[p_i d_j^2]\le\frac{\phi(b)}{\sqrt{\pi\nu}\,\sigma_A}
\le\sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}.
$$
The last inequality in (SC) follows from the Mills integration-by-parts bound proved in Step 4(a), since $\sqrt{2/\pi}<1$. This proof uses only the two unit marginal variances and their Gaussian joint law; it is uniform in factor dimension, all means allowed above, every correlation including original singularity, and all $N$.

Weighted Cauchy--Schwarz gives the further bound, for arbitrary $j,k,w,z$,
$$
\tag{SC2}
\mathbb E[p_i(v\mid X)d_j(w\mid X)d_k(z\mid X)]
\le\sqrt{\mathbb E[p_i d_j(w)^2]\mathbb E[p_i d_k(z)^2]}
\le\sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}.
$$
For the covariance path in this plan,
$$
\nu_a=\frac{1-a+\eta^2}{1+\eta^2},\qquad r_a^2=\frac a{1+\eta^2},\qquad
T_{a,\eta}=\theta+r_aX+\sqrt{\nu_a}\,\varepsilon
$$
with independent standard residual coordinates. The exact integral is
$$
\int_0^1\nu_a^{-1/2}da
=2\sqrt{1+\eta^2}\bigl(\sqrt{1+\eta^2}-\eta\bigr)
=\frac{2\sqrt{1+\eta^2}}{\sqrt{1+\eta^2}+\eta}\le2.
$$
Thus the scalar charges have an integrable endpoint bound uniform in $\eta$. They do not bound $\beta(H)$ unless a valid matrix aggregation removes the number of faces and indices; no such aggregation is asserted here.

## Proof

### Step 1: setting

Fix an arbitrary admissible finite $N$, positive-semidefinite unit-diagonal $\Sigma$, and $X\sim\mathcal N_N(0,\Sigma)$. Fix $0<\nu\le1$ and $r=\sqrt{1-\nu}$. Let $i\in I_0$, so $\theta_i\le0$, and fix deterministic $v\ge U\ge1$, arbitrary $j\in[N]$, and arbitrary deterministic $w\in\mathbb R$. All other means are unrestricted. Use $\phi,S,p_i,d_j$ as defined in the statement, and set $q=S(U)$. The construction below permits singular $\Sigma$ and coincident indices.

### Step 2: both Mills estimates

For $b>0$ and $x\ge b$, $1\le x/b$, so $\phi'(x)=-x\phi(x)$ gives
$$
S(b)\le b^{-1}\int_b^\infty x\phi(x)\,dx=\frac{\phi(b)}b.
$$
For $R>b$, integration by parts yields
$$
\int_b^R\phi(x)\,dx
=\frac{\phi(b)}b-\frac{\phi(R)}R-\int_b^R\frac{\phi(x)}{x^2}\,dx.
$$
The boundary term $\phi(R)/R$ tends to zero by its exponential decay. The last integrand is nonnegative and its integral is bounded by $b^{-2}S(b)<\infty$, so passage to the limit yields
$$
S(b)=\frac{\phi(b)}b-\int_b^\infty\frac{\phi(x)}{x^2}\,dx
\ge\frac{\phi(b)}b-\frac{S(b)}{b^2}.
$$
Rearrangement gives $\phi(b)\le(b+b^{-1})S(b)$. For $U\ge1$, $U^{-1}\le1$ and $\sqrt{2/\pi}<1$, whence
$$
\sqrt{2/\pi}\,\phi(U)
\le\sqrt{2/\pi}(U+U^{-1})S(U)
\le(U+1)S(U).
$$
These estimates were derived here without any premise from the failed source plan.

### Step 3: independent replicas and a pointwise density

Enlarge the probability space by independent standard normals $\varepsilon^0,\varepsilon^1,\varepsilon^2$, independent of $X$, and define
$$
Y_i=\theta_i+rX_i+\sqrt\nu\varepsilon^0,\qquad
Y_j^1=\theta_j+rX_j+\sqrt\nu\varepsilon^1,\qquad
Y_j^2=\theta_j+rX_j+\sqrt\nu\varepsilon^2.
$$
The superscripts distinguish the three residual variables even when $i=j$. Conditional on $X$, these three observations are independent, with the indicated normal means and variance $\nu>0$. For any Borel set $B\subseteq\mathbb R^2$, conditioning and Tonelli give
$$
\Pr\{Y_i\ge v,(Y_j^1,Y_j^2)\in B\}
=\int_B g(u_1,u_2)\,du_1du_2,
\qquad
g(u_1,u_2)=\mathbb E[p_i(v\mid X)d_j(u_1\mid X)d_j(u_2\mid X)].
$$
The integrand inside the expectation is continuous in $(u_1,u_2)$ and bounded by $(2\pi\nu)^{-1}$, since $0\le p_i\le1$ and each $d_j\le(2\pi\nu)^{-1/2}$. Dominated convergence makes $g$ continuous. Thus $g(w,w)$ is a defined pointwise continuous density, rather than an unspecified almost-everywhere version. The independent residuals supply this smoothing even when the law of $X$ is singular.

### Step 4: transformation, Jacobian and strict correlation

Set $A=(Y_j^1+Y_j^2)/2$ and $D=(Y_j^1-Y_j^2)/2$. Their explicit representations are
$$
A=\theta_j+rX_j+\frac{\sqrt\nu}{2}(\varepsilon^1+\varepsilon^2),\qquad
D=\frac{\sqrt\nu}{2}(\varepsilon^1-\varepsilon^2).
$$
Hence $\mathbb EA=\theta_j$, $\sigma_A^2=\operatorname{Var}(A)=1-\nu/2$, $\mathbb ED=0$, and $\operatorname{Var}(D)=\nu/2$. The displayed representations give $\operatorname{Cov}(D,A)=\nu(1-1)/4=0$ and $\operatorname{Cov}(D,Y_i)=0$, since $\varepsilon^0$ is independent of both other residuals and of $X$. These identities hold for $i=j$ too. Joint Gaussianity implies that $D$ is independent of $(A,Y_i)$.

Write $Z_i=Y_i-\theta_i$, $Z_A=(A-\theta_j)/\sigma_A$, and $b=v-\theta_i\ge U$. Both $Z_i,Z_A$ have mean zero and variance one. Their correlation is
$$
\rho=\frac{r^2\Sigma_{ij}}{\sigma_A}=\frac{(1-\nu)\Sigma_{ij}}{\sigma_A}.
$$
Every two-coordinate principal submatrix of the positive-semidefinite unit-diagonal matrix $\Sigma$ gives $|\Sigma_{ij}|\le1$ (also $\Sigma_{ii}=1$). Moreover,
$$
\sigma_A^2-(1-\nu)^2=\nu(3/2-\nu)>0
$$
for $0<\nu\le1$, so $|\rho|<1$. In particular the conditional law $Z_i\mid Z_A=t$ is the normal law with mean $\rho t$ and positive variance $1-\rho^2$; use this continuous conditional version for every real $t$.

The inverse transformation $(A,D)\mapsto(Y_j^1,Y_j^2)=(A+D,A-D)$ has determinant $-2$. Since $D$ has density $f_D(0)=1/\sqrt{\pi\nu}$, the continuous density of the event measure in Step 3, evaluated at $(w,w)$, is
$$
g(w,w)=\frac12 f_D(0)\frac{\phi(t)}{\sigma_A}
\Pr\{Z_i\ge b\mid Z_A=t\}
=\frac{\phi(t)}{2\sqrt{\pi\nu}\,\sigma_A}
\Pr\{Z_i\ge b\mid Z_A=t\},\qquad t=\frac{w-\theta_j}{\sigma_A}.
$$
Indeed the event density in $(A,D)$ factors as $f_D(D)$ times the event density in $A$ by independence. The transformed formula and $g$ are continuous densities of the same finite measure, so their almost-everywhere equality is equality at every point, including $(w,w)$. This proves the exact identity with its factor $1/2$.

### Step 5: the bivariate scalar estimate

For any standard bivariate normal pair $(Z_i,Z_A)$ with correlation $|\rho|<1$, put $s=\sqrt{1-\rho^2}>0$. Conditioning in the reverse direction, $Z_A\mid Z_i=x$ has density $s^{-1}\phi((t-\rho x)/s)$ at $t$. The joint density can therefore be factored in either order, which gives, at every $t\in\mathbb R$,
$$
\phi(t)\Pr\{Z_i\ge b\mid Z_A=t\}
=\int_b^\infty\phi(x)\frac1s\phi\left(\frac{t-\rho x}{s}\right)\,dx.
$$
If $|\rho|\ge1/2$, then $\rho\ne0$ and substitution $y=(t-\rho x)/s$, with absolute Jacobian $s/|\rho|$, gives
$$
\int_{\mathbb R}\frac1s\phi\left(\frac{t-\rho x}{s}\right)\,dx
=\frac1{|\rho|}.
$$
For $b\ge1$ and $x\ge b$, $\phi(x)\le\phi(b)$. Positivity of the kernel and the preceding identity therefore bound the event density by $\phi(b)/|\rho|\le2\phi(b)$. The absolute Jacobian treats negative correlation as well as positive correlation.

If $|\rho|<1/2$, including $\rho=0$, then $s>\sqrt3/2$. Using the kernel supremum and the upper Mills estimate from Step 2, the same density is bounded by
$$
\frac{S(b)}{s\sqrt{2\pi}}
\le\frac{\phi(b)}{b s\sqrt{2\pi}}
\le\phi(b),
$$
because $b\ge1$ and $s\sqrt{2\pi}>\sqrt{3\pi/2}>1$. Thus in both branches
$$
\phi(t)\Pr\{Z_i\ge b\mid Z_A=t\}\le2\phi(b).
$$

### Step 6: squared-density bound and all model endpoints

Combining the exact identity of Step 4 with Step 5 yields
$$
\mathbb E[p_i(v\mid X)d_j(w\mid X)^2]
\le\frac{\phi(b)}{\sqrt{\pi\nu}\,\sigma_A}
\le\sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}
\le\frac{S(U)(1+U)}{\sqrt\nu}.
$$
Here $\sigma_A^2=1-\nu/2\ge1/2$, and $b=v-\theta_i\ge v\ge U\ge1$ ensures $\phi(b)\le\phi(U)$; the last inequality is Step 2. The argument used no dimension bound, no restriction on $\theta_j$ or any other mean, and no restriction on $w$, since $t$ was arbitrary. It used only joint Gaussianity and $|\Sigma_{ij}|\le1$, so singular original covariance is allowed. The independent residual copies make $i=j$ valid throughout.

At the allowed endpoint $\nu=1$, $r=0$, the three $Y$ variables are independent even if the indices coincide, $\sigma_A^2=1/2$, and $\rho=0$. Directly the left side is $S(b)\phi(w-\theta_j)^2$, which is exactly $g(w,w)$ from Step 4: $\Pr\{Z_i\ge b\mid Z_A=t\}=S(b)$ and $\phi(t)/(2\sqrt\pi\sigma_A)=\phi(w-\theta_j)^2$ for $t=\sqrt2(w-\theta_j)$. Thus the same derived inequality includes $\nu=1$. For arbitrarily small positive $\nu$ all strict-correlation and smoothing arguments remain valid and give the stated $\nu^{-1/2}$ bound; no pointwise assertion at $\nu=0$ was made.

### Step 7: weighted mixed-density bound

Fix any further $k\in[N]$ and deterministic $z\in\mathbb R$. Set
$$
F=\sqrt{p_i(v\mid X)}\,d_j(w\mid X),\qquad
G=\sqrt{p_i(v\mid X)}\,d_k(z\mid X).
$$
These are well defined since $p_i\ge0$, and Step 6, applied separately to $(j,w)$ and $(k,z)$ with the identical weight $p_i(v\mid X)$, makes their second moments finite. Cauchy--Schwarz therefore gives
$$
\mathbb E[p_i(v\mid X)d_j(w\mid X)d_k(z\mid X)]
=\mathbb E[FG]
\le\sqrt{\mathbb E[p_i(v\mid X)d_j(w\mid X)^2]\,
\mathbb E[p_i(v\mid X)d_k(z\mid X)^2]}
\le\sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}.
$$
No independence of $F,G$ is required. Thus every coincidence among $i,j,k$, arbitrary $w,z$, and all the model parameters allowed in Step 6 are included.

### Step 8: exact path integral and uniform endpoint control

For $\eta>0$ and $0\le a\le1$, define
$$
\nu_a=\frac{1-a+\eta^2}{1+\eta^2},\qquad
r_a=\sqrt{\frac{a}{1+\eta^2}}.
$$
Then $\eta^2/(1+\eta^2)\le\nu_a\le1$ and $\nu_a+r_a^2=1$. Take $\varepsilon\sim\mathcal N_N(0,I_N)$ independent of $X$, so its coordinates are independent. The Gaussian vector $T_{a,\eta}=\theta+r_aX+\sqrt{\nu_a}\varepsilon$ has mean $\theta$ and covariance $r_a^2\Sigma+\nu_a I_N$, with unit marginal variances; conditional on $X$, it has the independent residual coordinates and conditional tails and densities of the statement with $\nu=\nu_a$. Thus all the preceding scalar inequalities apply at every $a$.

Substitution $h=1-a+\eta^2$ gives
$$
\begin{aligned}
\int_0^1\nu_a^{-1/2}\,da
&=\sqrt{1+\eta^2}\int_{\eta^2}^{1+\eta^2}h^{-1/2}\,dh\\
&=2\sqrt{1+\eta^2}\bigl(\sqrt{1+\eta^2}-\eta\bigr)\\
&=\frac{2\sqrt{1+\eta^2}}{\sqrt{1+\eta^2}+\eta}\le2.
\end{aligned}
$$
The rationalization uses $(1+\eta^2)-\eta^2=1$. In particular integrating the common scalar upper bound gives at most $2\sqrt{2/\pi}\phi(U)$, or $2S(U)(1+U)$ for its Mills comparison, uniformly for $\eta>0$. This is uniform integrable scalar endpoint control as the residual variance approaches zero, with no pointwise inclusion of $\nu=0$. Every level in this argument is deterministic. No random-level or matrix-aggregation assertion is inferred.
