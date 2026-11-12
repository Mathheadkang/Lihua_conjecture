---
type: idea
title: >-
  Common-shift rank sandwiches for Wasserstein FDR continuity without transverse
  roots
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
  - gaussian_bh_rare_clone_mills_variation
tags:
  - cross_field
  - monotone_crossing
  - wasserstein
---

Suggested by the teaching chat during the researcher's requested cross-field brainstorm. This is a candidate proof route, not an approved proof. It targets clause 3 of gaussian_bh_common_loading_wasserstein_fdr_continuity; its microscopic bound is already in clause 2 and is not a new target.

## Mechanism
Condition on the residual isonormal field and push the marked parameter law to the marked scalar score law nu of (A,ell), where A=theta+tau X(v), tau=sqrt(1-sigma^2). Write c_q(r)=barPhi^{-1}(qr) and
$$
R_\nu(z)=\sup\bigl(\{0\}\cup\{r\in(0,1]:\nu[A+\sigma z\ge c_q(r)]\ge r\}\bigr).
$$
The full BH largest rank R_nu(z) is monotone nondecreasing in the common shift z, even with competing roots. The mixed FDP itself need not be monotone. The proposed replacement for transverse-root analysis is a coupling sandwich for these monotone rank responses.

## Deterministic lemma to check first
Suppose a coupling of nu_n and nu has score discrepancy at most e and identical tags outside mass eta. Fix delta>0, eta<delta/2, and put
$$
L_{q,\delta}=\sup_{\delta/2\le r\le1}|c_q'(r)|,\qquad
h=(e+L_{q,\delta}\eta)/\sigma.
$$
If r>=delta qualifies for nu_n at z, then r-eta qualifies for nu at z+h: on the good part of the coupling the score loss is at most e, the lost mass at most eta, and c_q(r-eta)-c_q(r)<=L eta. Consequently R_nu_n(z)<=R_nu(z+h)+eta whenever the former rank is at least delta; exchange the laws for the reverse comparison. Use these two comparisons to obtain convergence at continuity points of z->R_nu(z). There are at most countably many discontinuities, and independent Gaussian Z hits none. Check rank 1 by clipping, not by excluding terminal rejection.

## Atoms and the marked numerator
First prove that the non-strict largest positive crossing is attained and its selected mass equals R, including R=1. For a score atom a, a selected threshold c_q(R)-sigma z=a then forces R=nu[A>=a], hence fixes z=(c_q(nu[A>=a])-a)/sigma. There are at most countably many such exceptional z. Away from them and rank-response discontinuities, marked tail masses converge under the coupling, so V_n/R_n converges wherever the limiting rank is positive. This permits mixed-label atoms; do not assume atomless parameters or unique crossings.

## From parameter W1 to this lemma
For any deterministic parameter coupling,
$$
\mathbb E_X|A(\theta,v)-A(\theta',v')|
\le|\theta-\theta'|+\tau\sqrt{2/\pi}\|v-v'\|.
$$
The discrete tag discrepancy is already paid by the metric c. Thus parameter W1 convergence gives mean convergence of a random marked-score coupling cost. Pass to a summable subsequence, get almost-sure good couplings via Markov's inequality, and apply the deterministic lemma. This avoids taking a supremum of the Gaussian field over all directions.

Use clause 2 to remove the rank cutoff. Its elementary pathwise starting inequality is
$$
D_\pi\,\mathbf1_{\{0<\rho_\pi\le a\}}
\le q\int_{\{\ell=1\}}\frac{\mathbf1_{\{p(x)\le qa\}}}{p(x)}\,\pi(dx).
$$
Conditional on Z=z, integrate using F_z, cap by 1, and then average over Z. In the Gaussian change of variable, the quadratic exponent is -sigma^2 u^2/(2 tau^2)+O_z(u), so the reciprocal-p integral is finite for each fixed sigma>0. This is a proposed direct proof of the already stated microscopic bound, not an independence assumption.

## Source and what it supplies
Ward Whitt, Limits for Cumulative Input Processes to Queues, Probability in the Engineering and Informational Sciences 14 (2000), 123-150, DOI 10.1017/S0269964800142019. Author PDF https://www.columbia.edu/~ww2040/LimitsCumInput.pdf ; publisher https://www.cambridge.org/core/journals/probability-in-the-engineering-and-informational-sciences/article/limits-for-cumulative-input-processes-to-queues/21EACF1FDDB4EA5FF172A49C2987E147 . Remark 2.5, printed p.132, motivates inverse/monotone-process convergence in M1 when many small jumps merge into one large jump. This is a method analogy; Whitt does not prove a BH theorem. The elementary sandwich above should be proved directly rather than importing a queueing limit theorem with unchecked hypotheses.

## Decisive tests and scope
Test two competing largest crossings, mixed-tag score atoms, merging small jumps, rho_n->0, and the terminal rank 1. The bad-shift exceptions must remain countable conditional on the same residual field. Both h and the tail estimate deteriorate as sigma->0; fixed-sigma continuity gives no uniform small-sigma estimate and no derivative extension at a nonatomic near-maximizer. If any sandwich fails, record the exact finite marked-score counterexample before using an implicit-function or delta-method substitute.
