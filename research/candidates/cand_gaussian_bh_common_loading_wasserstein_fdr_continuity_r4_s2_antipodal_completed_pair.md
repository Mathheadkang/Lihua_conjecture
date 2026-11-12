---
type: candidate
title: Antipodal two-score completed pair with negative Gaussian dependence
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
round: 4
slot: 2
direction: small_cases
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:53:50.411Z'
extension_version: 0.0.4
---

## Object

Take $q=1/4$, $\sigma=1/2$, $\tau=\sqrt3/2$ and $\mathcal H=\mathbb R$. For independent standard normals $G,Z$, let $X(v)=vG$ for $v\in\{-1,1\}$. Put
$$
\pi=\tfrac12\delta_{(0,1,1)}+\tfrac12\delta_{(0,-1,0)},\qquad
\pi_n=\tfrac12\delta_{(0,1,1)}+\tfrac12\delta_{(1/n,-1,0)}.
$$
Write $A=\tau G+\sigma Z$ and $B=-\tau G+\sigma Z$. These are standard normal with correlation $-1/2$. The limiting p-values are $U=S(A)$ and $W=S(B)$, and the approximating p-values are $U$ and $W_n=S(B+1/n)$.

This is a different dependence mechanism from the board's independent two-block family: the residual evaluations are perfectly anticorrelated, the two scores are negatively correlated, and the exact identity $F=q$ times true mass fails strictly. It is also not a coincident-score zero-tag pair. The intended obstruction was that retaining both crossing ranks while separating a completed alternative-zero tag might yield a nonvanishing jump under negative dependence.

## Checks

### H1

The fixed level $q=1/4$ lies in $(0,1/2)$.

### H2

The fixed common loading $\sigma=1/2$ lies in $(0,1)$.

### H3

The Hilbert space $\mathbb R$ is nonzero, real and separable. Both residual directions have unit norm.

### H4

All laws are deterministic probabilities in the closed tagged domain. The true point has mean zero; the completed alternative has mean zero; every approximating alternative has strictly positive mean. The first absolute mean moment is zero for $\pi$ and $1/(2n)$ for $\pi_n$.

### H5

The stated finite-dimensional isonormal evaluation and independent common $Z$ are exactly those of the definition. Every score has variance $\tau^2+\sigma^2=1$. In particular the negative dependence does not violate the common-loading representation.

### H6

Couple corresponding atoms with mass $1/2$. The only transport cost is the alternative mean change, so
$$
W_1(\pi_n,\pi)\le\frac1{2n}\longrightarrow0.
$$
Tags and directions are unchanged.

### NOT

NOT fails. All four conclusion clauses hold on these laws, as checked below.

**Clause 1: functional, rank and representative.** The finite evaluation is jointly measurable, and finite atomic integration makes $H,V$ measurable. For either law, with its associated second p-value $w$, the actual largest non-strict crossing is exactly
$$
\rho=
\begin{cases}
1,&\max(U,w)\le q,\\
1/2,&\min(U,w)\le q/2\text{ and }\max(U,w)>q,\\
0,&\text{otherwise}.
\end{cases}
$$
Indeed any positive qualifying rank must be at most the number of admitted atoms divided by two, and every admitted group makes its endpoint rank qualify. This accounts for both competing positive ranks, the endpoint one, and the zero case. Every positive rank is attained and satisfies $H(\rho)=\rho$. The full FDP is
$$
D=\tfrac12\mathbf1_{\{U\le q,\ w\le q\}}
  +\mathbf1_{\{U\le q/2,\ w>q\}}.
$$
It is measurable and lies in $[0,1]$. An evaluation change null under parameter-law times Gaussian probability affects neither atom's score outside a Gaussian-null set, so it changes neither FDP nor expectation. This also holds simultaneously for the countable collection $\pi,\pi_1,\ldots$.

