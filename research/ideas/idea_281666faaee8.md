---
type: idea
title: Exact rejected-index KL identities and two entropy-gate obstructions
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - exact_Q_entropy_gate
---

## Status and scope

Bounded analytic gate test of architecture A in [the three-architecture portfolio](idea_00ec9e272a12.md). All calculations below are draft and require fresh independent verification. They create no plan, asset, dependency, completion root, or approval. The unrestricted one-sided and two-sided targets and their historical records are unchanged. No complete executable proof of the exact unrestricted one-sided root follows from this architecture yet.

## Exact rejected-null-index law, including singular models

Write the finite Gaussian model as T_i=theta_i+v_i.G, with G standard Gaussian in a finite dimension and each v_i a unit vector; a PSD factorization gives this representation even when the original covariance is singular. Let I0 be the original null labels, m0=|I0|, R the actual largest BH rejection count and p=FDR. Cases m0=0 or p=0 need no Q. Otherwise put P=Unif(I0) times gamma and

$$
Q(i,dg)=\frac{\mathbf1\{i\in\mathcal R_q(g)\}}{pR(g)}\gamma(dg).
$$

The zero convention on R=0 is understood. Its total mass is E[V/(p(R vee 1))]=1. Its density relative to P is m0/(pR) on its support. Since 1<=R<=N there, its finite KL divergence is exactly

$$
D=D(Q\Vert P)=\log(1/p)+E_Q\log(m0/R).
$$

Let Z=v_I.G, X=-log S(Z), pi0=m0/N, and W=X-log(N/(qR)), where S is the standard Gaussian survival function and I denotes the label sampled by Q. Under P, Z is standard normal and X has Exp(1) law, including singular covariance. Under Q, theta_I<=0 and rejection imply Z>=z(qR/N)-theta_I>=z(qR/N), so W>=0. Finite N gives all needed expectations: the density of Q relative to P is bounded by m0/p, so X is integrable. Elementary substitution, with no entropy theorem, yields

$$
E_QX-D-E_QW=\log\frac{p}{q\,pi0}.
$$

Consequently the desired root is equivalent, for this exact Q and sufficiently small q, to

$$
E_QX-D-E_QW\le\log(1/pi0)+\tfrac12\log\log(1/q)+C.
$$

This equivalence is a diagnosis, not a mechanism proving the bound. A proposed gate without log(1/pi0) would prove the stronger pi0-scaled FDR bound and is false, as below. Data processing gives D>=E_QX-h_Q(X) whenever the scalar differential entropy is defined. Replacing D by this scalar lower bound creates a different, stronger marginal-entropy obligation, also false below.

## Basic stress tests from first principles

Independent central nulls: set a null p-value to zero and call the resulting largest rank R_i. The deterministic leave-zero-out identity is {i rejected}={U_i<=qR_i/N}, with R=R_i on this event. Independence and uniform U_i yield each null contribution q/N; hence p=q pi0. Conditional on the selected label and its background, U_i/(qR_i/N) is uniform, so W is independent Exp(1) and E_QW=1. Thus E_QX-D=1. This holds in particular for all-null independent tests with arbitrary finite N and fixed q. Negative null means need not satisfy this equality and have not been replaced by central ones in the general identities.

Identical central-null clones: R=N on U<=q, p=q and Q is the truncated uniform law U in (0,q). Thus D=log(1/q), E_QW=1 and E_QX-D=1.

Two antipodal central-null clone blocks of proportions a and b=1-a: for q<1/2 the two rejection events U<=qa and 1-U<=qb are disjoint; each event rejects exactly its triggering block. Hence p=q, Q chooses the sides with probabilities a,b, D=log(1/q)+a log(1/a)+b log(1/b), E_QW=1 and E_QX-D=1. Non-strict endpoints have Gaussian probability zero; no arbitrary tie-breaking is used.

## Exact critical-alternative falsification of the pi0-scaled joint gate

Fix any q in (0,1/2), N>=2 and t_r=qr/N, z_r=S^{-1}(t_r). Let G be scalar standard Gaussian and use N tests

$$
T_0=G,\qquad T_j=z_j+z_{j+1}-G\quad(1\le j\le N-1).
$$

All alternative means z_j+z_{j+1} are positive. The covariance is the rank-one Gram matrix of (1,-1,...,-1), so it is admissible. The sole null is label 0. Put U=S(G). Apart from finitely many probability-zero endpoints, U in (t_{r-1},t_r) means that the null is rejected at the actual largest rank R=r (t_0=0). Indeed G lies between z_r and z_{r-1}; the first r-1 alternatives and the null qualify at threshold z_r. At any s>r, the (s-1)st alternative has score z_{s-1}+z_s-G<z_s, so at most s-1 total tests reach z_s and s cannot qualify. For r=1 the same latter argument applies, with the null alone qualifying. When U>q no null can be rejected at any BH rank. Endpoints retain the stipulated non-strict BH rule; they do not change any integral.

Writing H_N=sum_{r=1}^N 1/r gives the exact formulas

$$
p=\frac qN H_N,\qquad Q(R=r)=\frac1{rH_N},\qquad pi0=1/N.
$$

Conditional on R=r under Q, U is uniform on (t_{r-1},t_r). Thus, with g_1=1 and g_r=1+(r-1)log(1-1/r) for r>=2,

$$
E_QW=\frac1{H_N}\sum_{r=1}^N\frac{g_r}{r}\le\frac2{H_N}\longrightarrow0.
$$

