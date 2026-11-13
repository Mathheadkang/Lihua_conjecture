---
type: falsification_check
title: 'Falsification check: gaussian_frozen_ray_order_bound'
target_asset: gaussian_frozen_ray_order_bound
outcome: no_counterexample_found
statement_digest: 282dae85ea4644795f6594864fde635d6b47cfbb089d6aaaa5923db5d8b578ac
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T04:30:23.383Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_frozen_ray_order_bound_r1_s1_rank_one_signed failed — NOT fails: $\Lambda\leq\sum_i\omega_ie^{(Z_i)_+^2/2}$ and the weak-$L^1$ tail $1/(s\sqrt{4\pi\log s})$ give $\mathbb E\min\{c,\Lambda\}\leq2(1+\sqrt{\log c/\pi})$ for rank one, and $\leq1+\pi^{-1/2}(\sqrt{\log c}+\sqrt{\log n+1/e})$ for any $\Sigma$, so a counterexample needs weight entropy $\gg\log c$ (super-polynomially many hypotheses in $c$).
- Round 1, boundary_degenerate: cand_gaussian_frozen_ray_order_bound_r1_s1_rank_two_circle failed — NOT fails: for $n\leq c$ the union bound applies, and for $n>c$ the Riemann-sum comparison with $I_0(wr)e^{-w^2/2}$ gives $\Lambda\lesssim e^{r^2/2}/(1+r)+\tfrac2ne^{r^2/2}$, whose truncated mean is $O(\sqrt{\log c})$ uniformly in $n$.
- Obstruction: Every object with low weight entropy fails NOT. Since $\sup_{w\geq0}e^{wz-w^2/2}=e^{z_+^2/2}$, we have $\Lambda\leq\sum_i\omega_ie^{(Z_i)_+^2/2}$. Each term has tail $P(e^{\xi_+^2/2}>s)\leq1/(s\sqrt{4\pi\log s})$ for $s\geq1$. For every $\Sigma$ (singular, either sign) this gives $\mathbb E\min\{c,\Lambda\}\leq1+\pi^{-1/2}\big(\sqrt{\log c}+\sum_i\omega_i\sqrt{\log(1/\omega_i)}\big)\leq1+\pi^{-1/2}\big(\sqrt{\log c}+\sqrt{\log n+1/e}\big)$. A counterexample therefore needs $\sum_i\omega_i\sqrt{\log(1/\omega_i)}\gg\sqrt{\log c}$, that is, weight entropy far above $\log c$ (in particular $n\geq c^{K}$ for every fixed $K$).
- Obstruction: The boundary cases $n=1$, rank-one $\Sigma=ss^{\mathsf T}$ (all-equal or antipodal coordinates), $\omega\equiv0$, total mass $<1$, and $c=2$ all fail NOT. Rank one gives $\mathbb E\min\{c,\Lambda\}\leq2(1+\sqrt{\log c/\pi})$. At $c=2$ the bound is trivial ($\leq2$). The case $n=1$ shows that the order $\sqrt{\log c}$ is attained, with $C_{\mathrm{FR}}\geq\pi^{-1/2}$ asymptotically, and is not exceeded.
- Obstruction: Isotropic angular spreading in low rank does not help. With rank two, equally spaced directions and uniform weights, a Riemann-sum comparison with $I_0(wr)e^{-w^2/2}$ gives $\Lambda\lesssim e^{r^2/2}/(1+r)+\tfrac2ne^{r^2/2}$. The factor $(1+r)^{-1}$ (cap width times the Bessel prefactor) turns the $\chi^2_2$ tail $1/s$ back into the one-dimensional tail $1/(s\sqrt{\log s})$, so the truncated mean is $O(\sqrt{\log c})$ uniformly in $n$. The Laplace heuristic on $S^{k-1}$ shows the same balance in every fixed rank $k$.

## Limitations

- Isotropic rank-$k$ families were checked only heuristically: the $k$-dependence of the constants was not tracked, and the regime where $k$ grows with $c$ was not examined.
- Not explored: non-uniform or multiscale weightings, hierarchical (ultrametric) clusters of directions at several correlation levels, near-identity $\Sigma$ with huge $n$ (independent-like coordinates), mixed-sign high-rank designs, and constructions in which different $w$ select different clusters. These are exactly the high-entropy regimes that the termwise bound leaves open.

Object search: 2 candidate(s) in 1 round(s).
