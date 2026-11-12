---
type: search_round
title: 'Round 2: joint-Gaussian admissibility and ordered scalar Mills marks'
target_asset: gaussian_bh_mixed_coherence_trace_budget
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_mixed_coherence_trace_budget_r2_s1_harmonic_nongaussian_copula
  - >-
    cand_gaussian_bh_mixed_coherence_trace_budget_r2_s2_antialigned_alternative_multiplicities
  - >-
    cand_gaussian_bh_mixed_coherence_trace_budget_r2_s3_mixed_antipodal_negative_trace
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:05:27.257Z'
extension_version: 0.0.4
---

## Obstructions

- A bivariate distribution with standard-normal marginals cannot be an admissible jointly Gaussian model if its copula excludes a nonempty open rectangle and it satisfies neither $P_2=P_1$ nor $P_2=1-P_1$ almost surely. Nonsingular bivariate Gaussian densities are positive on every open rectangle; the two singular Gaussian cases force those two equalities. Thus the tested harmonic-extremal mixture fails the joint-Gaussian hypothesis before any heat-trace conclusion is checked. Inverse-normal marginal transformation alone does not transfer an arbitrary-dependence extremizer into the target model.
- For every pair of positive multiplicities $m,k$, the rank-one model with $m$ identical true nulls $(\theta,v)=(0,1)$ and $k$ identical alternatives $(\mu,-1)$, with $\mu>2U$, has a decreasing scalar heat posterior and strictly negative signed trace. Precisely, writing $w=m/(m+k)$, $A=\overline\Phi^{-1}(qw)$, $T=\mu-U$, $L=\max(A,T)$, $E=[U,T]$, $J=(L,\infty)$, $b=1/h(U)$, and $c=1/h(A)<b$, the actual BH rule gives $f=w\mathbf1_E+\mathbf1_J$ and $B=wb\mathbf1_E+c\mathbf1_J$. Under the conditional terminal tilt, $a=c+(b-c)\pi$ with $\pi=\nu_{t,z}(E)$, and $\partial_z\pi=\pi(1-\pi)(\mathbb E[Y\mid E]-\mathbb E[Y\mid J])/(1-t)<0$. The candidate checks establish absolute trace integrability and the endpoint identity in this family. Consequently $M<0$ and $M_+=0$, uniformly for all displayed multiplicities and means, including arbitrary dependence of these parameters on $q$.
- In the specifically tested mixed-label pair with $v_1=1$, $v_2=-1$, $\theta_1=0$, $\theta_2=U+A+1$, and $A=\overline\Phi^{-1}(q/2)$, the actual largest BH rank falls from two to one at $L=A+1$. Its terminal Mills mark falls from $1/h(U)$ to $1/h(A)$; the heat posterior of the later tail increases, so the posterior field decreases. The explicit bound $F\mathbb E_{\mathbb Q}|K_t|\le (1/h(U)-1/h(A))\phi(L)$ proves absolute trace integrability, and the candidate independently checks the endpoint identity. Hence this actual mixed-label rank-loss mechanism also has $M<0$. It is a special case of the preceding multiplicity family, not an additional independent class of Gaussian models.

The scoped proof-step-like obstruction is recorded in [Ordered scalar Mills marks as a scoped nonpositive-trace proof step](../ideas/idea_97ed349e178b.md). Its use is limited to the displayed ordered two-component scalar geometry.

## Limitations

- No round-2 worker analyzed two or more noncollinear observation directions. Arbitrary covariance rank, dimension, nearly collinear perturbations, and directional complexity growing with $q^{-1}$ remain uncovered.
- The Gaussian mixed-label calculations cover exactly one block of identical zero-mean true nulls and one block of identical perfectly antialigned alternatives with $\mu>2U$. They do not cover $0<\mu\le2U$, nonzero nonpositive true-null means in these mixed models, unequal within-block means, multiple alternative blocks, general mixed-label covariance, or interlacing terminal rejection components. The specified $N=2$ rank-loss family adds a worked boundary calculation within that class, not coverage of these missing classes.
- Arbitrary $m,k$ and thus growing $N$ are covered only in that two-block model. Multiple interacting actual-rank changes, cascades across several distinct terminal Mills marks, and positive-trace scalar families remain unanalyzed this round.
- The harmonic mixture fails joint Gaussianity; later hypothesis checks and the target heat-trace conclusion were left unknown. It supplies neither an admissible counterexample nor a conclusion about all harmonic-type Gaussian constructions or Gaussian approximations to that mixture.
- The tested admissible families have $M_+=0$ and require neither budget term. They do not establish the entropy-linear term, a positive-trace coherence-deficit estimate, uniform absolute trace integrability, or the endpoint identity in the unrestricted model. The round found no counterexample and supplies no universal proof.