For the bound, g_r<=log(r/(r-1))<=1/(r-1), so the r>=2 sum is at most sum 1/(r(r-1))<=1. The map G to X is invertible and there is only one null label; therefore there is no conditional entropy loss in data processing and

$$
h_Q(X)=E_QX-D=\log H_N+E_QW.
$$

At fixed q this tends to infinity. It refutes any joint residual gate E_QX-D-E_QW<=B(q) independent of N and pi0, in particular the pi0-scaled root certificate. It does not refute the exact unrestricted root: p/q=H_N/N remains small. Allowing the necessary log(1/pi0)=log N term makes this example harmless.

Strictly negative null means can also exhibit the same obstruction. Let a=z_1, delta=1/a, change T_0 to G-delta and each alternative mean to z_j+z_{j+1}+delta. The same rank argument uses U0=S(G-delta). Its density relative to uniform u is w_delta(u)=exp(-delta z(u)-delta^2/2). For u in [q/N,q], w_delta(u)>=exp(-1-1/(2a^2)), so

$$
\frac{pN}{q}\ge e^{-1-1/(2a^2)}(H_N-1)\longrightarrow\infty.
$$

Here theta_0=-delta<0, all alternative means stay positive, and the general exact-Q identity still proves divergence of E_QX-D-E_QW=log(pN/q). This strengthens only the scope of the auxiliary falsification, not the root conclusion.

A small direct enumeration checked every midpoint rank r at q=.05 for N=2,3,10,100 using the actual sorted p-values and largest qualifying rank; all matched. This diagnostic corroborates, and does not replace, the analytic derivation.

## All-null heterogeneous clone blocks falsify the marginal entropy gate

This construction was supplied by the parent proof worker and checked here algebraically; it still requires fresh independent verification. For an integer m>=1, class j=1,...,m contains 2^j independent Gaussian blocks, each block containing n_j=2^(m-j) identical central nulls. Different blocks are independent. Thus N=m 2^m and each class has null mass 1/m. Let h index a block, n_h its size, pi_h=n_h/N. Force all members of block h to p=0 and call the resulting largest count R_h. Its background is independent of U_h, the common uniform p-value of block h.

The group leave-zero-out identity follows by monotonicity and self-consistency: h is rejected iff U_h<=qR_h/N, and R=R_h on that event. Integration in U_h gives contribution q pi_h, so p=q exactly and Q chooses block h with probability pi_h. Under Q conditional on block h, the background has its original distribution and

$$
X=\log(1/q)+\log(N/R_h)+E,\qquad W=E,
$$

where E is independent Exp(1). The selected class J is uniform on {1,...,m}. In the forced-zero model the same identity for every other block gives E[(R_h-n_h)/R_h]=q(1-pi_h). Therefore the bad-background probability P(R_h>=2n_h)<=2q.

On the good event B={R_h<2n_h}, put A=log(R_h/n_h) in [0,log2). Then

$$
X=\log(1/q)+\log m+J\log2-A+E.
$$

Define the integer estimator Jhat=floor((X-log(1/q)-log m)/log2). On B its error K=Jhat-J=floor((E-A)/log2) is at least -1, and E[K+1|B]<=1+1/log2. Entropy of a nonnegative integer with bounded mean is bounded by the entropy of the geometric law with that mean; this elementary maximum-entropy fact follows directly from nonnegativity of KL to that geometric law. Hence H(K|B)<=C0 universal. Encoding the bad-event indicator first gives, for fixed q<1/4,

$$
H(J\mid X)\le\log2+2q\log m+C0.
$$

Conditionally on J, X is an independent Exp(1) added to a bounded shift, so h(X|J)>=h(E)=1. This follows from concavity of differential entropy applied to the mixture of translated exponential densities. Thus

$$
h_Q(X)\ge1+(1-2q)\log m-\log2-C0,\qquad E_QW=1.
$$

It follows that no dimension-free bound h_Q(X)-E_QW<=B(q) can hold, even with pi0=1 and p=q. This refutes the scalar marginal entropy reduction that would suffice for the root. It does not refute a label-aware joint entropy mechanism: the exact-Q identity in this very model gives E_QX-D=1, so the divergence discarded by scalar data processing is essential. This is distinct from positive Mills-trace or per-face charging counterexamples.

## First unresolved root gate and next distinct route

The exact law is valid; the false gates are the pi0-scaled joint residual bound and the dimension-free scalar marginal entropy certificate. The root-level label-aware residual estimate with its log(1/pi0) allowance remains unproved, and its displayed form is exactly the original FDR upper bound, so listing it as a proof-plan step would be circular. No analytic falsification of the original target is asserted. Native library searches for Gaussian BH entropy/overshoot/rank, selected-score entropy, and the harmonic critical model returned no applicable joint entropy theorem. The closest OU reverse-isoperimetry entry has no Proof section; the positive-Gaussian Simes entry assumes nonnegative correlations and has no detailed proof to adapt. Neither supplies the missing unrestricted gate and neither is used as a black box.

The genuinely distinct next bounded test is architecture B: construct an actual PSD-compatible coherent/diffuse split, preserve common largest BH rank and block masses, and first analyze q-dependent near-equicorrelation, simplex directions and heterogeneous almost-orthogonal blocks. Test whether the rejection-weighted sum of coherent and diffuse costs is uniform before any new plan. The new critical-alternative staircase must be retained as a stress case for any block/mean or small-null-fraction reduction. No decomposition, diffuse count concentration or uniform covariance-budget theorem is being claimed. Architecture C remains blocked on its old global signed allocation, so renaming it is not a new plan.
