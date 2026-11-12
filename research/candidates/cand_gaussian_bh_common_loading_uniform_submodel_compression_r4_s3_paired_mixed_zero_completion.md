---
type: candidate
title: Antithetic mixed tags at the admitted zero-mean boundary
status: failed
target_asset: gaussian_bh_common_loading_uniform_submodel_compression
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
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:30:58.332Z'
extension_version: 0.0.4
---

## Object

For every positive integer m, fix q=1/4 and sigma=1/2, put tau=sqrt(3)/2, n=m^2, N=2n and d=n. For k=1,...,n use the paired parameters

$$
(\theta_{2k-1},v_{2k-1},\ell_{2k-1})=(0,e_k,1),\qquad
(\theta_{2k},v_{2k},\ell_{2k})=(0,-e_k,0).
$$

Thus the pair scores are tau G_k+sigma Z and -tau G_k+sigma Z. Sample m indices independently and uniformly from these 2n coordinates and retain the exact original scores and labels. This tests the permitted false-tagged-zero boundary with a growing number of antithetic mixed pairs. The earlier all-null orthogonal family does not already cover it: its positive-rank FDP is identically one, whereas the current mixed numerator fluctuates separately and its pairwise residual correlations are negative.

## Checks

### H1

The testing level q=1/4 lies in (0,1/2), and the common loading sigma=1/2 is fixed in (0,1), independently of m.

### H2

N=2m^2 and d=m^2 are finite positive integers. Every direction is a deterministic signed standard basis vector and has norm one. Singular dependence and repeated directions are permitted.

### H3

All means are zero. The true tags therefore satisfy theta<=0 and the alternative tags satisfy theta>=0. The latter are precisely the explicitly admitted analytic-completion boundary points.

### H4

Take G standard Gaussian in R^n and Z an independent standard Gaussian. The displayed paired scores have exactly the specified common-loading representation and unit marginal variances.

### H5

The indices I_1,...,I_m are iid uniform on [N], independent of (G,Z).

### H6

An index repeated in the sample reuses the same paired score and tag; there is no fresh Gaussian noise or relabeling.

### H7

Use ordinary largest non-strict BH on both arrays. Its normalized rank equals the largest continuous qualifying rank for the corresponding empirical score law. Indeed, a fractional qualifier r with count k/M>=r makes k/M a grid qualifier, since the cutoff qk/M is at least qr. At a positive actual rank r, the total count at its own cutoff is exactly r: a larger count c would itself qualify at the larger cutoff qc, contradicting maximality. These arguments retain ties and terminal rank one.

### NOT

The proposed nonvanishing discrepancy fails. The following bounds compute its vanishing without assuming monotonicity of mixed FDP.

Write H,V and H_m,V_m for residual-score tails, and put

$$
\Delta_m=\max\{\sup_t|H_m(t)-H(t)|,\sup_t|V_m(t)-V(t)|\},
\qquad
\beta_m=\sup_t|V(t)-H(t)/2|.
$$

Conditional iid index sampling gives E Delta_m <= C/sqrt(m). One direct distribution-free argument symmetrizes each nested threshold class; conditional on the sampled values, ordering them turns the Rademacher process into partial sums, whose expected maximum is at most 2 sqrt(m) by the L2 maximal inequality. Symmetrization and division by m give C/sqrt(m), also for the tagged subclass. This applies with atoms.

For the full paired population, let F_n^+(t)=n^{-1} sum_k 1{tau G_k>=t} and F_n^-(t)=n^{-1} sum_k 1{-tau G_k>=t}. Then

$$
H=(F_n^++F_n^-)/2,\qquad V=F_n^+/2,\qquad
V-H/2=(F_n^+-F_n^-)/4.
$$

Both empirical tails have the same expectation S(t/tau). Applying the same maximal estimate to the independent G_k within either sign, and using the triangle inequality between the two signs, yields E beta_m <= C/sqrt(n)=C/m. Independence between the two empirical tails is not needed. Consequently

$$
\sup_t|V_m(t)-H_m(t)/2|\le\beta_m+3\Delta_m/2.
$$

For completeness, ranks have a uniform comparison in this particular sampling coupling. Let 0<gamma<b/2 and condition on the event Delta_m<=gamma. If r>=b is a qualifying rank for one law at z, then r-gamma qualifies for the other at z+h, where

$$
h=L_{q,b}\gamma/\sigma,\qquad
L_{q,b}=\sup_{b/2\le s\le1}|u_q'(s)|.
$$

Indeed u_q(r-gamma)-sigma(z+h)<=u_q(r)-sigma z, and the total tail loses at most gamma. H7 identifies the resulting fractional qualifier with a lower bound on the actual grid rank. Both actual ranks are nondecreasing functions of z with values in [0,1]. For any such function f,

$$
E[f(Z+h)-f(Z)]\le h/\sqrt{2\pi},
$$

because its Stieltjes measure has mass at most one and each Gaussian interval of length h has probability at most h/sqrt(2 pi). The good event is independent of Z. Applying the transfer in both directions, and bounding its complement by Markov's inequality, gives

$$
E|\rho_m-\rho_N|
\le 2(b+\gamma)+2L_{q,b}\gamma/(\sigma\sqrt{2\pi})
  +C/(\gamma\sqrt m).
$$

Here L_{q,b}<=C_q/b: the ratio S(u)/phi(u) is bounded on u>=u_q(1)>0, and |u_q'(s)|=q/phi(u_q(s)). Taking b=m^{-1/8} and gamma=m^{-1/3}, for sufficiently large m, proves

$$
E|\rho_m-\rho_N|=O(m^{-1/8}).
$$

Let a=m^{-1/16}. When both ranks are at least a, exact self-consistency from H7 and the paired numerator estimates imply

$$
|D_m-D_N|\le(2\beta_m+3\Delta_m/2)/a.
$$

When both ranks are at most 2a, their expected FDP contribution is at most 2 B_{q,sigma}(2a) by the approved microscopic bound, applied to the full array and, conditional on the sampled indices, to its sampled multiset. This conditioning is valid because indices are independent of the Gaussian scores. The only remaining case has one rank below a and the other above 2a, so its probability is at most E|rho_m-rho_N|/a. Therefore

$$
E|D_m-D_N|
\le C/(a\sqrt m)+2B_{q,\sigma}(2a)
       +E|\rho_m-\rho_N|/a
\longrightarrow0.
$$

The microscopic term vanishes at the fixed q,sigma by the approved theorem in the supplied pack. Together with the rank estimate, this rules out a persistent expected error for this concrete growing mixed family, including its admitted zero-mean alternative tags.

## Failure

NOT fails: antithetic-pair symmetry controls the mixed numerator, common Gaussian shift controls sampled ranks, and the approved microscopic estimate removes the remaining small-rank contribution.
