---
type: idea
title: Complete candidate for regular angular Gaussian finite-array limits
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
  - gaussian_bh_two_sided_sharp_upper
tags:
  - candidate-complete-proof
  - regular-angular-density
  - finite-array-limit
---

New unverified extension candidate developed from idea_1f4a1c8ef0ce and the finite-array route. Source research-local/regular_angular_finite_gaussian_candidate_20261104.md SHA15015aa5e2b84d2d338184da5e0d69b1820916d48a82bc59f82bd84b490ccfb6. Whole fresh audit is pending. This allows continuous nonisotropic mean-dependent direction densities kappa<=f_mu<=K, retains actual folded CDF, and proposes both a population bound and a fixed-q,d,kernel finite-Gaussian-array limsup. It is NOT a theorem promotion, NOT a uniform finite-N bound, and NOT an unrestricted conjecture proof. Any native new statement must preserve all regularity and convergence hypotheses, reprove the changed projection and orientationwise steps, and undergo fresh verification. Full candidate follows for native context retrieval.

# Candidate: regular angular Gaussian populations and their finite-array limits

Date: 2026-11-04. Original local extension candidate; no research node or loop state is changed. This is not a verification verdict or an unrestricted Gaussian BH theorem. It adapts the analytic arguments in the spherical population candidate and the finite-array transfer candidate; every changed hypothesis is stated below.

## Model and proposed statement

Fix integer d>=4. Write sigma_d for normalized uniform sphere measure. Let W be any Borel probability measure on finite nonnegative means, with pi0=W({0}). For each mu>=0 let f_mu be a continuous sphere density, jointly Borel in (mu,v), satisfying fixed bounds

$$
0<\kappa\le f_\mu(v)\le K<\infty,\qquad \int f_\mu\,d\sigma_d=1.
$$

Thus kappa<=1<=K; set A=K/kappa>=1. The conditional direction density may depend on the mean, and need not be isotropic or antipodally symmetric. Z is standard d-dimensional Gaussian, R=||Z||, and Omega=Z/R. Every index (mu,v) has statistic mu+v·Z, variance one. The population has index measure W(dmu) f_mu(v) sigma_d(dv), with zero residual variance.

For fixed omega, define the actual folded tail

$$
F_\omega(r,x)=\int\!\int \mathbf1\{|\mu+r v\cdot\omega|\ge x\}
 f_\mu(v)\,d\sigma_d(v)\,dW(\mu).
$$

Let x_omega(r) be the smallest finite x>=u satisfying F_omega(r,x)>=2Q(x)/q, where u=Q^{-1}(q/2); use no rejections if none exists. This is the largest population BH p threshold. Its conditional FDP is the actual null sub-tail divided by F at this threshold, and zero without a threshold.

The proposed population bound, for u>=104 A, is

$$
\mathrm{FDR}_{\rm pop}\le q\pi_0 K\{2+4A M_d(1+u^{-2})\log(3u)\}+e^{-2u^2},\tag{P}
$$

where c_d=Gamma(d/2)/(sqrt(pi) Gamma((d-1)/2)) and

$$
M_d=\frac{c_d}{\sqrt{d-2}}
\left(\frac{d-3}{d-2}\right)^{(d-3)/2}\le1.
$$

The companion finite statement fixes q,d,W and the densities FIRST. Let deterministic unit vectors v_j,N and means mu_j,N>=0 define exactly Gaussian finite arrays T_j,N=mu_j,N+v_j,N·Z, covariance Gram matrix with unit diagonal. Assume their total and true-null empirical p-sub-CDFs converge uniformly in t∈[0,1], for Gaussian-almost every z, to the ACTUAL population CDFs above (not to an isotropic surrogate). Then the proposed limsup_N finite BH FDR obeys the same right side as (P). There exist deterministic sequences satisfying these assumptions. No finite-N uniform rate or bound for arbitrary arrays is asserted.

## 1. Projection densities and regularity

For fixed mu,omega,r, let g_mu,omega,r(y) be the density of r v·omega under f_mu sigma_d. If g_r is the uniform-sphere projection density and H_r its upper tail, latitude disintegration gives

$$
\kappa g_r(y)\le g_{\mu,\omega,r}(y)\le K g_r(y),\qquad
\kappa H_r(y)\le P(r v\cdot\omega\ge y)\le K H_r(y).
$$

