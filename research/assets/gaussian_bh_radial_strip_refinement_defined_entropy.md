---
type: lemma
title: One-sided radial strip refinement with defined extended entropy
status: draft
source:
  kind: original
  location: "Proposed repair of gaussian_bh_radial_strip_refinement; plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106, Progress / Step 4 (RS) and Corollary RS-c, source lines 219–233"
depends_on:
  - gaussian_bh_one_sided_free_central_window_core
  - directional_entropy_one_sided_fdr_bound
uses_definitions:
  - gaussian_multifactor_representation
  - gaussian_null_loading_coefficients
  - gaussian_oriented_null_directional_entropy
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian
  - one_sided
  - radial_strip
  - directional_entropy
  - proposed_repair
  - unproved
---

## Statement

### Full finite-model scope and procedure

For arbitrary positive integers $N,d$, arbitrary deterministic means $\theta\in\mathbb R^N$ and arbitrary deterministic loadings $a_i\in\mathbb R^d$ with $\|a_i\|\le1$, consider
$$
T_i=\theta_i+a_i^{\mathsf T}Z+s_i\varepsilon_i,\qquad
r_i=\|a_i\|,\quad s_i=\sqrt{1-r_i^2},
$$
where $Z\sim\mathcal N_d(0,I_d)$ and all $\varepsilon_i\sim\mathcal N(0,1)$ are mutually independent. Zero and unit loading norms, arbitrary alternative means and loadings, negative true-null means, and singular covariance matrices are included. Apply ordinary BH at level $0<q<1/2$ to $p_i=\overline\Phi(T_i)$: with ordered p-values including multiplicities,
$$
\widehat k=\max\bigl(\{0\}\cup\{k\in[N]:p_{(k)}\le qk/N\}\bigr),
$$
$$
\mathcal R_q=\begin{cases}\{i:p_i\le q\widehat k/N\},&\widehat k>0,\\\varnothing,&\widehat k=0,\end{cases}
\qquad R=|\mathcal R_q|.
$$
Let $I_0=\{i:\theta_i\le0\}$, $m_0=|I_0|>0$, $\pi_0=m_0/N$, and
$$
\gamma_i=\sqrt{\frac{1-r_i}{1+r_i}},\qquad
\overline\gamma_0=\frac1N\sum_{i\in I_0}\gamma_i,\qquad
\operatorname{FDR}=\mathbb E\frac{|\mathcal R_q\cap I_0|}{R\vee1}.
$$
Here $\overline\Phi$ and $\phi$ are the standard normal survival function and density, and all logarithms are natural.

### Arbitrary oriented null grouping and thresholds

Let $G_1,\ldots,G_H$ be any partition of $I_0$ into nonempty sets, with unit vectors $v_h\in\mathbb R^d$ satisfying $a_i=r_i v_h$ for every $i\in G_h$. Zero loadings may be assigned to any group; the standard normal projections $Y_h=v_h^{\mathsf T}Z$ need not be independent. Put
$$
\pi_h=\frac{|G_h|}{N}>0,\qquad \sum_h\pi_h=\pi_0,\qquad
\mathcal E_0=\sum_h\pi_h\log\frac1{\pi_h},
$$
$$
U=\overline\Phi^{-1}(q)>0,\quad t_k=qk/N,\quad
u_k=\overline\Phi^{-1}(t_k)\ge U,\quad b_h=\overline\Phi^{-1}(q\pi_h)\ge U.
$$
The thresholds are finite and $u_N=U$.

### Extended quotient conventions

Define, for $\pi\in(0,1]$ and $s\in[0,1]$,
$$
A(\pi,s)=\begin{cases}
\log(1/\pi)/s,&s>0,\\
0,&s=0,\ \pi=1,\\
+\infty,&s=0,\ \pi<1.
\end{cases}
$$
Every occurrence of $\log(1/\pi_h)/s_i$ means this extended quotient. Division of it by the positive constant $U\sqrt{2\pi}$ has its usual extended-real meaning. Define separately
$$
C_{hi}=\begin{cases}(b_h-U)/(s_i\sqrt{2\pi}),&s_i>0,\\+\infty,&s_i=0,\end{cases}
$$
retaining the source's $+\infty$ convention for the first entry even when $b_h=U$. Use $\min\{+\infty,x\}=x$ for finite $x$.

### Finite RS bound and comparisons

