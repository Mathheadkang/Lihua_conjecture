---
type: candidate
title: All-null edge in a dimension growing as the fourth power of the cutoff
status: failed
target_asset: spherical_isotropic_population_bh_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 4
slot: 8
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:27:47.684Z'
extension_version: 0.0.4
---

## Object

Take $u=105$, $q=2Q(105)$, $d=105^4=121550625$, and $W=\delta_0$, so that $\pi_0=1$. Use the product directional population $\delta_0\otimes\sigma_{d-1}$, $Z\sim N(0,I_d)$, and $T_{0,v}=v^\top Z$, with no residual noise. Apply the stated smallest finite admissible cutoff rule. This tests the all-null boundary in a dimension far larger than the cutoff, outside the board's fixed-dimension null-envelope exclusion.

## Checks

### H1

The dimension $d=121550625$ is an integer at least four.

### H2

$W=\delta_0$ is a Borel probability law on $[0,\infty)$ and $W(\{0\})=1$.

### H3

The directional kernel is $\sigma_{d-1}$ at every absolute mean and does not depend on the mean; the population measure is exactly $W\otimes\sigma_{d-1}$.

### H4

The statistic is $T_{0,v}=v^\top Z$ with $Z\sim N(0,I_d)$ and no additional random term, so the residual variance is zero.

### H5

$q=2Q(105)$ lies strictly between zero and one, and $Q^{-1}(q/2)=105\geq104$.

### H6

Here $F_r(x)=2H_r(x)$. At each $r>0$, take $x_r$ to be the smallest $x\geq u$ for which $H_r(x)\geq Q(x)/q$, and assign FDP zero if none exists. This is exactly the prescribed rule. Since every test is null, the FDP is one at a finite contact.

### NOT

The proposed conclusion does not fail. The following argument gives the stronger bound $\operatorname{FDR}_{\mathrm{pop}}\leq q$ and does not require a numerical approximation in this large dimension.

For each $x>u$, the map $r\mapsto H_r(x)$ is continuous and strictly increasing on $r>x$, from zero to $1/2$. Because $0<Q(x)/q<1/2$, there is a unique finite $b(x)>x$ satisfying
$$
H_{b(x)}(x)=Q(x)/q.
$$
Writing the spherical tail as a continuous strictly decreasing function of $x/r$ shows that $b(x)$ is continuous. Also $b(x)\to\infty$ as $x\downarrow u$: otherwise a bounded subsequence would give a finite radius with positive-cutoff cap mass $1/2$. Since $b(x)>x$, it also tends to infinity as $x\to\infty$. Thus it attains a finite minimum $b_*=b(x_*)$ at some $x_*>u$.

For $x=u$, $H_r(u)<1/2=Q(u)/q$ for every finite $r$. For $x>u$, admissibility is equivalent to $r\geq b(x)$. Therefore a finite contact exists exactly when $r\geq b_*$, and
$$
\operatorname{FDR}_{\mathrm{pop}}=\mathbb P(R\geq b_*).
$$
The Gaussian marginal identity $\mathbb E H_R(x_*)=Q(x_*)$ and radial monotonicity give
$$
Q(x_*)\geq \mathbb P(R\geq b_*)H_{b_*}(x_*)
=\mathbb P(R\geq b_*)\frac{Q(x_*)}{q}.
$$
Consequently $\operatorname{FDR}_{\mathrm{pop}}\leq q$. Since $\pi_0=1$ and $M_d>0$, the proposed right side is strictly greater than $2q$, so NOT fails.

## Failure

NOT is the first failed check: the all-null edge has one monotone radial onset of contact and FDR at most $q$, strictly below the proposed bound.
