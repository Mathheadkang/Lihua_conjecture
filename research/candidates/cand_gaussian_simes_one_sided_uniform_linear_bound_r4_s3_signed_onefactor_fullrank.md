---
type: candidate
title: Signed one-factor Gaussians with growing full rank
status: failed
target_asset: gaussian_simes_one_sided_uniform_linear_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 4
slot: 3
direction: drop_hypothesis
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:29:07.926Z'
extension_version: 0.0.4
---

## Object

For each integer $m\ge2$, let $N=2m$, $q_m=e^{-m}$, and let
$Z_0,Z_1,\ldots,Z_{2m}$ be independent standard normals. Put
$a_i=i/(i+1)$ and $s_i=1$ for $i\le m$, $s_i=-1$ otherwise. Define
$$
T_i=s_i a_i Z_0+\sqrt{1-a_i^2}\,Z_i,\qquad
p_i=\overline\Phi(T_i).
$$
This tests mixed-sign correlations with increasing dimension and loadings
approaching the singular boundary. Unlike the signed rank-one family on the
board, every coordinate has an independent residual: its covariance is full
rank and there are $2m$ distinct random p-value formulas. The board's exact
two-tail calculation and fixed-formula union bound therefore do not apply.

## Checks

### H1

Pass: $N=2m$ is a positive integer and tends to infinity.

### H2

Pass: writing $b_i=s_i a_i$, the covariance is
$$
\Sigma=bb^{\mathsf T}+\operatorname{diag}(1-a_i^2).
$$
Its diagonal equals one. For every nonzero $x$,
$$
x^{\mathsf T}\Sigma x=(b^{\mathsf T}x)^2+
\sum_i(1-a_i^2)x_i^2>0.
$$
Thus $\Sigma\in\mathcal C_N$, with rank $N$. Correlations within each sign
class are positive, and correlations between the classes are negative.

### H3

Pass: $T$ is an explicit linear image of an independent standard Gaussian
vector, with mean zero and covariance $\Sigma$.

### H4

Pass: use exactly $p_i=\overline\Phi(T_i)$ and the non-strict event
$$
E_q=\{\exists k\in[N]:p_{(k)}\le qk/N\}.
$$
Each marginal p-value is uniform on $(0,1)$.

### H5

Pass: $0<q_m<1/2$ and $q_m\downarrow0$, so this sequence eventually lies
below any proposed $q_0>0$.

### NOT

Fail: this whole family satisfies $\mathbb P(E_q)\le2q$ for every $0<q<1$.
Here is a derivation that does not assume a Simes comparison theorem.

First consider any centered Gaussian subvector $X_1,\ldots,X_n$ with unit
variances and nonnegative pairwise correlations. Write
$U_i=\overline\Phi(X_i)$, and let $R$ be its ordinary BH rejection count at
level $q$. Let $R_i^0$ be the BH count after replacing $U_i$ by zero. For
$r=1,\ldots,n$, the deterministic BH leave-zero identity is
$$
\{U_i\le qr/n,\ R=r\}=
\{U_i\le qr/n,\ R_i^0=r\}.
$$
Indeed, when coordinate $i$ is already rejected, decreasing it to zero
changes no order statistic beyond the rejection rank; conversely,
restoring a value at most $qr/n$ preserves the rank-$r$ crossing and cannot
create a larger crossing. Consequently, since every null is true,
$$
\mathbb P(R>0)=\frac qn\sum_{i=1}^n\sum_{r=1}^n
\mathbb P(R_i^0=r\mid U_i\le qr/n).
$$
For $t>0$ set
$$
f_{i,r}(t)=\mathbb P(R_i^0\ge r\mid U_i\le t),
\qquad f_{i,n+1}(t)=0.
$$
Each $f_{i,r}$ is nonincreasing in $t$. To check this, conditional on
$X_i=x$ the other coordinates have the representation
$$
X_{-i}=\Sigma_{-i,i}x+W,
$$
where the distribution of the centered Gaussian vector $W$ is independent
of $x$. All entries of $\Sigma_{-i,i}$ are nonnegative, and
$\{R_i^0\ge r\}$ is increasing in $X_{-i}$. Its conditional probability
is therefore nondecreasing in $x$, hence nonincreasing in
$U_i=\overline\Phi(x)$. Averaging this last nonincreasing function over
the uniform interval $(0,t)$ preserves that monotonicity.

With $t_r=qr/n$, it follows that
$$
\begin{aligned}
\sum_{r=1}^n\mathbb P(R_i^0=r\mid U_i\le t_r)
&=\sum_{r=1}^n\{f_{i,r}(t_r)-f_{i,r+1}(t_r)\}\\
&\le\sum_{r=1}^n\{f_{i,r}(t_r)-f_{i,r+1}(t_{r+1})\}\\
&=f_{i,1}(t_1)\le1.
\end{aligned}
$$
The terminal term is zero; one may set $t_{n+1}=q(n+1)/n$ there without
interpreting a conditioning event. This proves
$\mathbb P(R>0)\le q$ for the subvector.

Now partition the candidate coordinates into $G_+=\{1,\ldots,m\}$ and
$G_-=\{m+1,\ldots,2m\}$. Both subvectors have nonnegative correlations,
so their separate Simes events $E_q^+$ and $E_q^-$ each have probability
at most $q$. If the full vector crosses at rank $k$, set $t=qk/(2m)$ and
let $k_+,k_-$ count p-values at most $t$ in each group. Since
$k_++k_-\ge k$, at least one group has
$k_s/m\ge k/(2m)$ and $k_s\ge1$. Its rank $k_s$ satisfies
$p_{(k_s)}^s\le t\le qk_s/m$. Hence
$$
E_q\subseteq E_q^+\cup E_q^-,\qquad
\mathbb P(E_q)\le2q.
$$
The ratio is bounded uniformly even as the rank, dimension, and number of
distinct p-value formulas diverge. Thus this family does not violate the
existence of an unspecified finite universal linear constant.

## Failure

NOT fails: splitting the signed one-factor family by loading sign gives two nonnegatively correlated Gaussian subvectors and a uniform bound $\mathbb P(E_q)\le2q$.
