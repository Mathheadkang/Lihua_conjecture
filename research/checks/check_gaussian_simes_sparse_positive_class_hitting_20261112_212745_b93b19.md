---
type: falsification_check
title: 'Falsification check: gaussian_simes_sparse_positive_class_hitting'
target_asset: gaussian_simes_sparse_positive_class_hitting
outcome: no_counterexample_found
statement_digest: 890cfc3a9c9940c136cc16ee0457d5a898e3cb8394ae61c9b578e3710d695ad7
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T21:27:45.868Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_simes_sparse_positive_class_hitting_r1_s1_antipodal_pairs failed — NOT fails: antipodal pairs halve the effective dimension and leave an exact independent Simes problem with $\mathbb P(E_\alpha)=\alpha$; uniform transversals are hit with probability at least $1/2$.
- Round 1, boundary_degenerate: cand_gaussian_simes_sparse_positive_class_hitting_r1_s1_negative_equicorrelation_singletons failed — NOT fails: although only singleton positive classes exist (so $h\le\pi(\mathcal A_\alpha)$ and no prior can satisfy the hitting requirement on $E\setminus D$), the weak negative equicorrelation is a Gaussian perturbation of independence and $\mathbb P(E_\alpha)\le 5\alpha<1/4$.
- Round 1, boundary_degenerate: cand_gaussian_simes_sparse_positive_class_hitting_r1_s1_rank_one_signed_frame failed — NOT fails: for a rank-one signed $\Sigma$ the Simes/BH global-null rejection probability is exactly $\alpha\le1/4$, and the two sign clusters are positive classes that a two-point prior hits with probability $1/2$.
- Obstruction: Every $\Sigma$ with $\mathbb P_{N,0,\Sigma}(E_\alpha\setminus D_{\alpha,\delta_0})\le1/4$ satisfies the conclusion with any prior. The quantifiers can always be met formally: singletons are positive classes, so a prior $\pi$ always exists. A counterexample therefore needs a global-null BH/Simes event of probability $>1/4$ at arbitrarily small $\alpha$, located on sparse crossings ($1\le r_\alpha<N\overline\Phi(u_\alpha+\delta_0)/\alpha$).
- Obstruction: Arbitrary-dependence bound: $\mathbb P(E_\alpha)\le\alpha H_N$, since $p_i$ is uniform. Proof: on $E_\alpha$, $1=\sum_i\mathbf 1\{p_i\le\alpha r_\alpha/N\}/r_\alpha$, and each term is at most $\sum_j\mathbf 1\{\alpha(j-1)/N<p_i\le\alpha j/N\}/j$. So every candidate needs $N\ge e^{1/(4\alpha)-1}$. All small and fixed-$N$ cases fail.
- Obstruction: Entrywise nonnegative $\Sigma$ fails: $\pi=\delta_{[N]}$ gives $h=1$ on $E_\alpha$. More generally, if a few positive classes cover the indices that can be rejected (rank-one signed frames $vv^{\mathsf T}$, where the two sign clusters are covered by $\pi=\frac12(\delta_P+\delta_M)$), then $h$ is bounded below.
- Obstruction: Correlations at $\pm1$ (rank-one signed frames, independent antipodal pairs) only merge or halve coordinates. What remains is an exact independent or all-equal Simes problem with $\mathbb P(E_\alpha)=\alpha$.
- Obstruction: Weak negative equicorrelation $-1/(N-1)$ fails. Adding an independent $(N-1)^{-1/2}G\mathbf 1$ term gives iid coordinates, and monotonicity on $\{G\ge0\}$ gives $\mathbb P(E_\alpha)\le2(1+o(1))\alpha$. The same works for any $\Sigma=\lambda I-\mu J$ type matrix that becomes diagonal after adding a small positive rank-one term.
- Obstruction: Reduction (not a refutation, but it limits where a counterexample can live): if every positive class has size $\le s$, then $h\le\pi(S\cap\mathcal A_\alpha\ne\varnothing)$. Hence $\mathbb E[h;E\setminus D]\le\mathbb E_\pi|S|\,\overline\Phi(u_\alpha+\delta_0)\le s\alpha$, and for such $\Sigma$ the lemma is equivalent, up to $s\alpha/c_*$, to the sparse Simes cap $\mathbb P(E_\alpha\setminus D_{\alpha,\delta_0})\le1/4$. In this regime the prior adds no slack. Refuting the lemma there means exhibiting a Gaussian Simes failure of size $>1/4$ at small $\alpha$.

## Limitations

- No construction was tried with $\mathbb P(E_\alpha)$ large: no Gaussian $\Sigma$ with super-exponential $N$ and adversarial signed structure, such as many overlapping signed frames or nearly antipodal clusters with nonzero overlap, that could approach the $\alpha H_N$ bound.
- No case was covered where large positive classes exist but are each rejected only in a fraction below $c|S|r_\alpha/N$. That is the proportional-hitting failure, separate from the bare-hit failure.
- No dependence of the prior on the constants $\delta_0,c_{\mathrm{hit}},c_*$ was exploited or attacked. Mixed regimes with both dense and sparse crossings (the $D_{\alpha,\delta_0}$ boundary at $k$ with $\alpha k/N=\overline\Phi(u_\alpha+\delta_0)$) were not examined.

Object search: 3 candidate(s) in 1 round(s).
