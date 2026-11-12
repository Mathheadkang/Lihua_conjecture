---
type: candidate
title: Growing independent antipodal pairs with null means approaching zero
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
slot: 3
direction: drop_hypothesis
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T22:10:51.594Z'
extension_version: 0.0.4
---

## Object

For every integer m>=1, take N=2m, d=m, independent standard Gaussian coordinates G_1,...,G_m, and delta_m=1/m. Set
$$
T_{2j-1}=-\delta_m+G_j,\qquad T_{2j}=-\delta_m-G_j,
\qquad 1\le j\le m.
$$
Use any 0<q<=S(1), one-sided p-values, and ordinary BH. All scores are original true nulls. This tests strictly negative null means approaching the label boundary while both actual rank m and null count 2m grow.

This is not latent padding or replication of a single random variable: separate pairs depend on independent coordinates, and the covariance has rank m. The new mechanism checked here is an exact reduction to BH on independent superuniform folded p-values. The board's rank-one antipodal calculation and restricted-null-count distance bound alone do not establish this reduction.

## Checks

### H1

N=2m is positive and finite, and every mean equals the finite real number -1/m.

### H2

Take v_{2j-1}=e_j and v_{2j}=-e_j. Each vector has norm one, and their Gram matrix is positive semidefinite with unit diagonal. Its rank is m. Singular covariance is legal.

### H3

The specified q obeys precisely 0<q<=S(1)<1/2; it may vary with m.

### H4

Every mean is negative, so I_0=[2m] and pi_0=1. No labels are changed, removed, or reassigned.

### H5

Within pair j, the smaller p-value is
$$
W_j=S(|G_j|-\delta_m),
$$
and the larger is S(-delta_m-|G_j|)>=S(-delta_m)>1/2, whereas every W_j<=S(-delta_m). Thus no rank k>m can qualify under BH, since its order statistic is at least 1/2 while qk/(2m)<=q<1/2. For k<=m the relevant order statistics are exactly the sorted W_j. Consequently the original 2m-test BH has a rejection if and only if m-test BH at level q, applied to U_j=min{1,2W_j}, has a rejection: clipping at one changes no comparison with qk/m<1. This is an identity for the original procedure's nonzero-rejection event, including ties; it is not a replacement testing model used to define f.

### H6

Because every original hypothesis is null, the fixed full FDP is f(G)=1{original BH rejects}. J(f) is its full Euclidean OU integrated gradient norm, without separating positive and negative boundary terms. It is finite: direct Mehler differentiation and 0<=f<=1 give, with rho=e^{-t},
$$
\|\nabla T_t f(x)\|_2
\le \frac{\rho}{\sqrt{1-\rho^2}}\,\mathbb E\|G'\|_2,
\qquad
J(f)\le\frac\pi2\mathbb E\|G'\|_2<\infty.
$$
Differentiation is justified by the integrable derivative of the finite-dimensional Gaussian kernel. No value of J or unsigned jump charge is used below.

### H7

On the positive-probability event G_1>=delta_m+S^{-1}(q/(2m)), at least one original p-value is <=q/(2m), so BH rejects. Therefore F>0 for every finite m.

### NOT

The U_j are independent and superuniform. Indeed, for 0<t<1, u=S^{-1}(t/2)>0 and
$$
\mathbb P(U_j\le t)
=2S(u+\delta_m)\le 2S(u)=t.
$$
Here 0<U_j<=1, so these are ordinary independent superuniform p-values, with a possible atom at one. Their global-null BH rejection probability is at most q. To verify this directly, let R^{(j,0)} be the BH rejection count after replacing U_j by zero. For each r>=1, the deterministic step-up identity is
$$
\{j\text{ rejected},R=r\}
=\{U_j\le qr/m,\ R^{(j,0)}=r\}.
$$
To see it, decreasing a rejected entry to zero preserves the sorted values above rank r; conversely U_j<=qr/m ensures the first r entries still qualify when a zero is restored to U_j, and increasing that zero cannot create a larger qualifying rank. Since R^{(j,0)} depends only on the other entries, independence and superuniformity yield
$$
\begin{aligned}
\mathbb P(R>0)
&=\sum_{j=1}^m\sum_{r=1}^m\frac1r
\mathbb P(U_j\le qr/m,\ R^{(j,0)}=r)\\
&\le\sum_{j=1}^m\sum_{r=1}^m\frac qm
\mathbb P(R^{(j,0)}=r)=q.
\end{aligned}
$$
The event identity in H5 and all-null original labels therefore give F<=q=q pi_0. The numerator F(F-q pi_0)_+ vanishes, hence the bridge ratio is zero under the target's convention for every m and legal q. In the limiting mean-zero version the folded p-values are exactly independent uniforms and the displayed inequality is equality, giving F=q. Thus this growing-rank family cannot refute any finite universal A. No conclusion follows for general growing mixed-sign null-direction families.

## Failure

NOT fails: independent antipodal folding makes the full FDR at most q, so the positive excess and bridge ratio are identically zero even as rank and null count grow and negative means approach zero.
