---
type: candidate
title: >-
  Two- and three-factor arrays with independent null residuals and three signal
  types
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 1
direction: idea_28ab51ce8127
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T08:53:53.945Z'
extension_version: 0.0.4
---

## Object

This candidate checks both exactly specified residual-array variants from the assigned test case. The estimate below is uniform over the choice of two or three factors, which may itself depend deterministically on $q$.

For $q<e^{-10}$ set $L=\log(1/q)$, $r=1/L$, $s=\sqrt{1-r^2}$, $u=\overline\Phi^{-1}(q/2)$, $\rho=1/\sqrt2$, $a_1=u/3$, $a_2=2u/3$, and $p(c)=2\overline\Phi(c)$. Set
$$
N=\lceil e^{L^4}\rceil,\quad
w_0=r,\quad w_j=\frac{p(a_j/r)}{4q}\ (j=1,2),\quad
n_j=\lfloor Nw_j\rfloor,\quad m=N-n_0-n_1-n_2,
$$
and set the three nonzero means to
$$
\mu_0=p^{-1}(qr)+1,\qquad \mu_j=a_j/r+a_j\quad(j=1,2).
$$
The $m$ null coordinates have independent standard normal residuals, independent of all factors. With two independent standard normal factors $Z=(Z_1,Z_2)$ their values are $rZ_1+s\varepsilon_i$, and the $n_j$ alternative coordinates of type $j$ are identical copies of $\mu_j+v_j^{\mathsf T}Z$, where
$$
v_0=(-\rho,\rho),\qquad v_1=(\rho,\rho),\qquad v_2=(-\rho,-\rho).
$$
In the three-factor variant split the $m$ nulls into counts $\lfloor m/2\rfloor$ and $\lceil m/2\rceil$, with values $rZ_1+s\varepsilon_i$ and $rZ_2+s\varepsilon_i$. The alternative loadings are instead
$$
v_0=(-\rho,0,\rho),\qquad v_1=(\rho,0,\rho),\qquad v_2=(0,-\rho,-\rho),
$$
with $Z\sim\mathcal N_3(0,I_3)$. Apply the specified two-sided p-values and ordinary global BH rule at level $q$.

## Checks

### H1

Pass: $N$ is finite and positive at each $q$. Since $L>10$, $a_1/r=Lu/3>u$ and $a_2/r>u$, so $w_1,w_2<1/4$ and $w_0<1/10$. Thus $m>0$. All three alternative counts are positive for sufficiently small $q$: $\log N=L^4+o(1)$ while $\log(1/w_j)=O(L^3)$. These deterministic, arbitrarily large dimensions and counts are admissible.

### H2

Pass: the $m$ null means are zero and each $\mu_j$ is positive and finite. Every parameter is deterministic and may depend on $q$.

### H3

Pass: each variant is an exact linear transformation of independent standard normal variables plus its mean vector. Writing $A$ for the matrix of factor loadings and $D$ for the diagonal matrix with entries $s^2$ on null coordinates and zero on alternatives, its covariance is $AA^{\mathsf T}+D$. This is symmetric positive semidefinite with diagonal one. The null residuals are retained with variance $s^2>0$; there are $m$ genuinely distinct random null p-values.

### H4

Pass: the global finite-$N$ BH cutoff, including all null residuals and all alternative ties, admits the following bound without replacing its empirical distribution by a population crossing:
$$
\operatorname{FDR}_{\rm BH}^{(2)}(q)\leq16q\frac mN.
$$
Here is a proof.

