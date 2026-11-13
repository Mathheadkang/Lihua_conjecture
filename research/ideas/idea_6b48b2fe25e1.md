---
type: idea
title: >-
  Tensor lift to nonnegative correlations: test the negative variation of
  Gaussian Simes size along the Schur-square path
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_simes_one_sided_uniform_linear_bound
  - gaussian_simes_sparse_crossing_fixed_level_cap
tags:
  - global-null-simes
  - schur-square-interpolation
  - signed-flux
  - unproved-approach
---

Suggested by this chat while the researcher asked whether there was a new idea after the loop stopped. This is a new variant for the current all-null blocker, not a claim of literature novelty or a completed proof. It explicitly reuses the existing three-face identity. No research-loop stage was advanced.

## Covariance path and tensor realization

Let $F_q(R)$ denote the centered one-sided Gaussian Simes rejection probability at level $q$ for correlation matrix $R$. For a fixed correlation matrix $\Sigma=(\rho_{ij})$, set
$$
R_t=(1-t)\Sigma+t(\Sigma\circ\Sigma),\qquad 0\le t\le1,
$$
where $\circ$ denotes entrywise product. The Schur product theorem makes $\Sigma\circ\Sigma$ positive semidefinite, with unit diagonal and nonnegative entries. Therefore every $R_t$ is a correlation matrix and [the positive-Gaussian Simes theorem](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) gives $F_q(R_1)\le q$.

If $\rho_{ij}=\langle v_i,v_j\rangle$ for unit vectors $v_i$, take independent standard Gaussian vectors $G$ and $H$ in the original and tensor-product feature spaces. Put $Z_i=\langle v_i,G\rangle$ and $W_i=\langle v_i\otimes v_i,H\rangle$. Then $\operatorname{Cov}(W_i,W_j)=\rho_{ij}^2$ and $\sqrt{1-t}Z_i+\sqrt t\,W_i$ realizes this Gaussian path. The endpoint scores are Gaussian linear functions of tensor features.

## Why this differs from the failed interpolation budget

The covariance velocity is
$$
\Delta_{ij}=\rho_{ij}^2-\rho_{ij}=-\rho_{ij}(1-\rho_{ij}).
$$
For small correlation it retains an $O(|\rho_{ij}|)$ factor. For positive near-clones it retains an $O(1-\rho_{ij})$ factor, and exact positive clones remain identical throughout the path. Thus exact duplication of a coordinate with its physical multiplicity is preserved.

[The failed three-face noise-packing plan](../plans/plan_one_sided_order_three_face_noise_packing_20261106.md) reports that its budget maximized against a covariance independently of the original one, discarded a necessary small-correlation factor, and could grow logarithmically with dimension. Its recorded failure recommends retaining the true covariance contraction. The present proposal responds to that obstruction, restricts the objective to all-null rejection, and changes the endpoint to an already controlled positive-correlation model. It does not assume that the recorded failed-budget counterexample has native independent verification.

## Exact signed derivative to retain

