---
type: candidate
title: Arbitrarily unbalanced orthogonal unit-loading blocks
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
slot: 2
direction: extremal
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:46:27.817Z'
extension_version: 0.0.4
---

## Object

Fix $q=1/20$, use the two-sided track, and set $d=2$. For any integer $n\geq2$, put $m=n+1$, all means equal to zero, and
$$
a_i=e_1\quad(1\leq i\leq n),\qquad a_{n+1}=e_2.
$$
Thus $T_1=\cdots=T_n=Z_1$ and $T_{n+1}=Z_2$, where $Z_1,Z_2$ are independent standard normal variables. The concrete choice $n=10^6$ is one finite object. The same calculation covers the extreme sequence $n\to\infty$: one block occupies a proportion tending to one, the orthogonal singleton a proportion tending to zero, and every null loading remains exactly norm one.

## Checks

### H1

The number of tests $m=n+1$ and factor dimension $d=2$ are positive integers for each finite $n$.

### H2

The displayed loadings have norm one and the model is the required Gaussian multifactor representation with zero idiosyncratic coefficients. Independent auxiliary standard normal variables $\varepsilon_i$ may be supplied; their coefficients vanish. The covariance has one all-ones $n$ by $n$ block and one independent unit diagonal entry, so is positive semidefinite with unit diagonal. No non-Gaussian randomization or data-dependent loading is used.

### H3

The selected track is $s=2$ and $q=1/20$ lies in $0<q\leq2\overline\Phi(1)$. Every mean is zero, so every test is a true null.

### H4

Here $\pi_0=1$, every $r_i=1$, every $\gamma_i=0$, and $m^{-1}\sum_{i\in I_0}\gamma_i=0$. The ordinary BH procedure is applied to
$$
p_1=\cdots=p_n=U_1,\qquad p_{n+1}=U_2,
$$
where $U_1=2\overline\Phi(|Z_1|)$ and $U_2=2\overline\Phi(|Z_2|)$ are independent uniform random variables.

### H5

For $d=2$, $\mathbb P(\|Z\|>b)=\exp(-b^2/2)$, so the required quantile is
$$
b=\sqrt{2\log(20)}.
$$
Since $\|Z\|\geq |Z_1|$, its upper-$q$ quantile is at least $u_2(q)$. Consequently $2\overline\Phi(b)\leq q$ and $\Delta_2(2,q)\geq0$. Thus the preliminary quantile and nonnegativity conclusions hold for this object.

### NOT

Put $\alpha=n/(n+1)$ and $\beta=1/(n+1)$. The event of at least one BH rejection is exactly
$$
\{U_1\leq\alpha q\}\ \cup\ \{U_2\leq\beta q\}\ \cup\ \{U_1\leq q,\ U_2\leq q\}.
$$
Indeed, if the large block is the smaller p-value, its largest block rank is $n$; if the singleton is the smaller p-value, its first rank is one; and the only remaining largest block endpoint is rank $m$. Intermediate ranks cannot qualify without the endpoint of the same tied block qualifying.

The probability of the first two events' union is
$$
\alpha q+\beta q-\alpha\beta q^2=q-\alpha\beta q^2.
$$
The additional part of the third event is the rectangle
$$
\{\alpha q<U_1\leq q,\quad \beta q<U_2\leq q\},
$$
whose probability is $\beta q\cdot\alpha q=\alpha\beta q^2$. Hence the probability of any rejection, and therefore the all-null FDR, is exactly $q$ for every $n$.

The asserted radial bound for this object is
$$
\min\{1,\ q(3/2+\Delta_2(2,q))\}.
$$
Both entries of this minimum are strictly larger than $q$, because $q<1$ and $\Delta_2(2,q)\geq0$. The required violation therefore fails. Arbitrarily many tests, an arbitrarily unbalanced block, norm-one loadings, and two orthogonal factor directions do not inflate the FDR in this family.

## Failure

NOT fails: the exact FDR is $q$, strictly below the finite-level radial bound for every finite member of the sequence.
