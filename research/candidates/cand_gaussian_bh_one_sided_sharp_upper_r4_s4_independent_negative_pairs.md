---
type: candidate
title: >-
  Independent replication of negatively correlated Gaussian pairs with composite
  null means
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 4
slot: 4
direction: known_counterexamples
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:36:58.955Z'
extension_version: 0.0.4
---

## Object

For $0<q<e^{-2}$ set
$$
L=\log(1/q),\qquad B=2\left\lceil e^{L^2}\right\rceil,\qquad N=2B.
$$
Let $(X_b,Y_b)$, $1\leq b\leq B$, consist of $2B$ mutually independent standard normal variables. Set
$$
\nu_b=\begin{cases}0,&1\leq b\leq B/2,\\-q,&B/2<b\leq B,\end{cases}
$$
and define
$$
T_{2b-1}=\nu_b+X_b,\qquad T_{2b}=\nu_b-\frac12X_b+\frac{\sqrt3}{2}Y_b.
$$
Thus each pair has correlation $-1/2$, pairs are independent, and every coordinate is a one-sided true null. Apply ordinary BH at level $q$ to $p_i=\overline\Phi(T_i)$ and compute its full-law FDR. This tests whether replication of small negatively dependent Gaussian blocks can accumulate enough inflation when the total covariance rank and dimension grow very rapidly. It is not a fixed-dimension or rank-one family.

## Checks

### H1

The testing level satisfies $0<q<e^{-2}<1/2$ and tends to zero through an entire interval. The candidate is a family on the target's asymptotic range.

### H2

For every fixed $q$, $B$ is an even positive finite integer and $N=2B$ is finite. All means are finite deterministic numbers. The target permits their displayed dependence on $q$.

### H3

The covariance is block diagonal, with $B$ identical blocks
$$
\begin{pmatrix}1&-1/2\\-1/2&1\end{pmatrix}.
$$
Each block has eigenvalues $1/2$ and $3/2$. Hence the covariance is symmetric positive definite, has unit diagonal, and has full rank $N$. No low-covariance-rank obstruction is used.

### H4

The displayed $T$ is a deterministic affine transformation of $2B$ mutually independent standard normal variables. It is therefore exactly jointly Gaussian with the covariance in H3. Independence across pairs holds for the full observations and not merely for their marginals.

### H5

The p-values are exactly the prescribed one-sided Gaussian p-values. Every mean equals either $0$ or $-q$, so
$$
I_0^{(1)}(\theta)=\{1,\ldots,N\}.
$$
In particular all negative-mean coordinates are included as true nulls. For every $t\in[0,1]$, marginal validity gives $\mathbb P(p_i\leq t)\leq t$.

### H6

The tested procedure is ordinary BH on all $N$ original p-values, with the target's largest qualifying rank and non-strict inequalities. The group procedure introduced below is only a comparison used to bound the rejection event; it does not replace the candidate's procedure.

### H7

The FDR is the unconditional expectation $\mathbb E[V/(R\vee1)]$. Since all coordinates are true nulls, $V=R$ and this equals $\mathbb P(R>0)$ exactly.

### NOT

This check fails by a comparison that is uniform in $B$. For each pair define the auxiliary group p-value
$$
W_b=\min\{1,\,2\min(p_{2b-1},p_{2b})\}.
$$
For $0\leq t<1$, the union bound and the actual composite-null marginal validity give
$$
\mathbb P(W_b\leq t)
\leq\mathbb P(p_{2b-1}\leq t/2)+\mathbb P(p_{2b}\leq t/2)
\leq t.
$$
The inequality also holds at $t=1$. The $W_b$ are independent across $b$, although the two original p-values within each pair are dependent.

On an original BH event with $R>0$, let $S$ count pairs containing at least one rejected coordinate. Then $1\leq S\leq B$ and $R\leq2S$. Every such pair satisfies
$$
\min(p_{2b-1},p_{2b})\leq\frac{qR}{2B}\leq\frac{qS}{B},
\qquad W_b\leq\frac{2qS}{B}.
$$
Consequently at least $S$ group p-values satisfy the group BH rank-$S$ inequality at level $\alpha=2q$. Thus
$$
\{R>0\}\subseteq\{\text{BH at level }2q\text{ rejects among }W_1,\ldots,W_B\}.
$$
For completeness the independent superuniform group p-values give rejection probability at most $\alpha$. If $K$ is their BH rejection count and $K_b^0$ is the count after replacing $W_b$ by zero, the ordinary BH leave-one-out identity gives
$$
\mathbb E\left[\frac{\boldsymbol1\{b\text{ is rejected}\}}{K\vee1}\right]
=\mathbb E\left[\frac{\mathbb P(W_b\leq\alpha K_b^0/B\mid K_b^0)}{K_b^0}\right]
\leq\frac\alpha B.
$$
Here $K_b^0\geq1$ depends only on the other group p-values, so independence and superuniformity justify the last inequality. Summing over $b$ proves $\mathbb P(K>0)\leq\alpha$.

Combining this with H7 and the event inclusion yields, for every finite member of the family,
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)\leq2q.
$$
It follows on the target's asymptotic scale that
$$
0\leq\frac{\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)}{q\sqrt{\log(1/q)}}
\leq\frac2{\sqrt{\log(1/q)}}\longrightarrow0.
$$
This exclusion uses independent pairs and the all-null setting. It supplies no reduction of general mixed-null configurations or dependence between blocks.

## Failure

NOT fails: independent group p-values dominate the original all-null rejection event at level $2q$, giving FDR at most $2q$ uniformly in the rapidly growing full covariance rank.