First, the null-only p-value vector satisfies the Simes bound at every level $\alpha\in(0,1)$:
$$
\mathbb P\left\{\exists k\leq m:\ p^{\rm null}_{(k)}\leq\alpha k/m\right\}\leq\alpha.
$$
To see the required positive regression property directly, consider one null block $Y_i=rZ+s\varepsilon_i$. Conditional on $|Z|=v$, the variables $|Y_i|$ are independent and each is stochastically increasing in $v\geq0$, since
$$
\frac{\partial}{\partial v}\mathbb P\{|r v+s\varepsilon|\geq c\}
=\frac r s\left[\phi\left(\frac{c-rv}s\right)-\phi\left(\frac{c+rv}s\right)\right]\geq0
\quad(c,v\geq0).
$$
The conditional density of $|Z|=v$ given $|Y_i|=x$ is proportional, on $v\geq0$, to
$$
\exp\left(-\frac{v^2}{2s^2}\right)\cosh\left(\frac{r x v}{s^2}\right).
$$
For $x_2\geq x_1\geq0$, the ratio of these densities is increasing in $v$: the derivative of its log, apart from a constant, is
$$
\frac r{s^2}\left[x_2\tanh\left(\frac{r x_2v}{s^2}\right)-x_1\tanh\left(\frac{r x_1v}{s^2}\right)\right]\geq0.
$$
Consequently the remaining absolute null coordinates are stochastically increasing in $|Y_i|$. The remaining p-values are stochastically increasing in $p_i$. The same conclusion holds for the two independent null blocks in the three-factor version, since the other block is independent of $p_i$.

For completeness this regression property implies the displayed Simes bound as follows. Let $K$ be the null-only BH count at level $\alpha$, and $K_i^0$ the same count after replacing $p_i$ by zero. Both depend only on the null p-values. The exact BH replacement identity and marginal uniformity give
$$
\mathbb E\frac{\mathbf1\{i\text{ rejected}\}}{K\vee1}
=\frac\alpha m\sum_{k=1}^m
\mathbb P\{K_i^0=k\mid p_i\leq\alpha k/m\}.
$$
Write $h_k(t)=\mathbb P\{K_i^0\geq k\mid p_i\leq t\}$. The event in this definition is coordinatewise decreasing in the remaining p-values. By the proved regression property $h_k(t)$ is nonincreasing in $t$. Therefore, with $t_k=\alpha k/m$,
$$
\sum_{k=1}^m\mathbb P\{K_i^0=k\mid p_i\leq t_k\}
=\sum_{k=1}^m[h_k(t_k)-h_{k+1}(t_k)]
\leq\sum_{k=1}^m[h_k(t_k)-h_{k+1}(t_{k+1})]=1,
$$
where $h_1=1$ and $h_{m+1}=0$. Summing over $i$ proves the all-null Simes bound because its FDR is $\mathbb P(K>0)$.

Now return to global BH and write $R=V+A$, where $A$ counts rejected alternative hypotheses. Each alternative type is rejected in its entirety or not at all, so the positive values of $A$ belong to a deterministic set $\mathcal S$ of at most $2^3-1=7$ subset-sums of $n_0,n_1,n_2$. On $\{A=a,V\leq A\}$, $a>0$, the global cutoff obeys
$$
qR/N\leq2qa/N,
$$
and its FDP is bounded by $V(2qa/N)/a$, where $V(t)=\sum_{i\in I_0}\mathbf1\{p_i\leq t\}$. Uniform null marginals therefore give
$$
\mathbb E\left[\frac V{R\vee1}\mathbf1\{A=a,V\leq A\}\right]
\leq\frac{\mathbb EV(2qa/N)}a=2q\frac mN.
$$
On $\{V>A\}$, $V\geq1$ and $R<2V$, so some null order statistic satisfies
$$
p^{\rm null}_{(V)}\leq qR/N<2qV/N.
$$
The null-only Simes bound at $\alpha=2qm/N<1$ implies $\mathbb P(V>A)\leq2qm/N$. Bounding FDP by one on this event and summing the at most seven previous contributions proves $\operatorname{FDR}\leq16qm/N$. The argument includes the case $R=0$, all ties, arbitrary dependence between alternatives and nulls, and the largest-rank BH rule.

### NOT

Fail: for each of the two- and three-factor variants,
$$
0\leq\frac{\operatorname{FDR}_{\rm BH}^{(2)}(q)}{q\sqrt{\log(1/q)}}
\leq\frac{16}{\sqrt{\log(1/q)}}\longrightarrow0.
$$
This is a finite-$N$ global-cutoff obstruction for the exact residual models, not an argument at $r=0$ and not a separate sum of local population crossings. More generally the same proof gives $2^{K+1}q\,m/N$ when the alternatives have $K$ deterministic groups of identical p-values and the null-only vector has the Simes property. Thus every fixed number of these signal types is insufficient; growing or residual-noise signal types require a separate analysis.

## Failure

NOT fails: both prescribed residual families have global FDR at most $16q$, uniformly in their diverging dimension, means, and vanishing tail masses.
