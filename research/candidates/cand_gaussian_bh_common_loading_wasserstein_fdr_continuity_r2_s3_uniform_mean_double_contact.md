---
type: candidate
title: Uniform negative means with a nonatomic interior double-contact BH birth
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
round: 2
slot: 3
direction: idea_9491db8dc586
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:46:49.625Z'
extension_version: 0.0.4
---

## Object

Take q=1/4, sigma=1/2, tau=sqrt(3)/2, and the real Hilbert space R. Every parameter has v=+1 and true tag ell=1. Let pi be the law of (-A,+1,1), where A is uniform on [0,10], independently of the Gaussian randomness. Define
$$
\pi_n=\frac1n\sum_{j=1}^n\delta_{(-10(j-1/2)/n,+1,1)}.
$$
Write u=S^{-1}, G=tau X(1)+sigma Z, and
$$
b(r)=u(qr)+10r,\qquad B=\min_{0<r\le1}b(r),\qquad
B_n=\min_{1\le k\le n}\{b(k/n)-5/n\}.
$$
The proposed obstruction is the positive interior double contact at the birth of a qualifying rank. We test all four conclusion clauses on this population and its specified empirical sequence; the microscopic estimate below is additionally verified uniformly over parameter laws.

## Checks

### H1

The constants satisfy q in (0,1/2) and sigma in (0,1).

### H2

R is a nonzero separable real Hilbert space, v=+1 has unit norm, X(v)=v xi with xi standard normal, and Z is an independent standard normal. Thus G is standard normal and every score has variance tau^2+sigma^2=1. All finite score vectors are jointly Gaussian; their common covariance matrix has every entry equal to one and is positive semidefinite.

### H3

The uniform interval law and each displayed empirical probability law are deterministic Borel probability laws, fixed independently of xi and Z. The index n ranges over the positive integers, as required.

### H4

Every mean is nonpositive and every tag is one. Thus every parameter belongs to the closed tagged domain, and every atom of every pi_n has its canonical ordinary one-sided true-null label. The pi_n means are in fact strictly negative.

### H5

All means belong to [-10,0], so the laws have finite first moment; the absolute-mean first moment is 5 for pi and every pi_n.

### H6

Couple each uniform quantile interval [(j-1)/n,j/n] to its midpoint. Directions and tags agree, so only the absolute difference of means contributes. One-dimensional monotone transport gives the exact value
$$
W_1(\pi_n,\pi)
=10\sum_{j=1}^n\int_{(j-1)/n}^{j/n}|s-(j-1/2)/n|\,ds
=\frac{10}{4n}\longrightarrow0.
$$

### NOT

Fail: the double contact does not violate any conclusion tested on this object. The following are analytic checks, rather than numerical agreement.

**Clause 1: actual largest rank, measurability, and the contact.** For 0<r<=1 and G=g,
$$
H_\pi(r;g)=V_\pi(r;g)
=\min\{1,\max\{0,(g-u(qr))/10\}\}.
$$
Consequently H_pi(r;g)>=r if and only if g>=b(r). Moreover,
$$
b'(r)=10-\frac q{\phi(u(qr))},\qquad
b''(r)=\frac{q^2u(qr)}{\phi(u(qr))^2}>0.
$$
Here u(qr)>0 because qr<=1/4. The derivative tends to minus infinity at zero, while b'(1)>0: u(1/4) is between zero and one, so phi(u(1/4))>phi(1)>1/40=q/10. Thus b has exactly one minimizer r_* in (0,1), with
$$
\phi(u(qr_*))=q/10,\qquad B=b(r_*),\qquad b(r)\to\infty\quad(r\downarrow0).
$$
The actual largest crossing is exactly
$$
\rho_\pi(g)=
\begin{cases}
0,&g<B,\\
r_*,&g=B,\\
r_+(g),&B<g<b(1),\\
1,&g\ge b(1),
\end{cases}
$$
where r_+(g) is the unique root on (r_*,1) of b(r)=g. For B<g<b(1) there are two roots and the displayed formula selects the larger one; at g=b(1) the larger root is the endpoint one. At g=B the interior non-strict contact is retained. At every positive selected rank H_pi(rho)=rho, including the endpoint one. All these functions are Borel measurable, and
$$
D_\pi=\mathbf1_{\{G\ge B\}},\qquad F_\pi=S(B).
$$
There is no issue with an infinite series in this one-dimensional Hilbert space: X(v)=v xi is jointly measurable and defined simultaneously for all v. For a replacement representative agreeing product-almost-everywhere, Fubini gives equality of scores for parameter-almost-everywhere x on a probability-one event. Then all H and V values agree simultaneously, hence so do the rank and FDP. The same event can be intersected over the countable displayed laws.

For pi_n, H and V are finite sums of measurable threshold indicators. Its rank is the maximum qualifying k/n and its numerator equals that rank. Thus its rank and FDP are measurable, every positive rank is attained with H_pi_n(rho)=rho, and 0<=D_pi_n<=1.