For positive-definite matrices, Price differentiation of the bounded Simes indicator gives
$$
\frac{d}{dt}F_q(R_t)=\sum_{i<j}\Delta_{ij}J_{ij,t}.
$$
The analytic tool is [Voigtlaender, A general version of Price's theorem](https://arxiv.org/abs/1710.03576), which allows distributional derivatives; it supplies no Simes bound.

The terms $J_{ij,t}$ come from [the existing leave-two-out three-face reduction](idea_ec681eb191fb.md), not a new identity. Freeze all p-values other than $i,j$ and let $C_k=\#\{\ell\ne i,j:p_\ell\le qk/N\}$. If the frozen coordinates already have $C_k\ge k$ for some $k$, the indicator is constant in the pair and its mixed derivative is zero. Otherwise let
$s=\max\{k:C_k=k-1\}$ and $r=\max\{k:C_k=k-2\}$. Both exist and $r>s$. With $Q=\bar\Phi$, put $x=Q^{-1}(qs/N)$ and $y=Q^{-1}(qr/N)$, so $x>y$. Rejection is
$\{\max(Z_i,Z_j)\ge x\}\cup\{\min(Z_i,Z_j)\ge y\}$.
Its mixed distributional derivative is
$$
\delta_y\otimes\delta_y-\delta_x\otimes\delta_y-\delta_y\otimes\delta_x.
$$
Thus $J_{ij,t}$ is the expectation over the remaining coordinates of
$f_{ij\mid-ij,t}(y,y)-f_{ij\mid-ij,t}(x,y)-f_{ij\mid-ij,t}(y,x)$.
The remaining coordinates determine the thresholds and the conditioning; do not replace them by independent deterministic levels.

For singular $\Sigma$, first use $\Sigma^\varepsilon=(1-\varepsilon)\Sigma+\varepsilon I$ and its Schur-square path. Require every proposed bound to be uniform in $\varepsilon$. Pass to the limit for each fixed finite model using the absence of atoms at the finitely many deterministic BH threshold hyperplanes.

## A new falsifiable gate, stronger than endpoint comparison

Fix one sufficiently small universal level $q_*\le1/4$. Test whether the total downward variation
$$
V_-(q_*,\Sigma)=
\int_0^1
\left[-\sum_{i<j}\Delta_{ij}J_{ij,t}\right]_+\,dt
$$
is at most $1/2$, uniformly over dimension, correlation and regularization. Here $a_+=\max(a,0)$. If so,
$F_{q_*}(\Sigma)\le F_{q_*}(\Sigma\circ\Sigma)+V_-\le q_*+1/2\le3/4$.
[Fixed-level amplification](../assets/gaussian_simes_fixed_level_amplification.md) would then prove the linear Simes bound. A stronger estimate $V_-(q,\Sigma)\le Cq$ would also suffice.

The positive part is taken AFTER summing the signed pair contributions. Bounding individual face magnitudes or replacing $\Delta$ by an independently optimized PSD matrix would repeat the old obstruction. The signed integral without the positive part is merely an endpoint identity and does not by itself constitute progress. The variation gate is a stronger, potentially false claim, and needs tests before becoming a proof plan.

## An exact benchmark: arbitrarily replicated signed rank one

Suppose one group, of mass $w=m/N\in(0,1)$, consists of copies of $G$, and the other of copies of $-G$. The path keeps each group tied and moves their mutual correlation from $-1$ to $1$ via $r=2t-1$. Let
$C_r(a,b)=\Pr(P_1\le a,P_2\le b)$ for one-sided Gaussian p-values at correlation $r$. Direct counting gives
$$
F_q(r)=q+C_r(q,q)-C_r(qw,q)-C_r(q,q(1-w)).
$$
For $q<1/2$, every displayed copula term is zero at $r=-1$; at $r=1$ they equal $q$, $qw$, and $q(1-w)$, respectively. Each is nondecreasing in $r$ by the bivariate Gaussian derivative formula. Therefore total variation of $F_q(r)$ over $[-1,1]$ is at most $2q$. Its endpoints both equal $q$, so its downward variation is at most $q$. This verifies the proposed scale of the gate on signed rank-one designs with arbitrary multiplicities, independently of $N$. If one sign group is absent the path is constant and downward variation is zero.

This benchmark is an elementary side-chat derivation, not a native verified asset.

## Remaining research obligation

The researcher asks that the following exact remaining problem be available for a later research-loop attempt. This section is a problem specification inside a draft idea, not an executable proof plan or a proved lemma.

### Precise problem: one fixed level with a uniform downward-variation budget

For each positive integer $N$, let $\mathcal C_N$ be the set of real symmetric positive-semidefinite $N\times N$ matrices with diagonal entries one. For $R\in\mathcal C_N$ and $0<q<1$, define
$$
F_q(R)=
\Pr_{Z\sim N_N(0,R)}
\left\{\exists k\in\{1,\ldots,N\}:
 p_{(k)}\le\frac{qk}{N}\right\},
\qquad p_i=\bar\Phi(Z_i),
$$
where the order statistics include multiplicities and comparisons are non-strict. All coordinates are true nulls.

For $\Sigma\in\mathcal C_N$, define
$$
R_t^\Sigma=(1-t)\Sigma+t(\Sigma\circ\Sigma),
\qquad f_{q,\Sigma}(t)=F_q(R_t^\Sigma),
\qquad 0\le t\le1.
$$
For a real function $f$ on $[0,1]$, define its downward variation by
$$
\mathcal V_-(f)=
\sup_{0=t_0<t_1<\cdots<t_m=1}
\sum_{\ell=1}^{m}
\bigl[f(t_{\ell-1})-f(t_\ell)\bigr]_+,
$$
where the supremum is over all finite partitions and $a_+=\max(a,0)$. This definition permits infinite variation and does not assume absolute continuity.

**Prove or find an obstruction to the following assertion:**
$$
\exists q_*\in(0,1/4]\quad
\forall N\ge1\quad
\forall\Sigma\in\mathcal C_N:
\qquad
\mathcal V_-(f_{q_*,\Sigma})\le\frac12.
\tag{SV}
$$
The single level $q_*$ must be universal. Dimension, covariance rank, signs of correlations, numbers and multiplicities of clone groups, and all singular limits are unrestricted. No covariance operator-norm, correlation-gap, graph-degree or entropy bound may be added. Any one fixed level satisfying (SV) is enough; no specified numerical value or sharp constant is required.

### Why (SV) is sufficient

The endpoint has nonnegative correlations, so $f_{q_*,\Sigma}(1)\le q_*$. By the definition of downward variation,
$$
f_{q_*,\Sigma}(0)
\le f_{q_*,\Sigma}(1)+\mathcal V_-(f_{q_*,\Sigma})
\le q_*+\frac12\le\frac34.
$$
Taking the supremum over all $N,\Sigma$ gives $B(q_*)\le3/4$. The approved [fixed-level amplification lemma](../assets/gaussian_simes_fixed_level_amplification.md) then yields
$$
B(q)\le\frac{2\log4}{q_*}\,q
\qquad(0<q\le q_*/2).
$$
Thus a proof of (SV) closes the unrestricted linear Simes target. Conversely, the Simes endpoint bound alone does not control downward variation: a path could have many oscillations while remaining small.

### Exact analytic summation that remains open

For positive-definite $\Sigma$, set $\rho_{ij}=\Sigma_{ij}$ and
$\Delta_{ij}=\rho_{ij}^2-\rho_{ij}$. Price's formula gives
$$
\mathcal V_-(f_{q,\Sigma})=
\int_0^1
\left[-\sum_{i<j}\Delta_{ij}J_{ij,t}\right]_+\,dt,
$$
with the signed conditional three-face terms $J_{ij,t}$ defined above. On a frozen configuration of all remaining coordinates that already forces rejection, the term is zero. Otherwise its two ranks $s<r$ and thresholds $x>y$ are selected by that same frozen configuration; the conditional density combination is
$$
f_{ij\mid-ij,t}(y,y)
-f_{ij\mid-ij,t}(x,y)
-f_{ij\mid-ij,t}(y,x).
$$
The concrete missing estimate is a uniform bound of $1/2$ on this integral at one universal $q_*$, retaining the random rank restrictions and the actual factors $\Delta_{ij}$. The pair contributions must be summed with their signs before taking the positive part. The partial proof could not sum these terms in unrestricted dimension. Dropping the rank restrictions, bounding every conditional probability by one, and summing individual corner magnitudes introduces a growing number of rank and pair terms.

It is legitimate to prove the estimate first for positive-definite $\Sigma$, provided the constants are independent of the regularization $\Sigma^\varepsilon=(1-\varepsilon)\Sigma+\varepsilon I$. For each fixed finite $N$, Gaussian probabilities along the regularized paths converge to the singular-path probabilities because the event boundary is contained in finitely many deterministic marginal threshold hyperplanes. Lower semicontinuity of downward variation under pointwise convergence then gives (SV) for singular matrices. Do not assume absolute continuity of a singular limiting path without proof.

### Available progress, acceptable alternatives and failure tests

The [partial variation calculation](idea_a0805e98f90d.md) supplies draft side-chat proofs of $\mathcal V_-\le2q$ for two exact clone groups with arbitrary mutual correlation and multiplicities, $\mathcal V_-\le q$ for the signed rank-one start, and $\mathcal V_-\le16q$ for every trivariate covariance matrix. They must be independently checked if used as proof dependencies. They do not control a growing number of distinct Gaussian directions.

A dimension-uniform bound $\mathcal V_-(f_{q,\Sigma})\le g(q)$ with $g(q)\to0$ as $q\downarrow0$ is sufficient; a rate $Cq$ is optional and stronger than needed. Likewise any rigorously justified variant giving $q_*+\mathcal V_-<1$ uniformly at one level would close the same target, even if it does not prove the numerical budget in (SV). Record such a variant precisely rather than silently changing the assertion being tested.

Test multiscale clone blocks, small common loadings, simplex frames and high-dimensional mixed-sign configurations. Exact positive clones must stay tied along the unregularized path; retain their actual multiplicities. Do not optimize the covariance direction against an unrelated PSD matrix or discard the factors $\rho_{ij}$ and $1-\rho_{ij}$.

Many narrow oscillations in $t$ are the main possible obstruction to (SV). Failure of a stronger $Cq$ rate does not refute the fixed-level assertion. A counterexample at one chosen level rejects that choice, not the existence of some other universal $q_*$. If an obstruction is found, state exactly which quantified variation assertion it defeats; it is not automatically a counterexample to the Simes endpoint conjecture.

## Proof attempt in this chat

[The partial variation calculation](idea_a0805e98f90d.md) proves a side-chat bound $V_-\le2q$ for two exact clone groups with arbitrary mutual correlation and arbitrary multiplicities, sharpens this to $q$ for the signed rank-one start, and obtains $V_-\le16q$ for every trivariate Gaussian correlation matrix. It also records exploratory trivariate quadratures. These remain draft observations. The attempted proof did not obtain a bound uniform in unrestricted dimension: dropping the conditional rank restrictions in the three-face formula creates a growing number of corner terms.
