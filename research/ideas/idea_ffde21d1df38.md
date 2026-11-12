---
type: idea
title: >-
  Exposed-alternative surface factorial moments from truncated Gaussian
  convolution
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - one-sided
  - independent-nulls
  - marked-crossings
  - surface-factorial-moments
  - native-plan-first-tests
---

## Constructive mechanism and status

The root agent proposed exposing one Gaussian alternative while retaining the actual-rank marked crossing. For independent nulls, conditioning on that alternative produces a rank-one residual correlation: splitting nulls by the signs of their correlations gives negatively correlated groups. Instead of bounding the possibly huge conditional mean and then losing the face density, the calculation below keeps that density inside a factorial-moment kernel.

This is a new finite intermediate estimate, not a proof of the unrestricted FDR theorem or an approved lemma. Its independence assumption concerns the centered true-null scores only; alternative means, correlations and all rank masks are otherwise unrestricted. Native library search for log-concave convolution/density-variance/truncated normal returned no applicable node. The auxiliary one-dimensional log-concavity facts are explained below and would have to be checked inline in an executed proof, rather than cited as undeclared dependencies.

## Proposed surface estimate

Let X_1,...,X_m be independent standard normals and let Y be any jointly Gaussian standard normal with Cov(X_i,Y)=b_i. Necessarily sum_i b_i^2<=1. Let theta_i<=0, u>=1, t=barPhi(u), and
$$
V_u=\sum_{i=1}^m1_{\{X_i+\theta_i>=u\}}.
$$
There is a universal C such that, for every integer 1<=d<=m and every real y (at continuous conditional-density versions),
$$
\phi(y)E[(V_u)_d\mid Y=y]
\le C(u+1)(m)_d t^d. \tag{SF}
$$
Here (n)_d=n(n-1)...(n-d+1). Crucially, y is arbitrary. At an alternative's physical rank-r face it can be y=u(qr/N)-mu_j with arbitrary positive alternative mean mu_j. No lower bound on y or conditional variance is required.

## Detailed derivation for one subset

Fix a d-subset S of the null indices, and put a_i=u-theta_i>=u and A=max_{i in S}a_i. Write
$$
Y=\sum_{i\in S}b_iX_i+\sigma Z,\qquad
\sigma^2=1-\sum_{i\in S}b_i^2,
$$
where Z is independent standard Gaussian, including sigma=0.

Conditional on all X_i>=a_i (i in S), the variables W_i=X_i|X_i>=a_i remain independent. Their densities are proportional to exp(-x^2/2)1{x>=a_i}. Such a density is log-concave; reflection and nonzero scaling preserve log-concavity. The independent sum
$$
Y_S=\sum_{i\in S}b_iW_i+\sigma Z
$$
therefore has a one-dimensional log-concave density. The sum cannot be a point mass: sigma^2+sum b_i^2=1, and each nonzero truncated component has a nondegenerate continuous law. Convolution preservation of log-concavity is the usual one-dimensional Prékopa argument; it remains an explicit elementary proof obligation if this route is executed.

For every a>=1,
$$
Var(Z\mid Z>=a)\ge c/(a+1)^2. \tag{TV}
$$
One direct check uses the excess E=Z-a. Its density is proportional to exp(-a e-e^2/2), e>=0. The intervals [0,1/(a+1)] and [2/(a+1),3/(a+1)] each have probability at least a universal positive constant, using barPhi(a)/phi(a)<=1/a. Their separation is at least 1/(a+1), proving (TV) by the independent-copy variance identity. Thus
$$
Var(Y_S)=\sigma^2+\sum_{i\in S}b_i^2 Var(W_i)
\ge c_0/(A+1)^2.
$$

For a one-dimensional log-concave probability density f with variance v, one has ||f||_infinity<=C_0/sqrt(v). A short coarse-constant proof places a mode at zero and writes M=f(0). On either side, the first distance where f falls to M/e is at most e/M, since the integral up to that distance is at least its length times M/e. Concavity of log f then gives an exponential upper envelope beyond that distance. Integrating x^2 against the central M bound and these exponential tails gives E[(X-mode)^2]<=C/M^2, hence v<=C/M^2 and the claimed maximum-density bound. Finite-support or one-sided endpoints follow by the same envelope or a limit. Applying it to Y_S gives
$$
||f_{Y_S}||_\infty<=C(A+1).
$$