For every model and grouping above,
$$
\operatorname{FDR}\le\frac32q\pi_0+
\frac{qU}{\sqrt{2\pi}}\overline\gamma_0+q\mathcal E_{\min},\qquad
\mathcal E_{\min}=\frac1N\sum_h\sum_{i\in G_h}
\min\left\{C_{hi},\log\frac1{\pi_h}\right\}.
$$
Moreover, with $\mathcal E_s$ allowed to equal $+\infty$,
$$
b_h-U\le\frac{\log(1/\pi_h)}U,\qquad
\mathcal E_s=\frac1N\sum_h\sum_{i\in G_h}A(\pi_h,s_i),
$$
$$
\mathcal E_{\min}\le\frac1N\sum_h\sum_{i\in G_h}
\min\left\{\frac{A(\pi_h,s_i)}{U\sqrt{2\pi}},\log\frac1{\pi_h}\right\}
\le\frac{\mathcal E_s}{U\sqrt{2\pi}}.
$$

### Corollary RS-c, with all source sufficient conditions

Along any sequence $q\downarrow0$ of models and groupings in this statement with
$$
\mathcal E_{\min}=o\!\left(\sqrt{\log(1/q)}\right),
$$
in particular whenever either $\mathcal E_s=o(\log(1/q))$ or $\mathcal E_0=o(\sqrt{\log(1/q)})$, one has
$$
\limsup_{q\downarrow0}\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}\le\frac1{\sqrt\pi}.
$$
The number of tests, factor dimension, means, covariance, loadings, null grouping, and group count may vary arbitrarily with $q$ subject only to the displayed conditions. No block or fixed-dimension restriction is imposed. Little-oh conditions on the extended quantity $\mathcal E_s$ mean its displayed ratio tends to zero and thus exclude infinite values eventually.

## Proof

## Proposal provenance and unresolved dependency gate

Proposed new ID: `gaussian_bh_radial_strip_refinement_defined_entropy`. This is a NEW unproved proposal defining the source's formerly undefined entropy quotient. It retains the full finite RS bound, its comparisons, and all sufficient conditions of Corollary RS-c. It neither edits nor certifies the exact original draft and does not alter either unrestricted main target.

Exact source: `plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106`, Progress / Step 4 (RS) and Corollary RS-c (source lines 219–233), extracted as `gaussian_bh_radial_strip_refinement`, SHA256 `c4dadb246180bb71ff61119c4d3569024d72326581297a8119b90bd5b39c8368`. The copied proof under that old asset's Proof heading is an adaptation candidate only. Cold observation: `idea_544b0fa5c908`.

At proposal preparation, the [directional entropy bound](./directional_entropy_one_sided_fdr_bound.md) was approved and the [central-window core](./gaussian_bh_one_sided_free_central_window_core.md) was a newly created draft. The latter's Claim includes the central-integral and pointwise estimates for $0<q<1/2$, including $r=0$, and the $r=1$ integral endpoint. Its separate BH central-contribution consequence retains its source range $q\le1/10$; that narrower consequence does not supply the kernel estimate required for this all-$q<1/2$ RS derivation. These were dependency-scope checks at preparation, not a proof or approval of this RS proposal.

## Proposed reproof checklist and first failure condition

1. Reconstruct the conditional BH partial-FDP inequality using the approved entropy proof, conditioning on the full $Z$, preserving inclusive ties, $R=0$, negative null means, zero/unit loadings, and singular covariance.
2. Use only the exact future core Statement for the central integral at $0<r<1$ and the pointwise bound when $s>0$. Handle $r=0$ by $M_i\le1$ and $\Phi(U)\le1/2+U/\sqrt{2\pi}$, and $r=1$ directly by the deterministic conditional CDF. If the future core omits an estimate, stop rather than silently import the old unverified dependency.
3. Reprove the strip integral both ways, using the entropy envelope and the pointwise density bound; use the partial-FDP cap on the upper tail. Check summation with masses normalized by all $N$.
4. Prove the Gaussian tail translation bound for $b_h-U$ and the entire comparison chain. Check explicitly $\pi_h=1,s_i=0$: the original $C_{hi}=+\infty$ and the proposed $A=0$ must yield the same zero minimum, without using the false intermediate inequality $C_{hi}\le A/(U\sqrt{2\pi})$.
5. Derive RS-c with all three sufficient conditions for arbitrary varying models. Verify the needed large-$U$ lower and upper Gaussian-quantile bounds rather than treating the source argument as a certificate.

The source proof's final equal-group illustration claims $\mathcal E_s\le\pi_0\log H/\delta$ when $s_i\ge\delta$. Because its masses are normalized by all $N$, this illustration needs separate checking when $\pi_0<1$; it is not a stated part of RS-c and is not imported as a verified consequence here. This proposal does not silently repair that source illustration.

Stop at the first unsupported estimate, endpoint failure, mismatch of the future core scope, or admissible counterexample. Native planning, execution, and fresh verification remain required. This file supplies no proof or independent-review verdict.
