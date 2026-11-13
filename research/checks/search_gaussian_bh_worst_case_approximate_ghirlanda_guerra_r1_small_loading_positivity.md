---
type: search_round
title: >-
  Refute search round 1 for approximate Ghirlanda-Guerra near-maximizers
  (boundary and degenerate cases; small common loading)
target_asset: gaussian_bh_worst_case_approximate_ghirlanda_guerra
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_worst_case_approximate_ghirlanda_guerra_r1_s1_small_loading_lei_gap
statement_digest: 0fa059894da56d1c7aa170ddad938948acb823f2dc7eea7e4574aa98d3831230
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T07:26:07.964Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- **The PRDS step of idea_eb7b129c2e8e holds, including composite nulls.** Take covariance $(1-\sigma^2)C+\sigma^2\mathbf1\mathbf1^{\mathsf T}$ with $C_{ij}\ge0$ (or only $C_{ij}\ge-\sigma^2/(1-\sigma^2)$), any null means $\theta_i\le0$, and possibly singular $C$. Conditioning on $T_i=s$ shifts the other coordinates by $\Sigma_{ji}(s-\theta_i)$, which is nondecreasing in $s$. So $t\mapsto\Pr(R\le k\mid p_i\le t)$ is nondecreasing. The null CDF $F(t)=\overline\Phi(\overline\Phi^{-1}(t)+|\theta_i|)$ has $F(t)/t$ nondecreasing (log-concavity of $\overline\Phi$). The Benjamini-Yekutieli/Blanchard-Roquain summation by parts then gives $\mathbb E[\mathbf1\{p_i\le qR/n\}/(R\vee1)]\le q/n$ for each null, so $\operatorname{FDR}\le q\,m_0/n\le q$. With $n=1$, $C=1$, $\theta=0$ the value is exactly $q$. Hence $U_\sigma(q)=q$ for every $\sigma$. The value-transfer lemma's conclusion therefore reads $\limsup_k\mathcal F(P_k)\le q$.
- **The value-transfer lemma (gaussian_bh_ghirlanda_guerra_ultrametric_value_transfer) is true, given Talagrand's positivity principle; it is not the lemma that fails.** Take any sequence with vanishing defects.
  - Compactify marks to $[-\infty,\infty]$. The finite conditional FDR $\mathbb E[D_n\mid\omega]$ is continuous on the compact extended space, because threshold ties have probability $0$ (unit residual diagonal) and infinite marks give $p\in\{0,1\}$.
  - A limit point $P_\infty$ satisfies the GG identities exactly. By positivity, $C_{ij}\ge0$ a.s.
  - By the PRDS bound, $\mathcal F_n(P_\infty)\le q$. The uniform completion (compactification item 1) then gives $\limsup_k\mathcal F(P_k)\le q=U_\sigma(q)$.
  - So Lei's family cannot refute the transfer. GG-exact arrays are nonnegative, while Lei's family has negative null-alternative correlations. Marks do not enter the defect, but they cannot rescue negativity of $C$.
  - In particular, every deterministic constant-overlap array $C_{ij}\equiv c\ge0$ (exact GG, arbitrary exchangeable marks) has value $\le q$. Random constant overlaps have nonzero defect $(1/n)\operatorname{Cov}(f,\psi(c))$.
- **This lemma (gaussian_bh_worst_case_approximate_ghirlanda_guerra) fails whenever $W_\sigma(q)>q$.** Its conclusion forces $W_\sigma(q)\le q$ by the previous bullet. Lei's positive-definite finite model, perturbed by $\sigma^2\mathbf1\mathbf1^{\mathsf T}$, is a total-variation limit, and $\ell_\le(q)>q$ for $q\le q_{\max}$. So for each $q\in(0,q_{\max}]$ there is $\sigma_0(q)>0$ with $W_\sigma(q)>q$ on $(0,\sigma_0(q))$, and the lemma is false there. This is the surviving candidate cand_gaussian_bh_worst_case_approximate_ghirlanda_guerra_r1_s1_small_loading_lei_gap. The route's inconsistency, flagged by idea_eb7b129c2e8e, is located in this lemma, not in the transfer.
- General principle: near-maximizers of a functional whose supremum exceeds $q$ must keep a non-vanishing mass of negative residual overlaps. Under any vanishing-GG sequence that mass tends to $0$ in law, by positivity at the limit. So no full-array GG/ultrametric reduction can work for one-sided BH. Only a null-restricted overlap variant (as in gaussian_bh_null_overlap_ghirlanda_guerra_maximizer) can avoid this.

## Limitations

- The positivity principle (Talagrand; Panchenko's 2013 monograph) is used as an external known theorem. It is not in the library and no theorem location is asserted. A verifier should source it. The case of $C$-arrays with unit diagonal and GG identities only for continuous $f,\psi$ of off-diagonal entries was reduced to the measurable case by monotone class.
- No explicit numerical $\sigma_0(q)$ was computed. Its existence uses only total-variation continuity at Lei's positive-definite covariance (or compactification item 5).
- Larger $\sigma$ (near $1$), where $W_\sigma(q)\le q$ might hold, was not examined. There the lemma might hold (for example, if $W_\sigma(q)=q$ is attained by GG-exact arrays).
- Only one slot's direction (boundary/degenerate) was covered by this worker.
