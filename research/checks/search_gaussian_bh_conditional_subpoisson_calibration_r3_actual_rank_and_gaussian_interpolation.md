---
type: search_round
title: >-
  Actual-rank and singular Gaussian obstructions to conditional calibration
  counterexamples
target_asset: gaussian_bh_conditional_subpoisson_calibration
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
performed_by: unknown
created_at: '2026-11-11T22:29:49.186Z'
extension_version: 0.0.4
---

## Obstructions

- If only a fixed set $M$ of $m$ original null coordinates remains random after the final conditioning $\mathcal H$, the aggregate first-moment implication yields $\mathbb E[\operatorname{FDP}\mid\mathcal H]\le\min\{1,(m+1)qK\}$ wherever $K<\infty$. All other coordinates, including alternatives, must be $\mathcal H$-measurable. For $k=0,\ldots,m$, let $r_k$ be the conditional deterministic BH rejection count after replacing the $M$ coordinates by $k$ zeros and $m-k$ ones. On the event that exactly $k$ of the original $M$ coordinates are rejected, the actual total rank is $r_k$: replacement preserves the count at the actual threshold, while at every larger threshold it can only remove originally unrejected coordinates. The deterministic-null FDP contribution is at most $qK$, since $D(s)\le\mathbb E[C(s)\mid\mathcal H]\le NKs$. For each $k\ge1$, the random-null contribution is $(k/r_k)\mathbb P(L=k\mid\mathcal H)\le\mathbb E[C_M(qr_k/N)\mid\mathcal H]/r_k\le qK$, where $L$ is the number of rejected $M$ coordinates. The finite-valued $\mathcal H$-measurable ranks permit use of the common full-measure set. Summing gives the asserted bound. Thus $m\le9$ cannot refute the $4e$ bound, regardless of $N$. The new proof-step obstruction is saved as approach idea_24a557d20b6f.
- In particular, rank-one conditional Gaussian covariance is structurally different from an arbitrary singular covariance: writing $Q=vv^\mathsf T$, the nonpositive off-diagonal condition allows at most one positive and at most one negative nonzero $v_i$. There are therefore at most two positive conditional variances. The remaining Gaussian coordinates are conditionally deterministic, so the preceding argument gives conditional FDR at most $\min\{1,3qK\}$. This excludes the entire rank-one boundary rather than merely changing the parameters of the earlier antithetic pair.
- Singular PSD conditional Gaussian covariance with nonpositive off-diagonal entries does not defeat the claimed count-mgf sufficient condition. Fix the conditional law, remove zero-variance coordinates as deterministic factors, and let $D=\operatorname{diag}(Q)$ on the remaining positive-variance coordinates. The covariance interpolation $Q_t=(1-t)D+tQ$ is positive definite for $t<1$ and has unchanged one-dimensional marginals. For smooth nonnegative nondecreasing approximations $g_i$ of $\exp\{\lambda\mathbf1_{\{T_i\ge\overline\Phi^{-1}(s)\}}\}$, Gaussian differentiation gives $\frac{d}{dt}\mathbb E\prod_i g_i(T_i(t))=\sum_{i<j}Q_{ij}\mathbb E[g_i'(T_i(t))g_j'(T_j(t))\prod_{\ell\ne i,j}g_\ell(T_\ell(t))]\le0$. At $t=0$ the coordinates are independent. Taking $t\uparrow1$ and then the indicator-approximation limit is valid because each remaining marginal has positive variance and hence zero probability at the finite threshold. Reinstating deterministic coordinates yields $\mathbb E[e^{\lambda C(s)}\mid\mathcal H]\le\prod_i[1+F_{i,\mathcal H}(s)(e^\lambda-1)]\le\exp\{(e^\lambda-1)\sum_iF_{i,\mathcal H}(s)\}$. The stated $K$ then gives the required count inequality. Zero-variance coordinates are factored before smoothing, so an atom exactly at a non-strict threshold is retained correctly. The covariance sign condition is required under this entire final conditioning; the argument asserts no preservation under further conditioning.

## Limitations

- Round 3 produced no candidate files and no surviving counterexample. The preceding arguments are search obstructions, not an independent verification or approval of the entire target lemma.
- The limited-random-null estimate grows as $m+1$ and therefore does not establish the target's dimension-uniform $4e$ coefficient for arbitrarily many conditionally random nulls. A complete proof or a counterexample for the count-mgf-to-actual-rank step in that regime remains necessary.
- The Gaussian interpolation addresses the sufficient condition only. It does not supply a finite or small calibration factor for arbitrary Gaussian means and variances, nor any unconditional Gaussian order bound.
- The current pack supplies no round-3 candidate bodies and only a brief interpolation report. The summary reconstructs the stated obstructions directly from the target assumptions; it does not inspect the omitted target proof or repeat the existing count-proof idea.
