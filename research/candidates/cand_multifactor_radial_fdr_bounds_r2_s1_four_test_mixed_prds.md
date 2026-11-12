---
type: candidate
title: Four two-sided tests with one shifted factor test
status: failed
target_asset: multifactor_radial_fdr_bounds
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 1
direction: idea_bf23916c98ed
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:46:27.817Z'
extension_version: 0.0.4
---

## Object

Take any level $0<q\leq2\overline\Phi(1)$, any $\mu>0$, and any
$0<r_1<r_2<r_3<1$. Put $m=4$, $d=1$,
$\theta=(0,0,0,\mu)$, and $a=(r_1,r_2,r_3,1)^{\mathsf T}$.
For independent standard normals $Z,\varepsilon_1,\varepsilon_2,\varepsilon_3$,
set
$$
T_i=r_iZ+\sqrt{1-r_i^2}\,\varepsilon_i\quad(1\leq i\leq3),
\qquad T_4=\mu+Z.
$$
Use two-sided p-values and ordinary BH at level $q$.
This is the complete test family named in the supplied context, not a
numerically selected survivor. The calculation below excludes every member.

## Checks

### H1

The positive integers are $m=4$ and $d=1$. Every loading norm is at most one,
and the independent residual construction has unit marginal variances.
Thus this is an admissible Gaussian multifactor representation, including
the conditionally deterministic fourth coordinate.

### H2

Use track $s=2$ with $P_i=2\overline\Phi(|T_i|)$ and ordinary BH.
Since $\mu>0$, the exact true-null set is $I_0=\{1,2,3\}$ and $\pi_0=3/4$.
No hypothesis is imposed on the sign of the observed alternative statistic.

### H3

The stipulated level is in the target's two-sided range. In particular
$q<1/2$, so all four Simes thresholds used below are strictly below one.

### H4

For a one-dimensional standard normal factor,
$\mathbb P(|Z|>b)=2\overline\Phi(b)=q$. Hence $b=u_2(q)$ and
$\Delta_2(1,q)=0$; the target's quantile side claims hold exactly.

### H5

The prescribed coefficients are
$\gamma_i=\sqrt{(1-r_i)/(1+r_i)}$ for the three true nulls.
The target's right side is
$$
B=\min\left\{1,\ q\left[\frac{11}{8}
+\frac{u_2(q)}{4\sqrt{2\pi}}\sum_{i=1}^3\gamma_i\right]\right\}.
$$
Since $q<1/2$ and the gamma term is nonnegative, $B\geq11q/8$.

### NOT

**Fail.** In fact the entire family satisfies
$$
\operatorname{FDR}\leq\frac{29}{24}q<\frac{11}{8}q\leq B.
$$
Here is a self-contained derivation, independent of the target's proof.