The joint surface identity is exact:
$$
\phi(y)P(X_i>=a_i\ \forall i\in S\mid Y=y)
=\left[\prod_{i\in S}barPhi(a_i)\right]f_{Y_S}(y).
$$
Because every a_i>=u and one equals A, its right-hand side is at most
$$
C(A+1)barPhi(A)t^{d-1}
\le C(u+1)t^d.
$$
The last inequality follows because (x+1)barPhi(x) decreases for x>=1: its derivative is barPhi(x)-(x+1)phi(x)<0. Summing over ordered distinct d-tuples gives (SF), with no d-dependent constant.

## Consequences at an actual rank face

For every integer l>=d,
$$
\phi(y)P(V_u>=l\mid Y=y)
\le \frac{C(u+1)(m)_d t^d}{(l)_d}.
$$
This controls a null-count mark with the Gaussian face density already paid. It avoids the invalid step of bounding a conditional mean and then suppressing its 1/phi(y) cost. Choosing d comparable to l gives a conditional surface count tail when the actual face enforces many null rejections.

This is not a null-only supremum bound: the original intended application is to the mark for an actual alternative rank face, with the largest-rank mask retained. Additional marks bounded by one may be included on the left and then discarded for this upper bound. Their dependence is unrestricted.

## Exact whole-share kernel still to be allocated

For one alternative j, let r_j^+ be BH's largest rank after forcing its p-value to zero and r_j^- the largest rank after forcing it to infinity, leaving physical denominator N fixed. Varying only its p-value makes the actual rank either r_j^- or r_j^+, with the jump at p_j=q r_j^+/N. Since j is an alternative, its exact FDP jump is
$$
K_j=\frac{V(qr_j^+/N)}{r_j^+}
-\frac{V(qr_j^-/N)}{r_j^-\vee1}.
$$
The whole-null share is used: this includes both newly selected nulls and dilution of previously selected nulls. In a generic smooth Gaussian path, its signed marked crossing expression is the sum over physical ranks r of
$$
\phi(u(qr/N)-mu_j)
E[\dot T_j\,1_{\{r_j^+=r\}}K_j
\mid T_j=u(qr/N)].
$$
The position/velocity normalization and boundary regularization must be specified for the chosen path; this display is the formal finite-cell coarea kernel to prove, not an already audited formula.

(SF) controls its actual null-count tail marks and preserves every negative null mean. It does not by itself control the velocity mark without further Gaussian regression, does not make all intermediate physical-rank masks disjoint after conditioning at different levels, and does not justify summing positive parts instead of the signed K_j. In ranks that can be supplied largely by alternatives, it also gives no large mandatory null-count threshold. These are the next concrete allocation questions.

The general-correlated true-null block remains outside (SF); no reduction to independent nulls or model change is assumed. A pending main-target plan needs an explicit further transfer/aggregation step rather than treating (SF) as the universal theorem.

## Inline convolution check

The log-concavity preservation used above can be reconstructed in one dimension without adding a library dependency. For log-concave densities f,g, put h(x)=integral f(x-y)g(y)dy. Fix x_0,x_1 with h(x_l)>0, and normalize p_l(y)=f(x_l-y)g(y)/h(x_l). Let T be the increasing transport from p_0 to p_1, so p_0(y)=p_1(T(y))T'(y) almost everywhere on their supports. For 0<lambda<1, define x_lambda=(1-lambda)x_0+lambda x_1 and y_lambda=(1-lambda)y+lambda T(y). Log-concavity of f and g gives
$$
f(x_\lambda-y_\lambda)g(y_\lambda)
\ge h(x_0)^{1-\lambda}h(x_1)^\lambda
p_0(y)^{1-\lambda}p_1(T(y))^\lambda.
$$
The Jacobian satisfies (1-lambda)+lambda T'(y)>=(T'(y))^lambda by weighted arithmetic-geometric mean. Multiplication and the transport density identity therefore lower-bound the transformed integrand by h(x_0)^{1-lambda}h(x_1)^lambda p_0(y). Integrating over y gives h(x_lambda)>=h(x_0)^{1-lambda}h(x_1)^lambda. One first applies this to positive smooth restrictions/approximations and passes by monotone truncation and density approximation; for the half-line truncated normals the monotone transport is smooth on the interior and endpoint limits give the same conclusion directly. Repeated convolution and reflection supply exactly the log-concavity required in the subset calculation.
