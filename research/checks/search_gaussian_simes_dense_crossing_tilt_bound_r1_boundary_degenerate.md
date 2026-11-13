---
type: search_round
title: >-
  Refute search round 1 for the dense Simes crossing bound under Gaussian
  correlation (boundary and degenerate cases)
target_asset: gaussian_simes_dense_crossing_tilt_bound
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_simes_dense_crossing_tilt_bound_r1_s1_extreme_negative_equicorrelation
  - cand_gaussian_simes_dense_crossing_tilt_bound_r1_s1_rank_one_sign_pattern
  - cand_gaussian_simes_dense_crossing_tilt_bound_r1_s1_rank_two_uniform_circle
statement_digest: 6e714bc6bdb2353b928e977aa5b3c27aa068b24a6df42caf55510b6b8e0b24c8
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:14:45.821Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Because $C_D,q_D$ are existential, a counterexample must be a family with $q\to0$ and $\mathbb P(D_{q,\delta})/q\to\infty$. Every family with $q$ bounded below fails trivially, and the following reductions force three quantities to diverge together.
- Every family with $u_q\delta$ bounded fails `NOT` under arbitrary dependence (Gaussian not used). The Hommel-type weighting $\mathbf 1_{D}\le\sum_i\bigl[\mathbf 1\{p_i\le qk_0/N\}/k_0+\sum_{k_0<k\le N}\mathbf 1\{q(k-1)/N<p_i\le qk/N\}/k\bigr]$ with $k_0=\lceil N\overline\Phi(u_q+\delta)/q\rceil$ gives $\mathbb P(D_{q,\delta})\le q\bigl(1+\log(N/k_0)+1\bigr)\le q\bigl(2+\log\frac{\overline\Phi(u_q)}{\overline\Phi(u_q+\delta)}\bigr)=q\,(O(1)+u_q\delta+\delta^2/2)$. So the degenerate edges $\delta\downarrow0$ (only $k$ near $N$ admissible; for $\overline\Phi(u_q+\delta)>q(N-1)/N$ the event is $\{\max_ip_i\le q\}$, of mass $\le q$) and fixed $\delta$ with fixed $q$ are ruled out; a counterexample needs $\delta u_q\to\infty$ and can gain at most a factor $u_q\delta\le u_q$.
- Every family with $(N,\Sigma)$ fixed and $q\to0$ fails: for $\rho_{ij}<1$, $\mathbb P(T_i>u,T_j>u)=o(\overline\Phi(u))$, so up to $o(q)$ the event splits over the classes of perfectly correlated coordinates, a class of size $m$ contributing at most $qm/N$; hence $\limsup\mathbb P(D_{q,\delta})/q\le1$. A counterexample needs $N\to\infty$ (also $\mathbb P(D_{q,\delta})\le Nq$).
- Every rank-one covariance (all correlations $\pm1$, including the all-equal equality case) gives $\mathbb P(D_{q,\delta})\le q$, with equality for all-equal p-values: the count takes only the values $0,m,N-m$ and the event lies in two one-dimensional tails.
- Singular directions that are independent of the configuration do not help: for the extreme exchangeable matrix $\rho=-1/(N-1)$ the kernel direction splits off an independent scalar, giving $\le q/\overline\Phi(1)$ for $N\ge(u_q+1)^2$, while for $N<(u_q+1)^2$ (and any nonpositive correlation pattern with $N\lesssim u_q^2$) pairwise exceedances cost $N^2q^2=o(q)$.
- In rank two with equally spaced directions on the full circle, a $k$-fold crossing at angular width $\pi(k-1)/N$ costs the radial factor $e^{-4y^2}$, $y=v_k(k-1)/N$, which cancels the angular gain $v_kk/N$; the bound $\mathbb P(D_{q,\delta})\le5.8q$ holds without using $\delta$. The Rayleigh excess $\mathbb P(R\ge u_q)\asymp u_qq$ is not collected by a uniform angular configuration.

## Limitations

- Only rank-one, extreme exchangeable, and uniform rank-two configurations were worked out. Nonuniform or multiscale angular configurations in rank two or higher (dense nested clusters at many angular scales between $1/u_q$ and $1$, where the obstruction above gives only $O(q)$ per scale) were not covered. That is the natural place to try to accumulate the $u_q\delta$ Hommel factor across $\asymp u_q\delta$ disjoint scales.
- Mixed sign patterns combining near-antipodal clusters with independent blocks, and covariances where $N$, $\delta$ and the cluster geometry are tuned jointly with $q$, were not searched.
- The fixed-$(N,\Sigma)$ obstruction is asymptotic in $q$ and uniform constants were not extracted; it rules out families only, not single instances with a large constant.
