---
type: candidate
title: Independent tensorization of antipodal null pairs has exact baseline FDR
status: failed
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
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
slot: 2
direction: small_cases
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T22:10:51.594Z'
extension_version: 0.0.4
---

## Object

For every integer $m\geq1$ and every $0<q\leq S(1)$, take $N=2m$, $d=m$, all means zero, and independent standard normal coordinates $G_1,\ldots,G_m$. Set
$$
T_{2\ell-1}=G_\ell,\qquad T_{2\ell}=-G_\ell,\qquad 1\leq\ell\leq m.
$$
The covariance is a block diagonal matrix with $m$ blocks $\left(\begin{smallmatrix}1&-1\\-1&1\end{smallmatrix}\right)$. All hypotheses are true nulls. This attempts a new mechanism beyond a single antipodal pair: independent blocks grow the actual score rank to $m$ and might produce noise sensitivity of the global BH rejection event. These are independent latent coordinates, rather than clones or unused extra coordinates.

## Checks

### H1

$N=2m$ is a finite positive integer for each member of the family.

### H2

$\theta=0\in\mathbb R^{2m}$; the prescribed null set is the entire index set and $\pi_0=1$.

### H3

Each covariance block is positive semidefinite with eigenvalues $0,2$ and unit diagonal. Their direct sum is therefore a legal singular Gaussian covariance.

### H4

The chosen range $0<q\leq S(1)$ is exactly the target's range and in particular is below $1/2$.

### H5

The vectors $v_{2\ell-1}=e_\ell$, $v_{2\ell}=-e_\ell$ are unit vectors with this Gram matrix. Their span has dimension $m$, so increasing $m$ increases effective rank.

### H6

Use ordinary BH on all $2m$ original p-values. Since all labels are null, its full actual FDP is $f=\mathbf1\{R_q>0\}$; no rank cutoff or partial FDP is substituted. The OU operator acts on this indicator in $\mathbb R^m$.

For completeness, the full budget is finite without using a positive-jump surrogate. Direct differentiation of the Mehler Gaussian convolution gives, with $\rho=e^{-t}$ and $s=\sqrt{1-\rho^2}$,
$$
\nabla T_t f(x)=\frac{\rho}{s}\mathbb E[G'f(\rho x+sG')].
$$
Boundedness of $f$ and integrability of the differentiated Gaussian kernel justify differentiation for every $t>0$. Hence $\|\nabla T_t f(x)\|\leq(\rho/s)\sqrt m$ and integration of this nonnegative bound gives $J(f)\leq(\pi/2)\sqrt m<\infty$. The original signed spatial gradient is retained throughout.

### H7

In pair $\ell$, the smaller p-value is $W_\ell=S(|G_\ell|)<1/2$ almost surely and the larger is $1-W_\ell>1/2$. Since all BH thresholds are at most $q<1/2$, no rank greater than $m$ can qualify. Define
$$
U_\ell=2W_\ell=2S(|G_\ell|).
$$
The $U_\ell$ are independent uniform random variables on $(0,1)$: for $0<u<1$, $\mathbb P(U_\ell\leq u)=\mathbb P(|G_\ell|\geq S^{-1}(u/2))=u$. For every $1\leq k\leq m$,
$$
W_{(k)}\leq\frac{qk}{2m}
\quad\Longleftrightarrow\quad
U_{(k)}\leq\frac{qk}{m}.
$$
Thus the original BH count is exactly the BH count for the $m$ independent $U_\ell$ at level $q$, sample by sample.

Here is the exact FDR calculation for the reduced model. Let $R^{(\ell,0)}$ be its BH count after replacing $U_\ell$ by zero. Conditional on all other uniforms, $R^{(\ell,0)}\geq1$ is fixed. The deterministic BH identities are
$$
\{\ell\text{ rejected}\}=\{U_\ell\leq qR^{(\ell,0)}/m\},
\qquad R=R^{(\ell,0)}\text{ on this event}.
$$
For the converse identity, decreasing an already rejected coordinate to zero does not change whether any rank above the original count qualifies; all its larger rank thresholds already contained that coordinate. Independence and uniformity now give
$$
\mathbb E\frac{\mathbf1\{\ell\text{ rejected}\}}{R\vee1}=\frac qm,
\qquad F=\mathbb P(R>0)=q>0.
$$

The exact conditional-p-path charges also cancel at the original-coordinate level without replacing them by a positive part. Fix original coordinate $i$. On $0<t<q$, its antipodal partner has score $-u(t)<0$ and can never be rejected, and all remaining pairs have fixed residual scores. The path therefore inserts the single varying p-value $t$ into fixed p-values. Its rejection count is nonincreasing in $t$. At any count drop from a largest qualifying rank $k$, the crossing is at $t=qk/N$; the left limit of $A_i$ is one and the clipped right limit is also one. Thus $A_i$ has no net jumps: $J_i=\varnothing$. Its exact signed charge and its positive charge $B_i$ are separately zero. The approved finite identity therefore yields $F_i=q/N$ for every original coordinate, consistent with $F=q$ above.

### NOT

The numerator is exactly
$$
F(F-q\pi_0)_+=q(q-q)_+=0.
$$
Consequently the tested bridge ratio is zero for every $m$ and every legal $q$, including under its stated zero-budget convention. Independent antipodal tensorization cannot produce an unbounded ratio, regardless of how small its full OU budget becomes.

A short standard-library diagnostic checked the exact rejection-count reduction on 15,000 sample/level combinations with $m\in\{1,2,3,4,6\}$ and $q\in\{0.01,0.1,S(1)\}$. This is only a consistency check; the all-$m$ obstruction is the exact calculation above. It does not cover non-antipodal blocks, mixed labels, or growing correlated interactions between blocks.

## Failure

NOT is the first failing check: independent antipodal blocks reduce exactly to iid-uniform BH, so the full FDR equals its baseline and the bridge ratio vanishes uniformly even as effective rank grows.