**Clause 2: microscopic ranks and conditional integral.** The only true atom has mean zero, so its conditional p-value distribution is exactly $F_z$; the stipulated marginal comparison is equality. For $u_0=S^{-1}(b)$,
$$
\int_{(0,b]}\frac{dF_z(t)}t
=\int_{u_0}^{\infty}
\frac{\exp(-(u-\sigma z)^2/(2\tau^2))}
{\tau\sqrt{2\pi}\,S(u)}\,du<\infty.
$$
To verify finiteness, the reciprocal Mills bound for $u\ge1$ is $1/S(u)\le C(1+u)e^{u^2/2}$. The resulting exponent has quadratic coefficient $-\sigma^2/(2\tau^2)<0$; the remaining bounded interval is harmless. As $b\downarrow0$ the integral tends to zero by integrability of this tail.

More explicitly, on $0<\rho\le a$, a rejected true atom obeys $U\le q\rho\le qa$ and $1/\rho\le q/U$. Hence
$$
D\mathbf1_{\{0<\rho\le a\}}
\le\frac q2\frac{\mathbf1_{\{U\le qa\}}}{U}.
$$
Conditional expectation and the bound $D\le1$ give
$$
\mathbb E[D\mathbf1_{\{0<\rho\le a\}}\mid Z=z]
\le\min\!\left\{1,\frac q2\int_{(0,qa]}\frac{dF_z(t)}t\right\}
\le\min\!\left\{1,q\int_{(0,qa]}\frac{dF_z(t)}t\right\}.
$$
This is the proposed bound on the tested laws. Its right side tends to zero after Gaussian averaging by bounded convergence. In this particular pair the left side is already zero whenever $a<1/2$. These calculations do not claim to prove the supremum bound for untested laws.

**Clause 3: full mixed FDR under the stated approximation.** Define
$$
C_n(s,t)=\mathbb P\{U\le s,\ W_n\le t\},\qquad
C(s,t)=\mathbb P\{U\le s,\ W\le t\}.
$$
Using the actual full FDP above and the uniform true marginal gives the exact formulas
$$
F_{\pi_n}=\frac q2+\frac12 C_n(q,q)-C_n(q/2,q),\qquad
F_\pi=\frac q2+\frac12 C(q,q)-C(q/2,q).
$$
Every boundary in these events has probability zero, since both scores have continuous normal marginals. Since $W_n\to W$ pointwise, bounded convergence gives $C_n(s,t)\to C(s,t)$ at the displayed thresholds and therefore $F_{\pi_n}\to F_\pi$.

The dependence change is substantive: $F_\pi>q/2$. To see this, conditional on $U=u$, the probability $g(u)=\mathbb P(W\le q\mid U=u)$ is strictly increasing in $u$ because the score correlation is strictly negative. Thus
$$
C(q/2,q)=\int_0^{q/2}g(u)\,du
<\frac12\int_0^qg(u)\,du=\frac12C(q,q).
$$
Consequently the previous independent-block identity is unavailable, but the correct correlated full FDR remains continuous. Equivalently, the rank and FDP converge almost surely away from the four threshold boundary events; this retains both positive ranks rather than selecting one root in advance.

**Clause 4: ordinary canonical arrays and replication.** Each $\pi_n$ already is the empirical law of the two-coordinate ordinary Gaussian array with means $(0,1/n)$, true-null labels $(1,0)$ and covariance
$$
\begin{pmatrix}1&-1/2\\-1/2&1\end{pmatrix}.
$$
This covariance is positive definite, and the array has exactly the prescribed common loading. The ordinary largest BH ranks $0,1,2$ are exactly $2\rho$, and the ordinary FDP is the displayed $D$. Thus its FDR is exactly $F_{\pi_n}$, converging to the completed law's value. For each individual $\pi_n$, the constant empirical-law sequence provides its finite approximation.

Replicating each coordinate $M$ times produces only possible largest positive BH ranks $M$ and $2M$: if any rank inside a tied block qualifies, the endpoint of that same block also qualifies. The resulting thresholds, fractions of rejected true atoms and FDP are unchanged. These arrays therefore satisfy the claimed exact replication and completed-value approximation assertions for this example.

## Failure

NOT fails: antipodal negative dependence strictly changes the completed FDR away from the independent-block value, but the exact full-FDR formula is continuous and all four conclusion clauses hold for the tested pair and its canonical approximations.
