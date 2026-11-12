---
type: candidate
title: Circular null directions and regular polygon approximations
status: failed
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 3
slot: 2
direction: idea_bef048aab3dc
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:50:40.547Z'
extension_version: 0.0.4
---

## Object

Take q=1/4, sigma=1/2, tau=sqrt(3)/2 and H=R². Let pi be the law of (0,v(t),1), with t uniform on [0,2pi) and v(t)=(cos(t),sin(t)). Let pi_n give mass 1/n to (0,v(2pi j/n),1), j=0,...,n-1. Use X(v)=G dot v, where G is standard bivariate Gaussian, and an independent standard Gaussian Z. Put R=||G|| and b=sigma Z. All parameters are true nulls.

This is the direction-valued test case idea_bef048aab3dc, rather than a perturbation of a continuum of means.

## Checks

### H1

The fixed testing level q=1/4 belongs to (0,1/2).

### H2

The fixed common loading sigma=1/2 belongs to (0,1), with tau=sqrt(1-sigma²).

### H3

The real Hilbert space R² is nonzero and separable; every v(t) has norm one.

### H4

All laws are deterministic Borel probability laws on the specified closed tagged space: theta=0, ell=1 satisfies its null constraint. Their first absolute mean moments vanish. Their finite approximations already have canonical null labels.

### H5

X(v)=G dot v is the stipulated finite series representative. Its covariance is v dot w, and Z is independent. The score tau G dot v + sigma Z is jointly Gaussian over every finite parameter family and has marginal variance tau²+sigma²=1.

### H6

Couple each circular direction to its nearest regular polygon vertex. Their angular distance is at most pi/n and their Euclidean distance is no greater. Means and labels agree, so W1(pi_n,pi)<=pi/n tends to zero.

### NOT

Fails. All four conclusion clauses hold on this object and its specified approximation; the following checks include the actual largest ranks, rather than only nonempty rejection.

**1. Well-definedness and actual largest crossings.** For R>0 put A=tau R and

$$
g_R(r)=S^{-1}(qr)-A\cos(\pi r),\qquad 0<r\le1.
$$

Define h(u)=1 for u<=-1, h(u)=acos(u)/pi for -1<u<1, and h(u)=0 for u>=1. Circular projection gives exactly

$$
H_\pi(r)=V_\pi(r)=h\!\left(\frac{S^{-1}(qr)-b}{A}\right),
\qquad H_\pi(r)\ge r\ \Longleftrightarrow\ b\ge g_R(r).
$$

In particular the actual rank is

$$
\rho_\pi=\max\bigl(\{0\}\cup\{r\in(0,1]:g_R(r)\le b\}\bigr).
$$

Indeed, g_R is continuous and tends to infinity at zero. Every nonempty sublevel set is therefore compact in (0,1], and its maximum is attained. For a positive rank below one, continuity of H shows H(rho)=rho: strict inequality would persist immediately to its right. At rank one, H(1)>=1 implies H(1)=1. The endpoint occurs exactly when b>=S^{-1}(q)+A. If R=0, the score is constant, the rank is one when S(b)<=q and zero otherwise, again with equality H(rho)=rho at a positive rank.

For any a>0, the event rho>=a is exactly

$$
\left\{\min_{a\le r\le1}g_R(r)\le b\right\}.
$$