**Monotone regression for the three null p-values.** Write $W=|Z|$ and
$X_i=|T_i|$. The variables $X_1,X_2,X_3$ are independent given $W=w$:
conditioning on either sign of $Z$ gives the same product distribution of
the absolute values. For $s_i=\sqrt{1-r_i^2}$ their conditional densities are
$$
f_i(x\mid w)=\frac{2}{s_i\sqrt{2\pi}}
\exp\left(-\frac{x^2+r_i^2w^2}{2s_i^2}\right)
\cosh\left(\frac{r_ixw}{s_i^2}\right),\qquad x,w\geq0.
$$
They are stochastically increasing in $w$, since the derivative with respect
to $w$ of $\mathbb P(X_i\geq x\mid W=w)$ is
$$
\frac{r_i}{s_i}\left[
\phi\left(\frac{x-r_iw}{s_i}\right)
-\phi\left(\frac{x+r_iw}{s_i}\right)\right]\geq0.
$$
For $x'>x\geq0$, the posterior density ratio of $W$ given $X_i=x'$ to that
given $X_i=x$ is, up to a positive constant,
$$
\frac{\cosh(c_ix'w)}{\cosh(c_ixw)},\qquad c_i=\frac{r_i}{s_i^2}.
$$
It is increasing in $w$, because its log derivative is
$c_i[x'\tanh(c_ix'w)-x\tanh(c_ixw)]\geq0$.
Reweighting a distribution by a positive increasing function increases the
expectation of every increasing function: this follows directly from
$\operatorname{Cov}(f(W),g(W))\geq0$ for increasing $f,g$.
The posterior $W\mid X_i=x$ is therefore stochastically increasing in $x$.
Combining this with conditional independence and the preceding stochastic
monotonicity shows that $(X_j)_{j\ne i}$ is stochastically increasing in
$X_i=x$, for the coordinatewise order. Since $P_i=2\overline\Phi(X_i)$ is
decreasing in $X_i$, $(P_j)_{j\ne i}$ is stochastically increasing in
$P_i=t$. Each $P_i$ is marginally uniform. Consequently, for any decreasing
event in the other two null p-values, its conditional probability given
$P_i\leq t$ is nonincreasing in $t$.

**Superuniform null Simes statistic.** Let
$$
S=\min_{1\leq j\leq3}\frac{3P_{(j),0}}{j},
$$
where $P_{(j),0}$ orders just the three null p-values. We prove
$\mathbb P(S\leq\alpha)\leq\alpha$ for $0<\alpha<1$.
Apply BH at level $\alpha$ to those three p-values alone, and let $R_i$ be
its rejection count when $P_i$ is replaced by zero. Write
$t_k=\alpha k/3$ and
$G_k(t)=\mathbb P(R_i\geq k\mid P_i\leq t)$.
The preceding monotone regression implies that each $G_k$ is nonincreasing
in $t$: $\{R_i\geq k\}$ is decreasing in the other null p-values.
The pointwise BH leave-one-out identity and uniformity of $P_i$ give
$$
\mathbb E\frac{\mathbf1\{i\text{ rejected}\}}{R\vee1}
=\frac{\alpha}{3}\sum_{k=1}^3
\bigl[G_k(t_k)-G_{k+1}(t_k)\bigr]\leq\frac{\alpha}{3}.
$$
Indeed, for $k=1,2$, replace $G_{k+1}(t_k)$ by the smaller
$G_{k+1}(t_{k+1})$; the resulting sum telescopes to $G_1(t_1)=1$,
with $G_4=0$. Summing over the three nulls proves the assertion, because
all discoveries in this three-test procedure are false and any rejection
occurs exactly when $S\leq\alpha$.

**A pointwise four-test FDP envelope.** Let $V$ be the number of rejected
nulls in the original four-test procedure, and let $A$ indicate rejection
of the fourth test. If $A=0$ and $V>0$, then
$P_{(V),0}\leq qV/4$, so $S\leq3q/4$ and FDP is one.
If $A=1$ and $V=v\in\{1,2,3\}$, then
$P_{(v),0}\leq q(v+1)/4$, so
$S\leq3q(v+1)/(4v)$ and FDP is $v/(v+1)$.
All these cases are bounded by the single decreasing step function
$$
\operatorname{FDP}\leq
\frac14\mathbf1\{S\leq3q/4\}
+\frac1{12}\mathbf1\{S\leq q\}
+\frac16\mathbf1\{S\leq9q/8\}
+\frac12\mathbf1\{S\leq3q/2\}.
$$
This argument places no restriction on how the fourth p-value depends on
the null p-values. Taking expectations and using the superuniformity just
proved yields
$$
\operatorname{FDR}\leq q\left(
\frac3{16}+\frac1{12}+\frac3{16}+\frac34\right)
=\frac{29}{24}q.
$$
Thus NOT fails uniformly over $q,\mu,r_1,r_2,r_3$ in this object's domain.
No numerical quadrature or simulation is used. This excludes the specified
family only; it is not a proof of the target for general multifactor models.

## Failure

NOT fails: positive regression among the three null p-values gives the
uniform bound $29q/24$, below the target's lower bound $11q/8$ for this family.
