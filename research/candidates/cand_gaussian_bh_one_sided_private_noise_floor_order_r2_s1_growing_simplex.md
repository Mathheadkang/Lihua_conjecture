---
type: candidate
title: Growing negatively correlated simplex null array with fixed private noise
status: failed
target_asset: gaussian_bh_one_sided_private_noise_floor_order
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  NOT: fail
mode: refute
round: 2
slot: 1
direction: known_counterexamples
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:19:23.549Z'
extension_version: 0.0.4
---

## Object

Fix $s_0=1/2$. For $0<q<1/4$, let $N=\lceil q^{-2}\rceil$, $d=N$, $\theta_i=0$, and, with $e_i$ the standard basis vectors of $\mathbb R^N$ and $\mathbf 1$ its all-ones vector, set
$$
a_i=\frac{\sqrt 3}{2}\sqrt{\frac{N}{N-1}}\left(e_i-\frac1N\mathbf1\right),\qquad s_i=\frac12.
$$
Use independent standard Gaussian vectors $G\in\mathbb R^N$ and $\varepsilon\in\mathbb R^N$, and put $T=AG+D\varepsilon$. The covariance has diagonal one and off-diagonal entries $-3/[4(N-1)]$.

This growing regular-simplex geometry tests the negative-dependence direction familiar from failures of positive-dependence hypotheses for Simes-type assertions. No external sharp counterexample or non-Gaussian dependence construction is asserted. Unlike the previous two-coordinate near-miss, dimension here diverges with $q^{-1}$, so the board's bounded-dimension obstruction does not resolve this family. Unlike the full-private-noise endpoint, every null has genuine common-factor loading.

## Checks

### H1

Pass: $s_0=1/2$ is one fixed number in $(0,1]$, independent of $q$.

### H2

Pass: $N=d=\lceil q^{-2}\rceil$ are finite positive integers for every $q$, with $N\to\infty$ as $q\downarrow0$.

### H3

Pass: $\theta=0\in\mathbb R^N$, $A\in\mathbb R^{N\times N}$ is deterministic, and $D=(1/2)I_N$ is diagonal with nonnegative entries. The original one-sided null labels give $I_0^{(1)}(\theta)=[N]$; there are no alternative coordinates.

### H4

Pass: $\|e_i-N^{-1}\mathbf1\|^2=(N-1)/N$, so $\|a_i\|^2=3/4$ and $\|a_i\|^2+s_i^2=1$ for every coordinate.

### H5

Pass: every coordinate is a true null, and $s_i=s_0=1/2$ for every $i$.

### H6

Pass: $G$ and $\varepsilon$ have exactly the required independent standard Gaussian laws. Thus $T$ is jointly Gaussian with mean zero and covariance $AA^{\mathsf T}+D^2$. This covariance is positive definite since $D^2=I_N/4$, and has unit diagonal by H4.

### H7

Pass: use the original one-sided Gaussian p-values $p_i=\overline\Phi(T_i)$, so each null p-value is uniform on $(0,1)$.

### H8

Pass: for every $q$ in the displayed interval, apply exactly the largest qualifying rank, non-strict ordinary BH rule in the target, retaining all multiplicities. No smaller-rank selection or modified denominator is used.

### NOT

Fail: this family has a dimension-uniform bound of order $q$ and therefore cannot make the target's normalized FDR unbounded.

For completeness, its off-diagonal covariances are nonpositive. For every subset $S$ of $k$ coordinates and every $t$, Gaussian interpolation to independent coordinates gives
$$
\mathbb P(T_i\ge t\text{ for every }i\in S)\le\overline\Phi(t)^k.
$$
Here is a direct justification of this comparison. Interpolate the subset covariance $K$ to $I_k$ as $K(u)=(1-u)K+uI_k$. Every off-diagonal derivative is nonnegative, and diagonal derivatives vanish. For a product $f(x)=\prod_{j=1}^k f_j(x_j)$ of smooth increasing functions taking values in $[0,1]$, the covariance differentiation identity yields
$$
\frac{d}{du}\mathbb E f(X_u)=\sum_{i<j}K'_{ij}(u)\,\mathbb E\!\left[f_i'(X_{u,i})f_j'(X_{u,j})\prod_{\ell\ne i,j}f_\ell(X_{u,\ell})\right]\ge0.
$$
All interpolated matrices are positive definite. Approximate the indicators of $[t,\infty)$ monotonically at their continuity points and use bounded convergence to get the displayed comparison. At $u=1$ the coordinates are independent.

Let $C_k=\sum_i\mathbf1\{p_i\le qk/N\}$. A nonempty ordinary BH rejection set requires $C_k\ge k$ for at least one $k\in[N]$. Union bounds over $k$ and over the subsets of size $k$, followed by the comparison, give
$$
\operatorname{FDR}=\mathbb P(R>0)\le\sum_{k=1}^N\binom Nk\left(\frac{qk}{N}\right)^k\le\sum_{k=1}^N(eq)^k\le\frac{eq}{1-eq}\qquad(eq<1).
$$
In particular, for $q\le1/(2e)$,
$$
\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}\le\frac{2e}{\sqrt{\log(1/q)}}\longrightarrow0.
$$
The comparison also excludes all-zero-mean, all-null Gaussian arrays with nonpositive off-diagonal covariance by the same argument. It makes no assertion about mixed-sign loading geometry or alternative blocks, and proves no general fixed-floor result.

## Failure

NOT is the first failing check: Gaussian upper-orthant comparison and the BH rank union bound give $\operatorname{FDR}\le eq/(1-eq)$ uniformly in this growing simplex family.