The minimum is continuous in R, since |g_R(r)-g_{R'}(r)|<=tau|R-R'| uniformly. This proves rank measurability; the explicit H,V prove their measurability. V=H implies D=1 on positive ranks and zero otherwise, so 0<=D<=1. The finite-dimensional series is jointly continuous. Any replacement equal almost everywhere for the product of one of these parameter laws and Gaussian probability gives, by Fubini, identical scores for parameter-almost-every point on one probability-one event. All H,V values, ranks and FDPs then agree on that event. Intersect these events for this countable collection of laws when needed.

For the polygon let a_(k)(G) be the kth largest value of G dot v(2pi j/n), including multiplicities. The exact largest rank is

$$
\rho_{\pi_n}=\frac1n\max\left(\{0\}\cup
\left\{k\in\{1,\ldots,n\}:b\ge S^{-1}(qk/n)-\tau a_{(k)}(G)\right\}\right).
$$

The count at this positive rank equals the rank, since any additional accepted observations would themselves produce a larger qualifying integer rank. This also handles ties. All finite quantities are measurable.

**2. Microscopic ranks.** Every parameter here has theta=0 and a unit direction, so its conditional marginal p-value distribution is exactly F_z. The asserted marginal comparison is equality for these parameters. More generally theta<=0 gives the stated inequality by the monotonicity of S.

For fixed z, b0 in (0,1), and u0=S^{-1}(b0), change variables t=S(u) to obtain

$$
\int_{(0,b_0]}\frac{dF_z(t)}{t}
=\frac1\tau\int_{u_0}^{\infty}
\frac{\phi((u-\sigma z)/\tau)}{S(u)}\,du<\infty.
$$

To verify finiteness, the part over any bounded interval is finite. For sufficiently large positive u, the elementary Mills bound 1/S(u)<=C(u+1)exp(u²/2) bounds the remaining integrand by a constant depending on z times

$$
(u+1)\exp\!\left\{-\frac{\sigma^2}{2\tau^2}u^2+
\frac{\sigma z}{\tau^2}u\right\},
$$

which is integrable since sigma>0.

For any of the laws under discussion the pathwise inequality at the actual positive rank is

$$
D_\pi\mathbf1_{\{0<\rho_\pi\le a\}}
\le q\int \ell\,\frac{\mathbf1_{\{0<p(x)\le qa\}}}{p(x)}\,\pi(dx).
$$

It follows from p(x)<=q rho at each counted null, hence 1/rho<=q/p(x). Conditional Tonelli and the conditional marginal formula give an upper bound q integral_(0,qa] dF_z(t)/t; the left side also is at most one. Thus its expectation is bounded by precisely E_Z min{1,q integral_(0,qa] dF_Z(t)/t}. This verifies the claimed inequality for every a, for the circle and every polygon. In fact the same argument is law- and dimension-independent: conditional stochastic domination bounds the expectation of the decreasing nonnegative function 1_{0<t<=qa}/t for any true theta<=0; the total null mass is at most one. Consequently it proves the displayed supremum inequality as well, once the ranks satisfy the specified bounds. At each z the finite integral over (0,qa] tends to zero as a decreases to zero. Dominated convergence for the outer minimum establishes the stated limit.

**3. Continuity and competing ranks.** Define the finite critical levels

$$
C(R)=\min_{0<r\le1}g_R(r),\qquad
C_n(G)=\min_{1\le k\le n}\{S^{-1}(qk/n)-\tau a_{(k)}(G)\}.
$$

Nearest-angle coupling also bounds the scalar projection difference by pi R/n. The resulting quantile bound, using the continuous circular quantile and the empirical decreasing order statistics, is

$$
\left|a_{(k)}(G)-R\cos(\pi k/n)\right|\le\pi R/n,
\qquad 1\le k\le n.
$$

For fixed finite R, the functions g_R tend to infinity at zero. The same lower bound S^{-1}(qr)-tau R applies to the discrete levels, so minimizers cannot escape to zero. On a remaining compact interval g_R is uniformly continuous. The mesh minima and the displayed quantile error therefore imply C_n(G)->C(R).

The ranks themselves converge almost surely. For fixed R>0, g_R is analytic on (0,1] and

$$
g_R'(r)=-\frac q{\phi(S^{-1}(qr))}+A\pi\sin(\pi r).
$$

The derivative is negative near zero and near one; analyticity on each intervening compact interval implies it has only finitely many zeros. Exclude their finitely many values g_R(r) and the endpoint value g_R(1) from b. A largest interior sublevel endpoint then is a regular root, with strict sublevel values immediately to its left and strict superlevel values to its right. The uniform quantile error on the grid, continuity, and coercivity give convergence of the largest discrete sublevel endpoint to that root. If the sublevel is empty, b<C(R) and it is eventually empty discretely. If the largest rank is one, b>g_R(1) and the discrete endpoint is eventually qualifying. This checks all largest-rank regimes, including competition between several crossings. Conditional on G the excluded b values have Gaussian probability zero; hence the result holds almost surely jointly. The event R=0 also has probability zero and its ranks were explicitly treated above.

Here the full original numerator equals H, so the exact FDRs, without optimizing a different functional, are

$$
F_\pi=\mathbb E_R S(C(R)/\sigma),\qquad
F_{\pi_n}=\mathbb E_G S(C_n(G)/\sigma).
$$

The finite critical levels converge and S is bounded and continuous, proving F_pi_n->F_pi by dominated convergence. Equality at a critical common shift does not change these expectations because Z has no atoms.

**4. Ordinary finite approximation and replication.** Each pi_n is already a finite rational law, with k_nj=1 and N_n=n, zero means and canonical true labels. Its observation vector has covariance

$$
\Sigma_{ij}=\tau^2\langle v_i,v_j\rangle+\sigma^2,
$$

which is positive semidefinite, has diagonal one, and has rank at most three. It is an admissible possibly singular ordinary Gaussian model. The largest-rank formula above is exactly ordinary n-coordinate BH. Its null count equals its total rejection count, so its ordinary FDR is exactly F_pi_n. Their Wasserstein and FDR limits were proved above. Replacing each coordinate by L identical copies leaves its empirical parameter law unchanged and gives exactly L times the ordinary rejection count; thus uniform replication preserves FDR. The tested completion value is therefore a limit of admissible finite FDR values at the same fixed loading.

## Failure

NOT fails: the circular population and canonical regular polygons satisfy all checked conclusion clauses, their actual largest ranks converge almost surely outside Gaussian-null conditional critical levels, and their full FDRs converge.