**Clause 2: conditional comparison and the full uniform microscopic estimate.** This check does not rely on independence of residual evaluations. For any true parameter and fixed z, theta<=0 implies, using one scalar standard normal U,
$$
S(\theta+\tau U+\sigma z)\ge S(\tau U+\sigma z).
$$
It yields the asserted conditional marginal CDF comparison, with the exact displayed CDF in the target. Put t=S(y). The integral in the target is
$$
I_z(b):=\int_{(0,b]}\frac{dF_z(t)}t
=\int_{u(b)}^\infty
\frac{\phi((y-\sigma z)/\tau)}{\tau S(y)}\,dy.
$$
On a finite interval the integrand is continuous. For y>=1, the lower Mills bound S(y)>=phi(y)y/(1+y^2) bounds it by a constant depending on z,tau times
$$
(y+y^{-1})
\exp\left\{-\frac{\sigma^2}{2\tau^2}y^2
+\frac{\sigma z}{\tau^2}y\right\}.
$$
This is integrable because sigma>0. Hence I_z(b)<infinity for every b<1, and I_z(b)->0 as b decreases to zero.

For completeness, the rank equality needed for the bound is pathwise: for any population law with rho>0, qualifying ranks approaching rho show H(rho)>=rho by monotonicity. If H(rho)>rho and rho<1, a slightly larger rank below H(rho) would qualify, a contradiction. For rho=1 the equality follows from H<=1. Thus V(rho)<=rho. Scores are finite for parameter-almost-everywhere x almost surely, by the parameterwise Gaussian validity and Fubini.

On {0<rho<=a}, every rejected parameter has 0<p<=q rho<=qa, so 1/rho<=q/p. Therefore, for any parameter law,
$$
0\le D\mathbf1_{\{0<\rho\le a\}}
\le q\int\ell\,p^{-1}\mathbf1_{\{p\le qa\}}\,d\pi,
\qquad D\mathbf1_{\{0<\rho\le a\}}\le1.
$$
The function t^{-1}1_{t<=qa} is nonnegative and decreasing on (0,1). Conditional marginal comparison, Tonelli, and true mass at most one imply
$$
\mathbb E[D\mathbf1_{\{0<\rho\le a\}}\mid Z=z]
\le\min\{1,qI_z(qa)\}.
$$
Integrating and taking the supremum proves exactly the target's uniform bound. Its limit is zero by dominated convergence in z. For the uniform mean limit there is the additional explicit fact rho>0 implies rho>=r_*, so its microscopic FDP is identically zero whenever a<r_*.

**Clause 3: continuity through the actual double contact.** The kth largest score for pi_n is G-10(k-1/2)/n. Thus ordinary BH has a positive rank exactly when G>=B_n. All hypotheses are true, giving the exact formula
$$
D_{\pi_n}=\mathbf1_{\{G\ge B_n\}},\qquad F_{\pi_n}=S(B_n).
$$
There is no replacement of the largest root by the smaller one: its complete rank formula is
$$
\rho_{\pi_n}(g)
=\frac1n\max\bigl(\{0\}\cup
\{k\in\{1,\ldots,n\}:g\ge b(k/n)-5/n\}\bigr).
$$
Since b>=B, B_n>=B-5/n. Taking k_n=ceil(n r_*) gives k_n/n->r_* and
$$
B_n\le b(k_n/n)-5/n\longrightarrow B.
$$
It follows that B_n->B and F_pi_n->S(B)=F_pi. In particular, a discrepancy at the contact G=B cannot have positive probability under the standard Gaussian G. This is an exact limiting argument, with no numerical root tracking.

**Clause 4: ordinary finite approximation and replication.** Each pi_n is a rational law of n canonical parameters, with k_nj=1 and N_n=n. Its finite observation is exactly the jointly Gaussian vector
$$
T_j=-10(j-1/2)/n+G,\quad 1\le j\le n,
$$
whose covariance matrix is the all-ones matrix. The canonical true set is all of [n], and the kth BH inequality is precisely G>=b(k/n)-5/n as above. The population empirical rank agrees with the ordinary largest BH rank divided by n: any fractional qualifying rank r has k= n H(r)>=nr, and the rank k/n also qualifies. Conversely every qualifying discrete BH rank qualifies for the empirical population law. At its largest rank H=r, so the common-cutoff numerator and the ordinary finite FDP coincide exactly. Hence its ordinary FDR is exactly F_pi_n, and the established limit is F_pi.

If each of these n coordinates is replicated L times, all copies of a score form a block. Any qualifying rank inside a block makes the last rank of that block qualify, because the p-value stays fixed and the threshold increases. The last rank of the kth block has threshold qk/n. Thus the largest qualifying block is unchanged, both counts are multiplied by L, and its FDR is exactly unchanged. There are no alternative-tagged zero parameters to approximate in this object.

These checks exclude this assigned nonatomic double-contact population and its empirical sequence as a counterexample. They do not assert continuity for every nonatomic law or every different perturbation family.

## Failure

NOT fails: the actual largest-root double contact yields F_pi=S(B), its exact canonical finite FDRs are S(B_n), B_n tends to B, and the remaining conclusion clauses hold on the tested laws, including the uniform microscopic estimate above.