The same bounds hold for lower reflected tails by symmetry of the reference sphere law, without assuming symmetry of f_mu. The density g_mu,omega,r(y) is continuous in (omega,r,y), including support endpoints when d>=4. Indeed, in a local continuous rotational chart sending e1 to omega, it is g_r(y) times the latitude average of the continuous bounded f_mu. The average varies continuously for |y|<r; at |y|=r the uniform-sphere factor tends to zero and the bounded density handles the limit. A finite chart cover handles the sphere. Joint measurability in mu follows from the Borel kernel. Bounds on compact r,x rectangles allow differentiation and continuity after W integration, even when W has no moments or has unbounded support: nonzero derivative terms require mu<=x+r.

Consequently F_omega is C1 in (r,x), with derivatives continuous also in omega. For its two boundary densities put

$$
b_\mu=g_{\mu,\omega,r}(x-\mu)+g_{\mu,\omega,r}(-x-\mu),
$$

$$
d_\mu=(x-\mu)g_{\mu,\omega,r}(x-\mu)
 +(x+\mu)g_{\mu,\omega,r}(-x-\mu).
$$

Then B=int b_mu dW=-F_x and D=int d_mu dW=r F_r. These signs retain both actual folded boundaries.

## 2. Relative negative-radial budget

If d_mu<0, necessarily mu>x. That component's rejection probability is at least P(v·omega>=0)>=kappa/2, while (d_mu)_-<=K M_d. Hence the integrated negative part is <=2 A M_d F. If D<=0, its positive part is no larger, and

$$
-D\le2 A M_d F.
$$

For 0<ell<r and x>=ell, split means at mu=x-ell. Below the split b_mu<=d_mu/ell. Above it the component rejection probability is >=kappa H_r(ell), while b_mu<=2K g_r(0). Therefore, including D=0,

$$
B\le A\{2M_d/\ell+2g_r(0)/H_r(\ell)\}F\qquad(D\le0).\tag{B}
$$

These are bounds relative to the actual total rejection CDF; no positive lower bound on alternative mass is imposed.

## 3. Global first-contact comparison

Use ell=r/(2sqrt(d)), r0=max(u,52 A sqrt(d)/u), L=sqrt(d)+2u. The spherical moment estimate P(U1>=1/(2sqrt(d)))>=3/32, c_d<=sqrt(d), and M_d<=1 give the brace in (B) at most 26sqrt(d)/r. Thus its multiple by A is <=u/2 on [r0,L]; also ell<=u.

At a zero of f=F_omega-2Q/q, f_x=h(x)F-B. When D<=0, f_x>=(x/2)F>0. A zero with f_x=0 therefore has D>0. For any finite initial first contact, use the strict moving barrier X'=4 A M_d/(r X)+epsilon. The compact maximum of f over [u,X(r)] cannot cross below zero: an interior maximizer has f_x=0 and hence positive f_r; an upper maximizer has f_x>=0 and f_r+X'f_x>0 by the negative budget; a lower zero at u means F=1 and hence f_x=2phi(u)/q>0. Compactness and epsilon→0 give, for all r2>=r1 in the core,

$$
x_\omega(r_2)^2\le x_\omega(r_1)^2+8 A M_d\log(r_2/r_1)
$$

whenever the first contact at r1 is finite. No regular-branch-only inference is used. Clip at T>L; y=min(x,T), including x=∞, satisfies the same all-pairs bound. Thus y²-8 A M_d log r is nonincreasing and y is regulated. Root births, switches and absence are included.

## 4. Transport with a uniform-sphere null upper envelope

The ACTUAL folded null tail is at most 2K H_r(x). At a contact F=2Q/q, this bounds conditional FDP by q pi0 K H_r(x)/Q(x). The Gaussian radius R is independent of Omega, even though the selected cutoff depends on Omega.

For the reference Gaussian radius let C(r,s)=P(||Z||<=r | Z1>=s) and k=C_r=f_chid(r)H_r(s)/Q(s). Its partial derivative in s belongs to [-h(s),0], and h(s)<=s+1/s. For each FIXED omega, elementary partition telescoping plus the all-pairs bound yields

$$
\int_{r_0}^L k(r,x_\omega(r))\,dr
\le1+4 A M_d(1+u^{-2})\log(L/r_0).
$$

