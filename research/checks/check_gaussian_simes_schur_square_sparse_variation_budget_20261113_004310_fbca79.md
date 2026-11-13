---
type: falsification_check
title: 'Falsification check: gaussian_simes_schur_square_sparse_variation_budget'
target_asset: gaussian_simes_schur_square_sparse_variation_budget
outcome: no_counterexample_found
statement_digest: 86f7bdd265309432fe20f975ae839c30202be6cc9ff8b792c372f7c4362c61e9
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T00:43:10.292Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_simes_schur_square_sparse_variation_budget_r1_s1_independent_antipodal_pairs failed — NOT fails: each block is pivotal only when the rest already has $R_k\ge k-2$, a Poisson-type tail of mean $\le qk$ uniform in $r$, so the Plackett corner terms total $O(q)$ and $\mathcal V_-\to0$ as $q\to0$, uniformly in $M$.
- Round 1, boundary_degenerate: cand_gaussian_simes_schur_square_sparse_variation_budget_r1_s1_signed_rank_one_two_groups failed — NOT fails: with two clone directions the Plackett corner terms integrate to at most $3qK/N<3q$, so $\mathcal V_-\to0$ as $q\to0$.
- Round 1, boundary_degenerate: cand_gaussian_simes_schur_square_sparse_variation_budget_r1_s1_zero_one_fixed_points failed — NOT fails: $\Sigma\circ\Sigma=\Sigma$ for $\{0,1\}$ entries, so the path is constant and $\mathcal V_-=0$.
- Obstruction: Every $\Sigma\in\mathcal C_N$ with entries in $\{0,1\}$ (the identity, $J_N$, $N=1$, exact-clone partitions, singular or not) is a fixed point of the Schur square: $\rho^2=\rho$, so $R_t^\Sigma=\Sigma$ for all $t$, $f_{q,\Sigma}$ is constant and $\mathcal V_-=0$.
- Obstruction: At fixed $N$ the sparse ranks run out: a sparse rank $k$ needs $k<N\overline\Phi(u_q+1)/q$, and $\overline\Phi(u_q+1)<q$. So if $N\le q/\overline\Phi(u_q+1)$ (in particular $N=1$), then $S_q=\emptyset$, $f\equiv0$ and $\mathcal V_-=0$. Letting $q\to0$ at fixed $N$ never gives a counterexample. A counterexample needs $N\gtrsim q/\overline\Phi(u_q+1)$, which grows like $e^{u_q}$.
- Obstruction: Two antipodal clone groups ($\Sigma=ss^{\mathsf T}$, $s\in\{\pm1\}^N$, which covers every $\{\pm1\}$ correlation matrix): the path is a bivariate pair with correlation $r=2t-1$. The event is $\{X\ge\alpha\}\cup\{Y\ge\beta\}\cup\{X,Y\ge\gamma\}$. Its $r$-derivative is a signed sum of three Plackett corner densities, and each integrates over $r\in[-1,1]$ to at most $\overline\Phi(\gamma)=qK/N$. Hence $\mathcal V_-\le3qK/N<3q$. More generally, any family with a bounded number of distinct clone directions has $\mathcal V_-=O(q)$ by the same corner-integral argument.
- Obstruction: Independent antipodal pairs ($I_M\otimes\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$, entries in $\{0,\pm1\}$): a block is pivotal at rank $k$ only when the other blocks already give a count $R_k\ge k-2$. That count is a sum of independent $[0,2]$ variables with mean at most $qk$ for every $r$, so its Chernoff tail is uniform along the path. Summing the Plackett corner terms gives $\mathcal V_-\le\frac{3q}{2}\sum_kk^3C_k=O(q)$, uniformly in $M$. The variation from many independent degenerate blocks is damped by this pivotality tail, not by the number of blocks.

## Limitations

- No worker in this direction tried many genuinely mixed-sign directions, i.e. correlations not in $\{0,\pm1\}$ with many distinct Gaussian directions. This is where the narrow oscillations of $f_{q,\Sigma}$ in $t$, the obstruction expected in the motivation, would have to come from.
- Not tried: simplex frames (equiangular negative correlation $-1/(N-1)$ and their block versions), small common loadings (weak one-factor models with sign patterns), and mixtures of clone groups with unequal sizes inside signed blocks (the third candidate used singleton pairs only).
- None of the bounds addresses whether $\mathbb P_{N,0,\Sigma}(S_q)$ itself can be large under some $\Sigma$. That is the open fixed-level sparse-crossing cap, and any counterexample to it would also refute this target.
- The bounds above are analytic, with Chernoff constants evaluated at $q=1/100$. No numerical scan of $f_{q,\Sigma}(t)$ was run.

Object search: 3 candidate(s) in 1 round(s).