Precisely, an upward increment of y costs at most .5(1+u^-2) Delta(y²), bounded by 4 A M_d(1+u^-2) Delta log r; a downward increment adds nonnegative C and helps. Right-endpoint step functions converge almost everywhere because y is regulated, and k is bounded continuous on the clipped compact rectangle. T>L makes C=k=0 wherever no root or x>=T. This proves the integral bound without an a.e.-derivative shortcut or an unproved BV assumption. Average over Omega; all constants are uniform in it.

## 5. Lower and upper radii

Since u>=104 A, r0²-u²<=d-3. The reference polar Bayes identity and the increasing part of the chi-square_(d-1) density give

$$
\int_0^{r_0} f_{\chi_d}(r)\sup_{x\ge u}H_r(x)/Q(x)\,dr\le1.
$$

The actual null upper envelope therefore costs at most q pi0 K. Above L, FDP<=1 and chi-square Chernoff gives P(R>L)<=exp(-2u²). In the core L/r0<=3u; combining its transport cost with the lower and upper pieces proves the candidate (P).

For fixed K,kappa, the bound is O(q log u)=o(qu), uniformly in d and in the whole mean-dependent angular kernel. More generally the bound is o(qu) if K A log u=o(u) with u>=104 A eventually. This condition excludes singular/atomic angular populations.

## 6. Transfer to deterministic finite Gaussian arrays

Let the empirical total and true-null p-sub-CDFs converge uniformly in t, for Gaussian-almost every z, to the actual nonisotropic population CDFs. Exact finite largest-rank BH gives G_N(t_N)=t_N/q and FDP_N=q G_N^0(t_N)/t_N for t_N>0, including ties. At a fixed z with radius r, every zero-residual null p-value is >=2Q(r)>0. Thus subsequential thresholds tending to zero have eventually zero FDP.

For each fixed orientation, F_omega is C1 and every core zero with f_x=0 has f_r>0. The zero set is locally a C1 graph r=rho(x); tangencies project to critical values of rho and form a null set of radii by the elementary one-dimensional C1 Sard argument. This critical set is measurable jointly in (r,omega): on compact x intervals it is the projection of a closed subset with compact x-fiber, and a countable union covers all finite x. Fubini and independence of R and Omega therefore make exceptional core Gaussian samples null. At every other radius the first root is a strict upcrossing; empirical uniform convergence and the exact BH grid force convergence to the largest population p-threshold. A population without a positive root forces t_N→0 and hence no false discoveries eventually.

On lower radii, an arbitrary positive selected-threshold subsequential limit has limiting FDP bounded by q pi0 K times the same reference envelope; zero limits have FDP zero. Upper radii use FDP<=1. Bounded reverse Fatou, core convergence, and the three bounds above give limsup_N FDR_N bounded by (P). The conditional core estimate, not merely the final global population theorem, is used here.

Deterministic sequences satisfying the empirical-CDF assumption exist. Draw iid (mu_j,v_j) from W(dmu)f_mu(v)sigma_d(dv). For each fixed z!=0 the conditional p-CDF and null sub-CDF are continuous (the projected density is atomless). SLLN at rational thresholds, then Fubini, yields auxiliary-almost every infinite sequence good for Gaussian-almost every z. Monotonicity and continuity upgrade rational convergence to uniform convergence. Fix one such realization permanently. Every finite prefix is then an exactly jointly Gaussian vector with deterministic means and unit-diagonal PSD Gram covariance. No unconditional Gaussian-mixture assertion or uniform finite-N rate is made.

## Scientific boundary and provenance

This is a complete candidate argument to be independently checked, not a theorem promotion. The isotropic population candidate is recovered by K=kappa=1. The finite conclusion is a fixed-q,d,W,kernel large-N limsup; only afterwards may one choose a sufficiently accurate diagonal N(q). It does not give a bound for arbitrary finite arrays, or for angular densities whose regularity constants grow too fast, and does not resolve either unrestricted conjecture.

Frozen sources: spherical_radial_bh_global_population_bound_20261104.md SHA8fa9133ab87e6f718f36e1b368b7619999d338341562fca0f6822c11a6385188; spherical_finite_array_transfer_candidate_20261104.md SHAa7a651b3b44567449b3d966b33455074bd2960465d6f579b6885658bbd043ef4. The elementary partition variant is native idea_7dd1ad550ece; its independent local audit covers only that transport step under d>=4.
